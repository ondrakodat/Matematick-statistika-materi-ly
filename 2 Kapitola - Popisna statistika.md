# 2. Jednorozměrný statistický soubor

Při zpracování údajů o spojitém kvantitativním statistickém znaku (případně o nespojitém znaku s velkým počtem variant) máme dvě hlavní možnosti, jak velké množství naměřených hodnot zjednodušit a přehledně popsat:

1. **Intervalové rozdělení četností** – rozdělení jednotlivých hodnot do intervalů a zjištění počtu pozorování v každém intervalu.
2. **Konstrukce statistických charakteristik a kvantilů** – použití statistických měr polohy, variability, šikmosti a špičatosti, které popisují vlastnosti statistického souboru.

---

## 2.1. Intervalové rozdělení četností

Intervalové rozdělení četností představuje způsob, jak zjednodušit rozsáhlý statistický soubor rozdělením jednotlivých pozorování do několika intervalů. Následně zjišťujeme, kolik hodnot připadá na každý interval.

Tento postup nám umožňuje lépe pochopit rozložení dat a následně jej graficky znázornit například pomocí histogramu nebo polygonu četností.

### Příklad intervalového rozdělení

Mějme k dispozici jednorozměrný statistický soubor obsahující údaje o příjmech 51 osob:

```text
6400   7975   8434   9059   9808
9876   10015  10349  10560  10805
10825  10884  10923  11143  11429
12000  12420  12956  13075  13213
13243  13630  13804  13809  13899
14390  14406  14569  14890  14906
14928  15243  15300  15908  15963
16075  16343  16451  16983  17473
17825  17875  17962  18563  19849
20016  20102  20377  22012  22865
25416
```

Celkový počet pozorování je:

$$
n = 51
$$

Abychom mohli hodnoty rozdělit do intervalů, musíme nejprve určit jejich počet.

### Stanovení počtu intervalů

Pro orientační stanovení počtu intervalů \(k\) se používají následující pravidla:

**a) První pravidlo:**

$$
k \leq 5\log_{10}(n)
\tag{10}
$$

**b) Druhé pravidlo:**

$$
k \approx \sqrt{n}
\tag{11}
$$

**c) Sturgesovo pravidlo:**

$$
k \approx 1 + 3{,}3\log_{10}(n)
\tag{12}
$$

Pro náš statistický soubor, kde \(n = 51\), získáme:

- Podle prvního pravidla:

$$
k \leq 5\log_{10}(51) \approx 8{,}54
$$

- Podle druhého pravidla:

$$
k \approx \sqrt{51} \approx 7{,}14
$$

- Podle Sturgesova pravidla:

$$
k \approx 1 + 3{,}3\log_{10}(51) \approx 6{,}64
$$

Na základě těchto pravidel zvolíme **7 intervalů**.

### Výpočet šířky intervalu

Nejprve určíme variační obor, který představuje rozdíl mezi nejvyšší a nejnižší hodnotou statistického souboru.

$$
R = x_{\max} - x_{\min}
$$

Po dosazení:

$$
R = 25416 - 6400 = 19016
$$

Šířku jednoho intervalu vypočítáme jako podíl variačního oboru a počtu intervalů:

$$
h = \frac{R}{k}
$$

Po dosazení:

$$
h = \frac{19016}{7} \approx 2716{,}57
$$

Výslednou šířku zaokrouhlíme nahoru na praktickou hodnotu:

$$
h \approx 2800
$$

Zaokrouhlujeme nahoru, aby zvolené intervaly pokryly celý variační obor statistického souboru.

### Sestavení intervalového rozdělení četností

Po stanovení počtu a šířky intervalů rozdělíme jednotlivá pozorování do příslušných tříd. Pro každou třídu určíme její střed, absolutní a relativní četnost a také kumulativní četnosti.

| Č. | Interval příjmů (Kč) | Střed intervalu | Absolutní četnost | Relativní četnost | Kumulativní abs. četnost | Kumulativní rel. četnost |
|---:|---:|---:|---:|---:|---:|---:|
| 1. | 6 100–8 900 | 7 500 | 3 | 0,059 | 3 | 0,059 |
| 2. | 8 900–11 700 | 10 300 | 12 | 0,235 | 15 | 0,294 |
| 3. | 11 700–14 500 | 13 100 | 12 | 0,235 | 27 | 0,529 |
| 4. | 14 500–17 300 | 15 900 | 12 | 0,235 | 39 | 0,764 |
| 5. | 17 300–20 100 | 18 700 | 7 | 0,137 | 46 | 0,901 |
| 6. | 20 100–22 900 | 21 500 | 4 | 0,079 | 50 | 0,980 |
| 7. | 22 900–25 700 | 24 300 | 1 | 0,020 | 51 | 1,000 |
| **Celkem** | — | — | **51** | **1,000** | — | — |

