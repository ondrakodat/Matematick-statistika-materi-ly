# 3. Popisná statistika

## 3.1 Momenty

Momenty jsou charakteristiky vypočítané ze všech hodnot statistického souboru. Pomáhají popsat **polohu, variabilitu, šikmost a špičatost**.

Uvažujme soubor hodnot:

$$
x_1,x_2,\ldots,x_n
$$

Obecná definice $k$-tého momentu je:

$$
{}_a m_{x,k}=\frac{1}{n}\sum_{i=1}^{n}(x_i-a)^k
$$

*(Vzorec 21)*

**Vysvětlení symbolů:**

- $x_i$ – jednotlivá naměřená hodnota.
- $i$ – pořadí hodnoty.
- $n$ – počet pozorování.
- $a$ – konstanta, kolem které moment počítáme.
- $k$ – stupeň momentu, tedy mocnina.
- $\sum$ – součet všech příslušných členů.
- $1/n$ – vydělení součtu počtem pozorování.

## 3.1.1 Obecné momenty

Dosadíme $a=0$. Obecný moment je průměr $k$-tých mocnin hodnot.

$$
{}_0m_{x,k}=\frac{1}{n}\sum_{i=1}^n x_i^k
$$

*(Vzorec 22)*

První obecný moment je aritmetický průměr:

$$
{}_0m_{x,1}=\bar{x}=\frac{1}{n}\sum_{i=1}^n x_i
$$

*(Vzorec 23)*

Vyšší obecné momenty:

$$
{}_0m_{x,2}=\frac{1}{n}\sum_{i=1}^n x_i^2
$$

*(Vzorec 24)*

$$
{}_0m_{x,3}=\frac{1}{n}\sum_{i=1}^n x_i^3
$$

*(Vzorec 25)*

$$
{}_0m_{x,4}=\frac{1}{n}\sum_{i=1}^n x_i^4
$$

*(Vzorec 26)*

### Příklad

Máme hodnoty $1,2,2,3,7$, tedy $n=5$.

$$
\bar{x}=\frac{1+2+2+3+7}{5}=3
$$

$$
{}_0m_{x,2}=\frac{1^2+2^2+2^2+3^2+7^2}{5}=13{,}4
$$

## 3.1.2 Centrální momenty

Za počátek počítání zvolíme aritmetický průměr, tedy $a=\bar{x}$.

$$
{}_{\bar{x}}m_{x,k}=\frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})^k
$$

*(Vzorec 27)*

Výraz $x_i-\bar{x}$ je odchylka hodnoty od průměru.

První centrální moment je vždy nula. Druhý centrální moment nazýváme **rozptyl**.

$$
s_x^2={}_{\bar{x}}m_{x,2}=\frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})^2
$$

*(Vzorec 28)*

Pro stejná data jsou odchylky $-2,-1,-1,0,4$.

$$
s_x^2=\frac{(-2)^2+(-1)^2+(-1)^2+0^2+4^2}{5}=4{,}4
$$

Rozptyl lze vypočítat také pomocí obecných momentů:

$$
s_x^2={}_0m_{x,2}-({}_0m_{x,1})^2=13{,}4-3^2=4{,}4
$$

*(Vzorec 29)*

**Směrodatná odchylka** je odmocnina rozptylu. Má stejné jednotky jako původní data.

$$
s_x=\sqrt{s_x^2}=\sqrt{4{,}4}\approx2{,}10
$$

### Vztahy mezi obecnými a centrálními momenty

Pro stručnost v následujících vztazích označíme $M_k={}_0m_{x,k}$ a $C_k={}_{\bar{x}}m_{x,k}$.

$$
C_1=0
$$

*(Vzorec 30)*

$$
C_2=M_2-M_1^2
$$

$$
C_3=M_3-3M_1M_2+2M_1^3
$$

$$
C_4=M_4-4M_1M_3+6M_1^2M_2-3M_1^4
$$

Třetí vztah je algebraicky opravený oproti (31), kde je vytištěno −2M₁³ místo +2M₁³. Vztah pro C₄ odpovídá (32).

## 3.1.3 Charlierův test

Slouží ke kontrole výpočtu momentů pomocí binomické věty, nikoli k testování statistické hypotézy.

