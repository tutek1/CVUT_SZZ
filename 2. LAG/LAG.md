# 2. Lineární prostor, báze a dimenze, řešení soustav lineárních rovnic, lineární zobrazení, základy maticového počtu

## Těleso
Množina F s operacemi + a \*, která splňuje:
	- **Komutativita** - a+b = b+a
	- **Asociativita** - (a \* b) \* c = a \* (b \* c)
	- **Neutrální prvek** - a + 0 = a
	- **Distributivita** - a \* (b + c) = ab + ac
	- **Opačný prvek (negace)**  - a + b = 0, b = -a
	- **Inverzní prvek** - a \* b = 1, b = $a^{-1}$, kromě a = 0
	- **Alespoň 2 prvky** 0 a 1
	- Zn je těleso pro n prvočíslo

## Lineární prostor
Neprázdná množina L se nazývá lineární vektorový prostor nad tělesem R , jestliže je splněno následujících deset podmínek.
1. Pro každé dva prvky $u,v \in L$ je jednoznačně určen prvek $u+v \in L$ nazývaný součet prvků $u$ a $v$. (uzavření na sčítání)
2. Pro každý prvek $u \in L$ a pro každý prvek $\lambda \in R$ je jednoznačně určen prvek $\lambda \cdot u \in L$ nazývaný násobek prvku $u$ prvkem $\lambda$. (uzavření na násobení)
3. $u+v=v+u$ pro každé dva prvky $u,v \in L$ (**komutativita**)
4. $( u+v ) +w=u+( v+w )$ pro každé tři prvky $u,v,w \in L$ (**asociativita**)
5. Existuje prvek $0 \in L$ . takový, že pro každý prvek $u \in L$ platí $u+0=0+u=u$ (existence 0)
6. Pro každý prvek $u \in L$ existuje prvek $-u \in L$ takový, že $u+( -u ) =( -u ) +u=0$ (existence negace)
7. $\lambda \cdot ( u+v ) = \lambda u + \lambda v$ pro každé dva prvky $u,v \in L$ a pro každý prvek $\lambda \in R$.
8. $( \lambda + \alpha ) u = \lambda u + \alpha u$ pro každý prvek $u \in L$ a pro každé dva prvky $\lambda, \alpha \in R$.
9. $( \lambda \alpha ) u= \lambda ( \alpha u )$ pro každý prvek $u \in L$ a pro každé dva prvky $\lambda, \alpha \in R$.
10. $1 u = u$ pro každý prvek $u \in L$

## Lineární podprostor
Neprázdná podmnožina W vektorového prostoru V nad tělesem T se nazývá podprostorem V, pokud pro libovolné vektory $u,v \in W$ a libovolný skalár $\lambda \in T$ platí:
- $u+v \in W$
- $\lambda a \in W$

Množina W je tedy uzavřená vzhledem k operacím sčítání vektorů a násobení vektoru skalárem. Lépe $span(W)\subseteq W$. 

## Lineární kombinace
Nechť $L$ je lineární prostor, $v_1,v_2,...,v_n \in L$  a $\lambda_1,\lambda_2,...,\lambda_n \in R$ . Prvek $\lambda_1 v_1 + \lambda_2 v_2 + ... + \lambda_n v_n \in L$ se nazývá lineární kombinace prvků $v_1,v_2,...,v_n$ s koeficienty $\lambda_1,\lambda_2,...,\lambda_n$ .

- Lineární kombinace $\lambda_1 v_1, \lambda_2 v_2,..., \lambda_n v_n$ se nazývá **netriviální**, pokud existuje $i \in \{1,2,...,n\}$ takové, že $\lambda_i \neq 0$
- Lineární kombinace $\lambda_1 v_1, \lambda_2 v_2,..., \lambda_n v_n$ se nazývá **triviální**, jestliže $\lambda_i = 0$ pro každé $i=1,2,...,n$

## Lineární závislost a nezávislost
Prvky $v_1,v_2,...,v_n$ množiny $M$ se nazývají **lineárně závislé**, pokud existuje taková **netriviální lineární kombinace** těchto prvků, která vyhovuje vztahu $\sum_{i=1}^{n} a_i v_i = 0$ kde $a_i$ je skalár a alespoň jedno $a_i$ je nenulové. V opačném případě jsou lineárně nezávislé.

- Pro **lineárně nezávislé** prvky je jediným řešením výše uvedeného vzorce triviální řešení, tedy $a_i = 0$
- Jsou-li prvky **lineárně závislé**, je možné nějaký z nich vyjádřit jako lineární kombinaci ostatních prvků

