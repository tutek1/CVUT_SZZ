----------
\http://math.feld.cvut.cz/demlova/teaching/lgr/text_lgr_2017.pdf
https://math.fel.cvut.cz/en/people/demlova/lgr/predn_lgr.html
----------
# Výroková logika
**Syntax výrokové logiky. Sémantika výrokové logiky. Důkazový systém - přirozená dedukce.  
Významová (sémantická) ekvivalence formulí výrokové logiky. Normální formy formulí. Dů-  
sledek ve výrokové logice. Úplné systémy logických spojek. Schopnost formalisace a řešení  
logických úloh s využitím výrokové logiky.**

## Výroková logika

### Výroky

Máme danou neprázdnou množinu $A$ tzv. *atomických výroků* (též jim říkáme *logické proměnné*). Konečnou posloupnost prvků z množiny $A$, logických spojek a závorek nazýváme *výroková formule* (zkráceně jen *formule*), jestliže vznikla podle následujících pravidel:

1. Každá logická proměnná (atomický výrok) a ∈ A je výroková formule.
2. Jsou-li $\alpha$, $\beta$ výrokové formule, pak $\lnot \alpha$, $(\alpha \land \beta)$, $(\alpha \lor \beta)$, $(\alpha \Rightarrow \beta)$, $(\alpha \Leftrightarrow \beta)$ jsou také výrokové formule.
3. Nic jiného než to, co vzniklo pomocí konečně mnoha použití bodů 1 a 2, není výroková formule.

Všechny formule, které vznikly z logických proměnných množiny$A$ , značíme $P(A)$.
**Poznámka**: Spojka $\lnot$ se nazývá *unární*, protože vytváří novou formuli z jedné formule. Ostatní zde zavedené spojky se nazývají *binární*, protože vytvářejí novou formuli ze dvou formulí.
V dalším textu logické proměnné označujeme malými písmeny např. $a$,$b$,$c$, … nebo $x$,$y$,$z$, … , výrokové formule označujeme malými řeckými písmeny např. $α$ , $β$ , $γ$ , … nebo $\varphi$ , $\psi$ , … . Také většinou nebudeme ve formulích psát ty nejvíc vnější závorky - tj. píšeme $a \lor ( b \Rightarrow c )$ místo $(a\lor(b\Rightarrow c))$ .

### Podformule

Ze syntaktického stromu formule α jednoduše poznáme všechny její podformule: *Podformule* formule α jsou všechny formule odpovídající podstromům syntaktického stromu formule α .

### Pravdivostní ohodnocení
*Pravdivostní ohodnocení*, též pouze *ohodnocení formulí*, je zobrazení $u:P( A ) → { 0,1 }$ , které splňuje pravidla

1. **Negace** ($\lnot \alpha$) je pravdivá právě tehdy, když α je nepravdivá, tj. $u( ¬ α ) =1$ právě tehdy, když $u( α ) =0$ ;
2. **Konjunkce** ($\alpha\land\beta$) je pravdivá právě tehdy, když α a β jsou obě pravdivé, tj. u( α ∧ β ) =1 právě tehdy, když u( α ) =u( β ) =1
3. **Disjunkce** ($\alpha\lor\beta$) je nepravdivá právě tehdy, když α a β jsou obě nepravdivé, tj. u( α ∨ β ) =0 právě tehdy, když u( α ) =u( β ) =0 ;
4. **Implikace** ($\alpha\Rightarrow\beta$) je nepravdivá právě tehdy, když $α$ je pravdivá a $β$ nepravdivá, tj. $u(\alpha\Rightarrow\beta)=0$ právě tehdy, když $u(\alpha)=0$ a $u(\beta)=0$;
5. **Ekvivalence** ($\alpha\Leftrightarrow\beta$) je pravdivá právě tehdy, když buď obě formule α a β jsou pravdivé nebo obě jsou nepravdivé, tj. $u(\alpha\Leftrightarrow\beta)=1$ právě tehdy, když $u( α ) =u( β )$ .
- Dvě pravdivostní ohodnocení jsou shodná, pokud mají pro všechny logické proměnné shodný výsledek

### Pravdivostní tabulky
Vlastnosti, které ohodnocení formulí musí mít, znázorňujeme též pomocí tzv. pravdivostních tabulek logických spojek. Jsou to: 

| α | ¬ α |
| - | --- |
| 0 | 1   |
| 1 | 0   |

| α | β | α ∧ β | α ∨ β | α ⇒ β | α ↔ β |
| - | - | ----- | ----- | ----- | ----- |
| 0 | 0 | 0     | 0     | 1     | 1     |
| 0 | 1 | 0     | 1     | 1     | 0     |
| 1 | 0 | 0     | 1     | 0     | 0     |
| 1 | 1 | 1     | 1     | 1     | 1     |


## Tautologie, kontradikce, splnitelné formule
- Formule se nazývá *tautologie*, jestliže je pravdivá ve všech ohodnoceních formulí.
- Formule se nazývá se *kontradikce*, jestliže je nepravdivá ve všech ohodnoceních formulí. 
- Formule je *splnitelná*, jestliže existuje aspoň jedno ohodnocení formulí, ve kterém je pravdivá.

### Příklady
1. Formule α ∨ ¬ α , α ⇒ α , α ⇒ ( β ⇒ α ) jsou tautologie.
2. Formule a ∨ b , ( a ⇒ b ) ⇒ a jsou splnitelné, ale ne tautologie.
3. Formule α ∧ ¬ α je kontradikce. Kontradikce je také každá negace tautologie.

## Úplné systémy logických spojek
Množiny logických spojek, pomocí, kterých lze popsat všechny možné formule.
například: {∨, ¬}, {∧, ¬},  {⇒, ¬}

