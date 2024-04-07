# 1. Vlastnosti celých čísel, euklidův algoritmus, binární relace, matematická indukce, rekurzivní vztahy

# Vlastnosti celých čísel
- celá čísla $Z$ se skládají z přirozených čísel, nuly a záporných celých čísel
- množina je uzavřena na operaci sčítání, odčítání a násobení
## Dělitelnost
**Definice:** Nechť $a,b \in Z$. Řekneme, že $a$ dělí $b$, značeno $a|b$, jestliže existuje $k \in Z$ takové, že $b=a \cdot k$. V takovém případě říkáme, že $a$ je faktor $b$ a že $b$ je násobek $a$. Také říkáme, že $b$ je dělitelné číslem $a$. Pokud toto není pravda, tak píšeme $a ⫮ b$. Transitivita, pokud $a|b$ a $b|c$, tak $a|c$.

- Číslo $d \in N$ je **společný dělitel** (common divisor) čísel $a,b$, jestliže $d\mid a$ a $d \mid b$.
- **největší společný dělitel** (greatest common divisor), značeno $gcd(a, b)$ je největší prvek množiny jejich společných dělitelů, pokud je alespoň jedno z $a,b$ nenulové.
- Číslo $d \in N$ je **společný násobek** (common multiple) čísel a, b, jestliže a|d a b|d.
- **nejmenší společný násobek** (least common multiple), značeno lcm(a, b) je nejmenší prvek množiny jejich společných násobků, pokud jsou obě a,b nenulové.
- $lcm(a, 0) = lcm(0, b) = 0$
- $gcd(0, 0) = 0$
- $lcm(a, b) \cdot gcd(a, b) = |a| \cdot |b|$
- čísla $a,b \in Z$ jsou **nesoudělná**, jestliže $gcd(a,b)=1$

## Prvočíslo
- je přirozené číslo, které je beze zbytku dělitelné **právě dvěma různými přirozenými čísly**, a to číslem **jedna** a **sebou samým** (tedy 1 není prvočíslo)
- Přirozená čísla různá od jedné, která nejsou prvočísla, se nazývají **složená čísla**.

## Počítání modulo
- **Definice** Nechť $n \in N$. Řekneme, že čísla $a,b \in Z$ jsou **kongruentní modulo** n, značeno a ≡ b (mod n), jestliže n|(a−b).

Nechť n ∈ N. Pro čísla a, b ∈ Z jsou následující podmínky ekvivalentní:
- $a\equiv b (\mod n)$
- existuje $k \in Z$ takové, že $a=b+k \cdot n$
- $a \mod n = b \mod n$, tj. jsou si rovny zbytky po dělení číslem n.

**Vlastnosti**
Nechť $n \in N$, uvažujme $a, b, u, v \in Z$ takové, že $a \equiv u \mod n$ a $b \equiv v \mod n$:
- $a+b \equiv u +v \mod n$
- $a-b \equiv u -v \mod n$
- $ab \equiv uv \mod n$

**Inverzní číslo**
- Řekneme, že $b \in Z$ je inverzní číslo k $a$ mod $n$, $a \in Z$, jestliže $a * b \equiv 1$ (mod $n$).
- Převede libovolné číslo na 1 ve světě $Z_n$.
- Existuje když $gcd(a, n) = 1$. 
- Výpočet pomocí Euklidova algoritmu.

# Eukleidův algoritmus
Lze jím vypočítat **největšího společného dělitele** dvou přirozených čísel.
- **vychází z lemmatu**: Nechť $a,b \in N$, nechť $q,r \in N_0$ splňují $a = q \cdot b + r$ a $0 \leq r < b$. Pak platí následující: $d \in N$ je společný dělitel $a,b$ právě tehdy, když je to společný dělitel $b,r$.
- $gcd(a, b) = gcd(b, r)$
- opakovaně hledáme $gcd$ pro dvojici $b, r$ místo $a,b$
- rozšířená verze počítá i s indexy jak se dostat k gcd (bezout)

