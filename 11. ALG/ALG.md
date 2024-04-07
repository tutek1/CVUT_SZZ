# 11. Základní algoritmy a datové struktury pro vyhledávání a řazení. Vyhledávací stromy, rozptylovací tabulky. Prohledávání grafu. Úlohy dynamického programování. Asymptotická složitost a její určování.

# Řád růstu funkcí, asymptotická složitost algoritmu.
Asymptotická složitost je způsob klasifikace počítačových algoritmů. Určuje operační náročnost algoritmu tak, že zjišťuje jakým způsobem se bude chování algoritmu měnit v závislosti na změně velikosti (počtu) vstupních dat.

## Třída složitosti
Funkce vyjadřující počet operací potřebných ke zpracování dat.
$1 \ll log ( n ) \ll n \ll n \cdot log ( n ) \ll n^k \ll k^n \ll n! \ll n^n$
Pokud spadají dva algoritmy do různých tříd asymptotické složitosti, pak vždy existuje takové množství dat, od kterého je asymptoticky lepší algoritmus vždy rychlejší, bez ohledu na to, kolikrát je některý z počítačů výkonnější.

## Řád růstu funkcí
U většiny algoritmů nelze říci, že jejich složitost odpovídá přesně jedné třídě, protože rychlost algoritmu závisí také na povaze dat. Z tohoto důvodu se používáme řád růstu funkcí, který zohledňuje nejhorší i nejlepší možný běh algoritmu.

- $O(f(x))$ - $Omicron(f(x))$ – algoritmus probíhá asymptoticky stejně rychle nebo pomaleji než $f( x )$, horní odhad
- $\Omega (f(x))$ - $Omega(f(x))$ – algoritmus probíhá asymptoticky stejně rychle nebo rychleji než $f( x )$, spodní odhad
- $\Theta (f(x))$ - $Theta(f(x))$ – algoritmus probíhá asymptoticky stejně rychle jako $f( x )$, zároveň platí $O(f(x))$ a $\Omega (f(x))$

Funkce f(x) ohraničuje funkci našeho algoritmu g(x) ,Ο(f(x)) vyjadřuje ohraničení shora, zatímco Ω(f(x)) zdola. Θ(f(x)) pak značí ohraničení z obou stran.

