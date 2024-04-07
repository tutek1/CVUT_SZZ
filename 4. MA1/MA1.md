# 4. Funkce jedné proměnné, určitý a neurčitý integrál, řady

----------

~~http://math.feld.cvut.cz/tkadlec/ma1.htm~~
~~http://math.feld.cvut.cz/tkadlec/ftp/vyuka/ma1.pdf~~ - jiz nefunkcni, dochazi k presunu na moodle
[Výuka - ČVUT - Fakulta elektrotechnická (cvut.cz)](https://math.fel.cvut.cz/cz/lide/tkadlec/vyuka.html) - aktualizovany odkaz alespon s castecnymi info a odkazy na moodle (prof Tkadlec)
[ČVUT - Fakulta elektrotechnická (cvut.cz)](https://math.fel.cvut.cz/cz/mt) - Math Tutor (prof Habala)

----------
# Maximum, minimum, infimum...

Maximum množiny M (max M) je největší prvek množiny M (pokud existuje).
Minimum množiny M (min M) je nejmenší prvek množiny M (pokud existuje).
Supremum množiny M (sup M) je nejmenší horní mez množiny M (pokud existuje).
Infimum množiny M (inf M) je největší dolní mez množiny M (pokud existuje).
+∞/-∞ je pouze suprema/infima.

# Funkce jedné proměnné

Zobrazení $A \to R$ kde $A \subset R$ je neprázdná. $A$ je definiční obor funkce. 

**Prostá**
Funkce je prostá když $x_1 \not= x_2$ => $f(x_1) \not= f(x_2)$, každé x se zobrazí na jiné y

**Složené funkce**
Složená funkce $f: A \to B$ a $g : B \to C$ pak složená funkce $g \circ f: A \to C$ je dána předpisem: $(g \circ f)(x) = g(f(x))$

**Inverzní funkce**
Pro inverzní funkci platí $(g \circ f)(x)=x$, značíme $g=f^{-1}$
Funkce má inverzní funkci právě tehdy když je prostá
Inverzní funkce je symetrická podle osy 1. a 3. kvadrantu => pokud je funkce rostoucí pak i inverzní funkce je rostoucí

**Spojitost**
Řekneme, že funkce f je spojitá v bodě a, jestliže k libovolně zvolenému okolí bodu f(a) existuje takové okolí bodu a, že pro všechna x z tohoto okolí bodu a patří hodnoty f(x) do zvoleného okolí bodu f(a).

Na uzavřeném intervalu je funkce spojitá pokud je spojitá na otevřeném a na krajních bodech je spojitá jednostranně.

Součet, rozdíl, skládání a násobení spojitých funkcí je spojitá funkce.
U dělení je potřeba zajistit podmínku, že dělící funkce v daném bodě není nulová.

**Definice.**
Řekneme, že funkce _f_ splňuje **vlastnost mezihodnoty** na množině _M_, jestliže pro libovolné dva body _x_,_y_ z _M_ a libovolnou hodnotu _d_ mezi čísly _f(x)_, _f(y)_ existuje číslo _c_ v _M_ splňující _f_ (_c_) = _d_.

**Věta** (o extrémní hodnotě).  
Každá funkce spojitá na omezeném uzavřeném intervalu nabývá své maximum a minimum na tomto intervalu.

**Co můžeme vyšetřovat na funkci:**
- shora (existuje supremum) nebo zdola (existuje infimum) omezená
- rostoucí, klesající, nerostoucí, neklesající → monotónní funkce, rostoucí a klesající jsou ryze monotónní
- lichá, sudá
- periodická
- mohutnost/spočetnost množiny, množiny mají stejnou mohutnost pokud existuje bijekce z jedné do druhé
- maximum, minimum, infimum, supremum
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558779028881_Screenshot_2019-05-25+ma1+pdf.png)

## Limita funkce

**Funkce**
- Pokud najdeme limitu L, která je **reálné číslo**, řekneme, že je to **vlastní limita a že limita konverguje**. Jinak řekneme, že limita diverguje. Limita **nekonečno nebo mínus nekonečno** se nazývá **nevlastní limita**. Pokud najdeme nějakou limitu (vlastní či nevlastní), řekneme, že limita existuje. Jinak řekneme, že limita neexistuje.

**Věta.**  
Jestliže má funkce limitu (oboustrannou, jednostrannou) v nějaké bodě _a_, pak je tato limita jednoznačně určena.

**Výpočet**
![[Pasted image 20230603223929.png]]
![[Pasted image 20230603223639.png]]

**L'Hopitalovo pravidlo**
Při hledání limity podílu dvou funkcí (i posloupností) dostaneme “neurčitý podíl” → řešíme L'Hopitalovým pravidlem

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558785700003_Screenshot_2019-05-25+ma1+pdf3.png)



