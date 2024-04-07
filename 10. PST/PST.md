# 10. Způsoby popisu rozdělení  náhodných veličin a vektorů. Odhady parametrů rozdělení. Základní statistické testy. Markovské řetězce a jejich asymptotické vlastnosti.

----------

http://cmp.felk.cvut.cz/~navara/stat/PMS_ebook.pdf
http://cmp.felk.cvut.cz/~navara/stat/

----------

https://cs.wikipedia.org/wiki/Rozd%C4%9Blen%C3%AD_pravd%C4%9Bpodobnosti - dobrý shrnutí popisu náhodných veličin a vektorů

Testování hypotéz - příklad
[https://youtu.be/VMRZO_yYWrA](https://youtu.be/VMRZO_yYWrA)

# Základní pojmy pravděpodobnosti

**Laplaceova (klasická) pravděpodobnost**

- **Náhodný pokus** má n ∈ N různých, vzájemně se vylučujících výsledků, které jsou stejně možné.
- **Elementární jevy** = výsledky náhodného pokusu
- **Množina všech elementárních jevů**: Ω
- **Jev** je podmnožina všech elementárních jevů ( A ⊆ Ω )
- **Pravděpodobnost jevu** A : $$P(A) = \frac{|A|}{|\Omega|}$$(Prostě počet správných výsledků děleno počet všech možných)
- **Jevové pole**: všechny jevy pozorovatelné v náhodném pokusu, zde expΩ (=množina všech podmnožin množiny Ω)

**Kolmogorovova pravděpodobnost**
- Elementárních jevů (=prvků množiny Ω) může být nekonečně mnoho, nemusí být stejně pravděpodobné
- **Jevy** jsou podmnožiny množiny Ω, ale ne nutně všechny. Tvoří podmnožinu A ⊆ exp Ω , která splňuje podmínky σ-algebry (viz. níže).
- **Pravděpodobnost** není určena strukturou jevů jako u Laplaceova modelu, je to funkce P: A → ⟨ 0,1 ⟩ , splňující podmínky: 
- (P1) P( 1 ) =1,
- (P2) P( ⋃n ∈ NAn ) = ∑ n ∈ N P(An) , pokud jsou množiny (=jevy) A n , n ∈ N , po dvou neslučitelné
- **Pravděpodobnostní prostor** je trojice ( Ω , A ,P ) , kde Ω je neprázdná množina, A je σ-algebra podmnožin množiny Ω a P je pravděpodobnost.

**σ-algebra**
σ-algebra je teoretický koncept výběru jistých podmnožin dané množiny, který splňuje pevně definované podmínky. Koncept σ-algebry umožňuje například zavést míru, čehož se dále využívá zejména v matematické analýze k budování pojmu integrál a právě v teorii pravděpodobnosti [wikipedia]. Systém podmnožin A nějaké množiny Ω musí splňovat podmínky:

1. ∅ ∈ A
2. A ∈ A ⇒ A ‾ ∈ A (uzavřenost vůči doplňku)
3. ( ∀ n ∈ N : A n ∈ A ) ⇒ ⋃ n ∈ N A n ∈ A ) (uzavřenost vůči sjednocení)

Nejmenší σ-algebra podmnožin R , která obsahuje všechny intervaly, se nazývá **Borelova σ-algebra**. Obsahuje všechny intervaly otevřené, uzavřené i polouzavřené, i jejich spočetná sjednocení, a některé další množiny, ale je menší ́než exp R . Její prvky nazýváme borelovské množiny.


# Nezávislost náhodných jevů
Pokud jsou jevy A a B nezávislé pak platí:
$P(A\cap B) = P(A) * P(B)$.
$P(A| B) = P(A)$.

$P(A\cup B) = P(A) + P(B) - P(A\cap B)$.

# Podmíněná pravděpodobnost
$P(A) = P(B)*P(A|B) +P(\neg B)*P(A|\neg B)$
$P(A|B) = \frac{P(A \cap B)}{P(B)}$

# Bayesova věta
$P(A|B) = \frac{P(B|A) * P(A)}{P(B)}$
$P(A \cap B) = P(A | B) * P(B) = P(B | A) * P(A)$

# Náhodná veličina (NV)
Měřitelná f-ce, její chování popisuje neklesající distribuční $F_x(t) = P(X <= t)$. Přiděluje hodnoty od 0 do 1. Pravděpodobnostní fce $p_x(t) = P(X=t)$.