## Tautologická ekvivalence formulí
Řekneme, že formule $\varphi$ a $ψ$ jsou *tautologicky ekvivalentní* (také *sémanticky ekvivalentní*), jestliže pro každé ohodnocení u platí $u(\varphi) = u(\psi)$ . Tautologickou ekvivalenci značíme $\varphi|\!\!\!=\!\!\!|ψ$.
- Tautologická ekvivalence je reflexivní, symetrická a tranzitivní (takže ekvivalence)
- Jsou-li $α$ , $β$ , $γ$ , $δ$ formule splňující $α|\!\!\!=\!\!\!|β$ a $\gamma|\!\!\!=\!\!\!|\delta$, pak platí
	- $¬α|\!\!\!=\!\!\!|¬β$;
	- $( α ∧ γ ) |\!\!\!=\!\!\!| ( β ∧ δ )$
	- $( α ∨ γ ) |\!\!\!=\!\!\!| ( β ∨ δ )$
	- $( α ⇒ γ ) |\!\!\!=\!\!\!| ( β ⇒ δ )$
	- $( α ↔ γ ) |\!\!\!=\!\!\!| ( β ↔ δ )$
- Zákony pro formule
	- $α ∧ α |\!\!\!=\!\!\!| α$ , $α ∨ α |\!\!\!=\!\!\!| α$ (idempotence $∧$ a $∨$);
	- $α ∧ β |\!\!\!=\!\!\!| β ∧ α$, $α ∨ β |\!\!\!=\!\!\!| β ∨ α$ (komutativita $∧$ a $∨$);
	- $α ∧ ( β ∧ γ ) |\!\!\!=\!\!\!| ( α ∧ β ) ∧ γ$, $α ∨ ( β ∨ γ)|\!\!\!=\!\!\!|(α∨β)∨γ$ (asociativita $∧$ a $∨$);
	- $α ∧ ( β ∨ α ) |\!\!\!=\!\!\!| α$, $α ∨ ( β ∧ α ) |\!\!\!=\!\!\!| α$ (absorpce $∧$ a $∨$);
	- $¬ ¬ α |\!\!\!=\!\!\!| α$;
	- $( α ⇒ β ) |\!\!\!=\!\!\!| ( ¬ α ∨ β )$
- Dvě formule jsou sémanticky ekvivalentní právě když je jejich ekvivalence tautologií

| $x$ | $f_1$ | $f_2$ | $f_3$ | $f_4$ |
| - | --- | --- | --- | --- |
| 0 | 0   | 0   | 1   | 1   |
| 1 | 0   | 1   | 0   | 1   |

Funkce $f_1$ je konstantní 0, jedná se o *kontradikci* a budeme ji značit $\mathbf{F}$. Podobně funkce $f_4$ je  *tautologie* (konstantní 1), značíme je $\mathbf{T}$. Funkce $f_2$ je vlastně logická proměnná $x$ a funkce $f_3$ je $¬ x$.

## Normální formy formulí
- **Disjunktivní normální forma (DNF)**
	- Formule je v DNF pokud je disjunkcí jedné nebo několika formulí z nichž každá je literálem nebo konjunkcí literálů
- **Konjuktivní normální forma (CNF)**
	- Formule je v CNF pokud je konjunkcí jedné nebo několika formulí, z nichž každá je literálem nebo disjunkcí literálů
- Ke každé formuli najdeme ekvivalentní formuli v DNF i v CNF

## Důsledek ve výrokové logice
- $\varphi$ je *sémantickým* *důsledkem*, též *konsekventem* množiny formulí *S* právě tehdy, když je pravdivá ve všech ohodnoceních, kdy je pravdivá formule $S$. Tento fakt značíme $S⊨\varphi$
- Dvě formule jsou sémanticky ekvivalentní pokud si jsou vzájemně sémantickým důsledkem
- $α⊨β$ právě tehdy, když $α⇒β$ je tautologie
- $S ⊨ \varphi$ právě tehdy, když $S ∪\{¬\varphi\}$ je nesplnitelná
- $S∪\{\varphi\}⊨ψ$ právě tehdy, když $S ⊨ (\varphi⇒ ψ )$

### Příklady
- Pro každé tři formule α , β , γ platí:
	1. { α , α ⇒ β } ⊨ β .
	2. { α ⇒ β , β ⇒ γ } ⊨ ( α ⇒ γ ) .
	3. { α ⇒ β , ¬ β } ⊨ ¬ α .
	4. { α ∨ β , α ⇒ γ , β ⇒ γ } ⊨ γ .

- Pro konsekventy platí následující tvrzení:
	1. Je-li $S$ množina formulí a $\varphi∈S$, pak $\varphi$ je konsekventem $S$, tj. $S⊨\varphi$ pro každou $\varphi∈S$
	2. Tautologie je konsekventem každé množiny formulí $S$
	3. Formule $\varphi$ je tautologie právě tehdy, když je konsekventem každé množiny formulí
	4. Každá formule je konsekventem nesplnitelné množiny formulí

## Rezoluční metoda
- Rezoluční metoda rozhoduje, zda daná množina klausulí je splnitelná nebo je nesplnitelná. Tím je také ”universální metodou” pro řešení základních problémů ve výrokové logice, neboť:
- Je "univerzální metodou" pro řešení základních problémů ve výrokové logice neboť lze použít k ověření sémantického důsledku i pravdivosti složitých výrokových formulí
- Základní pojmy rezoluční metody:
	- *Klausule* = literál nebo disjunkce konečně mnoha literálů, speciálním případem je prázdná klausule značená $F$ (kontradikce)
		- Pokud $C$ je klausule a $p$ je literál, pak $C\backslash p$ je klausule, která obsahuje všechny literály z $C$ kromě $p$
	- Klausule $D$ je rezolventa klauzulí $C_1$ a $C_2$ právě když existuje literál $p$, který se vyskytuje v klausuli $C_1$ a jehož negace se vyskytuje v klausuli $C_2$, a zároveň platí $D=(C_1\backslash p)\lor(C_2\backslash\lnot p)$. Značíme $D=res_p(C_1,C_2)$
