# 2. Jednorozměrný statistický soubor

Ke zhuštění údajů o spojitém kvantitativním statistickém znaku (respektive o nespojitém znaku s velkým počtem variant) máme dvě možnosti:

1. **Přes intervalové rozdělení četností.**
2. **Přes konstrukci měr polohy, variability, šikmosti a špičatosti**, které mohou být založeny na tzv. kvantilech.

---

## 2.1. Intervalové rozdělení četností

První způsob zhuštění dat spočívá v rozdělení jednotlivých hodnot do intervalů. Následně zjišťujeme, kolik pozorování spadá do každého intervalu.

Tento postup nám umožňuje vytvořit přehlednou tabulku četností a následně také histogram nebo polygon četností.

### Příklad intervalového rozdělení

Máme k dispozici jednorozměrný statistický soubor s jedním sledovaným znakem – údaji o příjmech 51 osob.

### Určení počtu intervalů

Pro rozdělení pozorování do tříd se orientačně doporučuje využít některé z následujících pravidel:

**a) První pravidlo**

$$
k \leq 5\log_{10}(n)
$$

**b) Druhé pravidlo**

$$
k \approx \sqrt{n}
$$

**c) Sturgesovo pravidlo**

$$
k \approx 1 + 3{,}3\log_{10}(n)
$$

Kde:

- $k$ – doporučený počet intervalů.
- $n$ – počet pozorování.

V našem případě máme 51 pozorování:

$$
n = 51
$$

Dosazením získáme:

| Pravidlo | Výpočet | Výsledek |
|---|---|---:|
| První | $5\log_{10}(51)$ | 8,5 |
| Druhé | $\sqrt{51}$ | 7,14 |
| Sturgesovo | $1+3{,}3\log_{10}(51)$ | 6,64 |

Na základě těchto pravidel zvolíme přibližně 7 intervalů.

### Výpočet délky intervalu

Nejprve vypočítáme variační obor, tedy rozdíl mezi největší a nejmenší hodnotou:

$$
R = x_{\max} - x_{\min}
$$

V našem případě:

$$
R = 25416 - 6400 = 19016
$$

Následně rozdělíme variační obor do sedmi intervalů:

$$
h = \frac{R}{k}
$$

$$
h = \frac{19016}{7} \approx 2717
$$

Délku intervalu zaokrouhlíme nahoru na praktickou hodnotu:

$$
\boxed{h = 2800}
$$

**Důležité:** Délku intervalu zaokrouhlujeme vždy nahoru, aby intervaly pokryly celý rozsah sledovaných hodnot.

### Tabulka intervalového rozdělení četností

Náš statistický soubor rozdělíme do sedmi tříd a určíme jejich četnosti.

| Č. | Interval | Střed intervalu | Absolutní četnost | Relativní četnost | Kumulativní absolutní četnost | Kumulativní relativní četnost |
|---:|---|---:|---:|---:|---:|---:|
| 1. | 6 100–8 900 | 7 500 | 3 | 0,059 | 3 | 0,059 |
| 2. | 8 900–11 700 | 10 300 | 12 | 0,235 | 15 | 0,294 |
| 3. | 11 700–14 500 | 13 100 | 12 | 0,235 | 27 | 0,529 |
| 4. | 14 500–17 300 | 15 900 | 12 | 0,235 | 39 | 0,764 |
| 5. | 17 300–20 100 | 18 700 | 7 | 0,137 | 46 | 0,901 |
| 6. | 20 100–22 900 | 21 500 | 4 | 0,079 | 50 | 0,980 |
| 7. | 22 900–25 700 | 24 300 | 1 | 0,020 | 51 | 1,000 |
| **Celkem** | — | — | **51** | **1,000** | — | — |

### Druhy četností

**Absolutní četnost**

Udává počet pozorování, která se nacházejí v konkrétním intervalu.

Například v intervalu 8 900–11 700 se nachází 12 osob.

**Relativní četnost**

Udává, jakou část celkového souboru představuje daný interval.

$$
\boxed{f_i = \frac{n_i}{n}}
$$

Kde:

- $f_i$ – relativní četnost.
- $n_i$ – absolutní četnost daného intervalu.
- $n$ – celkový počet pozorování.

Příklad pro druhý interval:

$$
f_i = \frac{12}{51} \approx 0{,}235
$$