**Rychlost růstu**
škála mocnin

## Derivace
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558780021414_Screenshot_2019-05-25+ma1+pdf1.png)


**Vlastnosti derivace**

- jestliže je f diferencovatelná v bodě "a" a f′( a ) ≠ 0, pak je i příslušná inverzní funkce f −1 diferencovatelná v b
- Jestliže je funkce f diferencovatelná v bodě a, pak je f spojitá v a.
- Nechť $a < b$ jsou reálná čísla. Nechť $f$ je funkce spojitá na intervalu $a,b$ a diferencovatelná na $(a,b)$. Jestliže $f(a) = f(b)$, pak existuje $c$ z $(a,b)$ takové, že $f'( c ) =0$ (věta o střední hodnotě - **Rolleova věta**)

**Význam derivace**

1. geometrický význam
- směrnice tečny ****ke grafu dané funkce v daném bodě
2. fyzikální význam
- derivace podle časové proměnné, vyjadřující rychlost změny nějaké proměnné v čase (např. okamžitá rychlost: v= ds dt )
- diferenciální rovnice

**Monotonie**
- vlastnost, označující, zda je funkce v bodě či na daném intervalu monotónní

existuje nějaké okolí U(a) bodu a takové, že pro všechna x v tomto okolí platí:
Je-li $f'(x) > 0$ uvnitř I pak je $f$ **rostoucí** v I
Je-li $f'(x) < 0$ uvnitř I pak je $f$ **klesající** v I
Je-li $f'(x) \geq 0$ uvnitř I pak je $f$ **neklesající** v I
Je-li $f'(x) \leq 0$ uvnitř I pak je $f$ **nerostoucí** v I

Pokud $f'(a) = 0$
1. Je-li $f''(a)>0$, pak $f$ má v $a$ ostré lokální minimum
2. Je-li $f''(a)<0$, pak $f$ má v $a$ ostré lokální maximum

**Kritický bod**
**Definice:** Nechť je funkce f definovaná na nějakém okolí bodu c. Řekneme, že c je **kritický bod**, jestliže f '(c) = 0 nebo f '(c) neexistuje.
**Lokální extrémy**
Funkce $f$ má v bodě a lokální minimum (lokální maximum), jestliže $f(x)\geq f(a)$ ($f(x)\leq f(a)$) na některémprstencovém okolí bodu $a$.
$-$ => minimum
$+$ => maximum
**Inflexní bod** - f přechází z konvexní na konkávní nebo naopak a je tam dvakrát diferencovatelná

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558786935941_Screenshot_2019-05-25+konvexita-navod+pdf.png)



![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558787058489_Screenshot_2019-05-25+ma1+pdf5.png)


**Asymptoty**
viz. příklady

**Parciální derivace**
Parciální derivace funkce více proměnných představuje v matematice takovou derivaci dané funkce, při které se derivuje pouze vzhledem **k jedné z proměnných**, ostatní proměnné jsou považovány za konstanty
**Gradient**
= diferenciální operátor udávající směr růstu

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558780537103_general.PNG)

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558780548683_75403_vzorce2-derivC3A1cie.png)


**Význam derivace:**

$\frac{f(x)-f(a)}{x-a}$ … směrnice sečny body $[a,f(a)],[x,f(x)]$
$f'(a)$ … směrnice tečny v $[a,f(a)]$
tečna:

     $y - f(a) = f'(a)(x-a)$
    $y=f(a) + f'(a) (x-a)$

směrový vektor tečny (kolmý k normále): 

    $(1,f'(a))$

normála:

    $x+f'(a)y=a+f'(a)f(a)$
                                $x=a$ pro $f'(a) = 0$
                                $y=f(a)-\frac{1}{f'(a)}(x-a)$ pro $f'(a) \neq 0$
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558785537413_Screenshot_2019-05-25+ma1+pdf2.png)

**Taylorův Polynom**

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558785816816_Screenshot_2019-05-25+ma1+pdf4.png)

## Shrnutí
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558787189691_Screenshot_2019-05-25+ma1+pdf6.png)


Návod z matfyzu:

![](https://paper-attachments.dropbox.com/s_5CD6A6B063C6713890C513CD03C9B464E251280793318B4D47C55BA65906580D_1649519539931_image.png)

Příklad: Vyšetřete průběh funkce $f(x) = xe^{-\frac{x^2}{2}}$.
Definiční obor je $D(f) = \mathbb{R}$.

Limity v krajních bodech definičního oboru jsou
$\lim_{x \to -\infty}x e^{-\frac{x^{2}}{2}} = \lim_{x \to -\infty} \frac{x}{e^{\frac{x^{2}}{2}}} = - \frac{\infty}{\infty} \stackrel{\text{L'H}}{=} \lim_{x \to -\infty} \frac{1}{x \cdot e^{\frac{x^{2}}{2}}} = \frac{1}{-\infty} = 0^{-}$,
$\lim_{x \to \infty}x e^{-\frac{x^{2}}{2}} = \lim_{x \to \infty}\frac{1}{x \cdot e^{\frac{x^{2}}{2}}} = \frac{1}{\infty} = 0^{+}$.

Abychom zjistili, zda je $f$ sudá, podíváme se, zda $f(-x) = f(x)$. 
Protože $f(-x) = -x e^{-\frac{x^{2}}{2}} \neq f(x)$, funkce není sudá.

Abychom zjistili, zda je $f$ lichá, podíváme se, zda $-f(-x) = f(x)$.
Protože $-f(-x) = x e^{-\frac{x^{2}}{2}} = f(x)$, je funkce lichá.

Průsečík s osou $x$ získáme tak, že dosadíme $y = 0$:
$0 = x e^{-\frac{x^2}{2}} \Rightarrow x = 0$, takže dostáváme bod $(0, 0)$.

Průsečík s osou $y$ získáme dosazením $x = 0$:
$y = 0 \cdot e^{0} = 0$,  tedy opět bod $(0, 0)$.

První derivace funkce $f$ je $f'(x) = e^{-\frac{x^{2}}{2}}(1 - x)(1 + x)$.

Položením $f'(x) = 0$ dostáváme stacionární body $(1, \frac{1}{\sqrt{e}})$, $(-1, -\frac{1}{\sqrt{e}})$.

$f'(x) < 0$ na intervalu $(-\infty, -1) \cup (1, \infty)$. Funkce $f$ je tedy na tomto intervalu klesající.
$f'(x) > 0$ na intervalu $(-1 ,1)$. Funkce $f$ je tedy na tomto intervalu rostoucí.

Z toho, kdy funkce $f$ roste a klesá, je vidět, že bod $(1, \frac{1}{\sqrt{e}})$ je lokální maximum a bod  $(-1, -\frac{1}{\sqrt{e}})$ lokální minimum.

Druhá derivace funkce $f$ je $f''(x) = e^{-\frac{x^2}{2}} x (x - \sqrt{3})(x + \sqrt{3})$.

$f'' < 0$ na intervalu $(-\infty, -\sqrt{3}) \cup (0, \sqrt{3})$. Funkce $f$ je na tomto intervalu konkávní.
$f'' > 0$ na intervalu $(-\sqrt{3}, 0) \cup (\sqrt{3}, \infty)$. Funkce $f$ je na tomto intervalu konvexní.

Inflexní body jsou tedy $(-\sqrt{3}, -\sqrt{3} e^{-\frac{3}{2}})$, $(\sqrt{3}, \sqrt{3} e^{-\frac{3}{2}})$ a $(0, 0)$.

Protože $D(f) = \mathbb{R}$, nemáme žádné asymptoty bez směrnice.

Rovnice asymptoty se směrnicí je $y = kx + q$. Spočítáme
$k = \lim_{x \to \pm \infty}\frac{f(x)}{x} = \lim_{x \to \pm \infty} e^{-\frac{x^2}{2}} = \frac{1}{e^{\infty}} = 0$,
$q = \lim_{x \to \pm \infty} (f(x) - k \cdot x) = \lim_{x \to \pm \infty}(x e^{-\frac{x^2}{2}}) = 0$.
Dostáváme asymptotu $y = 0$.

Ze zjištěných faktů lze pak snadno sestrojit graf funkce $f$.

![](https://paper-attachments.dropbox.com/s_5CD6A6B063C6713890C513CD03C9B464E251280793318B4D47C55BA65906580D_1649586167574_image.png)



# Určitý integrál

**Riemannův (určitý) integrál** odpovídá matematickému obsahu oblasti pod grafem f, který je roven geometrickému obsahu částí nad osou x mínus obsah částí pod osou x.
Nekonečný součet nekonečně malých (úzkých) sloupců pod křivkou
$\int_a^b f(x)\,\mathrm{d}x$

## Výpočet určitého integrálu
- Standardní způsob výpočtu určitého integrálu je založen na **základní větě integrálního počtu**

Nejprve se najde primitivní funkce $F$ k dané funkci $f$ na daném intervalu $a,b$ a pak se použije Newton-Leibnizův vzorec: $\int_a^b f(x)\,\mathrm{d}x = F(b) - F(a)$, $F(b) - F(a) = [F(x)]_a^b$
funguje jen pro funkce $f$, které jsou spojité na uzavřeném intervalu $\langle a,b \rangle$, jinak řešíme jako **nevlastní integrál**

- při hledání primitivní funkce se používá metoda **substituce** a **per-partes**
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558788296382_Screenshot_2019-05-25+ma1+pdf8.png)

## Nevlastní integrál

**Definice:** Nechť a je reálné číslo, nechť $b > a$ je reálné číslo nebo $b = \infty$ . Nechť $f$ je funkce Riemannovsky integrovatelná na intervalech $a, B$ pro všechna $B$ z $(a, b)$. Pak definujeme nevlastní Riemannův integrál z $f$ od $a$ do $b$ jako: 
$\int_a^b f(x)\,\mathrm{d}x = \lim\limits_{A \to a^+}(\int_A^b f(x)\,\mathrm{d}x) + \lim\limits_{B \to b^-}(\int_a^B f(x)\,\mathrm{d}x)$

Níže je to, co tu bylo původně. Je to asi špatně, pokud se nepletu.
$\int_a^b f(x)\,\mathrm{d}x = \lim\limits_{B \to b^-}(\int_a^B f(x)\,\mathrm{d}x)$
$\int_a^b f(x)\,\mathrm{d}x = \lim\limits_{A \to a^+}(\int_A^b f(x)\,\mathrm{d}x)$

**O nevlastní integrál se jedná pokud**:
- jedna či obě integrační meze (koncové body integračního intervalu) jsou nekonečné
- integrovaná funkce není spojitá v některých bodech integračního intervalu

## Metody výpočtu
1. substituce
**obecně**

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719517093_substituce.gif)
**příklad**
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719526245_substituce_priklad.gif)

2. per-partes
**obecně**
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719544061_perpartes.gif)