- Pro resolventu $D$ z klauzulí $C_1$ a $C_2$ platí, že je sémantickým důsledkem množiny $\{C_1,C_2\}$

### Rezoluční princip
- Značení:
	- $A$ je množina literálů
	- $R(S)=S∪\{res_p(C_1,C_2)|C_1,C_2\in S,\ p\in A\}$
	- $R_0(S)=S$
	- $R_{i+1}(S)=R(R_i(S))$ pro $i∈\mathbb{N}$
	- $R^\star(S)=\bigcup\{R_i(S)\ |\ i≥0\}$
- Existuje vždy $n$ takové, že $R_n(S)=R_{n+1}(S)$, takže $R_n(S)=R^\star(S)$
- Množina klausulí $S$ je splnitelná právě tehdy, když $R^\star(S)$ neobsahuje prázdnou klausuli $F$

### Postup rezoluční metody
1. Formule množiny $M$ převedeme do CNF a $M$ pak nahradíme množinou $S$ všech klausulí vyskytujících se v některé formuli v CNF. Klausule, které jsou tautologiemi, vynecháme. Jestliže nám nezbyde žádná klausule, množina $M$ se skládala z tautologií a je pravdivá v každém pravdivostním ohodnocení.
2. Vytvoříme $R^\star(S)$
3. Obsahuje-li $R^\star(S)$ prázdnou klausuli, je množina $M$ nesplnitelná, v opačném případě je $M$ splnitelná.
- Lze použít i výhodnější postup, ve kterém pouze kontrolujeme zda $R^\star(S)$ obsahuje $F$

### Výhodnější postup
- Nejprve si zvolíme proměnnou $x$ a rozdělíme klauzule v $S$ do tří skupin, klauzule $M_0$ které neobsahují $x$, klauzule $M_x$ které obsahují $x$ a klauzule $M_{\lnot x}$ které obsahují negaci $x$
- Vytvoříme množinu $N$ všech rezolvent z $M_x$ a $M_{\lnot x}$, kde vyřadíme všechny tautologie
- Vytvoříme množinu $S_1=M_0\cup N$
- Položíme $S=S_1$ a opakujeme pro další proměnné
- Na konci získáme buď prázdnou množinu ($S$ je splnitelná) nebo množinu $\{F\}$, ($S$ není splnitelná)

## Přirozená dedukce ve výrokové logice
- Je formálním důkazovým systémem
- Zabývá se odvoditelností, nikoliv pravdivostí
- Nepoužívá žádné axiomy, ale pouze pomocné předpoklady
- Definuje dva druhy pravidel, I-pravidla (zavádějí logické spojky) a E-pravidla (odstraňují logické spojky)
- Při přirozené dedukci se odvozuje odvození, což je posloupnost $\varphi_1,...,\varphi_n$, kde každá formule je buď předpoklad, nebo pomocný předpoklad, nebo vznikla z předchozích formulí pomocí některého odvozovacího pravidla

### Logický důsledek
- $\varphi$ je logický důsledek množiny $S$, pokud $\varphi_n=\varphi$
- Značíme $S\vdash\varphi$
- Platí, že $S\vdash\varphi\Leftrightarrow S\vDash\varphi$

### Odvozovací I-pravidla
- Pro konjunkci:
$$\frac{\varphi,\ \psi}{\varphi\land\psi},\quad\frac{\varphi,\ \psi}{\psi\land\varphi}$$
- Pro disjunkci:
$$\frac{\varphi}{\varphi\lor\psi},\quad\frac{\varphi}{\psi\lor\varphi}$$
- Pro implikaci:
$$\frac{\boxed{\begin{array}{c}\varphi\\\vdots\\\psi\end{array}}}{\varphi\Rightarrow\psi}$$
- Pro ekvivalenci:
$$\frac{\boxed{\begin{array}{c}\varphi\\\vdots\\\psi\end{array}},\ \ \boxed{\begin{array}{c}\psi\\\vdots\\\varphi\end{array}}}{\varphi\Leftrightarrow\psi}$$
- Pro negaci (důkaz sporem):
$$\frac{\boxed{\begin{array}{c}\varphi\\\vdots\\\bot\end{array}}}{\lnot\varphi}$$
- Pro spor nelze zavést
- Pro dvojitou negaci:
$$\frac{\varphi}{\lnot\lnot\varphi}$$

### Odvozovací E-pravidla
- Pro konjunkci:
$$\frac{\varphi\land\psi}{\varphi},\quad\frac{\varphi\land\psi}{\psi}$$
- Pro disjunkci:
$$\frac{\varphi\lor\psi,\ \ \varphi\Rightarrow\alpha,\ \ \psi\Rightarrow\alpha}{\alpha}$$
- Pro implikaci (Modus Ponens):
$$\frac{\varphi,\ \ \varphi\Rightarrow\psi}{\psi}$$
- Pro ekvivalenci:
$$\frac{\varphi,\ \ \varphi\Leftrightarrow\psi}{\psi},\quad\frac{\psi,\ \ \varphi\Leftrightarrow\psi}{\varphi}$$
- Pro negaci:
$$\frac{\varphi\land\lnot\varphi}{\bot}$$
- Pro spor:
$$\frac{\bot}{\varphi}$$
- Pro dvojitou negaci:
$$\frac{\lnot\lnot\varphi}{\varphi}$$
## Speciální pravidla
- Obrácená implikace:
$$\frac{\lnot\psi,\ \ \varphi\Rightarrow\psi}{\lnot\varphi}$$
- Vyloučení třetího:
$$\frac{}{\varphi\lor\lnot\varphi}$$
 ![[Pasted image 20230606120225.png]]