$$
\frac{1}{n}\sum_{i=1}^n(x_i+1)^4=M_4+4M_3+6M_2+4M_1+1
$$

*(Vzorec 33)*

## 3.1.4 Úloha

Skripta zadávají zvolit vlastní data (například teploty nebo znečištění z meteorologické stanice) a určit všechny uvedené momenty. Pro vlastní procvičení lze využít již uvedený soubor 1, 2, 2, 3, 7.

## 3.2 Normované momenty

Normováním získáme bezrozměrné hodnoty:

$$
u_i=\frac{x_i-\bar{x}}{s_x}
$$

*(Vzorec 34)*

- $u_i$ – normovaná hodnota.
- $s_x$ – směrodatná odchylka, musí být nenulová.

Například pro hodnotu $7$ platí $u_i=(7-3)/\sqrt{4{,}4}\approx1{,}91$. Hodnota je přibližně 1,91 směrodatné odchylky nad průměrem.

Normované hodnoty mají průměr nula a rozptyl jedna.

$$
m_{u,k}=\frac{1}{n}\sum_{i=1}^n u_i^k=\frac{{}_{\bar{x}}m_{x,k}}{s_x^k}
$$

### Odvození normovaných momentů (str. 27–28)


$$
{}_0m_{u,1}=\frac{1}{n}\sum_{i=1}^{n}u_i=\bar{u}
$$

*(Vzorec 35)*


$$
\bar{u}=\frac{1}{ns_x}\sum_{i=1}^{n}(x_i-\bar{x})=0
$$

*(Vzorec 36)*


$$
{}_0m_{u,k}=\frac{1}{n}\sum_{i=1}^{n}u_i^k=\frac{1}{n}\sum_{i=1}^{n}(u_i-\bar{u})^k
$$

*(Vzorec 37)*


$$
m_{u,2}=\frac{1}{ns_x^2}\sum_{i=1}^{n}(x_i-\bar{x})^2=1
$$

*(Vzorec 38)*


$$
m_{u,3}=\frac{C_3}{s_x^3}=\frac{C_3}{C_2^{3/2}}
$$

*(Vzorec 39)*


$$
m_{u,4}=\frac{C_4}{s_x^4}=\frac{C_4}{C_2^2}
$$

*(Vzorec 40)*
Protože průměr normované proměnné je nula, její obecné a centrální momenty jsou stejné. Rozptyl i směrodatná odchylka jsou jedna.

## 3.2.1 Příklad – domácnosti a počet dětí (str. 28–29)

Hodnoty: $3,1,1,3,1,1,2,1,0$.

$$
M_1=\frac{13}{9},\quad M_2=\frac{27}{9},\quad M_3=\frac{67}{9},\quad M_4=\frac{183}{9}
$$

$$
C_2=3-\left(\frac{13}{9}\right)^2\approx0{,}914
$$

$$
C_3\approx0{,}472,\qquad C_4\approx1{,}817
$$

$$
m_{u,3}\approx0{,}540,\qquad m_{u,4}\approx2{,}177
$$

Výsledky jsou přepočtené bez předčasného zaokrouhlení; v předloze jsou nesrovnalosti.

### Úplná výpočtová tabulka

| Domácnost | x | x² | x³ | x⁴ | (x+1)⁴ |
|---:|---:|---:|---:|---:|---:|
| 1 | 3 | 9 | 27 | 81 | 256 |
| 2 | 1 | 1 | 1 | 1 | 16 |
| 3 | 1 | 1 | 1 | 1 | 16 |
| 4 | 3 | 9 | 27 | 81 | 256 |
| 5 | 1 | 1 | 1 | 1 | 16 |
| 6 | 1 | 1 | 1 | 1 | 16 |
| 7 | 2 | 4 | 8 | 16 | 81 |
| 8 | 1 | 1 | 1 | 1 | 16 |
| 9 | 0 | 0 | 0 | 0 | 1 |
| Součet | 13 | 27 | 67 | 183 | 674 |

Charlierova kontrola s přesnými hodnotami:

$$
\frac{674}{9}=\frac{183+4\cdot67+6\cdot27+4\cdot13+9}{9}=74{,}8889\ldots
$$