**příklad**

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719551119_perpartes_priklad.gif)

3. parciální zlomky
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719587868_parcialni.gif)

4. tabulkové integrály
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719607541_tabulky.gif)
$$\int a^x \, dx = \frac{a^x}{ln(a)} +C$$
## Střední hodnota funkce na intervalu
Střední hodnota funkce $f$ na intervalu $a,b$ je $\frac{1}{b-a}\int\limits_a^b f(x)dx$

## Obsah plochy pod křivkou
Jednoduše hodnota určitého integrálu

# Neurčitý integrál
Poznámka: Habala ho ztotožňuje s Newtonovým (jsou i jiné definice, ale držel bych se jeho)
= množina primitivních funkcí integrované funkce
**Primitivní funkce**: Funkce F se nazývá primitivní funkce k funkci f na otevřeném intervalu I , pokud F' = f na intervalu I.
**Newtonův integrál:** Nechť f je funkce, která má na intervalu I primitivní funkci. Definujeme neurčitý integrál f na I jako množinu všech takových primitivních funkcí. Značení: ∫ f( x ) ⁢ ⅆ x = {F; F je primitivní funkce k f na I}. Jestliže máme jednu takovou primitivní funkci F, pak nepřesně ale tradičně píšeme ∫ f( x ) ⁢ ⅆ x =F( x ) +C, x ∈ I 

# Řady
**Definice:** Nechť $a_{k \geq n_0}$ je posloupnost (reálných čísel). Pojmem řada rozumíme $\sum_{k=n_0}^{\infty} a_k$
Pro všechna celá čísla $N > n_0$ definujeme její částečné součty řady vzorcem: $s_n = \sum_{k=n_0}^{n} a_k$

- řada konverguje k $A$, jestliže posloupnost $s_n$ konverguje k $A$.

$\sum_{k=n_0}^{\infty} a_k = a$

- řada diverguje, jestliže posloupnost $s_n$ diverguje.

$\sum_{k=n_0}^{\infty} a_k = \pm \infty$

**Hromadná hodnota posloupnosti**
Pokud v každém jejím okolí leží nekonečně mnoho členů posloupnosti
Příklad:

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558719937914_rada2.gif)


