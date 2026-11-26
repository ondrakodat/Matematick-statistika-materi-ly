# 2. Jednorozměrný statistický soubor – začátečnický výklad

Zdroj: J. Marek, *Statistické zpracování dat*, str. 21–24. Celá kapitola 2, vzorce (10)–(20).

Jednorozměrný soubor obsahuje jeden sledovaný statistický znak. U spojitého kvantitativního znaku (nebo nespojitého s mnoha variantami) skripta uvádějí dva způsoby zhuštění údajů: intervalové rozdělení četností a konstrukci měr polohy, variability, šikmosti a špičatosti, mimo jiné pomocí kvantilů.

## 2.1 Intervalové rozdělení četností (str. 21–22)

### Původní data – příjmy 51 osob

| | | | | |
|---:|---:|---:|---:|---:|
|6400|7975|8434|9059|9808|
|9876|10015|10349|10560|10805|
|10825|10884|10923|11143|11429|
|12000|12420|12956|13075|13213|
|13243|13630|13804|13809|13899|
|14390|14406|14569|14890|14906|
|14928|15243|15300|15908|15963|
|16075|16343|16451|16983|17473|
|17825|17875|17962|18563|19849|
|20016|20102|20377|22012|22865|
|25416|||||

### Počet tříd

Skripta doporučují tři orientační pravidla:

$$
k\leq 5\log n
$$

*(Vzorec 10)*

$$
k\sim\sqrt{n}
$$

*(Vzorec 11)*

$$
k\sim 1+3{,}3\log n
$$

*(Vzorec 12 – Sturgesovo pravidlo)*

**Vysvětlení jednotlivých symbolů:**

- **n** – počet pozorování.
- **k** – počet tříd.
- **log** – dekadický logaritmus.
- **∼** – zde přibližná orientační hodnota.

Pro n=51:

$$
5\log 51\approx 8{,}5
$$

$$
\sqrt{51}\approx 7{,}14
$$

$$
1+3{,}3\log 51\approx 6{,}635
$$

Volíme sedm tříd. Variační obor (rozpětí) je:

$$
R=x_{\max}-x_{\min}=25416-6400=19016
$$

Délka třídy:

$$
h\approx\frac{19016}{7}\approx2717
$$

Skripta zaokrouhlují nahoru na 2800, aby intervaly pokryly všechna data. První interval začíná na 6100; poslední končí na 25700.

**Jak postupovat:** 1. Najdi minimum a maximum. 2. Zvol počet tříd. 3. Vypočti šířku. 4. Vytvoř intervaly. 5. Spočítej, kolik pozorování do každého patří.

### Četnostní tabulka

| Třída | Interval | Střed | Absolutní | Relativní | Kumul. absolutní | Kumul. relativní |
|---:|---|---:|---:|---:|---:|---:|
|1|6100–8900|7500|3|0,059|3|0,059|
|2|8900–11700|10300|12|0,235|15|0,294|
|3|11700–14500|13100|12|0,235|27|0,529|
|4|14500–17300|15900|12|0,235|39|0,764|
|5|17300–20100|18700|7|0,137|46|0,901|
|6|20100–22900|21500|4|0,079|50|0,980|
|7|22900–25700|24300|1|0,020|51|1,000|
|Celkem|—|—|51|1,000|—|—|

Tabulka zachovává zaokrouhlené údaje skript. Při výpočtu z přesných četností vychází např. 39/51 přibližně 0,765 a 46/51 přibližně 0,902.

Doplňující zápis výpočtu sloupců:

$$
c_j=\frac{a_j+b_j}{2}
$$

$$
p_j=\frac{n_j}{n}
$$

$$
N_j=\sum_{l=1}^{j}n_l
$$

$$
P_j=\frac{N_j}{n}
$$

**Vysvětlení jednotlivých symbolů:**

- **aⱼ,bⱼ** – hranice třídy.
- **cⱼ** – její střed.
- **nⱼ** – absolutní četnost.
- **pⱼ** – relativní četnost.
- **Nⱼ** – kumulativní absolutní četnost.
- **Pⱼ** – kumulativní relativní četnost.
- **j,l** – indexy tříd.

Například ve druhé třídě:

$$
c_2=\frac{8900+11700}{2}=10300
$$

$$
p_2=\frac{12}{51}\approx0{,}2353
$$

$$
N_2=3+12=15,\qquad P_2=\frac{15}{51}\approx0{,}2941
$$

### Grafické zobrazení četností

Skripta na str. 22 ukazují čtyři grafy: histogram absolutních četností, histogram relativních četností, polygon absolutních četností a polygon relativních četností. Histogramy mají na vodorovné ose třídy (označené středy) a na svislé ose četnosti. Polygon spojuje body odpovídající středům tříd a četnostem; ve skriptech je uzavřen k nule u sousedních pomyslných středů 4700 a 27100. Nejvyšší četnost mají druhá až čtvrtá třída (12 osob každá).

## 2.2 Kvantily (str. 22–23)

Kvantil neboli fraktil je hodnota, která odděluje stanovenou část uspořádaného souboru. Skripta definují kvantil distribuční funkcí:

$$
F_X(\tilde{x}_{\alpha})=P(X\leq\tilde{x}_{\alpha})=\alpha
$$

*(Vzorec 13)*

**Vysvětlení jednotlivých symbolů:**

- **X** – náhodná veličina.
- **F(X)** – její distribuční funkce.
- **P** – pravděpodobnost.
- **α** – podíl mezi 0 a 1.
- **x̃(α)** – příslušný kvantil.

Rovnost je přímo použitelná, pokud distribuční funkce požadované hodnoty nabývá.

Výběrové kvantily skripta označují procentním indexem, například:

$$
\tilde{x}_{0.5},\ \tilde{x}_1,\ \tilde{x}_2,\ \tilde{x}_{10},\ \tilde{x}_{20}
$$

$$
\tilde{x}_{25},\ \tilde{x}_{40},\ \tilde{x}_{50},\ \tilde{x}_{95}
$$

Nezaměňujeme je s kritickými kvantily.

- Medián (x̃₅₀) rozděluje soubor na dvě poloviny.
- Dolní kvantily jsou menší než medián, horní větší (při shodných hodnotách mohou být rovny).
- Kvartily rozdělují soubor na čtvrtiny (25, 50, 75 %).
- Decily na desetiny (10, 20, ..., 90 %).
- Kvintily na pětiny (20, 40, 60, 80 %).
- Percentily na sto částí.

**Představa:** Když 25 % osob má příjem nejvýše kolem určité částky, tato částka je dolní kvartil.

### Kvantily přímo z uspořádaných dat

Doplňující obecný zápis metody použité ve skriptech: pro procentní index i vypočteme pořadí

$$
r=\frac{i}{100}(n+1)
$$

kde r je pořadová pozice a x((r)) označuje hodnotu na této pozici, pokud je celá.

Medián:

$$
r=\frac{51+1}{2}=26,\qquad \tilde{x}_{50}=14390
$$

Dolní kvartil:

$$
r=\frac{51+1}{4}=13,\qquad \tilde{x}_{25}=10923
$$

Horní kvartil:

$$
r=\frac{3(51+1)}{4}=39,\qquad \tilde{x}_{75}=16983
$$

Pokud je n=136, pozice dolního kvartilu je 34,25. Skripta nabízejí dvě možnosti: prostý průměr sousedních hodnot nebo váženou interpolaci.

$$
\tilde{x}_{25}=\frac{x_{(34)}+x_{(35)}}{2}
$$

$$
\tilde{x}_{25}=0{,}75x_{(34)}+0{,}25x_{(35)}
$$

V následujících příkladech skripta používají prostý průměr.

První decil:

$$
r=\frac{52}{10}=5{,}2
$$

$$
\tilde{x}_{10}=\frac{9808+9876}{2}=9842
$$

Druhý decil:

$$
r=\frac{2\cdot52}{10}=10{,}4
$$

$$
\tilde{x}_{20}=\frac{10805+10825}{2}=10815
$$

Poslední decil:

$$
r=\frac{9\cdot52}{10}=46{,}8
$$

$$
\tilde{x}_{90}=\frac{20016+20102}{2}=20059
$$

Zbývající decily (ověřovací úloha ze skript, doplněny mezivýpočty):

| Kvantil | Pozice | Výpočet | Výsledek |
|---|---:|---|---:|
|30 %|15,6|(11429 + 12000)/2|11714,5|
|40 %|20,8|(13213 + 13243)/2|13228|
|50 %|26|14390|14390|
|60 %|31,2|(14928 + 15243)/2|15085,5|
|70 %|36,4|(16075 + 16343)/2|16209|
|80 %|41,6|(17825 + 17875)/2|17850|

Poznámka k předloze: skripta uvádějí pro 60% kvantil 15090,5, ale z vypsaných dat vychází 15085,5. Obě hodnoty zde rozlišujeme.

### Kvantily z intervalového rozdělení – interpolace

Pokud máme pouze četnostní tabulku, neznáme přesnou polohu hodnot uvnitř třídy. Kvantil přibližně určíme interpolací mezi hranicemi třídy.

$$
\frac{\tilde{x}_i-x_d}{x_h-x_d}=\frac{i-i_d}{i_h-i_d}
$$

Po úpravě:

$$
\tilde{x}_i=x_d+\frac{i-i_d}{i_h-i_d}(x_h-x_d)
$$

*(Vzorec 14)*

Při označení délky intervalu h=xₕ-x(d) a třídní relativní četnosti v procentech:

$$
i_h-i_d=\frac{n_i}{n}\cdot100
$$

obdržíme:

$$
\tilde{x}_i=x_d+\frac{i-i_d}{\frac{n_i}{n}\cdot100}h
$$

*(Vzorec 15)*

**Vysvětlení jednotlivých symbolů:**

- **i** – požadovaný procentní kvantil.
- **x(d),xₕ** – dolní a horní hranice vybrané třídy.
- **i(d),iₕ** – kumulativní relativní četnosti na těchto hranicích v procentech.
- **h** – šířka intervalu.
- **nᵢ** – absolutní četnost dané třídy.
- **n** – celková četnost.

