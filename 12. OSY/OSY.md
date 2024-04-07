# 12. Operační systémy a jejich architektury. Systémová volání, vlákna, procesy. Správa virtuální a fyzické paměti, souborové systémy. Bezpečnost, virtualizace.

----------

https://cw.fel.cvut.cz/old/courses/b4b35osy/start

----------

## Operační systémy a přerušení

**Úkoly OS**: 
- Spouštět a dohlížet uživatelské programy 
- Efektivní využití HW 
- Usnadnit řešení uživatelských problémů 
- Učinit počítač (snáze) použitelný

**Jádro OS běží když**:
- nastane přerušení nebo výjimka
- uživatelský program zavolá službu OS (systémové volání)
- na začátku spuštění počítače, připraví vše pro běh procesů a spustí první proces. Pak už jen čeká na přerušení, výjimky a systémová volání.

V operačním systému jsou **přerušení** a **výjimky** mechanismy, které umožňují přerušení běžícího programu a přechod do režimu jádra operačního systému (tzv. privilegovaný režim). Tyto mechanismy jsou využívány pro zpracování událostí, chyb a asynchronních požadavků.

**Výjimka** (exception) je chybová situace, která se vyskytne během provádění programu. Může být způsobena například nedostupnou pamětí, dělením nulou nebo pokusem o neplatnou operaci. Když operační systém zachytí výjimku, provede obslužnou rutinu výjimky, která se stará o zpracování a řešení chyby. Obslužná rutina výjimky je spuštěna v privilegovaném režimu a může provést různé akce, jako například ukončení programu, obnovení správného stavu nebo zobrazení chybového hlášení.
Oba mechanismy, přerušení a výjimky, slouží k asynchronnímu vyvolání pozornosti operačního systému a umožňují mu správně reagovat na události a chyby v systému.

**Multitasking** - Zdánlivé spuštění více procesů současně je nejčastěji implementováno metodou sdílení času tzv. Time-Sharing Systems (TSS) - rozšiřuje plánovací pravidla o rychlé (spravedlivé, cyklické ) přepínání mezi procesy řešícími zakázky interaktivních uživatelů

Architektura - viz APO (Assembly, cyklus CPU, výjimky a přerušení)

**Ochrana jádra OS** - Uživatel má do jádra OS přístup pouze přes obsluhu přerušení, nebo podobný mechanismus

**Zdroje přerušení:**
- **Vnitřní přerušení** 
    - problém při zpracování strojové instrukce 
    - instrukce nebo data nejsou v paměti - chyba stránky, chyba segmentu instrukci nelze provést - dělení nulou, ochrana paměti, nelegální instrukce 
    - nutno reagovat okamžitě, nelze dokončit instrukci, někdy nelze ani načíst instrukci 
- **Vnější přerušení**
    - vstupně/výstupní zařízení asynchronní s během procesoru 
    - signalizace potřeby reagovat na vstup/výstup 
    - reakce po dokončení vykonávané instrukce 
- **Programové přerušení** – strojová instrukce proveď přerušení 
    - využívá se k ochraně jádra OS 
    - obsluha přerušení může používat privilegované instrukce 
    - lze spustit pouze kód připravený OS

## Systémová volání, vlákna, procesy