**Limita Posloupnosti**
- **Definice:** Uvažujme posloupnost $a_n$. Řekneme, že nekonečno je limita této posloupnosti pro n jdoucí do nekonečna, nebo že posloupnost jde do nekonečna pro n jdoucí do nekonečna, jestliže pro každé reálné číslo K existuje přirozené číslo N takové, že pro všechna n = N, N + 1, N + 2,... máme a n >K .
- Když má posloupnost limitu, která je reálné číslo, řekneme, že posloupnost konverguje. Taková limita se nazývá **vlastní limita**.
- Když má posloupnost limitu, která je plus či mínus nekonečno, říkáme této limitě **nevlastní limita**.
- Když má posloupnost limitu, vlastní či nevlastní, řekneme, že limita **existuje**.
- Pokud posloupnost nemá vůbec žádnou limitu, řekneme, že limita **neexistuje**.
- Posloupnosti s nevlastní limitou a bez limity se nazývají **divergentní**.

## Testování konvergence řad
**Věta** (nutná podmínka konvergence).  
Jestliže řada  ∑ $a_k$  konverguje, pak nutně posloupnost {$a_k$}  konverguje k 0.

**Absolutní konvergence:** Řada $\sum_{k=n_0}^{\infty} a_k$ absolutně konverguje, pokud konverguje $\sum_{k=n_0}^{\infty} \mid a_k \mid$ metody testování (všechny na http://math.feld.cvut.cz/mt/txte/2/txc3eb2.htm**)**
1.
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558720025323_integralni_kriterium.png)
2. (není v požadavkách)
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558720037397_srovnavaci.png)

3. (není v požadavkách)
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558720052807_limitni_srovnavaci.png)

4.
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558720069321_odmocninove.png)


5.
- pro alternující řady (“střídající +,-,+,... ”)
![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558720095455_liebnitz.png)

## Geometrická řada
=součet členů geometrické posloupnosti $( a_{n+1} = a_n \cdot q )$
**definice:** Nechť $a,q \in R$ . Řada $\sum_{k=n_0}^{\infty} a \cdot q^k$ se nazývá **geometrická řada**.
Součet geometrické řady je dán jako limita posloupnosti n-tých částečných součtů:

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558724719488_rada_soucet.png)

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558724726204_rada_soucet2.png)

## Aplikace řad

**Použití Fourierových řad pro frekvenční analýzu**
Slouží k zápisu jakéhokoliv periodického průběhu pomocí goniometrických funkcí sinus a kosinus.
Základní myšlenka Fourierových řad je, že danou funkci vyjádříme jako kombinaci oscilací, počínaje tou, jejíž frekvence je dána zadanou funkcí (buď její periodicitou nebo délkou omezeného intervalu, na kterém je zadána), a pak se berou násobky této frekvence čili používáme dělených period.

![](https://paper-attachments.dropbox.com/s_5A5458C98288EAACA9629EA164315A688B7A7F5CE93266D9D860DE89E731AB84_1560015968063_image.png)

![](https://paper-attachments.dropbox.com/s_5A5458C98288EAACA9629EA164315A688B7A7F5CE93266D9D860DE89E731AB84_1560015985189_image.png)

- **zvuková komprese:** Když dostaneme zvukový vzorek, Fourierova transformace nám umožňuje jej rozložit na základní vlny a uchovat v tomto tvaru.
- **uchovávání obrazové informace** (např. databáze otisků)

**Mocninná řada ve výpočtech**

- Před rozmachem kalkulaček se při výpočtech všechny funkce nahrazovaly Taylorovými řadami, popřípadě jejich konečnými částmi - polynomy.
- **vyčíslení Pí:** Pí je transcendentní číslo, což znamená, že jej nemůžeme vyjádřit pomocí algebraických operací. Jeden způsob jeho vyčíslení nabízí řady.
- **výpočet složitých integrálů,** které nelze vyjádřit pomocí elementárních funkcí a obvyklých operací (včetně skládání)
- **Taylorův polynom**

**Taylorův polynom a řada**
**Taylorův polynom** aproximuje hodnoty funkce, která má v daném bodě derivaci, pomocí polynomu, jehož koeficienty závisí na derivacích funkce v tomto bodě. Čím vyšší stupeň tím vyšší přesnost pro vzdálenější body.

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558724815148_taylorak.gif)


**Taylorova řada** se liší od polynomu tím, že se jedná o **nekonečný** součet

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558724823910_taylorova+rada.gif)


**Důležité řady**

![](https://paper-attachments.dropbox.com/s_B529A72B43B8403CE9C05DE86CD600B6E013D040D98A2C02331E1DA18778F882_1558724846113_rozvoje.gif)