# Bezoutova identita
- $gcd(a, b)$ lze zapsat jako $gcd(a, b) = a*k + b*j$, kde $k, j \in Z$ 
- Lze použít pro řešení diofantických rovnic ($ax +by = c$, kde $a,b,c \in Z$) nebo hledání inverzního čísla

## Malá fermatova věta
pro každé prvočíslo *p* a každé celé číslo *a* platí
${\displaystyle a^{p}\equiv a{\pmod {p}}}$
$a^{{p-1}}\equiv 1{\pmod  p}$

# Binární relace
**Definice:** Nechť $A,B$ jsou množiny. Libovolná podmnožina $R \subseteq A \times B$ se nazývá relace z $A$ do $B$. Jestliže $(a, b) \in R$, pak to značíme $aRb$ a řekneme, že a je v relaci s b vzhledem k R. Jestliže $(a, b) \notin R$, pak řekneme, že a není v relaci s b vzhledem k R.

## Druhy relací
- R je **reflexivní**, jestliže pro všechna a ∈ A platí $aRa$. např. “je stejný”
- R je **symetrická**, jestliže pro všechna a, b ∈ A platí ($aRb$ ⇒ $bRa$). Důkaz -> prohodit $a$ a $b$.
- R je **antisymetrická**, jestliže pro všechna a, b ∈ A platí ($[aRb ∧ bRa]$ ⇒ a = b). Důkaz -> do $aRb$ dosadíme $bRa$, dostaneme podmínku a tu vložíme do $bRa$, kde zjistíme, co musí být $a$. Tím dokážeme určit jestli $a=b$.
- R je **tranzitivní**, jestliže pro všechna a, b, c ∈ A platí ($[aRb ∧ bRc]$ ⇒ $aRc$). Důkaz -> do $bRc$ dosadíme $aRb$, a to dosadíme do $aRc$. 

## Ekvivalence
**Definice:** Nechť R je relace na nějaké množině A. Řekneme, že R je ekvivalence, jestliže je **reflexivní, symetrická a tranzitivní**.
0.2.1.1 Třída ekvivalence
Každá ekvivalence rozdělí množinu A na systém disjunktních množin, které pak nazýváme třídy ekvivalence.
**Definice:** Nechť R je relace ekvivalence na nějaké množině A. Pro a ∈ A definujeme třídu ekvivalence prvku a (equivalence class of a) vzhledem k R jako \[a\] R = ${b ∈ A; aRb}$.

## Částečné uspořádání
**Definice:** Nechť R je relace na nějaké množině A. Řekneme, že R je částečné uspořádání, jestliže je **reflexivní, antisymetrická a tranzitivní**. V tom případě řekneme, že dvojice (A, R) je částečně uspořádaná množina.

**Hasseův diagram**
- Uspořádané množiny můžeme zakreslit pomocí Hasseova diagramu.
- vrcholy představují prvky množiny
- hrana mezi vrcholy (a, b) nám říká, že a < b a zároveň neexistuje c takové, že a < c < b. Tedy mezi prvky a a b už žádný jiný prvek není. Přitom musí platit, že v grafu je vrchol a níže než vrchol b.
- největší prvek - prvek do, kterého se dá dostat ze všech prvků a nemá prvek nad sebou (nemusí existovat)
- maximum - prvek, který nemá prvek nad sebou
- nejmenší prvek - prvek ze, kterého všechno vychází a nemá prvek pod sebou (nemusí existovat)
- minimum - prvek, který nemá prvek pod sebou
- linearizace částeč. uspoř. - Hessův diagram od minima, po úrovních zapsat na řádek, za sebe. Rozdělovací symbol $<_L$.

# Matematická indukce
**Matematická indukce** je metoda dokazování matematických vět a tvrzení, která se používá, pokud chceme ukázat, že dané tvrzení platí pro všechna celá čísla $n \in Z$ počínající nějakým $n_0$.
Typický důkaz indukcí se skládá ze dvou kroků:

1. **Základní krok**: V tomto kroku se dokáže, že tvrzení platí pro nejmenší číslo $n_0$, nikoliv pro n=1, pro které nemusí vždy obecně platit.
3. ***Indukční krok***: Ukážeme, že *pokud* tvrzení platí pro $n=m$ **(***indukční předpoklad***), *pak* platí i pro $n=m+1$.

Princip matematické indukce pak již říká, že tvrzení platí pro každé $n \geq n_0$.
Často se v prvním kroku dokazuje, že tvrzení platí pro $n=0$.
Rozlišuje se slabý a silný princip matematické indukce: slabý princip v indukčním kroku předpokládá, že tvrzení platí pro $n = m$, zatímco silný předpokládá, že tvrzení platí pro všechna $n = n_0, n_0+1, ..., m$. Slabý a silný princip matematické indukce jsou ekvivalentní (tj. oběma lze dokázat stejnou množinu tvrzení).

# Rekurzivní vztahy
**Definice:** Rekurentní vztah či rekurzivní vztah pro posloupnost $\{ a_k \}$ je libovolná rovnice typu $F( a_n , a_{n-1} , a_{n-2}, ... , a_0 ) = 0$,  kde $F$ je nějaká funkce.
**Např.** podstata problému Hanojských věží se dá vyjádřit vztahem $H_{n}-2 \cdot H_{n-1} - 1 = 0$