# Predikátová logika
**Syntax predikátové logiky. Sémantika predikátové logiky. Významová (sémantická) ekviva-  
lence formulí predikátové logiky. Normální formy formulí. Důsledek v predikátové logice.  
Schopnost formalisace a řešení logických úloh s využitím predikátové logiky.**

## Syntaxe predikátové logiky
- *Jazyk* predikátové logiky $\mathcal{L}$
- Jazyk predikátové logiky se skládá z
	1. *logických symbolů*, tj.: 
		1. spočetné množiny individuálních proměnných: $\mathrm{Var}=\{x,y,…,x_1,x_2 …\}$
		2. výrokových logických spojek: $¬$, $∧$, $∨$, $⇒$, $\Leftrightarrow$
		3. obecného kvantifikátoru $∀$ a existenčního kvantifikátoru $∃$
	2. *speciálních symbolů*, tj.: 
		1. množiny $\mathrm{Pred}$ predikátových symbolů (nesmí být prázdná) - velká písmena
		2. množiny $\mathrm{Kons}$ konstantních symbolů (může být prázdná) - malá písmena na začátku abecedy
		3. množiny $\mathrm{Func}$ funkčních symbolů (může být prázdná) - například $f$, $g$ atp.
	3. pomocných symbolů, jako jsou závorky a čárka

## Arita
- Popisuje kolika objektů se daný predikát nebo funkce týká


## Pojmy
- *Term* - Množina termů je definována těmito pravidly:
	1. Každá proměnná a každý konstantní symbol je term
	2. Jestliže $f$ je funkční symbol arity $n$ a $t_1$, $t_2$, … , $t_n$ jsou termy, pak $f(t_1,t_2,…,t_n)$ je také term
- *Atomická formule* - predikátový symbol $P$ aplikovaný na tolik termů, kolik je jeho arita
- *Formule* - množina formulí je definována těmito pravidly:
	1. Každá atomická formule je formule.
	2. Jsou-li $\varphi$ a $\psi$ dvě formule, pak ($\lnot\varphi$) , ($\varphi\land\psi$) , ($\varphi\lor\psi$) , ($\varphi\Rightarrow\psi$) , ($\varphi\Leftrightarrow\psi$) jsou opět formule.
	3. Je-li $\varphi$ formule a $x$ proměnná, pak ($∀x\varphi$) a ($∃x\varphi$) jsou opět formule.
- *Podformule* -  libovolný podřetězec $\varphi$, který je sám formulí

## Volný a vázaný výskyt proměnné
- Máme proměnnou $x$, která je v listu syntaktického stromu formule $\varphi$
	- Jde o *vázaný výskyt* proměnné $x$ pokud jsme při postupu od listu ke kořeni narazili na kvantifikátor s touto proměnnou
	- V opačném případě jde o volný výskyt proměnné $x$
- Formule, která má pouze vázané výskyty proměnných se nazývá *uzavřená formule* (též *sentence*)
- Formule, která má pouze volné výskyty se nazývá *otevřená formule*
- Vázané výskyty nějaké proměnné můžeme přejmenovat, pokud jsou přejmenovány všechny výskyty vázané daným kvantifikátorem a při přejmenování se nestal žádný volný výskyt vázaným, tomu říkáme *legální přejmenování proměnné*
- Dvě formule jsou *stejné* pokud se liší pouze legálním přejmenováním

## Sémantika predikátové logiky

### Intepretace jazyka predikátové logiky
- Dvojice $\left<U,[\![-]\!]\right>$ , kde
	- $U$ je neprázdná množina nazývaná *universum*;
	- $[\![-]\!]$ je přiřazení, které 
	    1. Každému predikátovému symbolu $P\in\mathrm{Pred}$ arity $n>0$ přiřazuje podmnožinu $U^n$ , tj. *n*-ární relaci na množině $U$. Když $n = 0$, tak přiřazuje $P$ nulu nebo jedničku.
	    2. Každému konstantnímu symbolu $a\in\mathrm{Kons}$ přiřazuje prvek z $U$, značíme jej $[\![a]\!]$,
	    3. každému funkčnímu symbolu $f\in\mathrm{Func}$ arity $n$ přiřazuje zobrazení množiny $U^n$ do $U$, značíme je $[\![f]\!]$,
- Kontext proměnných $\rho$ je zobrazení, které každé proměnné $x\in\mathrm{Var}$ přiřadí prvek $\rho(x)\in U$
	- Update kontextu $\rho$ o hodnotu $d$ v $x$ $\rho[x:=d]$ je nový kontext proměnných, který se od $\rho$ liší jenom v proměnné $x$, která v něm má hodnotu $d$
- Termy jsou interpretovány následujícím způsobem:
	1. Je-li term konstantní symbol $a∈\mathrm{Kons}$ , pak jeho hodnota je prvek $[\![a]\!]_\rho=[\![a]\!]$. Je-li term proměnná $x$, pak jeho hodnota je $[\![x]\!]_\rho=\rho(x)$
	2. Je-li $f(t_1,t_2,…,t_n)$ term. pak jeho hodnota je
$$[\![f(t_1,t_2,…,t_n)]\!]_\rho=[\![f]\!]([\![t_1]\!]_\rho,…,[\![t_n]\!]_\rho)$$

### Pravdivostní hodnoty
- Formule v dané interpretaci a daném kontextu
	1. Nechť $\varphi$ je atomická formule. Tj. $\varphi=P(t_1,t_2,…,t_n)$ , kde $P$ je predikátový symbol arity $n$ a $t_1$, $t_2$, …, $t_n$ jsou termy. Pak $\varphi$ je pravdivá v interpretaci $\left<U,[\![-]\!]\right>$ a kontextu $ρ$ právě tehdy, když 
	$$([t_1]_\rho,…,[t_n]_\rho)\in[P]$$
	2. Jsou-li $\varphi$ a $\psi$ formule, jejichž pravdivost v interpretaci $\left<U,[\![-]\!]\right>$ a kontextu $ρ$ již známe, pak se řídíme tím co již známe z výrokové logiky 
	3. Je-li $\varphi$ formule a $x$ proměnná, pak 
	    - $\forall x \varphi(x)$ je pravdivá právě tehdy, když fromule $\varphi$ je pravdivá v každém kontextu $\rho[x:=d]$, kde $d$ je prvek $U$
	    - $\exists x\varphi(x)$ je pravdivá právě tehdy, když fromule $\varphi$ je pravdivá v aspoň jednom kontextu $\rho[x:=d]$, kde $d$ je prvek $U$