Po převedení na procenta:

$$
0{,}235 \cdot 100 = 23{,}5\,\%
$$

**Kumulativní absolutní četnost**

Představuje postupný součet absolutních četností od prvního intervalu až po aktuální interval.

Například pro třetí interval:

$$
3 + 12 + 12 = 27
$$

Do konce třetího intervalu tedy spadá celkem 27 pozorování.

**Kumulativní relativní četnost**

Představuje postupný součet relativních četností.

Například pro třetí interval:

$$
0{,}059 + 0{,}235 + 0{,}235 = 0{,}529
$$

To znamená, že přibližně 52,9 % všech pozorování má hodnotu nejvýše na horní hranici třetího intervalu.

### Grafické znázornění četností

Na takto zhuštěném statistickém souboru můžeme demonstrovat nástroje statistické grafiky.

**Histogram**

- Zobrazuje rozdělení absolutních nebo relativních četností.
- Jednotlivé intervaly jsou znázorněny sousedícími sloupci.
- Vodorovná osa představuje intervaly hodnot.
- Svislá osa představuje četnosti.

**Polygon četností**

- Vzniká spojením bodů představujících četnosti jednotlivých intervalů v jejich středech.
- Umožňuje sledovat průběh rozdělení četností.
- Může znázorňovat absolutní i relativní četnosti.

---

## 2.2. Kvantily

**Kvantil**, případně fraktil, označuje hodnotu kvantitativního statistického znaku, která rozděluje uspořádaný statistický soubor podle předem stanoveného podílu.

Například kvantil může rozdělit hodnoty tak, že určitá část souboru leží pod touto hodnotou nebo je jí rovna. Může se jednat například o 1 %, 5 %, 20 %, 25 %, 40 %, 50 % nebo 95 % pozorování.

Kvantily jsou definovány pomocí distribuční funkce:

$$
\boxed{F_X(x_\alpha) = P(X \leq x_\alpha) = \alpha}
$$

Kde:

- $F_X$ – distribuční funkce náhodné veličiny $X$.
- $x_\alpha$ – kvantil odpovídající podílu $\alpha$.
- $\alpha$ – požadovaný podíl, vyjádřený číslem od 0 do 1.
- $P(X \leq x_\alpha)$ – pravděpodobnost, že náhodná veličina nabude hodnoty menší nebo rovné danému kvantilu.

Například:

$$
\alpha = 0{,}50
$$

odpovídá 50% kvantilu, tedy mediánu.

Příslušné výběrové kvantily kvantitativního znaku můžeme značit například:

$$
\tilde{x}_{0{,}5},\ \tilde{x}_1,\ \tilde{x}_2,\ \tilde{x}_{10},
\tilde{x}_{20},\ \tilde{x}_{25},\ \tilde{x}_{40},
\tilde{x}_{50},\ \tilde{x}_{95}
$$

### Nejpoužívanější kvantily

**Medián – 50% kvantil**

$$
\boxed{\tilde{x}_{50}}
$$

- Člení uspořádaný soubor na dvě stejně velké poloviny.
- Nazývá se také prostřední hodnota.
- 50 % pozorování má hodnotu menší nebo rovnou mediánu.

**Dolní kvantily**

Kvantily menší než medián:

$$
\tilde{x}_\alpha < \tilde{x}_{50}
$$

**Horní kvantily**

Kvantily větší než medián:

$$
\tilde{x}_\alpha > \tilde{x}_{50}
$$

**Kvartily**

Rozdělují uspořádaný statistický soubor na čtyři stejně četné části.

| Kvartil | Označení | Význam |
|---|---|---|
| Dolní kvartil | $\tilde{x}_{25}$ | 25% kvantil |
| Prostřední kvartil | $\tilde{x}_{50}$ | 50% kvantil – medián |
| Horní kvartil | $\tilde{x}_{75}$ | 75% kvantil |

**Kvintily**

Rozdělují soubor na pět stejně četných částí.

**Decily**

Rozdělují soubor na deset stejně četných částí.

**Percentily**

Rozdělují uspořádanou řadu hodnot znaku na 100 stejně četných částí. Jeden percentil tedy odpovídá 1 % pozorování.

Například 90. percentil označuje hodnotu, pod kterou nebo na které leží přibližně 90 % pozorování.