## Lineární obal
Mějme množinu $M$, která je podmnožinou vektorového prostoru $V$. Průnik všech podprostorů prostoru $V$, které obsahují množinu M se nazývá lineárním obalem množiny $M$.
Zjednodušeně - lineární obal množiny $M$ podprostor prostoru V . Co obsahuje? Všechny ty prvky, ke kterým se mohu dostat libovolnou lineární kombinací vektorů z množiny $M$ .
$\langle M \rangle = \{ \sum_{i=1}^{n} a_i u_i \mid u_i \in M, a_i \in R, i=1,2,3,...,n \}$

## Báze
Báze vektorového prostoru V je nejmenší množina **lineárně nezávislých vektorů** taková, že její lineární obal je roven celému prostoru V. V konečně dimenzionálním prostoru dimenze n je bází každá množina obsahující n lineárně nezávislých vektorů.

- **Obal** báze prostoru V tvoří celý prostor V
- Vektory báze jsou **lineárně nezávislé**.
- Prostor může mít **více bází**. Všechny ale mají **stejný počet prvků**.

## Dimenze
Dimenze lineárního prostoru $L$ je **počet prvků báze** tohoto prostoru. Dimenzi prostoru $L$ značíme $dim\,L$. Dimenzi jednobodového lineárního prostoru $L = \{ \emptyset \}$ pokládáme rovnu $0$.
Nechť $L$ lineární prostor a $M \subseteq L$ je lineární podprostor $L$ pak $dim\,M \leq dim\,L$.

## Souřadnice vektoru v bázi
Jsou to koeficienty jednotlivých vektorů báze. Například bázové vektory $\begin{pmatrix} 1 \\ 1 \end{pmatrix}$ a $\begin{pmatrix} 0 \\ 1 \end{pmatrix}$, tak souřadnice pro vektor $\begin{pmatrix} 2 \\ 3 \end{pmatrix}$ jsou $\begin{pmatrix} 2 \\ 1 \end{pmatrix}$. Je to lineární zobrazení. Platí $coord_b(x + y) = coord_b(x) + coord_b(y)$ a násobení skalárem.

# Lineární zobrazení
Pojmem **lineární zobrazení** (lineární transformace) se v matematice označuje takové zobrazení mezi vektorovými prostory $U$ a $V$, které zachovává vektorové operace sčítání a násobení skalárem. Název lineární je odvozen z faktu, že grafem obecného lineárního zobrazení z reálných čísel do reálných čísel je přímka.

1. $L( u+v ) =L( u ) +L( v ), u \in U,v \in V$   (aditivita)
2. $L( \alpha u ) = \alpha L( u ), u \in U, \alpha \in R$   (homogenita)

**Prosté zobrazení:** $x_1 \not= x_2$ => $f(x_1) \not= f(x_2)$, každé x se zobrazí na jiné y
**Na zobrazení:** $\forall y \in Y, \forall x \in X: f(x) = y$, každé y má své x
**Bijekce:** $\forall y \in Y, \exists! x \in X: f(x) = y$, spojení prostého a na, má inverzi
($\exists!$ - existuje právě jedno)

**Monomorfismus** - prosté a lineární
**Epimorfismus** - na a lineární
**Isomorfismus** - bijekce a lineární

## Jádro zobrazení
Jádro lineárního zobrazení $A$ z $L_1$ do $L_2$ je: $Ker A = \{ x \in L_1 ; A(x) = o\}$

## Obraz zobrazení
Mějme lin. zobrazení z L1 do L2. Obraz zobrazení f, im(f), je poté množina všech y ∈ L2 takových, že existuje nějaké x ∈ L1, že f(x) = y.

## Defekt a hodnost zobrazení
Defekt je $def\,A=dim\,Ker\,A$, hodnost zobrazení $hod\,A = dim\, Im (A)$, platí $def\,A + hod\,A = dim\,L_1$
$hod\,A = rng\,A$
$null\,A = def\,A$

## Transformace souřadnic v jedné bázi na souřadnice v jiné bázi
První bázi zobrazíme do výsledného prostoru. U výsledku zjistíme souřadnice vhledem k první bázi. Tyto souřadnice dáme jako sloupce matice -> transformace souřadnic z první do druhé báze.

## Matice lineárního zobrazení
Nechť $U$ a $V$ jsou lineární vektorové prostory konečné dimenze nad tělesem $R, L:U \to V$ je lineární zobrazení. Mějme $u_1, u_2 ,..., u_k$ bázi prostoru $U$, $dim\,U=k$ a $v_1 , v_2 ,..., v_n$ bázi prostoru $V$, $dim\,V=n$. Matice $A$ typu $(n,k)$ která splňuje maticovou rovnost:

$(A*\vec u_1,A * \vec u_2,...,A * \vec u_k))=(\vec v_1, \vec v_2,..., \vec v_n)$
nazýváme maticí zobrazení $A$ vzhledem k uspořádaným bázím $(U)$ a $(V)$

**Sčítání** - stejné rozměry, složka po složce
**Násobení** - A o rozměru (n\*m) (n - počet řádků, m - počet sloupců) a matici B o rozměru (k\* l), lze násobit jen když k = m a výsledná matice má rozměry (n\*l)

**Inverze** - GEM z $(A|E)$ do $(E|A^{-1})$

Vyjádřeno méně formálně: každý vektor z U si můžeme vyjádřit jako kombinaci bázových vektorů U . Pak se podíváme na koeficienty, kterými násobíme tyto bázové vektory, a chceme z nich dostat koeficienty bázových vektorů v prostoru V . Pokud těmito koeficienty vynásobíme bázové vektory V , dostaneme lineární zobrazení původního vektoru do prostoru V . Díky matici lineárního zobrazení můžeme tyto koeficienty získat.
Platí: souřadnice v bází $V$ pro vektor z báze $U$ najdeme pomocí: $A \cdot \begin{pmatrix} u_1 \\ u_2 \\ \vdots \\ u_k \end{pmatrix} = \begin{pmatrix} v_1 \\ v_2 \\ \vdots \\ v_n \end{pmatrix}$

### Regulární matice
Platí Isomorfismus, čtvercová, má inverzi, det(A) != 0, A \* x = b má jedno řešení, defekt 0, sloupce a řádky LN

## Řešení soustav lineárních rovnic
$A$ matice reálných čísel typu $(m,n)$, dále $x$ je jednosloupcová matice symbolů$\begin{pmatrix} x_1 \\ \vdots \\ x_n \end{pmatrix}$ typu $(n,1)$ a $b$ je matice reálných čísel $\begin{pmatrix} b_1 \\ \vdots \\ b_m \end{pmatrix}$ typu $(m,1)$. Pak maticovou rovnost $Ax=b$ nazýváme **soustavou m lineárních rovnic o n neznámých**. Matici A nazýváme **maticí soustavy** a vektor $b^T = (b_1, \cdots, b_m)$ nazýváme **vektorem pravých stran**. Připíšeme-li k matici soustavy do dalšího sloupce matici b oddělenou svislou čarou, dostáváme matici $(A \mid b)$ typu $(m,n+1)$, kterou nazýváme rozšířenou maticí soustavy.
Řešení soustavy $Ax=b$ je takový vektor $\alpha = (\alpha_1,\cdots,\alpha_n) \in R^n$, pro který platí: dosadíme-li hodnoty $\alpha_i$ za symboly $x_i$, pak je splněna požadovaná maticová rovnost, tj.:
$A \cdot \begin{pmatrix} \alpha_1 \\ \vdots \\ \alpha_n \end{pmatrix} = \begin{pmatrix} b_1 \\ \vdots \\ b_n \end{pmatrix}$
Řešit soustavu $Ax=b$ znamená nalézt **všechna** její řešení.

**GEM** - získáme podobnou matici v horním blokovém tvaru (HBT)
	    - lze prohodit 2 řádky
	    - lze vynásobit řádek skalárem (ne 0)
	    - lze přičíst skalární násobek řádku k jinému řádku
	    - platí rank(A) je počet nenulových řádků v HBT = počet pivotů (p != 0)
	    - platí def(A) = počet sloupců - rank(A)

## Frobeniova Věta
Soustavě $Ax=b$ má řešení právě tehdy, když $hodA = hod(A\mid b)$
Pokud má řešení, tak množina řešení je p + ker(A), kde p je jedno řešení

## Permutace
**Permutace** na n je bijekce π : {1, 2, ..., n} → {1, 2, ..., n}. Množině všech permutací množiny {1, 2, ..., n} říkáme symetrická grupa permutací n-prvkové množiny, značíme $S_n$.

## Determinant čtvercové matice
Pouze čtvercová matice, výsledek je skalár, geometrický význam - je to velikost orientovaného objemu rovnoběžnostěnu
Vlastnosti - $det(A) = det(A^T)$,  $det(A^{-1}) = (det(A))^{-1}$, $det(E_n) = 1$, invariance vůči mat. násobení, $det(\alpha A) = \alpha^n det(A)$,  det(A) != 0 tak a1, ..., an jsou LN
![[Pasted image 20230602193600.png]]