![](https://paper-attachments.dropbox.com/s_9DE0B1142FF1CC9B1D789958165D40B186DA265F2D03EE6AA68F6526FFCE3B04_1662417467300_image.png)
**Služby jádra jsou číslovány**
- Registr eax obsahuje číslo požadované služby
- Ostatní registry obsahují parametry, nebo odkazy na parametry
- Problém je přenos dat mezi pamětí jádra a uživatelským prostorem
	- malá data lze přenést v registrech – návratová hodnota funkce
	- velká data – uživatel musí připravit prostor, jádro z/do něj nakopíruje data, předává se pouze adresa (ukazatel)
	- dle ChatGPT: registrový přenos, zásobníkový přenos, předávání ukazatelů, pomocí sdílené(shared) memory

**Služby jádra jsou očíslovány** - Application Binary Interface – ABI
- definuje rozhraní na úrovní strojového kódu

**Přehled služeb jádra(pomocí POSIX API)**
- Práce se soubory - open, close, read, write, lseek
- Správa souborů a adresářů - mkdir, rmdir, link, unlink, mount, umount, chdir, chmod, stat
- Správa procesů - fork, waitpid, execve, exit, kill, signal

### Monolitické jádro vs mikrojádro
![[Pasted image 20230607170005.png]]
#### Procesově orientované jádro
![[Pasted image 20230607170105.png]]

### Procesy

**Program**:
-  je soubor (např. na disku) přesně definovaného formátu obsahující instrukce, data, údaje potřebné k zavedení do paměti a inicializaci procesu 

**Proces**: 
- je spuštěný program – objekt jádra operačního systému provádějící výpočet podle programu
- je charakterizovaný svým paměťovým prostorem a kontextem (prostor v RAM se přiděluje procesům – nikoli programům!) 
- může vlastnit (kontext obsahuje položky pro) otevřené soubory, I/O zařízení a komunikační kanály, které vedou k jiným procesům, ... 
- obsahuje jedno či více vláken 
 
Proces je identifikovatelný jednoznačným číslem v každém okamžiku své existence  - PID (Process IDentifier)
 
 **Co tvoří proces:** 
-  Obsahy registrů procesoru (čítač instrukcí, ukazatel zásobníku, příznaky FLAGS, uživatelské registry, FPU registry)
-  Otevřené soubory
-  Použitá paměť: Zásobník – .stack, Data – .data, Program – .text

Rodič vytváří nový proces (potomka) voláním služby **fork** - vznikne identická kopie rodičovského procesu až na: 
- návratovou hodnotu systémového volání 
- hodnotu PID, PPID – číslo rodičovského procesu 

návratová hodnota určuje, kdo je potomek a kdo rodič (0 – jsem potomek, PID – jsem rodič a získávám PID potomka)
potomek může použít volání služby **exec** pro náhradu programu ve svém adresním prostoru jiným programem

**Stavy**

![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559035796095_image.png)


Přepnutí od jednoho procesu k jinému nastává výhradně v důsledku nějakého přerušení (či výjimky)
Procesy mohou čekat v různých frontách na vykonání (na přidělení procesoru, na dokončení I/O,  na přidělení místa v hlavní paměti,  na synchronizační událost, na zvětšení adresního prostoru)

**Meziprocesní komunikace**
![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559044521854_image.png)

### Vlákna

**Vlákno**:
- je sekvence instrukcí vykonávaných procesorem
- sdílí s ostatními vlákny procesu paměťový prostor a další atributy procesu (soubory, ... ) 
- má vlastní hodnoty registrů CPU

![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559036329854_image.png)


Objekt vytvářený v rámci procesu a viditelný uvnitř procesu 
Tradiční proces je proces tvořený jediným vláknem 
Vlákna podléhají plánování a přiděluje se jim strojový čas i procesory 
Vlákno se nachází ve stavech: běží, připravené, čekající, ukončené 
Když vlákno neběží, je kontext vlákna uložený v TCB (Thread Control Block) – analogie PCB
Vlákno může přistupovat k globálním proměnným a k ostatním zdrojům svého procesu, data jsou sdílena všemi vlákny stejného procesu:

-  Změnu obsahu globálních proměnných procesu vidí všechna ostatní vlákna téhož procesu 
-  Soubor otevřený jedním vláknem je viditelný pro všechna ostatní vlákna téhož procesu
![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559036761439_image.png)


**Přednosti**: 
- Vlákno se vytvoří i ukončí rychleji než proces 
- Přepínání mezi vlákny je rychlejší než mezi procesy 
- Dosáhne se lepší strukturalizace programu

Všechna vlákna jednoho procesu sdílejí společný adresní prostor

**Vlákna na uživatelské úrovni:**
-  OS zná jenom procesy 
- Vlákna vytváří uživatelská knihovna, která střídavě mění spuštěná vlákna procesu 
- Pokud jedno vlákno na něco čeká, ostatní vlákna nemohou běžet, protože jádro OS označí jako čekající celý proces 
- Pouze staré systémy, nebo jednoduché OS, kde nejsou vlákna potřeba 

**Vlákna na úrovni jádra:**
-  OS Procesy a vlákna jsou plně podporované v jádře 
- Moderní operační systémy (Windows, Linux, OSX, Android) 
- Vlákno je jednotka plánování činnosti systému

Realizace: - knihovna PThread, Java - třída Thread

**Plánování procesů**
preemptivní - CPU může být procesu násilně odebrán
nepreemptivní - nemůže

**Typy**:
- FCFS (First-Come First-Served) 
- SPN (SJF) (Shortest Process Next) 
- SRT (Shortest Remaining Time) - preemptivní SPN
- cyklické (Round-Robin) - každý proces dostane CPU na malý úsek a pak je vložen na konec fronty
- zpětnovazební (Feedback) - penalizace za dlouhé využití CPU

**Synchronizace**
- cílem je zabránit současný přístup více vláken do kritické sekce programu

**Nástroje**:
- **semafor** - Semafor je typ zámku založený na čítači. Semafor umožňuje dvě operace:
    - *wait* (acquire, take): Tato operace se volá před vstupem do kritické sekce. Při zavolání operace se vyhodnocuje hodnota čítače: pokud je nenulová, vlákno dekrementuje čítač (typicky o 1) a pokračuje dál ve vykonávání kritické sekce; pokud je nulová, vlákno se zablokuje až do doby, než je čítač opět nenulový.
    - post (release, give): Tato operace se volá ihned po vystoupení z kritické sekce. Při zavolání operace se inkrementuje čítač (typicky o 1). Inkrementování čítače o *n* způsobí probuzení *n* čekajících vláken (viz operace *wait*).

Semafor lze inicializovat na libovolné číslo - toto číslo vyjadřuje, kolik vláken současně může být v kritické sekci. Mutex lze simulovat semaforem s počáteční hodnotou čítače 1.
- **mutex** - typ zámku, který do kritické sekce vpustí jen jedno vlákno současně. Ostatní vlákna se před vstupem do kritické sekce zablokují, lock() a unlock() metody, lze uzamykat rekurzivně
- **monitor** - Monitor je typ zámku, který spojuje koncepty vlastníka a množiny čekajících vláken, kde vlákna čekají až do splnění určité podmínky. Vlákna mezi sebou mohou komunikovat a sdělovat si vzájemně, že byla podmínka splněna a mohou čekání přerušit. Vlastník se také může svého vlastnictví vzdát a připojit se tak k ostatním čekajícím vláknům. Platí, že kritickou sekci může spustit pouze aktuální vlastník monitoru.
- **Spin-lock** - semafor využívající aktivní čekání vlákna(busy wait) (v některých případech je to rychlejší než režie s procesy)

**Deadlock**
- nastane v případě, kdy dva procesy čekají na uvolnění zámku tím druhým procesem naráz
- **Coffmanovy podmínky** - 4 nutné podmínky pro to, aby mohl deadlock nastat
    - Vzájemné vyloučení (Mutual exclusion) - Prostředek může v jednom okamžiku používat jenom jeden proces (aby nedošlo k porušení konzistence dat). 
    - Drž a čekej (Hold & wait) - Proces může žádat o další prostředky, i když už má nějaké přiděleny. 
    - Neodnímatelnost (No preemption) - Jakmile proces zmíněný prostředek vlastní, nelze mu ho bezpečně odejmout, musí ho sám vrátit. 
    - Cyklické čekání (Circular wait) - Je možné uzavřít cyklus z procesů čekající každý na svého předchůdce – respektive k deadlocku dojde, jakmile je tento cyklus uzavřen.

## Správa virtuální a fyzické paměti, souborové systémy

Podobné jako v APO
**FAP** 
- fyzický adresní prostor 
- skutečná paměť počítače – RAM 
- velikost závisí na možnostech základní desky a na osazených paměťových modulech

**LAP** 
- logický adresní prostor 
- někdy také virtuální paměť 
- velikost záleží na architektuře CPU

**Výhody systému bez správy paměti:** 
- rychlost přístupu do paměti 
- jednoduchost implementace 
- lze používat i bez operačního systému – robustnost 

**Nevýhody systému bez správy paměti:** 
- Nelze kontrolovat přístup do paměti (kdokoli může cokoli v paměti přepsat) 
- Omezení paměti vlastnostmi HW

**Segmentace**
Program je kolekce segmentů - každý má svůj logický význam (hlavní program, procedura, funkce, objekt a jeho metoda, proměnné, pole, ..)
Základní úkol – převést adresu typu (segment selector, offset) na adresu FAP

![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559051379868_image.png)


Výhody segmentace 
- Segment má délku uzpůsobenou skutečné potřebě 
    - minimum vnitřní fragmentace 
    - Lze detekovat přístup mimo segment, který způsobí chybu segmentace – výjimku typu „segmentation fault“ 
- Lze nastavovat práva k přístupu do segmentu 
- Lze pohybovat s daty i programem v fyzické paměti - posun počátku segmentu je pro aplikační proces neviditelný a nedetekovatelný 

Nevýhody segmentace 
- Alokace segmentů v paměti je netriviální úloha 
    - Segmenty mají různé délky. 
    - Při běhu více procesů se segmenty ruší a vznikají nové. Problém s externí fragmentací 
- Režie při přístupu do paměti

**Fragmentace**
*Externí (vnější) fragmentace* - Celkové množství volné paměti je sice dostatečné, aby uspokojilo požadavek procesu, avšak prostor není souvislý, takže ho nelze přidělit 
*Interní (vnitřní) fragmentace* - Přidělená díra v paměti je o málo větší než potřebná, avšak zbytek je tak malý, že ho nelze využít

**Stránkování**
FAP se dělí na úseky zvané rámce - Pevná délka, zpravidla v celistvých mocninách 2 
LAP se dělí na úseky zvané stránky - Pevná délka, shodná s délkou rámců 
Proces o délce n stránek se umístí do n rámců, rámce ale nemusí v paměti bezprostředně sousedit 
Mechanismus překladu logická adresa → fyzická adresa  - pomocí tabulky stránek (PT = Page Table) 
Může vznikat vnitřní fragmentace - stránky nemusí být zcela zaplněny

**Nevýhody stránkování**
1. Fragmentace paměti: Paměť je rozdělena na menší stránky, což může vést k fragmentaci virtuální i fyzické paměti. Fragmentace paměti může ovlivnit výkon systému a může se stát obtížným najít dostatečně velký blok paměti pro zavedení nové stránky.
2. Zvýšená režie paměti: Při přístupu k paměti jsou potřebné další překlady adres mezi virtuální a fyzickou pamětí. Tyto překlady a správa tabulek stránek zvyšují režii paměti a mohou snížit efektivitu systému.
3. Zpoždění přístupu k paměti: Při přístupu k stránkám, které nejsou aktuálně v paměti, je nutné provést operaci nazývanou "page fault" (chyba stránky), která způsobuje zpoždění. Pokud je stránka načítána z disku, může dojít k výraznému zpomalení přístupu k paměti a ovlivnění celkového výkonu systému.
4. Potřeba správy tabulek stránek: Stránkování vyžaduje správu tabulek stránek, které mapují virtuální adresy na fyzické adresy. Správa těchto tabulek může zahrnovat dodatečnou režii a vyžadovat dodatečný prostor v paměti.
5. Vypršení stránek na disku: Pokud je fyzická paměť vyčerpána a je třeba uvolnit místo pro nové stránky, je nutné vyprázdnit stránky z paměti na disk. Toto vyprazdňování a přesouvání stránek může způsobit zpoždění a snížit výkon systému.

![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559052044789_image.png)

Může být i více úrovní tabulek

**Překlad virtuální adresy na fyzickou** (zdroj: YT David B lack-Schaffer)
- page offset podle velikosti stránky, zůstavá stejný i v FAP
- číslo stránky se převede pomocí stránkovací tabulky na fyzické číslo stránky
![[Pasted image 20230608171951.png]]
![[Pasted image 20230608172427.png]]

**Virtualizace paměti**
Kdy stránku zavádět do FAP? (Fetch policy) 
- Stránkování při spuštění 
    - Program je celý vložen do paměti při spuštění 
    - velmi nákladné a zbytečné, předem nejsou známy nároky na paměť, dříve se nevyužívalo, dnes je využívána 
- Stránkování či segmentace na žádost (Demand Paging/Segmentation) 
    - Tzv. „líná metoda“, nedělá nic dopředu 
    - Řeší problémy s dynamickou alokací proměnných 
- Předstránkování (Prepaging) 
    - Nahrává stránku, která bude pravděpodobně brzy použita 
- Čištění (Pre-cleaning) 
    - změněné rámce jsou ukládány na disk v době, kdy systém není vytížen 
- Kopírovat při zápisu (copy-on-write) 
    - Při tvorbě nového procesu není nutné kopírovat žádné stránky, ani kódové ani datové. U datových stránek se zruší povolení pro zápis. 
    - Při modifikaci datové stránky nastane chyba, která vytvoří kopii stránky a umožní modifikace

Stránkování – **politika nahrazování** - Musí se vyhledat vhodná stránka pro náhradu, když je FAP plná:
- LRU (Least recently used) - zahodí se nejdéle nepoužitá stránka
- Druhá šance - zahodí se až stránka, ke které se přistoupilo a byla již použita
- NRU (not recently used) - druhá šance s přidáním dirty bitu (stránka byla modifikována), zahodí se primárně stránka, která byla využita i modifikována

Thrashing – "Výprask" – Jestliže proces nemá v paměti dost stránek, dochází k výpadkům stránek velmi často a počítač nedělá nic jiného než výměny stránek

**Copy on write metoda**
The Copy on Write mechanism is a memory management technique used by modern operating systems to optimize memory usage and reduce overhead when creating new processes. Copy on Write works by allowing multiple processes to share the same memory pages until one of the processes modifies the page.

### TLB a víceúrovňové stránkování
- Cache obsahuje skutečná data z paměti
- TLB obsahuje pouze mapování do paměti(urychluje proces překladu adres)
- V TLB je tag - číslo stránky a příslušné číslo rámce v FAP
![[Pasted image 20230608173457.png]]
![[Pasted image 20230608174355.png]]
![[Pasted image 20230608174926.png]]
### Virtuální paměťový prostor

![](https://paper-attachments.dropbox.com/s_CBD745353E168C5CF1A67E4FA2573E59A956A598A03B4E79EA21DF1273428276_1559055898147_image.png)


### Typy alokace paměti:
- Explicitní – program alokuje a uvolňuje paměť pro dynamické proměnné (např. funkce malloc a free v jazyce C, new/delete v C++)
- Implicitní – program alokuje paměť pro nové proměnné, ale již je neuvolňuje (např. garbage collector v Jave nebo Pythonu)

Hlavní cíle:
- co nejrychlejší provedení funkcí malloc a free, měla by být rychlejší než lineárně k počtu alokovaných bloků 
- minimalizovat fragmentaci paměti, co nejlepší využití paměti souvisí s minimální fragmentací (vnitřní i vnější) 

Vedlejší cíle:
-  Prostorová lokalita: 
    - bloky alokované v podobném čase by měly být blízko u sebe 
    - bloky podobné velikosti by měly být blízko u sebe 
- Implementace by měla být robustní: 
    - operace free by měla proběhnout pouze na správně alokovaném objektu 
    - alokace by měla umožnit kontrolovat, zda se jedná o odkaz na alokované místo

Různé způsoby: 
- alokace a uvolňování
- udržování informace o volných blocích
- výběru volného bloku

viz https://cw.fel.cvut.cz/old/_media/courses/b4b35osy/lekce07.pdf

## Souborové systémy
- Trvalé úložiště dat. Rotační nebo flash. 
- Posloupnost bloků nebo sektorů
- Oddíly - jeden fyzický disk, vícero logicky → mám jednu plotnu ale disky C,D,E
- Na začátku disku je tabulka definující typ, (jméno), počáteční a koncový sektor oddílu
	- Master Boot Record (MBR) – pozůstatek MS-DOSu, 1. sektor na disku (512 B), obsahuje místo pro 4 oddíly.
	- GUID Partition Table (GPT) – modernější, více informací, „neomezený“ počet oddílů.

**Souborový systém**
- Způsob organizace dat na pevném disku 
- Data uložená v pojmenovaných souborech 
- Soubory v adresářích (složkách) 
- Hierarchická struktura adresářů
- Adresář je seznam dvojic («jméno souboru», «umístění»)
- Metadata = data o datech
- Organizace pomocí B stromu

**Rozložení dat na disku**
- Souborový systém definuje velikost bloku (např. 4 KiB)
- Prostor na disku je vždy alokován v násobcích velikosti bloku
- Superblok určuje umístění kořenového adresáře a další informace o souborovém systému Vždy na předem známém místě (např. 1. blok na disku) Často uložen ve více kopiích
- Informace o volných blocích OS musí mít přehled, který blok je volný a který obsazený Podobné jako v alokátorech paměti – např. freelist Typicky bitová mapa (1 bit na blok) Kopie v paměti pro urychlení přístupu (cache)
- Bloky ukládající obsah souborů Existuje mnoho způsobů, jak je organizovat
![[Pasted image 20230608185608.png]]
![[Pasted image 20230608185640.png]]
![[Pasted image 20230608185715.png]]
![[Pasted image 20230608185738.png]]
![[Pasted image 20230608185933.png]]
![[Pasted image 20230608190038.png]]
![[Pasted image 20230608190124.png]]
### Žurnálovací systém souborů
- Před tím, než se začne souborový systém modifikovat, se uloží seznam potřebných modifikací na vyhrazené místo – žurnál
- Pokud dojde k pádu systému, zkontroluje se žurnál, změny disku v něm nalezené se provedou dodatečně
- Žurnálování se někdy nazývá „dopředné logování“
- Implementováno: NTFS, ext3, …
![[Pasted image 20230608191520.png]]

**Sekvenční** čtení - vhodnější spojové struktury - FAT, méně vhodné indexové systémy(ext)
**Náhodné** čtení - nevhodné FAT, vhodnější indexové - ext

## Bezpečnost
**TCB**
Všechny systémy obsahují entity, kterým se věří
- pokud selžou, systém nemusí být bezpečný
- hardware, OS, administrátor serveru, …
Trusted Computing Base (TCB):
- množina všech takových entit
Bezpečné systémy musí mít důvěryhodné TCB
- minimalizace TCB je klíčem k důvěryhodnosti

![[Pasted image 20230608192141.png]]
![[Pasted image 20230608192327.png]]
Předejít útoku lze pomocí náhodného rozložení adresního prostoru

**Běžné mechanismy zabezpečení v OS:**
- Systémy pro kontrolu přístupu - kontrola, k čemu může daný proces přistupovat 
- Autentizační systémy - potvrzení identity toho, jehož „jménem“ proces běží 
- Logování - Kvůli auditům, detekci útoků, vyšetřování a obnovu 
- Šifrování souborových systémů - HW lze šifrovat celý disk, SW jen souborový systém (nelze šifrovat partition table) 
- Správa pověření (credentials) 
- Automatické aktualizace

Safety – ochrana okolí před systémem
Security – ochrana systému před okolím

## Virtualizace
![[Pasted image 20230610102016.png]]
![[Pasted image 20230610102234.png]]
![[Pasted image 20230610102344.png]]
![[Pasted image 20230610102413.png]]
![[Pasted image 20230610102438.png]]
![[Pasted image 20230610102515.png]]
![[Pasted image 20230610102621.png]]
![[Pasted image 20230610102651.png]]
![[Pasted image 20230610102709.png]]