*(Vzorec 33)*
Skripta uvádějí po zaokrouhlení 74,89 a 74,85. U centrálních momentů uvádějí 0,93; −0,53; 1,90 a normované −2,83; 2,20. Tyto výsledky nejsou konzistentní s daty; přepočtené hodnoty jsou uvedeny výše.

## 3.2.2 Výpočet momentů u rozdělení četností

Pokud se některé hodnoty opakují, použijeme jejich absolutní četnost $n_i$. Počet různých hodnot označíme $r$.

$$
n=\sum_{i=1}^r n_i
$$

$$
{}_0m_{x,k}=\frac{1}{n}\sum_{i=1}^r n_i x_i^k
$$

$$
{}_{\bar{x}}m_{x,k}=\frac{1}{n}\sum_{i=1}^r n_i(x_i-\bar{x})^k
$$

| Hodnota | Četnost |
|---:|---:|
| 1 | 1 |
| 2 | 2 |
| 3 | 1 |
| 7 | 1 |

$$
\bar{x}=\frac{1\cdot1+2\cdot2+3\cdot1+7\cdot1}{5}=3
$$

U intervalového třídění používáme středy intervalů; výsledky jsou přibližné.

### První čtyři obecné momenty z četností


$$
{}_0m_{x,1}=\frac{1}{n}\sum_{i=1}^{r}n_i x_i
$$

*(Vzorec 41)*


$$
{}_0m_{x,2}=\frac{1}{n}\sum_{i=1}^{r}n_i x_i^2
$$

*(Vzorec 42)*


$$
{}_0m_{x,3}=\frac{1}{n}\sum_{i=1}^{r}n_i x_i^3
$$

*(Vzorec 43)*


$$
{}_0m_{x,4}=\frac{1}{n}\sum_{i=1}^{r}n_i x_i^4
$$

*(Vzorec 44)*


## 3.2.3 Výpočet momentů u intervalového rozdělení četností

### Metoda vhodně zvoleného počátku

Pro stejně široké intervaly šířky $h$ a zvolený počátek $a$:

$$
v_i=\frac{x_i-a}{h}
$$

$$
\bar{x}=a+h\bar{v},\qquad C_k(x)=h^k C_k(v)
$$

Například intervaly 10–20, 20–30, 30–40 s četnostmi 2, 3, 1 mají středy 15, 25, 35. Zvolíme $a=25$, $h=10$. Potom $v_i=-1,0,1$.

$$
\bar{v}=-\frac{1}{6},\quad C_2(v)=\frac{1}{2}-\frac{1}{36}=\frac{17}{36}
$$

$$
\bar{x}\approx23{,}33,\qquad C_2(x)\approx47{,}22
$$

### Momenty pomocné proměnné


$$
{}_0m_{v,1}=\frac{1}{n}\sum_{i=1}^{r}n_i v_i
$$

*(Vzorec 46)*


$$
{}_0m_{v,2}=\frac{1}{n}\sum_{i=1}^{r}n_i v_i^2
$$

*(Vzorec 47)*


$$
{}_0m_{v,3}=\frac{1}{n}\sum_{i=1}^{r}n_i v_i^3
$$

*(Vzorec 48)*


$$
{}_0m_{v,4}=\frac{1}{n}\sum_{i=1}^{r}n_i v_i^4
$$

*(Vzorec 49)*
## 3.2.4 Příklad ze skript (str. 30–31)

Počátek a = 15900, šířka h = 2800, celkem 51 pozorování.

| Interval | Střed | Četnost | v | vn | v²n | v³n | v⁴n | (v+1)⁴n |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| 6100–8900 | 7500 | 3 | -3 | -9 | 27 | -81 | 243 | 48 |
| 8900–11700 | 10300 | 12 | -2 | -24 | 48 | -96 | 192 | 12 |
| 11700–14500 | 13100 | 12 | -1 | -12 | 12 | -12 | 12 | 0 |
| 14500–17300 | 15900 | 12 | 0 | 0 | 0 | 0 | 0 | 12 |
| 17300–20100 | 18700 | 7 | 1 | 7 | 7 | 7 | 7 | 112 |
| 20100–22900 | 21500 | 4 | 2 | 8 | 16 | 32 | 64 | 324 |
| 22900–25700 | 24300 | 1 | 3 | 3 | 9 | 27 | 81 | 256 |
| Součet | — | 51 | — | -27 | 119 | -123 | 599 | 764 |