### Rozvoj podle řádku nebo sloupce
Vybereme si nejvhodnější řádek/sloupec (R), pak det(A) = $R_1 * (-1)^{R_{idxX} + R_{idxY}}$ \* det(matice bez sloupce a řádku daného aktuálním prvkem) + ...  

### GEM determinant
Je-li matice horní/dolní trojúhelníková je det(A) roven součinu prvků na diagonále, přičítání řádků determinant nemění, násobení řádku $\alpha$ pak je potřeba determinant vydělit $\alpha$, prohození řádků mění znaménko

## Vlastní číslo
Číslo $\lambda \in C$ je vlastním číslem zobrazení $A$ pokud existuje vektor $x\in L, x \neq o$ takový, že $A(x)=\lambda x$. Vektor $x$ nazýváme pak vlastní vektor $A$ příslušný vlastnímu číslu $\lambda$.

Postup: 
	- víme, že $Av=\lambda v$ -> upravíme na $Av -\lambda v = o$ -> vytkneme v $(A -\lambda E_n)v = o$
	- z toho víme že $v \in ker(A -\lambda E_n)$
	- z toho víme že A - $\lambda E_n$ musí být singulární ->det(A - $\lambda E_n$) = 0
	- z toho získáme vlastní čísla a jejich násobnost
	- pro všechna vlastní čísla spočítáme eigen($\lambda_i, A$) = $(A-\lambda*E_n | o)$ -> span vlastních vektorů, kde pro diagonalizaci musí platit dim(eigen($\lambda_i, A$)) = násobnost $\lambda_i$ 

### Diagonalizace
Pouze čtvercová, D = $(\lambda_1 * e_1, ..., \lambda_n * e_n)$, D = $T^{-1} * A* T$, kde T je matice složena z vlastních vektorů a je regulární, 2 vlastní vektory příslušné různým vlastním číslům jsou LN

## Skalární a vektorový součin
**Skalární součin** definujeme mezi dvěma vektory. Výsledkem skalárního součinu je reálné číslo, není to vektor. Máme-li dva vektory u=\[ u1, u2 \] a v=\[ v1, v2 \] , pak jejich skalární součin je roven:
$u^T • v=  ∣u∣ ∣v∣ cos α$, kde α je velikost úhlu mezi vektory u a v. 
**Vlastnosti** - $<x|x>\space \ge 0$ . Také norma vektoru na druhou
				- Pořadí vektorů je jedno. 
				- Invariance k násobení skalárem.
				- $<x|y+z> = <x|y> + <x|z>$

**CSB nerovnost** - $|<x|y>| \le ||x|| * ||y||$
**Norma vlastnosti** - vždy kladná nebo rovna 0
							- $||ax|| = |a| * ||x||$
							- $||x + y|| \le ||x|| + ||y||$ (troj. nerovnost)
**Kosinova věta** - $||y - x||^2 = ||x||^2 + ||y||^2 - 2 *||x|| * ||y|| * cos(\alpha)$

**Metrika** - vzdálenost 2 vektorů, norma jejich rozdílu
**Ortogonalita vektorů** - když skalární součin = 0, jsou kolmé, všechny vektory jsou kolmé na nulový vektor, pokud chceme ověřit kolmost na span(M), stačí ověřit kolmost na množinu generátorů M

**Vektorový součin** je binární operace vektorů v trojrozměrném vektorovém prostoru. Výsledkem této operace je vektor, který je kolmý k oběma původním vektorům. Velikost tohoto vektoru je rovna obsahu rovnoběžníku tvořeného původními vektory. Spočítá se
u × v=\[ u2 v3 - u3 v2, u3 v1 - u1 v3, u1 v2 - u2 v1 \]=w a platí u T • w=0, v T • w=0

## Ortogonalizační proces
Ortogonální báze - všechny vektory báze jsou na sebe navzájem kolmé
Gram-Smith - B = (b1, b2, b3), C = ?
	1, c1 = b1
	2, c2 = b2 - ${<b2 | c1> \over <c1 | c1>} * c1$ 
	3, c3 = b3 -  ${<b3 | c1> \over <c1 | c1>} * c1$ -  ${<b3 | c2> \over <c2 | c2>} * c2$ 

Pro ortoNORMální bázi platí coord (x) = $(<x|b_1>, ..., <x|b_n>)^T$ 