- Sentence $\varphi$ je pravdivá v interpretaci $\left<U,[\![-]\!]\right>$ právě když je pravdivá v každém kontextu $ρ$

### Pojmy
- *Model sentence* je interpretace ve které je sentence $\varphi$ pravdivá
- *Tautologie* je sentence, která je pravdivá v každé interpretaci (například $\forall xP(x)\Rightarrow P(a)$)
- *Kontradikce* je sentence, která je nepravdivá v každé interpretaci (například $\forall xP(x)\land\exists x\lnot P(x)$)
- Sentence je *splnitelná*, pokud je pravdivá v alespoň jedné interpretaci
- *Splnitelná množina sentencí* je taková množina sentencí $M$, pro kterou existuje interpretace v níž jsou všechny sentence z $M$ pravdivé (i prázdná množina)
- *Nesplnitelná množina sentencí* je taková, kde v každé interpretaci je nepravdivá některá sentence z množiny $M$
- Sentence $\varphi$ a $\psi$ jsou *tautologicky (sémanticky) ekvivalentní*, když jsou pravdivé ve stejných interpretacích

### Tvrzení o tautologické ekvivalenci
1. $\lnot(\forall xP(x))|\!\!\!=\!\!\!|(\exists x\lnot P(x))$
2. $\lnot(\exists xP(x))|\!\!\!=\!\!\!|(\forall x\lnot P(x))$
3. $(\forall xP(x))\land(\forall xQ(x))|\!\!\!=\!\!\!|\forall x(P(x)\land Q(x))$

## Sémantický důsledek
- Sentence $\varphi$ je sémantickým důsledkem (nebo *konsekventem*) množiny sentencí $S$ právě tehdy, když každý model množiny $S$ je také modelem sentence $\varphi$
- Jestliže existuje interpretace $\left<U,[\![-]\!]\right>$ v níž je pravdivá každá sentence z množiny $S$, ale není pravdivá formule $\varphi$, pak $\varphi$ není sémantickým důsledkem $S$

## Rezoluční metoda v predikátové logice

### Základní pojmy
- *Literál* je atomická formule, nebo negace atomické formule
- *Komplementární literály* jsou dva literály z nichž jeden je negací druhého
- *Klausule* je sentence, která obsahuje pouze obecné kvantifikátory, které leží na jejím začátku. Za kvantifikátory následuje literál nebo disjunkce literálů
- *Rezolventy* - analogické k rezolventám ve výrokové logice, ale postup k jejich nalezení je složitější

### Vytváření rezolvent v predikátové logice
- Rezolventy v predikátové logice nemusejí vždy existovat
- Příklad - vytvoříme z klauzulí $K_1$ a $K_2$ rezolventu $K$
$$K_1=\forall x\forall y(P(x)\lor\lnot Q(x,y))$$
$$K_2=\forall x\forall y(Q(x,y)\lor R(y))$$
$$K=\forall x\forall y(P(x)\lor R(y))$$
- Unifikační algoritmus
	- **Vstup:** Dva positivní literály $L_1$ , $L_2$, které nemají společné proměnné.
	- **Výstup:** Hlášení neexistuje v případě, že hledaná substituce neexistuje, v opačném případě substituce ve tvaru množiny prvků tvaru $x/t$ , kde $x$ je proměnná, za kterou se dosazuje, a $t$ je term, který se za proměnnou $x$ dosazuje
	1. Položme $E_1:=L_1$, $E_2:=L_2$ , $\theta:=\emptyset$
	2. Jsou-li $E_1$, $E_2$ prázdné řetězce, stop. Množina $\theta$ určuje hledanou substituci. V opačném případě položíme $E_1:=E_1\theta$, $E_2:=E_2\theta$
	3. Označíme $X$ první symbol řetězce $E_1$ , $Y$ první symbol řetězce $E_2$
	4. Je-li $X=Y$, odstraníme $X$ a $Y$ z počátku $E_1$ a $E_2$ . Jsou-li $X$ a $Y$ predikátové nebo funkční symboly, odstraníme i jim příslušné závorky a jdeme na krok 2
	5. Je-li $X$ proměnná, neděláme nic. 
	6. Je-li $Y$ proměnná (a $X$ nikoli), přehodíme $E_1$ , $E_2$ a $X$, $Y$
	7. Není-li ani $X$ ani $Y$ proměnná, stop. Výstup neexistuje
	8. Je-li *Y* proměnná nebo konstanta, položíme $\theta:=\theta\cup\{X/Y\}$. Odstraníme $X$ a $Y$ ze začátků řetězců $E_1$ a $E_2$ (spolu s čárkami, je-li třeba) a jdeme na krok 2
	9. Je-li $Y$ funkční symbol, označíme $Z$ výraz skládající se z $Y$ a všech jeho argumentů (včetně závorek a čárek). Jestliže $Z$ obsahuje $X$, stop, výstup neexistuje
	10. V opačném případě položíme $\theta:=\theta\cup\{X/Z\}$, odstraníme $X$ a $Z$ ze začátků $E_1$ a $E_2$ (odstraníme čárky, je-li třeba) a jdeme na krok 2

### Rezoluční princip
- Stejný jako ve výrokové logice