Poznámka k předloze: četnosti na str. 30 jsou chybně vytištěny jako samé trojky. Zde jsou použity četnosti z tabulky na str. 22, které odpovídají součtům na str. 30.

$$
 v_i=\frac{x_i-15900}{2800}
$$

$$
M_1(v)=-\frac{27}{51},\quad M_2(v)=\frac{119}{51}
$$

$$
M_3(v)=-\frac{123}{51},\quad M_4(v)=\frac{599}{51}
$$

Charlierův test:

$$
\frac{764}{51}=\frac{599-4\cdot123+6\cdot119-4\cdot27+51}{51}
$$

Centrální momenty pomocné proměnné (bez předčasného zaokrouhlení):

$$
C_2(v)\approx2{,}05306,\quad C_3(v)\approx0{,}99735
$$

$$
C_4(v)\approx10{,}32604
$$

Převod na původní jednotky:

$$
\bar{x}=15900+2800\left(-\frac{27}{51}\right)\approx14417{,}65
$$

$$
s_x^2=2800^2 C_2(v)\approx16095963{,}09
$$

$$
m_{u,3}\approx0{,}33904,\quad m_{u,4}\approx2{,}44981
$$

Skripta uvádějí zaokrouhlené výsledky 14416, 16072000, 0,34 a 2,46; zde jsou hodnoty přepočtené z původních četností. Ve vzorci pro Charlierovu kontrolu je v předloze také překlep 64 místo 764.


## 3.2.5 Vztahy mezi charakteristikami polohy

- **Průměr** $\bar{x}$ – součet hodnot dělený jejich počtem.
- **Medián** $\tilde{x}$ – prostřední hodnota seřazených dat.
- **Modus** $\hat{x}$ – nejčastější hodnota.

U typického symetrického jednomodálního rozdělení se shodují. U typického kladně zešikmeného rozdělení platí $\hat{x}<\tilde{x}<\bar{x}$, u záporně zešikmeného opačně. Nejde o univerzální pravidlo.

Pro data $1,2,2,3,7$ je průměr 3, medián 2 a modus 2.

## 3.2.6 Vztahy mezi charakteristikami průměrné polohy


$$
\bar{x}<\tilde{x}<\hat{x}
$$

*(Vzorec 50)*


$$
\hat{x}<\tilde{x}<\bar{x}
$$

*(Vzorec 51)*


$$
\bar{x}-\hat{x}\approx3(\bar{x}-\tilde{x})
$$

*(Vzorec 52)*
První vztah popisuje typické záporné zešikmení (delší levý ocas), druhý kladné (delší pravý ocas). Třetí je přibližný vztah pro mírně nesouměrné rozdělení.

## 3.2.7 Míry variability

Stejný průměr ještě neznamená stejný soubor. Například hodnoty 4, 5, 6 a 0, 5, 10 mají průměr 5, ale druhý soubor je mnohem rozptýlenější.

## 3.2.8 Kvantilové míry variability

### Rozpětí

$$
R_x=x_{\max}-x_{\min}=7-1=6
$$

*(Vzorec 53)*

### Kvartilové rozpětí

$$
R_Q=\tilde{x}_{75}-\tilde{x}_{25}
$$

*(Vzorec 54)*

$\tilde{x}_{25}$ je 25% kvantil a $\tilde{x}_{75}$ je 75% kvantil. Kvartilové rozpětí popisuje šířku prostřední poloviny dat. Výpočet kvantilů závisí na použité konvenci.

### Variační koeficient

$$
c_x=\frac{s_x}{\bar{x}}
$$

*(Vzorec 60)*

Vyjadřuje relativní variabilitu. U našich dat:

$$
c_x=\frac{\sqrt{4{,}4}}3\approx0{,}699=69{,}9\,\%
$$

Je vhodný pro kladná poměrová data s průměrem vzdáleným od nuly.

## 3.2.9 Míry šikmosti

$$
m_{u,3}=\frac{{}_{\bar{x}}m_{x,3}}{s_x^3}
$$

Kladná šikmost obvykle znamená delší pravý ocas rozdělení, záporná delší levý. Nulová momentová šikmost sama nezaručuje symetrii.