Nejprve vyhledáme třídu, ve které kumulativní četnost dosáhne požadovaného procenta. Pak dosadíme. Příklady používají zaokrouhlené četnosti ze skript.

Medián (třetí třída):

$$
\tilde{x}_{50}=11700+\frac{50-29{,}4}{23{,}5}\cdot2800\approx14154{,}5
$$

Dolní kvartil (druhá třída):

$$
\tilde{x}_{25}=8900+\frac{25-5{,}9}{23{,}5}\cdot2800\approx11175{,}7
$$

Horní kvartil (čtvrtá třída):

$$
\tilde{x}_{75}=14500+\frac{75-52{,}9}{23{,}5}\cdot2800\approx17133{,}2
$$

První decil (druhá třída):

$$
\tilde{x}_{10}=8900+\frac{10-5{,}9}{23{,}5}\cdot2800\approx9388{,}5
$$

Ve skriptech jsou uvedeny výsledky 14155,6; 11176,4; 17132; 9387,2. Výše jsou výsledky přepočtené přímo z vytištěných zaokrouhlených vstupů; drobné rozdíly jsou výslovně označeny.

## 2.3 Grafy (str. 24)

### Krabicový diagram (boxplot)

Boxplot slouží k posouzení symetrie, variability a výskytu odlehlých či extrémních hodnot. Krabice sahá od dolního kvartilu po horní kvartil. Uvnitř je medián. Vousy zobrazují krajní hodnoty v rámci vnitřních hradeb (podle konkrétní konvence). Křížky ve skriptech označují odlehlé a extrémní hodnoty.

Skripta ukazují srovnávací boxplot cen pro KB, Unipetrol, Zentivu a ČEZ: rozdílné výšky krabic a polohy mediánů ukazují rozdíly v poloze a variabilitě. Druhý obrázek vysvětluje konstrukci boxplotu, vousy, kvartily a odlehlá či extrémní pozorování.

### Hradby a kvartilové rozpětí

Dolní vnitřní hradba:

$$
\tilde{x}_{25}-1{,}5R_Q
$$

*(Vzorec 16)*

Horní vnitřní hradba:

$$
\tilde{x}_{75}+1{,}5R_Q
$$

*(Vzorec 17)*

Dolní vnější hradba:

$$
\tilde{x}_{25}-3R_Q
$$

*(Vzorec 18)*

Horní vnější hradba:

$$
\tilde{x}_{75}+3R_Q
$$

*(Vzorec 19)*

Kvartilové rozpětí:

$$
R_Q=\tilde{x}_{75}-\tilde{x}_{25}
$$

*(Vzorec 20)*

**Vysvětlení jednotlivých symbolů:**

- **R(Q)** – kvartilové rozpětí.
- **x̃₂₅** – dolní kvartil.
- **x̃₇₅** – horní kvartil.

Koeficienty 1,5 a 3 určují vzdálenost vnitřních a vnějších hradeb.

Odlehlé měření leží mezi vnitřní a vnější hradbou na jedné ze stran. Extrémní hodnota leží za vnější hradbou. Samotná odlehlost není důkazem chyby měření (doplňující vysvětlení).

### Doplňující řešený příklad – boxplot pro 51 příjmů

Použijeme kvartily vypočtené přímo z původních dat:

$$
R_Q=16983-10923=6060
$$

$$
10923-1{,}5\cdot6060=1833
$$

$$
16983+1{,}5\cdot6060=26073
$$

$$
10923-3\cdot6060=-7257
$$

$$
16983+3\cdot6060=35163
$$

Minimum 6400 a maximum 25416 leží uvnitř vnitřních hradeb. Podle tohoto pravidla tedy nemá soubor odlehlé ani extrémní hodnoty. Krabice sahá od 10923 do 16983, medián je 14390 a vousy dosahují k minimu a maximu.

### Jak si to představit a co si zapamatovat

- Jednorozměrný soubor: představ si seznam příjmů, nikoli příjmů a věku současně.
- Absolutní četnost říká kolik osob; relativní jaká část všech osob; kumulativní kolik osob dohromady až po danou třídu.
- Například 15 z 51 osob spadá do prvních dvou tříd, tedy přibližně 29,4 %.
- Kvantil není procento, ale konkrétní hodnota znaku. Medián 14390 je příjem, nikoli 50 Kč nebo 50 %.
- Při počítání kvantilů z původních dat nejprve seřaď hodnoty. Při počítání z intervalů nejprve vyhledej správnou třídu.
- U boxplotu spočítej nejprve kvartilové rozpětí, potom čtyři hradby, nakonec porovnej jednotlivá pozorování s hradbami.

### Doplňující jednoduchý příklad

Mějme hodnoty 1, 2, 3, 4, 5, 6, 7. Medián je čtvrtá hodnota, dolní kvartil druhá a horní kvartil šestá.

$$
\tilde{x}_{50}=4,\qquad \tilde{x}_{25}=2,\qquad \tilde{x}_{75}=6
$$

$$
R_Q=6-2=4
$$

Dolní vnitřní hradba je -4, horní 12. Žádná hodnota není odlehlá.