*Poznámka: Intervaly jsou zapsány pomocí zaokrouhlených hranic. Při praktickém zařazování hodnot je nutné zajistit, aby každé pozorování patřilo právě do jednoho intervalu.*

### Druhy četností

**Absolutní četnost**

Absolutní četnost vyjadřuje počet pozorování, která spadají do konkrétního intervalu. Označujeme ji \(n_i\).

Například ve druhém intervalu se nachází 12 osob, takže jeho absolutní četnost je 12.

**Relativní četnost**

Relativní četnost vyjadřuje, jakou část celkového počtu pozorování tvoří hodnoty v daném intervalu.

$$
f_i = \frac{n_i}{n}
$$

Například pro druhý interval:

$$
f_2 = \frac{12}{51} \approx 0{,}235
$$

Po převedení na procenta:

$$
f_2 \cdot 100 \approx 23{,}5\,\%
$$

**Kumulativní absolutní četnost**

Kumulativní absolutní četnost představuje postupný součet absolutních četností od prvního intervalu až po aktuální interval.

Například pro třetí interval:

$$
N_3 = 3 + 12 + 12 = 27
$$

To znamená, že 27 osob má příjem spadající do prvních tří intervalů.

**Kumulativní relativní četnost**

Kumulativní relativní četnost představuje postupný součet relativních četností. Udává, jaká část všech pozorování má hodnotu menší nebo rovnou horní hranici aktuálního intervalu.

Například pro třetí interval:

$$
F_3 = 0{,}059 + 0{,}235 + 0{,}235 = 0{,}529
$$

To odpovídá přibližně 52,9 % všech pozorování.

---

## 2.2. Kvantily

Kvantilem, někdy označovaným také jako fraktil, nazýváme hodnotu kvantitativního statistického znaku, která rozděluje uspořádaný statistický soubor podle zvoleného podílu pozorování.

Například 25% kvantil představuje hodnotu, pod kterou nebo na které se nachází přibližně 25 % všech pozorování. Obdobně 90% kvantil představuje hodnotu, kterou nepřekračuje přibližně 90 % pozorování.

Kvantily jsou definovány pomocí distribuční funkce:

$$
F_X(x_\alpha) = P(X \leq x_\alpha) = \alpha
\tag{13}
$$

Kde:

- \(F_X\) je distribuční funkce náhodné veličiny \(X\),
- \(x_\alpha\) je kvantil odpovídající zvolené hodnotě \(\alpha\),
- \(P(X \leq x_\alpha)\) představuje pravděpodobnost, že náhodná veličina nabude hodnoty menší nebo rovné danému kvantilu,
- \(\alpha\) představuje požadovaný podíl, například 0,25 nebo 0,90.

Výběrové kvantily se obvykle označují symbolem:

$$
\widetilde{x}_{\alpha}
$$

Například:

- \(\widetilde{x}_{0{,}25}\) označuje 25% kvantil,
- \(\widetilde{x}_{0{,}50}\) označuje 50% kvantil,
- \(\widetilde{x}_{0{,}90}\) označuje 90% kvantil.

### Nejpoužívanější kvantily

**Medián**

Medián představuje 50% kvantil a rozděluje uspořádaný statistický soubor na dvě stejně velké části.

$$
\widetilde{x}_{50}
$$

Přibližně 50 % pozorování má hodnotu menší nebo rovnou mediánu a zbývajících 50 % má hodnotu větší nebo rovnou mediánu.

**Dolní a horní kvantily**

- Kvantily menší než medián označujeme jako dolní kvantily.
- Kvantily větší než medián označujeme jako horní kvantily.

**Kvartily**

Kvartily rozdělují uspořádaný statistický soubor na čtyři stejně velké části.

- Dolní kvartil \(Q_1\) představuje 25% kvantil.
- Druhý kvartil \(Q_2\) představuje medián, tedy 50% kvantil.
- Horní kvartil \(Q_3\) představuje 75% kvantil.

**Kvintily**