![|500](https://paper-attachments.dropbox.com/s_BC1E974E5ABEFC3F292D9998F274BE0C3006E1D22710D661A1E31861B511B37F_1559168412068_Screenshot_2019-05-30+Algorithms+and+Data+Structures+Cheatsheet6.png)

![|500](https://paper-attachments.dropbox.com/s_BC1E974E5ABEFC3F292D9998F274BE0C3006E1D22710D661A1E31861B511B37F_1559168416482_Screenshot_2019-05-30+Algorithms+and+Data+Structures+Cheatsheet7.png)

![|500](https://paper-attachments.dropbox.com/s_BC1E974E5ABEFC3F292D9998F274BE0C3006E1D22710D661A1E31861B511B37F_1559168422574_Screenshot_2019-05-30+Algorithms+and+Data+Structures+Cheatsheet8.png)

# Rekurze, Stromy, Binární stromy, prohledávání s návratem
## Rozděl a panuj
Tato metoda označuje ty algoritmy pro práci s daty, které řeší problém rozdělením řešené úlohy na **dílčí části (podproblémy)**, nad kterými se provádí algoritmická operace. Často se tato metoda implementuje rekurzivně nebo iterativně a původní úloha se dělí na stále menší části.

## Rekurze
Iterativně se úloha rozkládá do rekurzivních stromů (grafická vizualizace rozvoje rekurze).
![[Pasted image 20230607142412.png]]

## Mistrovská věta
$T(n) = aT(n/b) + f(n)$, kde $a >= 1$, $b > 1$ a f(n) je asymptoticky kladná funkce.
![[Pasted image 20230607143323.png]]

![[Pasted image 20230607143358.png]]

![[Pasted image 20230607143410.png]]
## Stromy
Jedná se o hierarchickou strukturu, kde každý rodič má 0 až mnoho dětí a každé dítě právě jednoho rodiče takovým způsobem, že v této struktuře nejsou cykly. Uzel, který je prarodičem všech ostatních uzlů nazveme kořenem (z pohledu teorie grafů tím vytvoříme orientovaný strom). Uzel, který nemá žádné potomky nazýváme listem.
Být stromem je rekurzívní vlastnost - každý podstrom stromu S je také stromem.

Lze reprezentovat aritmetický výraz, datovou strukturu (BVS, halda), rozhodovací strom, hierarchii (rodokmen, zaměstnanci), rekurzivní volání, stavový prostor, atd...

Hloubka stromu = hloubce nejhlubšího listu, přičemž kořen má hloubku 0.

## Binární strom
Binární strom je orientovaný graf s jedním vrcholem (kořenem), z něhož existuje cesta do všech vrcholů grafu. Každý vrchol binárního stromu může mít maximálně dva orientované syny a s výjimkou kořene právě jednoho předka. Kořen předka nemá.

V praktickém programování je obvykle binární strom reprezentován dvěma způsoby:
1. pomocí dynamické struktury, kde jsou hrany reprezentovány ukazateli 
2. pomocí pole, kde prvek s indexem i má následníky s indexem 2i+1 a 2i+2 (za předpokladu, že pole je indexováno od 0). Takto je například reprezentovaná halda v algoritmu heapsort. (také viz. PRP)

Za zmínku stojí speciální typ binárního stromu - **Vyvážený binární** strom, jehož hloubka listů se od sebe liší maximálně o jedna.

## Prohledávání s návratem
Začne se v kořeni a pro aktuální uzel se zpracuje a projde se levý a pravý podstrom.

Jsou 3 způsoby procházení a zpracování stromu:
- **PreOrder** - uzel -> levý podstrom -> pravý podstrom
- **InOrder** - levý podstrom -> uzel -> pravý podstrom
- **PostOrder** - levý podstrom -> pravý podstrom -> uzel

Příklad osmi dam na šachovnici - vytvoří se strom testovaných pozic, kde každé dítě má omezenější možnosti kvůli položení dány, velké zrychlení oproti Brute Force

# Fronta, zásobník, průchod stromem/grafem do šířky/hloubky.
## Fronta
- FIFO - first in first out, odebírá se z čela fronty a přidává na konec
- Lze implementovat v cyklickém poli

## Zásobník
- LIFO - last in first out, odebírá se poslední vložený prvek (čelo) a vkládá se na čelo
- Lze implementovat jednoduše v poli

## BFS (průchod do šířky) stromu
Vytvoří se prázdná fronta, vloží se tam kořen a dokud není fronta prázdná tak se:
- Odebere první uzel z fronty a zpracuje se
- Po zpracování se do fronty vloží jeho potomci
- Repeat

Lze rozšířit na obecné ne/orientované grafy, s tím, že máme matici sousednosti nebo seznam sousedů pro každý vrchol. Složitost $O(|V| + |E|)$.

## DFS (průchod do hloubky)
Prohledává strom nebo graf do hloubky. Lze implementovat rekurzivně, nebo zásobníkem (jiné pořadí uzlů a uzel může být vložen opakovaně). Složitost $O(|V| + |E|)$.

# Binární vyhledávací stromy, AVL a B- stromy
## Binární vyhledávací strom (BVS/BST)
Binární vyhledávací strom (BST - z angl. Binary Search Tree) je datová struktura založená na binárním stromu, v němž jsou jednotlivé prvky (uzly) uspořádány tak, aby v tomto stromu bylo možné rychle vyhledávat danou hodnotu. To zajišťují tyto vlastnosti:
- Jedná se o binární strom, každý uzel tedy má nanejvýš dva syny − levého a pravého.
- Každému uzlu je přiřazen určitý klíč. Podle hodnot těchto klíčů jsou uzly uspořádány.
- Levý podstrom uzlu obsahuje pouze klíče menší než je klíč tohoto uzlu.
- Pravý podstrom uzlu obsahuje pouze klíče větší než je klíč tohoto uzlu.

1. **Vyhledávání**
Vyhledání konkrétní hodnoty v binárním vyhledávacím stromu typicky probíhá rekurzivně. Začíná v kořeni. V každém kroku porovná hledanou hodnotu s klíčem zkoumaného uzlu. Pokud jsou si rovny, hodnota byla nalezena. Je-li hledaná hodnota menší, pokračuje hledání v levém podstromu. Je-li větší, bude hledání pokračovat v pravém podstromu. Díky uspořádání stromu je cesta k hledané hodnotě jednoznačně určena. Časová složitost je $\theta(log N)$. Možné vylepšení pomocí exponenciálního vyhledávání dokud hodnotu nepřestřelíme a pak lineárně. Podobně jako při určení maximální rychlosti stahování dat z internetu.

![[Pasted image 20230607153825.png]]

2. **Přidání uzlu**
Vložení nového uzlu začíná hledáním jeho pozice ve stromu – postupuje se stejně jako při vyhledávání, jako hledaná hodnota se použije klíč vkládaného uzlu. Tato fáze může vést ke dvěma různým výsledkům:

- klíč byl nalezen, strom tedy dotyčnou hodnotu již obsahuje a není třeba ji vkládat (komplikovanější varianty připouštějící vícenásobný výskyt stejného klíče by pokračovaly dál do podstromu připouštějícího rovnost)
- algoritmus narazil na neexistující uzel, nový uzel bude vložen na toto místo, protože sem podle hodnoty svého klíče patří

3. **Odstranění uzlu**
- **Odstranění listu:** Odstranění uzlu bez potomků se jednoduše provede odstraněním uzlu ze stromu.
- **Odstranění uzlu s jedním potomkem:** Provede se nahrazením uzlu uzlem potomka.
- **Odstranění uzlu se dvěma potomky:** Nechť se odstraněný uzel nazývá N. Pak je hodnota uzlu N nahrazena nejbližší vyšší (uzel pravého podstromu, který je nejvíc vlevo (nejlevější)), nebo nižší hodnotou (uzel levého podstromu, který je nevíc vpravo (nejpravější)). Takový uzel má nanejvýš jednoho potomka, lze jej tedy ze stromu vyjmout podle jednoho z předchozích pravidel. V dobré implementaci je doporučeno obě varianty střídat, jinak dochází k narušení rovnováhy.
![[Pasted image 20230607154443.png]]
![[Pasted image 20230607164849.png]]

## AVL strom
AVL strom je datová struktura pro uchovávání údajů a jejich vyhledávání. Pracuje v logaritmicky omezeném čase. Jedná se o **samovyvažující se** **binární vyhledávací strom**.

- Vrchol má maximálně dva následníky (plyne z vlastností binárního stromu, kterým AVL strom je).
- V levém podstromu vrcholu jsou pouze vrcholy s menší hodnotou klíče
- V pravém podstromu vrcholu jsou pouze vrcholy s větší hodnotou klíče
- **Délka nejdelší větve levého a pravého podstromu se liší nejvýše o 1 (vyvážení AVL stromu).**
![[Pasted image 20230607165132.png]]

Poslední vlastnost je demonstrována na následující dvojici stromů.

1. **Vyhledávání**
Totožné jako u vyhledávání v BVS.

2. **Přidání uzlu**
Totožné jako u přidávání v BVS. Strom se ale po přidání může stát nevyváženým, proto je potřeba provést vyvažovací rotace.

3. **Rotace**
![](https://paper-attachments.dropbox.com/s_23B84C21F689A1624CC550CD5FDB1C77970B3950F7644345609CE3DFBEA20F1F_1558863471759_rotations.gif)

1. Ve směru rotace nahradíte špatně vyvážený uzel potomkem.
2. Pokud by se stalo, že by nově dosazený vrchol měl 3 potomky, tak jeho původního potomka umístíte pod právě sesazený vrchol.

Kdy jakou použít? Od přidaného (nebo smazaného, viz dále) uzlu postupujeme směrem ke kořenu a aktualizujeme hloubky podstromů v každém navštíveném uzlu.

- Když narazíme na rozvážený uzel, do kterého jsme bezprostředně došli dvěma hranami doleva nahoru, provedeme v tomto uzlu L rotaci. 
- Když narazíme na rozvážený uzel, do kterého jsme bezprostředně došli dvěma hranami doprava nahoru, provedeme v tomto uzlu R rotaci.
- Když narazíme na rozvážený uzel, do kterého jsme bezprostředně došli hranami doleva a pak doprava nahoru, provedeme v tomto uzlu LR rotaci (tedy nejprve levou a pak pravou).
- Když narazíme na rozvážený uzel, do kterého jsme bezprostředně došli hranami doprava a pak doleva nahoru, provedeme v tomto uzlu RL rotaci.

**Grafický příklad LR rotace**
![[Pasted image 20230607165454.png]]

4. **Odstranění uzlu**
Opět totožné jako u odstranění v BVS. Poté postupujeme od místa smazání nahoru ke kořeni a aktualizujeme výšky podstromů v každém uzlu. V případě nevyváženosti použijeme stejná pravidla jako u vkládání prvku.

## B-strom
![](https://paper-attachments.dropbox.com/s_23B84C21F689A1624CC550CD5FDB1C77970B3950F7644345609CE3DFBEA20F1F_1558863617583_btree-figure4b.png)


B-strom je druh stromu, který ale **nesouvisí** s binárními stromy. Jeho definice

- Kořen má nejméně dva potomky, pokud není listem
- Každý uzel kromě kořene a listu má nejméně $[ \frac{n}{2} ]$ a nejvýše $n$ potomků.
- Každý uzel kromě kořene má nejméně $[ \frac{n}{2} ] -1$ a nejvýše $n-1$ položek.
- Všechny cesty od kořene k listům jsou stejně dlouhé

B-strom je díky těmto vlastnostem vyvážený, operace přidání, vyjmutí i vyhledávání tedy probíhají v logaritmickém čase.

**Operace Find**
![[Pasted image 20230607165932.png|500]]
Operace Insert
- Pokud vložením nepřekročíme kapacitu uzlu, tak neprobíhá žádné vyvážení.
- Pokud překročíme tak:
![[Pasted image 20230607170130.png|500]]
- Pokud by se to stalo vícenásobně tak:
![[Pasted image 20230607170152.png|500]]![[Pasted image 20230607170215.png|500]]![[Pasted image 20230607170305.png|500]]

## Srovnání stromů

|         | AVL s n uzly    | BVS s n uzly     | B-strom s n uzly |                 |
| ------- | --------------- | ---------------- | ---------------- | --------------- |
| Operace | Vývážený        | Možná nevyvážený | Vyvážený         | Vyvážený        |
| Find    | Ο(log(n))       | Ο(n)             | Ο(log(n))        | Ο(log(n))       |
| Insert  | Θ(log(n))       | Ο(n)             | Θ (log(n))       | Θ(log(n))       |
| Delete  | Θ(log(n))       | Ο(n)             | Θ(log(n))        | Θ(log(n))       |

Pár poznámek na závěr
- označení binární strom je nadmnožina pro binární vyhledávací strom a AVL strom 
- Vyváženost zajišťuje AVL stromu lepší asymptotickou složitost. V tabulce srovnávající jednotlivé stromy je uveden sloupec „vyvážený binární vyhledávací strom”, nicméně to, že náš BVS na vstupu bude skutečně vyvážený, nemáme zaručeno. U AVL stromu to zaručeno je.
- B-strom a AVL strom mají stejnou složitost, každý se ale hodí v jiné situaci. Využití b-stromu může být v aplikacích, kdy není celá struktura uložena v paměti RAM, ale v nějaké sekundární paměti, jako je pevný disk (například databáze). Protože přístup do tohoto typu paměti je náročný na čas (hlavně vyhledání náhodné položky), snažíme se minimalizovat počet přístupů do této paměti. 

# Algoritmy řazení: Insert Sort, Selection Sort, Bubble Sort, QuickSort Merge Sort, Halda, Heap Sort, Radix sort, Counting Sort.
V popiscích jednotlivých algoritmů se vyskytují následující hesla a charakteristiky:

**Stabilní/nestabilní algoritmus**
Stabilním algoritmus je ten, který zachovává pořadí stejných prvků (mají stejnou hodnotu), tak jak byly na vstupu v seznamu. Seřadí je na odpovídající místo, ale v rámci stejných prvků zůstanou ve stejném pořadí. U nestabilního algoritmu toto nezaručíme.
**Nestabilní**: Selection sort, quick sort, heap sort
**Stabilní**: Merge, Bubble, Insertion, Radix

## Insert Sort
Prohlásím první prvek za seřazený. Vezmeme si další prvek a po dvojicích ho porovnáváme s předešlými "seřazenými" prvky. Pokud je předešlý prvek větší, tak je vyměníme a opakujeme dokud to platí. Jakmile toto neplatí, vezmeme první neseřazený prvek a postupujeme stejným způsobem. 

## Selection Sort
Pamatuji si ukazatel na první neseřazený prvek v seznamu. Procházím seznam dokud nenajdu nejmenší prvek a ten vyměním za první neseřazený prvek a posunu si ukazatel na začátek o jedna.

## Bubble Sort
Několikrát se prochází celý seznam po dvojících. Tyto dvojice se prohodí pokud pokud je první prvek větší než druhý. Takto se prochází celý seznam dokud není seřazený.

## Quicksort
Quicksort je velmi rychlý **nestabilní** řadící algoritmus na principu **rozděl a panuj** s asymptotickou složitostí $O(n^2)$ a s očekávanou složitostí $O(n \cdot log(n))$ .

**Průběh algoritmu**
1. Levý index se nastaví na začátek zpracovávaného úseku pole, pravý na jeho konec, zvolí se pivot, nejjednodušeji tak, že se vybere prvek na začátku zpracovávaného úseku. Levý index se pohybuje doprava a zastaví se na prvku větším nebo rovném pivotovi. Pravý index se pohybuje doleva a zastaví se na prvku menším nebo rovném pivotovi.
2. Pokud je levý index ještě před pravým, příslušné prvky se prohodí, a oba indexy se posunou o 1 ve svém směru. Jinak pokud se indexy rovnají, jen se oba posunou o 1 ve svém směru.
3. Cyklus se opakuje, dokud se indexy neprekříží, tj. pravý se dostane pred levého.
4. Následuje rekurzivní volání (zpracování „malých" a „velkých" zvlášť) na úsek od začátku do pravého indexu včetně a na úsek od levého indexu včetně až do konce, má-li príslušný úsek délku větší než 1.
![[Pasted image 20230608002304.png|500]]

## Mergesort
Mergesort je **stabilní** řadicí algoritmus typu **rozděl a panuj** s asymptotickou složitostí Ο(n\*log(n)). Merge sort pracuje na bázi **slévání** již seřazených částí pole.
![[Pasted image 20230608115544.png|500]]

**Merge**
Proces merge nebo-li slévání probíhá následovně. Máme dva seznamy, u kterých víme, že jsou seřazeny ve stejném pořadí. Postupně je procházíme a díváme se, který z právě iterovaných členů je větší (případně menší, záleží, jak srovnávám). Ten větší (resp. menší) z dvojice vložíme do pomocného seznamu. Takto se dostaneme do fáze, kdy jeden ze seznamů, kterými iterujeme, je už prázdný. Můžeme tedy zbytek druhého vzít a celý ho zkopírovat na konec do pomocného seznamu.

**Průběh algoritmu**
Algoritmu dodáme array, který postupným půlením rekurzivně rozdělíme do nejmenších skupin, tedy dvojic a případně lichého členu. Pak se aplikuje proces merge na tyto malé jednotky, a ve stacku, který se nám během rekurze vytvořil, skočíme o úroveň výš, kde sléváme podseznamy délky 4, případně 3. Takto skáčeme až do chvíle, kdy se ocitneme v hlavní smyčce programu a sléváme levou a pravou polovinu seznamu, který nám byl vložen na vstupu.
![[Pasted image 20230608115731.png|500]]![[Pasted image 20230608121153.png|500]]

## Heapsort
Heapsort (řazení haldou) je jedním z nejefektivnějších řadících algoritmů založených na porovnávání prvků s asymptotickou složitostí $O(n \cdot log(n))$. Heapsort je **nestabilní**.

**Vlastnosti haldy**
Halda je binární strom s rekurzivní vlastností býti haldou. Rekurzivita vlastnosti značí, že i každý podstrom haldy je taktéž haldou. V každé haldě také platí, že otec má vždy vyšší (v některých definicích nižší) hodnotu než jeho potomci. Při její implementaci polem pak také platí, že pokud je otec na indexu i , tak jsou jeho potomci na indexech 2i+1 a 2i+2 (indexováno od 0). Z tohoto uspořádání plyne, že tvar haldy je pyramida s částečně useknutou pravou stranou základny.

**Operace delete**
Odebírá se vždy kořen haldy, v takovém případě se místo něj vloží poslední prvek v haldě. Tím se však poruší vlastnost haldy a tak se porovná nový kořen s jeho dětmi a prohodí se podle hodnoty. To rekurzivně pokračuje dokud není vlastnost haldy obnovena.

**Průběh algoritmu**
![[Pasted image 20230608123150.png|500]]

## Radixsort
Princip radix sortu vychází přímo z definice stabilního řazení – řadicí algoritmus je stabilní, pokud zachovává pořadí klíčů, které mají stejnou hodnotu (tj. pokud struktury seřadíme napřed dle klíče **A**, poté podle klíče **B**, tak jsou seřazeny podle **B**, a kde jsou si hodnoty **B** rovny, tam jsou struktury v pořadí daném klíčem **A**).

**Postup**
1. Začneme s poslední číslicí a pole seřadíme podle ní (například pomocí Counting Sort nebo separátních polí pro každou číslici)
2. Opakujeme pro všechny číslice
![[Pasted image 20230608131544.png|500]]![[Pasted image 20230608131602.png|500]]![[Pasted image 20230608131621.png|500]]

Implementuje se pomocí pomocných polí s indexy pořadí v daných polí podle znaku. (https://cw.fel.cvut.cz/b211/_media/courses/b4b33alg/alg09_2011.pdf)

## Counting sort
Vytvoříme si pole četnosti každého čísla v seznamu (zjistíme max a min). Pak jednou projedeme polem a podle výskytu čísla upravíme četnost. Ve finále projdeme pole četností a do výstupního pole dáme tolik aktuálního prvku jako je jeho četnost.

## Srovnání složitostí

![](https://paper-attachments.dropbox.com/s_C9B1F88AC5AA284A409F6080E489C8DE67F157FBA659156DF39390DAA28A4805_1650386869125_prehledRadicichAlgoritmu.PNG)

# Dynamické programování, struktura optimálního řešení, odstranění rekurze.
Je to všeobecná strategie pro řešení optimalizačních úloh.
Významné vlastnosti:
- Hledané optimální řešení lze sestavit z vhodně volených optimálních řešení téže úlohy nad redukovanými daty.
- V rekurzivně formulovaném postupu řešení se opakovaně objevují stejné menší podproblémy. DP umožňuje obejít opakovaný výpočet většinou jednoduchou tabelací výsledků menších podproblémů, tedy volně řečeno, přepočítáním menších výsledků.

V následujícím příkladu je ukázána složitost rekurzivního volání, oproti přepočítání tabulky, kde vycházíme z předešle vypočítaných dat.
![[Pasted image 20230608133951.png|500]]![[Pasted image 20230608134015.png|500]]


# Nejdelší společná podposloupnost
Mějme dvě posloupnosti písmen a chceme najít nejdelší společnou podposloupnost.
Například u posloupností {BDCABA} {ABCBDAB} je řešení {BCBA}.
Časová složitost O(mn), kde m a n jsou délky řetězců.
![[Pasted image 20230609231658.png]]


# Optimální násobení matic
Různé pořadí násobení matic vyprodukuje různé množství operací a proto je vhodné počet operací minimalizovat.
![[Pasted image 20230608145413.png]] ![[Pasted image 20230608145426.png]]

Algoritmus probíhá pomocí sestrojení matice, kde na hlavní diagonále budou samé 0 (reprezentující počet operací na dosažení dané matice). Matice se pak naplňuje po diagonálách doprava nahoru
![[Pasted image 20230608150745.png]]
Pro každou buňku pak bereme minimum všech možných operací.
![[Pasted image 20230608151112.png]]
Nejmenší počet operací pak bude v pravém horním rohu.
Pokud chceme získat optimální uzávorkování, pamatujeme si v každé buňce i index matice (číslo sloupce), které bylo optimální a následujícím způsobem postupujeme:
![[Pasted image 20230608153823.png]]

# Problém batohu.
Máme $N$ předmětů a každý má nějakou váhu $V_i$ a nějakou cenu $C_i$ s tím, že máme batoh kapacity $K$. Naším úkolem je naplnit batoh tak, abychom maximalizovali cenu a nepřekročili kapacitu.

Rozdělujeme na:
- neomezenou variantu - lze použít každý předmět neomezeně
- 0/1 variantu - lze použít každý předmět nejvýše jednou

## Neomezená varianta
Úlohu převedeme na DAG, kde vrcholy jsou kapacity batohu od 1 do K a hrany reprezentují přidání předmětu (cena hrany = cena předmětu).

## 0/1 varianta
Uděláme si tabulku, kde sloupce budou reprezentovat jednotlivé kapacity od 0 do K a řádky použití jednotlivých objektů.

Tabulku vyplňujeme následujícím způsobem: (https://bbb04.felk.cvut.cz/playback/presentation/2.3/9e304a8d9f75b500527e81f95fcf96123c8a1602-1607075941901?meetingId=9e304a8d9f75b500527e81f95fcf96123c8a1602-1607075941901, slide 114)
![[Pasted image 20230608162038.png|500]]

# Rozptylovací tabulky (Hashing)
Základ datové struktury slovníku, kde operace search a insert mají konstantní složitost.

# Hashovací funkce, řešení kolizí
Vypočítává adresu z hodnoty klíče, závislá na vlastnostech klíčů a jejich reprezentaci v paměti. Ideálně by měl výpočet být co nejjednodušší, náhodný, rovnoměrně by měl využívat adresní prostor a generuje minimum kolizí.

## Řešení kolizí
Kolize nastávají, protože zobrazení z klíčů do adres hashovací funkce není prosté.

**Zřetězené tabulky**
Každá adresa si zachovává spojový seznam všech hodnot, které se namapují na danou adresu. Takže při kolizi se prvek zařadí na konec spojového seznamu. Insert je $O(1)$, search a delete v nejhorším případě $O(n)$.

**Otevřené tabulky**
Je dobré znát počet prvků předem (odhad). Tabulka může být více zaplněná než začne klesat výkonnost.
Pokud nastane kolize tak:
- Linear probing - prvek se buď vloží na pozici + "n", kde n je prvočíslo nebo číslo nesoudělné s velikostí pole, problém shlukování
- Double hashing - verze linear probing, kde se používá jedna hashovací funkce na určení adresy a druhá na určení "n"

## Srůstající tabulky (coalesced hashing)

### Standartní
**LISCH (late insert standard coalesced hashing)**
- Kolizní prvky se lineárně přidávají na konec tabulky
- Každý prvek, se kterým je kolize má v sobě ukazatel na místo, kde se kolidující prvek nachází
- Pokud nám nastane, že máme řetěz ukazatelů, tak nový prvek přidáme na konec
- ![[Pasted image 20230608173801.png]]

**EISCH (early insert standard coalesced hashing)**
- Funguje stejně jako LISCH, ale pokud nám nastane, že máme řetěz ukazatelů, tak nový prvek přidáme na začátek řetězu
- ![[Pasted image 20230608173629.png]]

### S pomocnou pamětí
**LICH a EICH**
- Analogické k LISCH a EISCH akorát máme pomocnou paměť sklepa na konci určenou pouze pro kolizní prvky

**VICH**
- připojuje prvek na konec řetězce, pokud řetězec končí ve sklepě (EICH), jinak na místo, kde řetězec opustil sklep (LICH)

## Univerzální hashování
Každá hashovací funkce má slabá místa, kdy pro různé klíče dává stejnou adresu. Proto je výhodné přizpůsobit hashovací funkci právě zpracovávaným klíčům.

Místo jedné hashovací funkce máme konečnou množinu funkcí mapujících U do intervalu $\{0, 1, …, m-1\}$. Tato množina je univerzální, pokud pro různé klíče $x,y \in U$ vrací stejnou adresu $h(x) = h(y)$ přesně v $|H|/m$ případech. Pravděpodobnost kolize při náhodném výběru funkce $h(k)$ je tedy přesně $1/m$.

Při spuštění programu jednu náhodně zvolíme. Funkci pak náhodně měníme jen v případě, že počet kolizí převyšuje přípustnou mez. V tomto případě je samozřejmě potřeba přehashovat celou tabulku.