### Nalezení kvantilů v našich datech

Nejprve musíme jednotlivé hodnoty statistického souboru seřadit vzestupně.

V našem příkladu máme:

$$
n = 51
$$

**Medián**

Medián je 26. člen seřazené řady hodnot:

$$
p_{50} = \frac{n+1}{2}
$$

$$
p_{50} = \frac{51+1}{2} = 26
$$

Medián tedy odpovídá 26. hodnotě:

$$
\boxed{\tilde{x}_{50} = 14390}
$$

**Dolní kvartil**

Dolní kvartil odpovídá 25% kvantilu:

$$
p_{25} = \frac{n+1}{4}
$$

$$
p_{25} = \frac{51+1}{4} = \frac{52}{4} = 13
$$

Dolní kvartil je tedy 13. hodnotou seřazeného souboru:

$$
\boxed{\tilde{x}_{25} = 10923}
$$

**Horní kvartil**

Horní kvartil odpovídá 75% kvantilu:

$$
p_{75} = \frac{3(n+1)}{4}
$$

$$
p_{75} = \frac{3 \cdot 52}{4} = 39
$$

Horní kvartil je tedy 39. hodnotou seřazeného souboru:

$$
\boxed{\tilde{x}_{75} = 16983}
$$

### Co když vyjde desetinné pořadové číslo?

Pokud má statistický soubor například 136 hodnot, může při výpočtu kvartilu vyjít desetinné pořadové číslo:

$$
p_{25} = \frac{n+1}{4}
$$

$$
p_{25} = \frac{136+1}{4} = \frac{137}{4} = 34{,}25
$$

Hledaná hodnota tedy leží mezi 34. a 35. členem seřazené řady.

Nabízejí se dvě možnosti:

**a) Aritmetický průměr 34. a 35. hodnoty**

$$
\tilde{x}_{25} = \frac{x_{34}+x_{35}}{2}
$$

**b) Vážený průměr 34. a 35. hodnoty**

$$
\tilde{x}_{25} = 0{,}75x_{34}+0{,}25x_{35}
$$

V druhém případě se zohledňuje, že pořadové číslo 34,25 leží pouze čtvrtinu vzdálenosti mezi 34. a 35. hodnotou.

**Poznámka:** Jedná se o dvě možné metody určení kvantilu. Výsledek může záviset na zvolené statistické metodě.

### Výpočet dalších kvantilů v našich datech

**První decil – 10% kvantil**

$$
p_{10} = \frac{n+1}{10}
$$

$$
p_{10} = \frac{52}{10} = 5{,}2
$$

Podle postupu uvedeného ve studijním materiálu:

$$
\tilde{x}_{10} = \frac{9808+9876}{2}
$$

$$
\boxed{\tilde{x}_{10} = 9842}
$$

**Druhý decil – 20% kvantil**

$$
p_{20} = \frac{2(n+1)}{10}
$$

$$
p_{20} = \frac{2 \cdot 52}{10} = 10{,}4
$$

Hledaná hodnota leží mezi 10. a 11. členem:

$$
\tilde{x}_{20} = \frac{10805+10825}{2}
$$

$$
\boxed{\tilde{x}_{20} = 10815}
$$

**Devátý decil – 90% kvantil**

$$
p_{90} = \frac{9(n+1)}{10}
$$

$$
p_{90} = \frac{9 \cdot 52}{10} = 46{,}8
$$

Podle postupu uvedeného ve studijním materiálu:

$$
\tilde{x}_{90} = \frac{20016+20102}{2}
$$

$$
\boxed{\tilde{x}_{90} = 20059}
$$

Další hodnoty k ověření:

| Kvantil | Výsledek |
|---|---:|
| $\tilde{x}_{30}$ | 11 714,5 |
| $\tilde{x}_{40}$ | 13 228 |
| $\tilde{x}_{50}$ | 14 390 |
| $\tilde{x}_{60}$ | 15 090,5 |
| $\tilde{x}_{70}$ | 16 209 |
| $\tilde{x}_{80}$ | 17 850 |

### Stanovení kvantilů pomocí interpolace

Pokud máme k dispozici pouze intervalové rozdělení četností, můžeme hodnotu kvantilu přibližně určit pomocí lineární interpolace.

Základní vztah:

$$
\frac{\tilde{x}_i-x_d}{x_h-x_d}
=
\frac{i-i_d}{i_h-i_d}
$$

Po úpravě získáme:

$$
\boxed{
\tilde{x}_i =
x_d +
\frac{i-i_d}{i_h-i_d}
(x_h-x_d)
}
$$

Kde:

- $\tilde{x}_i$ – hledaný kvantil.
- $i$ – hledaný kvantil v procentech.
- $x_d$ – dolní hranice příslušného intervalu.
- $x_h$ – horní hranice příslušného intervalu.
- $i_d$ – kumulativní relativní četnost před příslušným intervalem.
- $i_h$ – kumulativní relativní četnost na konci příslušného intervalu.

Délku intervalu můžeme označit:

$$
h = x_h-x_d
$$

Rozdíl kumulativních relativních četností odpovídá relativní četnosti příslušného intervalu:

$$
i_h-i_d = \frac{n_i}{n}\cdot 100
$$

Proto můžeme vzorec zapsat také ve tvaru:

$$
\boxed{
\tilde{x}_i =
x_d +
\frac{i-i_d}{\frac{n_i}{n}\cdot 100}
\cdot h
}
$$

### Příklady výpočtu kvantilů z intervalového rozdělení

**Medián – 50% kvantil**

$$
\tilde{x}_{50} =
11700 +
\frac{50-29{,}4}{23{,}5}
\cdot 2800
$$

$$
\boxed{\tilde{x}_{50} \approx 14155{,}6}
$$

**Dolní kvartil – 25% kvantil**

$$
\tilde{x}_{25} =
8900 +
\frac{25-5{,}9}{23{,}5}
\cdot 2800
$$

$$
\boxed{\tilde{x}_{25} \approx 11176{,}4}
$$

**Horní kvartil – 75% kvantil**

$$
\tilde{x}_{75} =
14500 +
\frac{75-52{,}9}{23{,}5}
\cdot 2800
$$

$$
\boxed{\tilde{x}_{75} \approx 17132}
$$

**První decil – 10% kvantil**

$$
\tilde{x}_{10} =
8900 +
\frac{10-5{,}9}{23{,}5}
\cdot 2800
$$

$$
\boxed{\tilde{x}_{10} \approx 9387{,}2}
$$

**Důležité:** Kvantily vypočítané interpolací z intervalového rozdělení jsou pouze přibližné. Neznáme totiž přesné hodnoty a jejich pořadí uvnitř jednotlivých intervalů.

---

## 2.3. Grafy

V popisné statistice se často pracuje s tzv. **krabicovým diagramem (boxplot)**.

Krabicový diagram nám umožňuje posoudit:

- Symetrii statistického rozdělení.
- Variabilitu sledovaných dat.
- Existenci odlehlých a extrémních hodnot.

Pro konstrukci boxplotu je nejprve nutné zavést následující pojmy.

### Kvartilové rozpětí

Kvartilové rozpětí představuje rozdíl mezi horním a dolním kvartilem. Udává rozsah prostředních 50 % hodnot statistického souboru.

$$
\boxed{R_Q = \tilde{x}_{75}-\tilde{x}_{25}}
\tag{16}
$$

Kde:

- $R_Q$ – kvartilové rozpětí.
- $\tilde{x}_{75}$ – horní kvartil.
- $\tilde{x}_{25}$ – dolní kvartil.

### Vnitřní hradby

**Dolní vnitřní hradba**

$$
\boxed{H_{DV} = \tilde{x}_{25}-1{,}5R_Q}
\tag{17}
$$

**Horní vnitřní hradba**

$$
\boxed{H_{HV} = \tilde{x}_{75}+1{,}5R_Q}
\tag{18}
$$

### Vnější hradby

**Dolní vnější hradba**

$$
\boxed{H_{DN} = \tilde{x}_{25}-3R_Q}
\tag{19}
$$

**Horní vnější hradba**

$$
\boxed{H_{HN} = \tilde{x}_{75}+3R_Q}
\tag{20}
$$

### Odlehlé a extrémní hodnoty

Na základě vypočítaných hradeb rozlišujeme dva druhy neobvyklých pozorování:

- **Odlehlé hodnoty:** Nacházejí se mezi vnitřní a vnější hradbou.
- **Extrémní hodnoty:** Nacházejí se za vnějšími hradbami.