### Skolemizace
- Odstranění existenčních kvantifikátorů s zachováním ekvisplnitelnosti
- $\exists x P(x) \approx P(c)$, kde $c$ je nový konstantní symbol
- $\forall x \exists y R(x, y) \approx \forall x R(x, f(x))$, kde $f$ je nový funkční symbol arity 1.  

# Teorie grafů
**Základní pojmy a definice teorie grafů; schopnost formální práce s těmito pojmy. Stromy a jejich vlastnosti. Minimální kostry a algoritmy na jejich hledání. Komponenty silné souvislosti a algoritmus na jejich hledání. Schopnost modelování praktických problémů s využitím grafů.**

## Definice orientovaného grafu
- Orientovaný graf je trojice $G=(V,E,\varepsilon)$ , kde $V$ je konečná množina vrcholů (též zvaných uzlů), $E$ je konečná množina jmen hran (též nazývaných orientovaných hran) a $\varepsilon$ je přiřazení, které každé hraně $e\in E$ přiřazuje uspořádanou dvojici vrcholů a nazývá se vztah incidence
- Jestliže $\varepsilon(e)=(u,v)$ pro $u,v\inV $, říkáme, že vrchol $u$ je *počáteční vrchol* hrany $e$ a vrchol $v$ je *koncový vrchol* hrany $e$. O vrcholech $u,v$ říkáme, že jsou krajní vrcholy hrany $e$, též že jsou incidentní s hranou $e$. Jestliže počáteční vrchol a koncový vrchol jsou stejné, říkáme, že hrana $e$ je orientovaná smyčka.

## Speciální případy grafů
- Graf o $n$ vrcholech, ve kterém $E = \binom{v}{2}(\frac{v!}{2!(v - 2)!})$  je množina všech dvouprvkových podmnožin množiny $V$ se nazývá *úplný graf*, značí se $\mathbf{K}_{n}$.