## Diskrétní
Nabývá konečného počtu hodnot, distribuční funkce je schodovitá
![[DNH14.gif]]

## Spojitá
Nekonečný počet hodnot, P(X = t) = 0
$F_x(t) = \int_{-\inf}^{t} f(t) dt$, kde f(t) je funkce udávající hustotu.
![[Pasted image 20230609192510.jpg]]

## Smíšená NV
Směs diskrétní a spojité
$Mix_{c}(D,S), c \in <0,1>$
Platí: 
$F_x(t) = c F_D(t) + (1-c)F_S(t)$
$p_x(t) = c p_D(t) + (1-c)p_S(t)$

## Střední hodnota
Průměrná hodnota NV, nemusí existovat
Diskrétní - $\sum t * P(t)$ 
Spojité - $\int_{-inf}^{inf} t * f_x(t) dt$

- Je to číslo
- $E(x + y) = E(x) + E(y)$  //platí i pro mínus
- $E(rX) = r * E(X)$
- $E(r+X) = r + E(X)$

## Rozptyl
Jak moc jsou hodnoty odchýlené od průměru E(x)
$D(x) = \sigma^2_x$ (směrodatná odchylka)
$D(x)=E((x - E(x))^2) = E(x^2) - E^2(x)$
$E(x^2) = E^2(x) + D(x)$

Diskrétní - $E(x^2)=\sum k^2 P(X=k)$
Spojité - $E(x^2)= \int_{-inf}^{inf} t^2 * f_x(t) dt$

- $D(x) \ge 0$
- $D(x + r) = D(x)$
- $D(r) = 0$
- $D(xr) = D(x) * r^2$

## Směrodatná odchylka
Průměrná odchylka od průměru
- $\sigma_x \ge 0$
- $\sigma_r = 0$
- $\sigma_x*r = |r| \sigma_x$
- $\sigma_x+r = \sigma_x$

## Normovaná NV
norm X = $\frac{X - E(X)}{\sigma_x}$

## Momenty náhodných veličin
Pro náhodnou veličinu N je k-tý moment definován jako $E (X^k)$
1. moment = střední hodnota
2. moment = rozptyl + střední hodnota nadruhou

# Základnı́ typy diskrétních rozdělenı́
## Rovnoměrné
m možných výsledků, kde každý má stejnou pravděpodobnost, hod kostkou
$E(x) = (A+B)/2$, kde A je nejmenší hodnota a B největší, $D(x) = (b-a)^2/12$

## Alternativní
2 možné hodnoty (pst q a (1-q)), hod mincí
$E(x) = P(1) = q, D(x) = q(1 - q)$

## Binomické
Vyjadřuje počet úspěchů v sérii m pokusů, každý pokus má pst úspěchu q, počet orlů při hodu 20 mincemi
$E(x) = m*q, D(x) = mq(1 - q)$

## Poissonovo
počet událostí během intervalu délky t, $\lambda$ průměrný počet za jednotku času (třeba 5 hovorů za hodinu)
$E(x)= \lambda = D(x)$

## Geometrické
Počet neúspěchů něž nastane úspěch, pokaždé je stejná pst úspěchu "p", hod mincí dokud nespadne orel
$E(x) =(1-p)/p, D(x) =(1-p)/p^2$

## Hypergeometrické
Například "M" losů z nichž "J" vyhrává, tak udává počet výherních losů, z vytažených "S" losů
$E(x) = \frac{S*J}{M}, D(x)=\frac{SJ*(M-J)(M-S)}{M^2(M-1)}$

# Základnı́ typy spojitých rozdělenı́
## Rovnoměrné
Stejně dlouhé intervaly mají stejnou pst
$E(x) = (A+B)/2$, kde A je nejmenší hodnota a B největší, $D(x) = (b-a)^2/12$

## Normální
$E(x) = \mu, D(x) = \sigma^2$

## Exponenciální
doba čekání mezi 2 následnými výskyty událostí

## Logaritmicko normální
existuje 👍

# Náhodné vektory
n-rozměrná náhodná veličina, měřitelná funkce X: Ω → $R^n$ 
Používáme ho v případech, kdy je k popisu výsledku náhodného pokusu nutné použít více čísel.
**Příklad:** Chceme popsat vztah např. mezi výškou a váhou osob. K tomu potřebujeme více informací než jen popis jednotlivých náhodných veličin.