## Lineární rekurentní rovnice
![](https://paper-attachments.dropbox.com/s_0A9175DF5C9F82F6DBF7669AD1AF17DAD775AF196069568096C595872016C27D_1558704791016_linearni+rekurentni+rovnice.png)
- Základnı́ vlastnosti - jejich množina řešenı́ tvořı́ vektorový prostor dimenze rovné řádu rovnice, takže řešenı́ lze generovat pomocı́ vhodné báze
- jak najı́t vhodnou bázi - pomocı́ kořenů charakteristického polynomu

**Řešení**
![](https://paper-attachments.dropbox.com/s_0A9175DF5C9F82F6DBF7669AD1AF17DAD775AF196069568096C595872016C27D_1558704842890_reseni.png)
viz příklad 5

**Charakteristická rovnice**
![](https://paper-attachments.dropbox.com/s_0A9175DF5C9F82F6DBF7669AD1AF17DAD775AF196069568096C595872016C27D_1558704866171_charakteristicka+rovnice.png)

K získání charakteristických čísel potřebujeme vyřešit rovnici $p(\lambda) = \lambda^k + c_{k-1}\lambda^{k-1} + ... + c_1\lambda + c_0 = 0$, které se také říká charakteristická rovnice.

----------
# Příklady
1. Chceme najít $gcd(408, 108)$
    408 = 3 · 108 + 84 (408 mod 108 = 84), proto gcd(408, 108) = gcd(108, 84).
    108 = 1 · 84 + 24, proto gcd(408, 108) = gcd(108, 84) = gcd(84, 24).
    84 = 3 · 24 + 12, proto gcd(408, 108) = gcd(108, 84) = gcd(84, 24) = gcd(24, 12).
    24 = 2 · 12, proto gcd(408, 108) = gcd(108, 84) = gcd(84, 24) = gcd(24, 12) = gcd(12, 0) = 12
2. ![[Pasted image 20230529231814.png]]
3. Relace ≤ je uspořádání na přirozených, celých, racionálních i reálných číslech.
    Relace ⊆ je uspořádání na třídě všech množin (na univerzální třídě).
    Relace dělitelnosti | (a dělí b) je uspořádáním na přirozených číslech
    Relace "Být potomkem" je uspořádáním na množině osob.
4. Vyřešte homogenní lineární rekurentní rovnici $F_{n} = F_{n - 1} + F_{n - 2}$ , $n \geq 2$.
    Nejdříve si přepíšeme indexy, aby byl nejnižší $n$. To si také můžeme představit jako substituci $n = m + 2$. Dostáváme $F_{m + 2} = F_{m + 1} + F_{m}$. Nezapomeneme na podmínku, do které také substituujeme za $n$: $m + 2 \geq 2$, neboli $m \geq 0$. 
    Nyní přepíšeme rovnici tak, aby na pravé straně byla $0$, tedy na $F_{m + 2} - F_{m + 1} - F_{m} = 0$.
    Dosadíme $\lambda^{i}$ za každé $F_{m + i}$ a vyřešíme kvadratickou  rovnici.
    $\lambda^{2} - \lambda - 1 = 0$
    $\lambda_{1} = \frac{1 + \sqrt{5}}{2}$, $\lambda_{2} = \frac{1 - \sqrt{5}}{2}$
    Dostáváme řešení $F_{n} = u \frac{1 + \sqrt{5}}{2} + v \frac{1 - \sqrt{5}}{2}$, $n \geq 0$. (kořeny na n ?)
5. Vyřešte homogenní lineární rekurentní rovnici $a_{n + 3} - 3a_{n + 2} + 3a_{n + 1} - a_{n} = 0$, $n \geq 1$.
    Znovu sestrojíme charakteristický polynom: $\lambda^3 - 3\lambda^2 + 3\lambda - 1 = 0$.
    Charakteristickými čísly jsou $\lambda_{1} = \lambda_{2} = \lambda_{3} = 1$.
    Protože je násobnost kořene rovna $3$, nebude řešením $a_{n} = u \cdot 1^n$, ale 
    $a_{n} = u \cdot (1^{n}) + v \cdot (n \cdot 1^{n}) + w \cdot (n^{2} \cdot 1^{n}) = u + v \cdot n + w \cdot n^{2}$, $n \geq 1$.
6. Vyřešte homogenní lineární rekurentní rovnici $a_{n + 2} - 2a_{n + 1} - 3a_{n} = -9n \cdot 2^{n}$, $n \geq 0$.
    Zjistíme charakteristická čísla pro homogenní rovnici (položíme rovno nule):
    $\lambda^{2} - 2\lambda - 3 = 0 \rightarrow \lambda_{1} = -1, \lambda_{2} = 3.$
    Tím pádem je homogenním řešením $a_{h,n} = u \cdot (-1)^n + v \cdot 3^{n}$, $n \geq 0$.
    Partikulární řešení zjistíme tak, že odhadneme pravou stranu přes polynom.
    Protože je na pravé straně $-9n \cdot 2^{n}$, odhadneme lineární polynom $a_{n} =(An + B) \cdot 2^{n}$.
    Kdyby ovšem na pravé straně bylo $-9n \cdot 3^{n}$, tak musíme odhadovat $a_{n} = n \cdot (An + B) \cdot 3^{n}$. Obecně - pokud má pravá straně $P(x) \cdot \lambda_{i}^{n}$, tak násobíme odhad $n^{m}$, kde $m$ je násobnost $\lambda{i}$.
    Ten dosadíme do levé strany za $a_{n}$:
    $(A(n + 2) + B) \cdot 2^{n + 2} - 2(A(n + 1) + B) \cdot 2^{n + 1} - 3(An + B) \cdot 2^{n} =$
    $4(An + 2A + B) \cdot 2^{n} - 4(An + A + B) \cdot 2^{n} - 3(An + B) \cdot 2^{n} =$
    $\left[(-3A)n + (4A - 3B)\right] \cdot 2^{n}$.
    Když výsledný výraz položíme roven $-9n \cdot 2^{n}$, dostáváme soustavu lineárních rovnic
    $-3A = -9$
    $4A - 3B = 0$, jejímž řešením je $A = 3, B = 4$. Partikulární řešení je tedy $a_{p, n} = (3n + 4) \cdot 2^{n}, n \geq 0$.
    Zkombinováním $a_{n} = a_{p,n} + a_{h, n}$ získáme obecné řešení
    $a_{n} = (3n + 4) \cdot 2^{n} + u \cdot (-1)^{n} + v \cdot 3^{n}, n \geq 0$.
    https://www.youtube.com/watch?v=6hkBATZVOjg