Hodnoty mezi dolní a horní vnitřní hradbou nejsou podle tohoto kritéria považovány za odlehlé.

Symbol křížku v boxplotu označuje odlehlá a extrémní pozorování.

### Konstrukce boxplotu

Krabicový diagram se skládá z několika základních prvků:

- **Krabice:** Ohraničuje oblast mezi dolním a horním kvartilem, tedy prostředních 50 % pozorování.
- **Medián:** Čára uvnitř krabice označuje 50% kvantil.
- **Vousy:** Znázorňují rozsah běžných hodnot, které nepřekračují vnitřní hradby.
- **Samostatné značky:** Označují odlehlá a extrémní pozorování.

### Příklad výpočtu hradeb

Máme následující kvartily:

$$
\tilde{x}_{25}=20
\qquad
\tilde{x}_{75}=40
$$

Nejprve vypočítáme kvartilové rozpětí:

$$
R_Q = 40-20
$$

$$
\boxed{R_Q=20}
$$

**Dolní vnitřní hradba:**

$$
H_{DV}=20-1{,}5\cdot20
$$

$$
\boxed{H_{DV}=-10}
$$

**Horní vnitřní hradba:**

$$
H_{HV}=40+1{,}5\cdot20
$$

$$
\boxed{H_{HV}=70}
$$

**Dolní vnější hradba:**

$$
H_{DN}=20-3\cdot20
$$

$$
\boxed{H_{DN}=-40}
$$

**Horní vnější hradba:**

$$
H_{HN}=40+3\cdot20
$$

$$
\boxed{H_{HN}=100}
$$

Výsledné hranice:

| Hranice | Hodnota |
|---|---:|
| Dolní vnější hradba | -40 |
| Dolní vnitřní hradba | -10 |
| Horní vnitřní hradba | 70 |
| Horní vnější hradba | 100 |

Interpretace:

- Hodnota 50 není odlehlá, protože leží mezi vnitřními hradbami.
- Hodnota 85 je odlehlá, protože leží mezi horní vnitřní a horní vnější hradbou.
- Hodnota 110 je extrémní, protože překračuje horní vnější hradbu.

**Důležité:** Hradby jsou vypočítané hranice, nikoliv nutně skutečně naměřené hodnoty. Vousy boxplotu obvykle končí na nejvzdálenějších skutečně naměřených hodnotách, které ještě leží uvnitř vnitřních hradeb.

---

## Shrnutí kapitoly 2

Jednorozměrný statistický soubor popisuje jednu sledovanou statistickou proměnnou. Pro jeho zpracování využíváme intervalové rozdělení četností, kvantily a grafické nástroje.

| Pojem | Význam |
|---|---|
| Intervalové rozdělení četností | Rozdělení hodnot do intervalů podle jejich četnosti. |
| Absolutní četnost | Počet pozorování v intervalu. |
| Relativní četnost | Podíl pozorování v intervalu vůči celému souboru. |
| Kumulativní četnost | Postupný součet četností. |
| Histogram | Grafické znázornění četností pomocí sousedících sloupců. |
| Polygon četností | Spojení bodů četností v jednotlivých středech intervalů. |
| Kvantil | Hodnota rozdělující uspořádaná data podle určitého podílu. |
| Medián | 50% kvantil. |
| Kvartil | Rozdělení souboru na čtyři stejně četné části. |
| Decil | Rozdělení souboru na deset stejně četných částí. |
| Kvintil | Rozdělení souboru na pět stejně četných částí. |
| Percentil | Rozdělení souboru na sto stejně četných částí. |
| Interpolace | Odhad hodnoty mezi dvěma známými hodnotami. |
| Boxplot | Grafické znázornění polohy, variability a odlehlých hodnot. |
| Kvartilové rozpětí | Rozdíl mezi horním a dolním kvartilem. |
| Vnitřní hradby | Hranice pro identifikaci odlehlých pozorování. |
| Vnější hradby | Hranice pro identifikaci extrémních pozorování. |

**Hlavní myšlenka kapitoly:** Intervalové rozdělení nám umožňuje přehledně uspořádat velké množství dat, kvantily popisují jejich rozložení a boxplot poskytuje rychlý grafický přehled o poloze, variabilitě a neobvyklých hodnotách.