**Kovariance**
- určuje míru statistické závislosti mezi náhodnými veličinami
- $cov(X,Y) =E(XY) -E(X)E(Y)$
- $cov(X,X) =D(X)$
- $cov(Y,X)=cov(X,Y)$
- $cov(aX+b, cY+d) =a*c*cov( X,Y )$
- $cov(X,Y) =0$ pro nezávislé veličiny

**Korelace**
- je to kovariace pro normované náhodné veličiny
- $ϱ(X,Y) = cov(normX, normY)$
- Korelace nabývá hodnot ⟨ -1,1 ⟩
- Pro ϱ =0 říkáme, že jsou veličiny **nekorelované**

pro vektory platí $D(X+Y) =DX+DY+2cov(X,Y)$ 

# Čebyševova nerovnost
![[Pasted image 20230609225558.png]]
![[Pasted image 20230609225606.png]]

# Centrální limitní věta
Pokud platí předpoklady centrální limitní věty, tak výběrový průměr má jakožto náhodná veličina _asymptoticky normální rozdělení_. Jinak řečeno - rozdělení součtu n nezávislých NV se stejným rozdělením se blíží k normálnímu rozdělení.

**Předpoklady**:
- Stejné rozdělení
- Nezávislé NV
- $D(x) \ne 0$

$P(X \le a) = P(norm(X) \le \frac{a - EX}{\sqrt{DX}})$
pak lze vyčíst hodnotu normálního rozdělení pro $y \le \frac{a - EX}{\sqrt{DX}}$ z tabulek a máme výsledek.

# Základ statistiky
Výběrový soubor rozsahu n označujeme jako náhodný výběr $X=( X_1 , … , X_n)$.

**Statistika** je každá měřitelná funkce, definovaná na náhodném výběru libovolného rozsahu. Následující statistiky se používají pro odhady číselných parametrů.

**Empirické rozdělení**

**Výběrový průměr**
z náhodného výběru $X=( X_1 , … , X_n )$ je nestranný konzistentní odhad střední hodnoty:
![[Pasted image 20230609234003.png]]
**Výběrový rozptyl**
náhodného výběru $X=( X_1 , … , X_n )$ je nestranný konzistentní odhad střední rozptylu:
![[Pasted image 20230609234138.png]]


# Obecné vlastnosti odhadů parametrů. Odhady střednı́ hodnoty, rozptylu, směrodatné odchylky, momentů.
Snaha o odhad neznámých veličin a jejich parametrů v závislosti na pozorovaných datech.
![[Pasted image 20230610085821.png]]
![[Pasted image 20230610085748.png]]


# Odhady parametrů metodou momentů 
Metoda momentů je založena na rovnosti výběrových momentů a momentů rozdělení. Nelze jednoznačně rozhodnout, která z metod dává lepší výsledky. Rozhodování provádíme podle konkrétní situace, nejčastěji rozhoduje jednoduchost získaných vzorců. Metoda momentů
zohledňuje všechna data z výběru a volíme ji v případech, kdy je soustava věrohodnostních rovnic obtížně řešitelná.
Pro základní rozdělení dávají obě metody shodné výsledky a v případě složitějších rozdělení můžeme jako další kritérium uvažovat, které vzorce jsou méně citlivé na zavlečené chyby do hodnot výběru.

Porovnáme teoretické k-té momenty $E(x^k)$ s jejich odhady
![[Pasted image 20230610083945.png]]
Pro k = 1 to je $EX$
Pro k = 2 to je $DX + E(x)^2$