Kvintily rozdělují uspořádaný statistický soubor na pět stejně velkých částí. Každá část tedy představuje 20 % pozorování.

**Decily**

Decily rozdělují uspořádaný statistický soubor na deset stejně velkých částí. Každá část představuje 10 % pozorování.

**Percentily**

Percentily rozdělují uspořádaný statistický soubor na sto stejně velkých částí. Každá část představuje 1 % pozorování.

Například 90. percentil znamená, že přibližně 90 % hodnot je menších nebo rovných této hodnotě.

### Nalezení kvantilů v našem statistickém souboru

Při výpočtu kvantilů nejprve seřadíme všechna pozorování vzestupně. Následně určíme pořadí hodnoty, která odpovídá požadovanému kvantilu.

Pro náš statistický soubor platí:

$$
n = 51
$$

**Medián**

Protože máme lichý počet pozorování, medián se nachází na pozici:

$$
\frac{n+1}{2} = \frac{51+1}{2} = 26
$$

Medián je tedy 26. hodnotou v uspořádaném souboru:

$$
\widetilde{x}_{50} = 14390
$$

**Dolní kvartil**

Pořadí dolního kvartilu vypočítáme:

$$
\frac{n+1}{4} = \frac{51+1}{4} = 13
$$

Dolní kvartil je 13. hodnotou:

$$
\widetilde{x}_{25} = 10923
$$

**Horní kvartil**

Pořadí horního kvartilu vypočítáme:

$$
\frac{3(n+1)}{4} = \frac{3 \cdot 52}{4} = 39
$$

Horní kvartil je 39. hodnotou:

$$
\widetilde{x}_{75} = 16983
$$

### Interpolace kvantilů

Pokud pořadí kvantilu nevyjde jako celé číslo, musíme jeho hodnotu určit interpolací mezi dvěma sousedními pozorováními.

Například kdyby měl statistický soubor 136 pozorování, pořadí dolního kvartilu by bylo:

$$
\frac{n+1}{4} = \frac{137}{4} = 34{,}25
$$

Hledaný kvartil se tedy nachází mezi 34. a 35. hodnotou.

Existují například dva způsoby interpolace:

**a) Aritmetický průměr sousedních hodnot**

$$
\widetilde{x}_{25} = \frac{x_{34}+x_{35}}{2}
$$

**b) Vážená interpolace**

$$
\widetilde{x}_{25} = 0{,}75x_{34}+0{,}25x_{35}
$$

Konkrétní způsob výpočtu závisí na zvolené metodě určování výběrových kvantilů. Různé statistické programy proto mohou u stejného souboru vracet mírně odlišné výsledky.

### Výpočet dalších kvantilů

Stejným způsobem můžeme určit také decily.

**První decil – 10% kvantil**

Pořadí prvního decilu:

$$
\frac{n+1}{10} = \frac{52}{10} = 5{,}2
$$

Hodnota se nachází mezi 5. a 6. pozorováním:

$$
\widetilde{x}_{10} = \frac{9808+9876}{2} = 9842
$$

**Druhý decil – 20% kvantil**

Pořadí druhého decilu:

$$
\frac{2(n+1)}{10} = \frac{2 \cdot 52}{10} = 10{,}4
$$

Hodnota se nachází mezi 10. a 11. pozorováním:

$$
\widetilde{x}_{20} = \frac{10805+10825}{2} = 10815
$$

**Devátý decil – 90% kvantil**

Pořadí devátého decilu:

$$
\frac{9(n+1)}{10} = \frac{9 \cdot 52}{10} = 46{,}8
$$

Hodnota se nachází mezi 46. a 47. pozorováním:

$$
\widetilde{x}_{90} = \frac{20016+20102}{2} = 20059
$$

Další hodnoty, které lze v našem statistickém souboru ověřit, jsou:

| Kvantil | Výsledná hodnota |
|---|---:|
| \(\widetilde{x}_{30}\) | 11 714,5 |
| \(\widetilde{x}_{40}\) | 13 228 |
| \(\widetilde{x}_{50}\) | 14 390 |
| \(\widetilde{x}_{60}\) | 15 090,5 |
| \(\widetilde{x}_{70}\) | 16 209 |
| \(\widetilde{x}_{80}\) | 17 850 |

*Poznámka: Výsledky interpolace se mohou lišit podle použité definice výběrového kvantilu.*

### Výpočet kvantilů z intervalového rozdělení