![](https://paper-attachments.dropbox.com/s_6AD8A941C8ED57352D633EB310A08C7851FB528B040210267C26261CFE27889B_1649780105177_image.png)


- Vlastnosti úplného grafu: $|E| = n \cdot \frac{n - 1}{2}$, je regulární a celý graf je svojí největší klikou

- *Bipartitní graf* je graf, jehož množina vrcholů se dá rozdělit na dvě disjunktní podmnožiny $V_{1}$, $V_{2}$ tak, že každá hrana grafu má jeden koncový vrchol ve $V_{1}$ a druhý ve $V_{2}$

![|300x150](https://paper-attachments.dropbox.com/s_6AD8A941C8ED57352D633EB310A08C7851FB528B040210267C26261CFE27889B_1649780518331_Biclique_K_3_5_bicolor.svg.png) ![|200x200](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e8/Simple-bipartite-graph.svg/800px-Simple-bipartite-graph.svg.png)

- Vlastnosti bipartitního grafu:
	- Neobsahuje kružnici liché délky. 
	- Bipartitní graf, který obsahuje všechny možné hrany se nazývá *úplný bipartitní graf*. Značí se $K_{m,n}$, kde $|V_{1}| = m$, $|V_{2}| = n$ jsou velikosti partit. Na obrázku s červenými a modrými vrcholy je např. $K_{5, 3}$.
	- $|E| = mn$.
	- Je regulární, právě když $m = n$.

- *Cesta* délky $n$ je graf isomorfní grafu $V = \{0, 1, \ldots, n\}$ a s množinou hran $E = \{\{0, 1\}, \{1, 2\}, \ldots, \{n - 1, n\}\}$. Značíme ji $P_{n}$.

![|200x200](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f9/Orientovan%C3%A1_kru%C5%BEnice.svg/800px-Orientovan%C3%A1_kru%C5%BEnice.svg.png)
![Příklad cesty $P_{5}$|300](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e1/Path-graph.svg/1920px-Path-graph.svg.png)

- *Kružnice* délky $n \geq 3$ je graf isomorfní grafu s množinou vrcholů $V = \{1, \ldots n\}$ a s množinou hran $E = \{\{1, 2\}, \{2, 3\}, \ldots \{n - 1, n\}\}$. Značíme ji $C_{n}$.

## Izomorfní graf
- Izomorfní grafy jsou grafy u kterých jsou shodné všechny důležité vlastnosti (obsahují stejné podgrafy, cesty, kružnice,...)
- Formálně řekneme, že grafy $G$ a $G'$ jsou izomorfní, pokud
$$\exists F:V(G)\rightarrow V(G'):\{x,y\}\in E(G)\Leftrightarrow\{(f(x),f(y)\}\in E(G')$$

| Regulární graf                     | Všechny vrcholy stejný stupeň                                                                                                                                                                     |
| ---------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Podgraf                            | $G'=(V', E')$, kde $V' \subseteq V$, $E' \subseteq E$                                                                                                                                       |
| Faktor grafu                       | Podgraf $G'=(V', E')$, kde $V' = V$                                                                                                                                                           |
| Podgraf indukovaný množinou $V'$ | Podgraf $G'=(V', E')$, kde $E'$ obsahuje všechny<br>hrany, které mají oba krajní vrcholy v množině $V'$                                                                                     |
| Sled                               | Sled délky $k$ je posloupnost vrcholů a hran $v_{0}, e_{1}, v_{1}, e_{2}, \ldots, v_{k - 1}, e_{k}, v_{k}$ taková, že hrana $e_{i}$ je incidentní s vrcholy $v_{i - 1}$ a $v_{i}$.      |
| Uzavřený sled                      | Sled, kde $v_{0} = v_{k}$                                                                                                                                                                       |
| Tah (uzavřený)                     | Sled (uzavřený), ve kterém se neopakují hrany.                                                                                                                                                    |
| Eulerovský tah (uzavřený)          | Tah (uzavřený), který obsahuje všechny hrany a všechny vrcholy grafu.                                                                                                                             |
| Cesta (uzavřená)                   | Tah (uzavřený), ve kterém se neopakují vrcholy (s výjimkou $v_{0} = v_{k}$).                                                                                                                    |
| Cyklus                             | Uzavřená orientovaná cesta, ve které se neopakují vrcholy.                                                                                                                                        |
| Kružnice                           | Uzavřená cesta, která má aspoň jednu hranu                                                                                                                                                        |
| Souvislý graf                      | Mezi každými jeho vrcholy existuje cesta.                                                                                                                                                         |
| Strom                              | Souvislý graf, který neobsahuje kružnici.                                                                                                                                                         |
| Kořenový strom                     | Orientovaný graf, který je strom a má kořen.                                                                                                                                                      |
| Les                                | Graf, který neobsahuje kružnice.                                                                                                                                                                  |
| Prostý graf                        | Graf bez paralelních hran.                                                                                                                                                                        |
| Obyčejný graf                      | Prostý graf bez smyček.                                                                                                                                                                           |
| Eulerovský graf                    | Graf, kde existuje eulerovský tah.                                                                                                                                                                |
| Silně souvislý graf                | Orientovaný graf, kde mezi každými dvěma vrcholy existuje orientovaná cesta.                                                                                                                      |
| Doplněk grafu                      | $G^{\mathrm{dop}} = (V, \binom{V}{2} - E)$, tedy s hranami, které nejsou v původním grafu.                                                                                                      |
| Vzdálenost vrcholů                 | Délka nejkratší cesty mezi dvěma vrcholy.                                                                                                                                                         |
| Komponenta souvislosti             | Maximální souvislý podgraf.                                                                                                                                                                       |
| Skóre grafu                        | Sestupně setříděná $n$-tice stupňů vrcholů.                                                                                                                                                     |
| Kostra grafu                       | Faktor, který je stromem.                                                                                                                                                                         |
| Komponenta silné souvislosti       | Maximální podgraf, který je souvislý.                                                                                                                                                             |
| Kořen                              | Vrchol u orientovaného grafu, z něhož vede orientovaná cesta do všech ostatních vrcholů.                                                                                                          |
| Jádro                              | Jádro orientovaného grafu $G = (V, E)$ je množina $J \subseteq V$ jeho vrcholů taková, že mezi libovolnými dvěma nevede hrana a z každého vrcholu mimo $J$ vede aspoň jedna hrana do $J$. |
| Obarvení vrcholů                   | Zobrazení $b: V \to B$ takové, že žádné dva vrcholy spojené hranou nemají stejnou barvu.                                                                                                        |
| $k$-barevný graf                 | Graf, který se dá obarvit $k$ barvami.                                                                                                                                                          |
| Barevnost grafu                    | Nejmenší počet barev, které jsou potřeba k obarvení jeho vrcholů.                                                                                                                                 |
| Klika                              | Maximální podmnožina vrcholů s vlastností, že každé dva různé vrcholy jsou spojeny hranou.                                                                                                        |
| Klikovost grafu                    | Počet vrcholů v nejpočetnější klice.                                                                                                                                                              |
| Nezávislá množina v grafu          | Množina vrcholů, jejíž žádné dva vrcholy nejsou spojeny hranou.                                                                                                                                   |
| Nezávislost grafu                  | Počet vrcholů v maximální nezávislé množině.                                                                                                                                                      |

## Definice neorientovaného grafu
- Neorientovaný graf je trojice $G=(V,E,\varepsilon)$, kde $V$ je konečná množina vrcholů (též zvaných uzlů), $E$ je konečná množina jmen hran a $\varepsilon$ je přiřazení, které každé hraně $e\in E$ přiřazuje množinu $\{u,v\}$ pro vrcholy $u,v ∈ V$ a nazývá se vztah *incidence*.
- Jestliže $\varepsilon(e)=\{u,v\}$ pro $u,v\in V$, říkáme, že $u,v$ jsou krajní vrcholy hrany $e$, též že jsou incidentní s hranou $e$.
- Je-li $u=v$, říkáme že $e$ je (neorientovaná) smyčka.

## Stromy
- Orientovaný nebo neorientovaný graf se nazývá strom, je-li souvislý a neobsahuje-li kružnici
- V každém stromu s alespoň dvěma vrcholy existuje vrchol stupně 1.
- Každý strom o $n$ vrcholech má $n-1$ hran.
- Strom je graf, který má nejmenší počet hran aby mohl být souvislý a současně největší počet hran aby v něm neexistovala kružnice.
- Je dán graf $G$, pak následující je ekvivalentní
	1. $G$ je strom
	2. Graf $G$ nemá kružnice a přidáme-li ke grafu libovolnou hranu uzavřeme přesně jednu kružnici.
	3. Graf $G$ je souvislý a odebráním libovolné hrany přestane být souvislý.

## Souvislost
- *Souvislý graf* je takový, kde $\forall u,v\in V$ existuje cesta z $u$ do $v$
- *Komponenta souvislosti* je maximální množina vrcholů grafu $G$ taková, že podgraf indukovaný množinou $A$ je souvislý
- *Maximální množina* je taková množina vrcholů, pro kterou nebude indukovaný podgraf souvislý ve chvíli kdy přidáme libovolný další vrchol z grafu $G$
- Graf je *silně souvislý*

## Silná souvislost
- Orientovaný graf je *silně souvislý*, pokud $\forall u,v\in V$ existuje orientovaná cesta z $u$ do $v$
- Souvislý graf je silně souvislý, pokud každá jeho hrana leží v nějakém cyklu

### Kosaraju, Sharir algoritmus
- Algoritmus na hledání silně souvislých komponent
1. Prohledáme graf do hloubky a vypíšeme vrcholy v pořadí ve kterém jsme je opouštěli
2. V grafu $G$ obrátíme hrany, dostaneme graf $G'$
3. Prohledáme graf $G'$ do hloubky, a to v pořadí opačném pořadí v kroku 1
4. Vrcholy stromů druhého prohledávání jsou pak vrcholy jednotlivých silně souvislých komponent

### Tarjanův algoritmus
- Rozšíření algorimtu DFS
- Kromě pořadových čísel jsou vrcholům přidělována i zpětná čísla
- Dělíme vrcholy do tří skupin:
	- Ještě nenavštívené vrcholy (ani pořadové, ani zpětné číslo)
	- Navštívené, ale nezařazené vrcholy
	- Vrcholy zařazené do nějaké komponenty souvislosti
- Značení:
	- Vrchol $x$
	- Pořadové číslo - $P(x)$
	- Zpětné číslo - $Z(x)$
	- Zásobník - $ZAS$
- Algoritmus
	1. Všechny vrcholy jsou nenavštívené a zásobník je prázdný
	2. Vybereme libovolný nenavštívený vrchol $x$, označíme $v$, přiřadíme $P(v)$, $Z(v):=P(v)$ a vložíme $v$ na vrchol $ZAS$. Jestliže nenajdeme nenavštívený vrchol, výpočet končí
	3. Vezmeme nějakou nepoužitou hranu $e$ začínající v e $v$ a koncový vrchol označíme $w$. Pokud taková hrana neexistujeme, jdeme na krok 7
	4. Je-li $w$ stále nenavštívený, přiřadíme mu $P(w)$, položíme $Z(w):=P(w)$, zařadíme $w$ na vrchol $ZAS a pokračujeme krokem 3
	5. Je-li vrchol $w$ nezařazený, zkontrolujeme zda $Z(v)>P(w)$, pokud ano tak položíme $Z(v):=P(w)$
	6. Pokud byl vrchol $w$ už zařazen, pokračujeme krokem 3
	7. Pokud $Z(v)<P(v)$, pokračujeme rovnou na krok 8. Pokud $Z(v)=P(v)$ utvoříme novou komponentu silné souvislosti z dosud nezařazených vrcholů $w$, pro které platí $P(w)\geq P(v)$. Tyto vrcholy pak odstraníme ze zásobníku a pokračujeme na krok 8
	8. Pokud je $ZAS prázdný, pokračujeme na krok 2, pokud ne tak označíme $x$ vrchol $ZAS$. Pokud nebyla uzavřena komponenta a $Z(x)>Z(v)$, položíme $Z(x):=Z(v)$, $v:=x$ a pokračujeme krokem 3.

## Minimální kostra
- *Faktor grafu*  $G$ je jeho podgraf, který má stejnou množinu vrcholů
- *Kostra grafu* $G$ je jeho faktor, který je zároveň stromem
- Máme-li graf $G$ s *ohodnocením* hran $c$, pak *minimální kostra grafu* $G$ je taková kostra $K=(V,L)$, která minimalizuje
$$\sum_{e\in L}c(e)$$
- V každém souvislém ohodnoceném grafu existuje minimální kostra, ale nemusí být jediná

### Obecný postup pro hledání minimální kostry
- Je dán souvislý graf $G=(V,E)$ a ohodnocení hran $c$
1. Na začátku máme $L=0$. Označíme $S$ množinu všech komponent souvislosti grafu $K=(V,L)$; tj. na začátku je $s=v;v ∈ V$
2. Dokud není graf $K=(V,L)$ souvislý (tj. dokud $S$ se neskládá z jediné množiny), vybereme hranu $e$ podle následujících pravidel: 
    1. $e$ spojuje dvě různé komponenty souvislosti $S,S'$ grafu $K$ (tj. dvě množiny z $S$)
    2. A pro $S$ nebo $S‘$ je nejlevnější hranou která vede z komponenty ven
3. Hranu $e$ přidáme do množiny $L$ a množiny $S$ a $S‘$ nahradíme jejich sjednocením.
4. Postup ukončíme, jestliže jsme přidali $n-1$ hran (tj. jestliže se $S$ skládá z jediné množiny).

### Borůvkův-Kruskalův algoritmus
- Modifikace obecného postupu pro hledání minimální kostry:
1. Setřídíme hrany podle ceny do neklesající posloupnosti, tj. $c(e_1)\leq c(e_2)\leq ... \leq c(e_m)$ . Položíme $L=\emptyset$, $\mathcal{S}=\{\{v\};v∈V\}$
2. Probíráme hrany v daném pořadí. Hranu $e_i$ přidáme do $L$, jestliže má oba krajní vrcholy v různých množinách $S,S'∈\mathcal{S}$ . V $\mathcal{S}$ množiny $S$ a $S'$ nahradíme jejich sjednocením. V opačném případě hranu přeskočíme.
3. Algoritmus končí, jestliže jsme přidali $n-1$ hran (tj. $S$ se skládá z jediné množiny).

### Jarníkův-Primův algoritmus
- Modifikace obecného postupu pro hledání minimální kostry:
1. Vybereme libovolný vrchol $v$. Položíme $L=\emptyset, S={v}$
2. Vybereme nejlevnější hranu $e$, která spojuje některý vrchol $x$ z množiny $S$ s vrcholem $y$, který v S neleží. Vrchol $y$ přidáme do množiny $S$ a hranu $e$ přidáme do $L$.
3. Opakujeme krok 2 dokud nejsou všechny vrcholy v množině $S$.

## Eulerovy grafy
- *Tah* je sled, ve kterém se neopakují hrany
- *Eulerovský* tah je takový, který prochází každou hranou grafu
- *Uzavřený eulerovský tah* je takový tah, kde se poslední vrchol shoduje s prvním (výjimka pravidla, že se vrcholy nesmí opakovat), jinak mluvíme o *otevřeném eulerovském tahu*
- *Eulerovský graf* je graf, ve kterém existuje eulerovský tah