# Odhady parametrů metodou maximálnı́ věrohodnosti. 
![](https://paper-attachments.dropbox.com/s_FBD9CB5AB5722A3251B1567EA9380D965430509BD4FBBE3BEF1FC8FEA194B83E_1560089316352_image.png)
Obvykle je vhodné nehledat maximum věrohodnostní funkce přímo, ale zlogaritmovat ji. Součiny se nám změní na součty ale na výsledek to nebude mít vliv.

Myšlenkou této metody je, že hledáme takové hodnoty parametrů, které by nejlépe vysvětlovali realizaci náhodného výběru, tj. při kterých by pozorované výsledky byly “nejméně nepravděpodobné”.

Pravděpodobnost je určena pro předpovídání výsledků budoucího pokusu při známém pravděpodobnostním modelu a tudíž má definiční obor jevy z nějaké σ-algebry. Naopak věrohodnost vyhodnocuje sérii pokusů již realizovaných a dovoluje jim přizpůsobit neznámé parametry pravděpodobnostního modelu, a proto je definována na prostoru Π všech možných hodnot parametrů rozdělení.

**Metoda maximální věrohodnosti** považuje za správný odhad parametrů takové hodnoty, které maximalizují věrohodnost.
![[Pasted image 20230610085533.png]]
![[Pasted image 20230610085545.png]]

# Intervalové odhady.
![[Pasted image 20230610090516.png]]
Symetrický odhad ve smyslu, že se stejnou pst ho překročíme nahoru nebo dolů (nemusí být vždy stejná vzdálenost od střední hodnoty).

# Princip statistického testovánı́ hypotéz.
Na základě testu chceme klasifikovat objekty (nebo skupiny objektů) na zdravé/nemocné, střízlivé/opilé, nevinné/vinné apod.

- **Nulová hypotéza**: objekt je „normální“, „negativní“; výsledkem testu je náhodná veličina T.
- **Alternativní hypotéza**: objekt je „anomální“, „pozitivní“; výsledkem (téhož) testu je náhodná veličina T\* .

**Příklad**: Máme považovat test nemoci za pozitivní?
**Nulová hypotéza H0:** Člověk není nakažený.
**Alternativní hypotéza H1:** Člověk je nakažený.

Vždy se testuje na nějaké hladině významnosti $\alpha$.

# Testy střednı́ hodnoty a rozptylu, porovnánı́ dvou rozdělenı́
$\bar x$ = EX
Test střední hodnoty - $t= \frac{\bar x - c}{\sigma} * \sqrt n$ , kde c je odhad EX podle hypotézy, n stupně volnosti, pokud neznáme odchylku tak ji nahradíme odhadem směrodatné odchylky.

Test rozptylu - $t= \frac{(n-1) * S_x^2 }{c}$ , kde c je odhad $\sigma^2$ podle hypotézy, n stupně volnosti

# χ2 -test
Slouží k testování hypotézy, že náhodná veličina má předpokládané rozdělení. Protože umíme hypotézy jen zamítat, nikdy nepotvrdíme, že takové rozdělení opravdu má.
![[Pasted image 20230610092048.png]]
![[Pasted image 20230610092106.png]]

# χ2 -test dobré shody
![[Pasted image 20230610092511.png]]

# Test nezávislosti v kontingenčnı́ tabulce.
Je to χ2-test nezávislosti dvou rozdělení
![[Pasted image 20230610092316.png]]
![[Pasted image 20230610092338.png]]

# Markovské řetězce a jejich asymptotické vlastnosti
https://cs.wikipedia.org/wiki/Markov%C5%AFv_%C5%99et%C4%9Bzec

P → Matice přechodu - je stochastická - součty řádků je 1
Vektor je sloupcový → Wernerovo náboženství.

## Klasifikace stavů
- Nedosažitelné - do takového stavu se nedostaneme nikdy
- Absorpční - z takového stavu se nelze dostat
- Dosažitelné - lze do něj dojít s nenulovou pst
- Trvalý - pokud z něj odejdeme je pst 1, že se sem v budoucnu vrátíme, opak je stav přechodný
- Komunikují - lze z 1. se dostat do 2. a zároveň naopak (silně souvislý graf)
- Periodické 
![[Pasted image 20230610095958.png]]
- ergodický - trvalý a neperiodický

## Absorpční řetězce
Absorpční řetězce jsou takové řetězce, které obsahují mimo stavy přechodný i stavy absorpční. Tzn., že pravděpodobnost setrvání v takovém stavu je rovna 1.

![[Pasted image 20230610095536.png]]

## Asymptotické chování Markovových řetězců
Do jakého stavu se konverguje po nekonečně mnoha krocích t.
Přechodové stavy - pst konverguje k 0
Vždy skončí v některém trvalém stavu jejich součet musí být 1.
![[Pasted image 20230610151741.png]]

## Rozložitelné a nerozložitelné řetězce
Asi je tím myšleno, že rozdělitelné lze rozdělit na více silných komponent souvislosti, které se dají řešit separátně, kdežto nerozložitelné mají pouze jednu komponentu silné souvislosti + absorpční stavy.