Pokud již nemáme k dispozici jednotlivá původní pozorování a známe pouze intervalové rozdělení četností, můžeme kvantily přibližně určit pomocí lineární interpolace.

Obecný vztah je:

$$
\frac{\widetilde{x}_i-x_d}{x_h-x_d}
=
\frac{i-i_d}{i_h-i_d}
$$

Po úpravě získáme:

$$
\widetilde{x}_i =
x_d+
\frac{i-i_d}{i_h-i_d}(x_h-x_d)
\tag{14}
$$

Kde:

- \(\widetilde{x}_i\) je hledaný kvantil,
- \(x_d\) je dolní hranice intervalu, ve kterém se kvantil nachází,
- \(x_h\) je horní hranice daného intervalu,
- \(i\) je požadovaná relativní kumulativní četnost vyjádřená v procentech,
- \(i_d\) je kumulativní relativní četnost předcházejícího intervalu,
- \(i_h\) je kumulativní relativní četnost na konci intervalu.

Rozdíl mezi hranicemi intervalu představuje jeho šířku:

$$
h = x_h-x_d
$$

Pokud označíme absolutní četnost příslušného intervalu jako \(n_i\), můžeme vztah zapsat také takto:

$$
\widetilde{x}_i =
x_d+
\frac{i-i_d}{\frac{n_i}{n}\cdot 100}h
$$

### Příklady výpočtu kvantilů z intervalové tabulky

**Medián – 50% kvantil**

Medián se nachází ve třetím intervalu, protože kumulativní relativní četnost předchozího intervalu je 29,4 % a po přičtení četnosti třetího intervalu dosahuje 52,9 %.

Dosadíme:

$$
\widetilde{x}_{50}
=
11700+
\frac{50-29{,}4}{23{,}5}\cdot 2800
$$

$$
\boxed{\widetilde{x}_{50}\approx 14155{,}6}
$$

**Dolní kvartil – 25% kvantil**

Dolní kvartil se nachází ve druhém intervalu.

$$
\widetilde{x}_{25}
=
8900+
\frac{25-5{,}9}{23{,}5}\cdot 2800
$$

$$
\boxed{\widetilde{x}_{25}\approx 11176{,}4}
$$

**Horní kvartil – 75% kvantil**

Horní kvartil se nachází ve čtvrtém intervalu.

$$
\widetilde{x}_{75}
=
14500+
\frac{75-52{,}9}{23{,}5}\cdot 2800
$$

$$
\boxed{\widetilde{x}_{75}\approx 17132}
$$

**První decil – 10% kvantil**

První decil se nachází ve druhém intervalu.

$$
\widetilde{x}_{10}
=
8900+
\frac{10-5{,}9}{23{,}5}\cdot 2800
$$

$$
\boxed{\widetilde{x}_{10}\approx 9387{,}2}
$$

*Důležité: Kvantily vypočítané interpolací z intervalového rozdělení jsou pouze přibližné. Při výpočtu totiž neznáme přesné umístění jednotlivých pozorování uvnitř intervalů.*

---

## 2.3. Grafy

Grafické znázornění představuje důležitou součást popisné statistiky. Umožňuje nám rychleji pochopit rozložení hodnot, jejich variabilitu, symetrii a případnou přítomnost odlehlých nebo extrémních pozorování.

Pro znázornění statistických dat se používají například:

- Histogram.
- Polygon četností.
- Krabicový diagram (boxplot).

### Histogram

Histogram slouží ke grafickému znázornění intervalového rozdělení četností.

Na vodorovné ose jsou zobrazeny jednotlivé intervaly sledované proměnné a na svislé ose jejich četnosti. Každý interval je reprezentován obdélníkem, jehož výška odpovídá četnosti pozorování v daném intervalu.

**Důležité vlastnosti histogramu:**

- Jednotlivé sloupce na sebe navazují bez mezer.
- Výška sloupce odpovídá četnosti daného intervalu.
- Histogram umožňuje posoudit, ve kterých intervalech se nachází nejvíce pozorování.
- Lze znázornit absolutní i relativní četnosti.

### Polygon četností

Polygon četností představuje grafické znázornění rozdělení četností pomocí spojnic jednotlivých bodů.

Každý bod představuje střed příslušného intervalu a jeho četnost. Následným propojením těchto bodů vznikne lomená čára, která znázorňuje průběh rozdělení četností.

Polygon lze vytvořit pro:

- Absolutní četnosti.
- Relativní četnosti.

Oproti histogramu umožňuje polygon lépe sledovat celkový průběh rozdělení hodnot a případně porovnávat více rozdělení mezi sebou.

### Krabicový diagram (Boxplot)

V popisné statistice se často používá také takzvaný **krabicový diagram (boxplot)**.

Krabicový diagram umožňuje posoudit:

- Polohu hodnot ve statistickém souboru.
- Variabilitu a rozptýlení pozorování.
- Symetrii rozdělení.
- Přítomnost odlehlých a extrémních hodnot.

Základem boxplotu jsou kvartily, medián a kvartilové rozpětí.

### Kvartilové rozpětí

Kvartilové rozpětí vyjadřuje rozdíl mezi horním a dolním kvartilem. Označujeme jej \(R_Q\).

$$
R_Q = \widetilde{x}_{75}-\widetilde{x}_{25}
\tag{20}
$$

Kvartilové rozpětí představuje šířku intervalu, ve kterém se nachází prostředních 50 % pozorování statistického souboru.

Čím větší je kvartilové rozpětí, tím větší je variabilita prostředních 50 % hodnot.

### Vnitřní a vnější hradby

Pro identifikaci odlehlých a extrémních hodnot se používají takzvané vnitřní a vnější hradby.

Jejich výpočet vychází z dolního kvartilu, horního kvartilu a kvartilového rozpětí.

**Dolní vnitřní hradba**

$$
H_{DV} = \widetilde{x}_{25}-1{,}5R_Q
\tag{16}
$$

**Horní vnitřní hradba**

$$
H_{HV} = \widetilde{x}_{75}+1{,}5R_Q
\tag{17}
$$

**Dolní vnější hradba**

$$
H_{DN} = \widetilde{x}_{25}-3R_Q
\tag{18}
$$

**Horní vnější hradba**

$$
H_{HN} = \widetilde{x}_{75}+3R_Q
\tag{19}
$$

### Odlehlé a extrémní hodnoty

Podle polohy pozorování vzhledem k vypočítaným hradbám rozlišujeme následující situace:

**Běžné hodnoty**

Běžná pozorování se nacházejí mezi dolní a horní vnitřní hradbou.

**Odlehlé hodnoty**

Odlehlé hodnoty se nacházejí za vnitřní hradbou, ale stále mezi vnitřní a vnější hradbou.

Jinými slovy:

- Menší odlehlé hodnoty leží mezi dolní vnější a dolní vnitřní hradbou.
- Větší odlehlé hodnoty leží mezi horní vnitřní a horní vnější hradbou.

**Extrémní hodnoty**

Extrémní hodnoty se nacházejí za vnějšími hradbami.

- Dolní extrémní hodnoty jsou menší než dolní vnější hradba.
- Horní extrémní hodnoty jsou větší než horní vnější hradba.

V boxplotu se odlehlá a extrémní pozorování obvykle zobrazují samostatnými symboly, například křížky nebo body.

### Jak číst krabicový diagram

Krabicový diagram se skládá z několika základních částí:

1. **Dolní kvartil (Q1)** – dolní okraj krabice, pod kterým se nachází přibližně 25 % pozorování.
2. **Medián (Q2)** – čára uvnitř krabice, která rozděluje soubor na dvě poloviny.
3. **Horní kvartil (Q3)** – horní okraj krabice, pod kterým se nachází přibližně 75 % pozorování.
4. **Krabice** – prostor mezi dolním a horním kvartilem, který obsahuje prostředních 50 % pozorování.
5. **Vousy** – úsečky vycházející z krabice, které obvykle sahají k nejvzdálenějším běžným hodnotám, tedy k hodnotám uvnitř vnitřních hradeb.
6. **Odlehlé a extrémní hodnoty** – samostatně vykreslené body nebo jiné symboly mimo vousy.

Délka krabice vyjadřuje kvartilové rozpětí. Poloha mediánu uvnitř krabice a délka jednotlivých vousů nám mohou napovědět, zda je rozdělení přibližně symetrické, nebo vykazuje určitou šikmost.

*Poznámka: Hradby představují teoretické hranice pro klasifikaci pozorování. Samotné vousy boxplotu obvykle nekončí přesně na těchto hranicích, ale na nejvzdálenějších skutečně pozorovaných hodnotách, které se ještě nacházejí uvnitř vnitřních hradeb.*