$$
{}_{\bar{x}}m_{x,3}=\frac{(-2)^3+(-1)^3+(-1)^3+0^3+4^3}{5}=10{,}8
$$

$$
m_{u,3}=\frac{10{,}8}{4{,}4^{3/2}}\approx1{,}17
$$

## 3.2.10 Míry špičatosti

$$
m_{u,4}=\frac{{}_{\bar{x}}m_{x,4}}{s_x^4}
$$

Popisuje zejména význam velkých odchylek. Normální rozdělení má momentovou špičatost 3. Exces je špičatost zmenšená o 3.

$$
{}_{\bar{x}}m_{x,4}=\frac{16+1+1+0+256}{5}=54{,}8
$$

$$
m_{u,4}=\frac{54{,}8}{4{,}4^2}\approx2{,}83
$$

## Další míry polohy, variability a tvaru

Pearsonův přibližný vztah pro mírně asymetrická rozdělení:

$$
\bar{x}-\hat{x}\approx3(\bar{x}-\tilde{x})
$$

*(Vzorec 52)*

Kvantilové míry variability (55–59):

$$
R_D=\tilde{x}_{90}-\tilde{x}_{10},\qquad R_P=\tilde{x}_{99}-\tilde{x}_1
$$

$$
Q=\frac{R_Q}{2},\qquad D=\frac{R_D}{8},\qquad P=\frac{R_P}{98}
$$

Skripta na str. 33 uvádějí vážený průměr dílčích rozptylů (ve vytištěném vztahu chybí zřetelné dělení):

$$
\frac{\sum_j n_j s_j^2}{\sum_j n_j}
$$

To je vnitroskupinová složka, nikoli obecně celý rozptyl. Celkový rozptyl skupin (doplnění ke skriptům):

$$
s^2=\frac{\sum_j n_j s_j^2}{n}+\frac{\sum_j n_j(\bar{x}_j-\bar{x})^2}{n}
$$

První člen je vnitroskupinový, druhý meziskupinový rozptyl.

Kvantilová šikmost (61); v předloze je v rozvinutém čitateli chybné znaménko u minima:

$$
\tau=\frac{x_{\max}+x_{\min}-2\tilde{x}}{x_{\max}-x_{\min}}
$$

$$
\tau_i=\frac{\tilde{x}_{100-i}+\tilde{x}_i-2\tilde{x}}{\tilde{x}_{100-i}-\tilde{x}_i}
$$

Pearsonova míra šikmosti:

$$
\frac{\bar{x}-\hat{x}}{s_x}
$$

Jednoduchá míra šikmosti:

$$
\frac{n'-n''}{n}
$$

kde $n'$ je počet hodnot pod průměrem a $n''$ počet hodnot nad průměrem.

Kvantilové míry špičatosti (66–68):

$$
K=\frac{x_{\max}-x_{\min}}{R_Q}
$$

$$
K'=\frac{\tilde{x}_{99{,}5}-\tilde{x}_{0{,}5}}{R_Q},\qquad K''=\frac{\tilde{x}_{99}-\tilde{x}_1}{R_Q}
$$

Výběrová šikmost a špičatost z četností (63 a 69):

$$
A_3=\frac{\sum_i n_i(x_i-\bar{x})^3}{n s_x^3}
$$

$$
A_4=\frac{\sum_i n_i(x_i-\bar{x})^4}{n s_x^4}
$$

Ve skriptech jsou u (63) a (69) nekonzistentní jmenovatele; zde je použita definice normovaných momentů z (39) a (40). Všechny podílové míry vyžadují nenulový jmenovatel.

## 3.2.11 Empirická distribuční funkce

Udává podíl pozorování menších nebo rovných zadané hodnotě $t$.

$$
F_n(t)=\frac{1}{n}\sum_{i=1}^n\mathbf{1}_{\{x_i\le t\}}
$$

Indikátor $\mathbf{1}_{\{x_i\le t\}}$ je 1, pokud podmínka platí, a 0 jinak.

Pro data $1,2,2,3,7$:

$$
F_5(2)=\frac{3}{5}=0{,}6
$$

Tedy 60 % hodnot je nejvýše 2.

$$
F_5(t)=\begin{cases}0&t<1\\0{,}2&1\le t<2\\0{,}6&2\le t<3\\0{,}8&3\le t<7\\1&t\ge7\end{cases}
$$

Funkce je neklesající, zprava spojitá a má hodnoty mezi 0 a 1.


### Příklad ze skript – ověření rovnoměrného rozdělení (str. 34)

Původní hodnoty: 0,93; 0,35; 0,66; 0,93; 0,14; 0,23; 0,08; 0,23; 0,21; 0,59.

V MATLABu lze deset náhodných hodnot vytvořit příkazem `X=rand(10,1)`.

Seřazené hodnoty: 0,08; 0,14; 0,21; 0,23; 0,23; 0,35; 0,59; 0,66; 0,93; 0,93.

| Interval | Empirická distribuční funkce |
|---|---:|
| x < 0,08 | 0 |
| 0,08 ≤ x < 0,14 | 0,1 |
| 0,14 ≤ x < 0,21 | 0,2 |
| 0,21 ≤ x < 0,23 | 0,3 |
| 0,23 ≤ x < 0,35 | 0,5 |
| 0,35 ≤ x < 0,59 | 0,6 |
| 0,59 ≤ x < 0,66 | 0,7 |
| 0,66 ≤ x < 0,93 | 0,8 |
| x ≥ 0,93 | 1 |

Teoretická distribuční funkce rovnoměrného rozdělení R(0,1):

$$
F_0(x)=\begin{cases}0 & x<0 \\ x & 0\le x<1 \\ 1 & x\ge1\end{cases}
$$

Skripta zde končí porovnáním obou funkcí; formální výsledek testu neuvádějí. Samotná blízkost funkcí není důkazem rovnoměrnosti.

# 4. Dvourozměrný statistický soubor (str. 35)

## 4.1 Charakteristiky náhodného vektoru, korelace

Na každé statistické jednotce sledujeme dva znaky X a Y. Lze pracovat se všemi dvojicemi nebo sestavit četnostní tabulku. Na této straně skripta rozebírají první možnost.

$$
(x_1,y_1),\ldots,(x_n,y_n)
$$

Průměry a rozptyly:

$$
\bar{x}=\frac{1}{n}\sum_{i=1}^n x_i,\qquad \bar{y}=\frac{1}{n}\sum_{i=1}^n y_i
$$

$$
s_x^2=\frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})^2
$$

$$
s_y^2=\frac{1}{n}\sum_{i=1}^n(y_i-\bar{y})^2
$$

Kovariance měří společné odchylky dvojic od jejich průměrů.

$$
s_{xy}=\frac{1}{n}\sum_{i=1}^n(x_i-\bar{x})(y_i-\bar{y})
$$

$$
s_{xy}=\frac{1}{n}\sum_{i=1}^n x_i y_i-\bar{x}\bar{y}
$$

*(Vzorec 70)*

Korelační koeficient je normovaná kovariance. Musí platit, že obě směrodatné odchylky jsou nenulové.

$$
r_{xy}=\frac{s_{xy}}{s_xs_y}
$$

$$
r_{xy}=\frac{n\sum x_i y_i-(\sum x_i)(\sum y_i)}{\sqrt{[n\sum x_i^2-(\sum x_i)^2][n\sum y_i^2-(\sum y_i)^2]}}
$$

*(Vzorec 71)*

- r = 1: dokonale kladná lineární závislost.
- r = −1: dokonale záporná lineární závislost.
- r = 0: žádná lineární korelace; jiný typ závislosti může existovat.

### Příklad ze skript – ceny žita a potravinářské pšenice

Období leden 1999 až leden 2006. Graf ve skriptech znázorňuje dvojice cen na plodinové burze.

| Charakteristika | Hodnota |
|---|---:|
| Průměr X | 3485,45 Kč |
| Průměr Y | 3699,20 Kč |
| Rozptyl X | 283510,97 |
| Rozptyl Y | 245469,57 |
| Kovariance | 156730,65 |
| Korelace | 0,59411 |

Ceny jsou kladně korelované, ale korelace není dokonalá. Korelace sama neprokazuje příčinný vztah (doplňující vysvětlení).


---
Zdroj: J. Marek, Statistické zpracování dat, str. 25–35 včetně. Zápis je studijní výklad, nikoli doslovný přepis. Opravy a vlastní příklady jsou označeny.
