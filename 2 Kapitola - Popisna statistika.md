# 3. Popisná statistika

## 3.1. Momenty

Momenty jsou statistické charakteristiky, které slouží k popisu vlastností statistického souboru. Na rozdíl od kvantilů, které představují konkrétní hodnoty statistického znaku, jsou momenty funkcemi všech hodnot daného znaku v souboru.

Pomocí momentů můžeme popsat například:
- **Polohu** – kde se hodnoty souboru přibližně nacházejí.
- **Variabilitu** – jak moc jsou hodnoty rozptýlené.
- **Šikmost** – zda je rozdělení hodnot symetrické, nebo vychýlené na jednu stranu.
- **Špičatost** – jak moc jsou hodnoty soustředěny kolem středu rozdělení.

Uvažujme jednorozměrný statistický soubor o rozsahu `n`.

Obecná definice k-tého momentu:

$$
{}_a m_{x,k} = \frac{1}{n}\sum_{i=1}^{n}(x_i-a)^k
\tag{21}
$$

**Vysvětlení symbolů:**
- $x_i$ – jednotlivá naměřená hodnota statistického znaku.
- $n$ – celkový počet pozorování.
- $a$ – konstanta, od které měříme odchylky jednotlivých hodnot.
- $k$ – řád momentu, tedy mocnina, na kterou umocňujeme odchylku.
- $\sum$ – symbol sumy, který znamená, že sečteme výsledky za všechna pozorování.
- $\frac{1}{n}$ – vydělení součtu počtem pozorování.

**Jak vzorec pochopit?**

Vezmeme každou hodnotu $x_i$, odečteme od ní konstantu $a$, výsledek umocníme na $k$-tou a nakonec všechny výsledky zprůměrujeme.

### 3.1.1. Obecné momenty

Pokud položíme $a=0$, získáme momenty počítané kolem nuly. Tyto momenty označujeme jako obecné momenty.

Obecná definice k-tého momentu kolem nuly:

$$
{}_0m_{x,k} = \frac{1}{n}\sum_{i=1}^{n}x_i^k
\tag{22}
$$

Nejdůležitější je první obecný moment, který představuje **aritmetický průměr**:

$$
{}_0m_{x,1} = \frac{1}{n}\sum_{i=1}^{n}x_i = \overline{x}
\tag{23}
$$

Aritmetický průměr nám říká, jaká je průměrná hodnota sledovaného statistického znaku.

Další obecné momenty:

**Druhý obecný moment:**

$$
{}_0m_{x,2} = \frac{1}{n}\sum_{i=1}^{n}x_i^2
\tag{24}
$$

**Třetí obecný moment:**

$$
{}_0m_{x,3} = \frac{1}{n}\sum_{i=1}^{n}x_i^3
\tag{25}
$$

**Čtvrtý obecný moment:**

$$
{}_0m_{x,4} = \frac{1}{n}\sum_{i=1}^{n}x_i^4
\tag{26}
$$

**Jak si to zapamatovat?**

- První obecný moment = aritmetický průměr.
- Druhý obecný moment = průměr druhých mocnin hodnot.
- Třetí obecný moment = průměr třetích mocnin hodnot.
- Čtvrtý obecný moment = průměr čtvrtých mocnin hodnot.

S rostoucím řádem momentu se tedy mění mocnina jednotlivých hodnot, ze kterých moment počítáme.

### 3.1.2. Centrální momenty

U obecných momentů jsme počítali odchylky od nuly. U centrálních momentů místo nuly použijeme jako střed počítání **aritmetický průměr**.

Centrální moment tedy sleduje, jak moc se jednotlivé hodnoty odchylují od průměru.

Obecná definice k-tého centrálního momentu:

$$
{}_{\overline{x}}m_{x,k} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^k
\tag{27}
$$

**Vysvětlení symbolů:**
- $x_i$ – jednotlivá naměřená hodnota.
- $\overline{x}$ – aritmetický průměr všech hodnot.
- $x_i-\overline{x}$ – odchylka konkrétní hodnoty od průměru.
- $k$ – řád centrálního momentu.
- $n$ – počet pozorování.

Nejdůležitější je druhý centrální moment, který se nazývá **rozptyl**:

$$
{}_{\overline{x}}m_{x,2} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^2
\tag{28}
$$

Rozptyl nám říká, jak moc jsou jednotlivé hodnoty vzdálené od aritmetického průměru.

- Malý rozptyl znamená, že hodnoty jsou blízko průměru.
- Velký rozptyl znamená, že hodnoty jsou více rozptýlené.

Druhý centrální moment lze vyjádřit také pomocí obecných momentů:

$$
{}_{\overline{x}}m_{x,2}
=
{}_0m_{x,2}-({}_0m_{x,1})^2
\tag{29}
$$

Jinými slovy: rozptyl získáme jako druhý obecný moment zmenšený o druhou mocninu prvního obecného momentu.

**První centrální moment:**

$$
{}_{\overline{x}}m_{x,1}
=
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})=0
\tag{30}
$$

První centrální moment je vždy roven nule, protože součet odchylek všech hodnot od jejich aritmetického průměru je vždy nulový.

**Třetí centrální moment:**

$$
{}_{\overline{x}}m_{x,3}
=
{}_0m_{x,3}
-3{}_0m_{x,1}{}_0m_{x,2}
+2({}_0m_{x,1})^3
\tag{31}
$$

Třetí centrální moment souvisí se šikmostí rozdělení. Pomáhá určit, zda jsou hodnoty rozděleny symetricky, nebo zda je rozdělení vychýlené na jednu stranu.

**Čtvrtý centrální moment:**

$$
\begin{aligned}
{}_{\overline{x}}m_{x,4}
={}&{}_0m_{x,4}
-4{}_0m_{x,1}{}_0m_{x,3}\\
&+6({}_0m_{x,1})^2{}_0m_{x,2}
-3({}_0m_{x,1})^4
\end{aligned}
\tag{32}
$$

Čtvrtý centrální moment souvisí se špičatostí rozdělení a pomáhá popsat koncentraci hodnot kolem středu.

**Důležité rozlišení:**

| Moment | Co vyjadřuje |
|---|---|
| 1. obecný | Aritmetický průměr |
| 2. obecný | Průměr druhých mocnin hodnot |
| 3. obecný | Průměr třetích mocnin hodnot |
| 4. obecný | Průměr čtvrtých mocnin hodnot |
| 1. centrální | Vždy 0 |
| 2. centrální | Rozptyl |
| 3. centrální | Souvisí se šikmostí |
| 4. centrální | Souvisí se špičatostí |

### 3.1.3. Charlierův test

Charlierův test slouží ke kontrole správnosti výpočtu momentů. Historicky se používal především při ručních výpočtech, kdy bylo možné snadno udělat početní chybu.

Kontrola je založena na následujícím vztahu:

$$
\begin{aligned}
\frac{1}{n}\sum_{i=1}^{n}(x_i+1)^4
={}&{}_0m_{x,4}
+4{}_0m_{x,3}\\
&+6{}_0m_{x,2}
+4{}_0m_{x,1}+1
\end{aligned}
\tag{33}
$$

**Jak test funguje?**

1. Vypočítáme levou stranu vzorce, tedy průměr čtvrtých mocnin hodnot zvýšených o jedničku.
2. Vypočítáme pravou stranu pomocí již vypočtených obecných momentů.
3. Porovnáme výsledky.

Pokud se výsledky přibližně shodují, výpočet momentů je pravděpodobně správný. Drobné rozdíly mohou vzniknout zaokrouhlováním.

### 3.1.4. Úloha

Zvolte statistická data, například teplotní řadu nebo hodnoty znečištění z vybrané meteorologické stanice.

Určete všechny uvedené momenty:
- První až čtvrtý obecný moment.
- První až čtvrtý centrální moment.
- Ověřte správnost výpočtů pomocí Charlierova testu.

---

## 3.2. Normované momenty

Jednotlivé hodnoty statistického znaku jsou vyjádřeny v určitých měrných jednotkách, například v korunách, kilogramech, metrech nebo kusech.

Stejné jednotky mají také odchylky jednotlivých hodnot od aritmetického průměru.

Abychom odstranili závislost na měrných jednotkách, vydělíme odchylku směrodatnou odchylkou. Tím získáme takzvanou **směrodatnou proměnnou**.

Její definice:

$$
u_i=\frac{x_i-\overline{x}}{s_x},
\qquad i=1,2,\ldots,n
\tag{34}
$$

**Vysvětlení symbolů:**
- $u_i$ – normovaná hodnota konkrétního pozorování.
- $x_i$ – původní naměřená hodnota.
- $\overline{x}$ – aritmetický průměr.
- $s_x$ – směrodatná odchylka.
- $n$ – počet pozorování.

**Co vlastně děláme?**

Nejprve zjistíme, o kolik se konkrétní hodnota liší od průměru. Potom tuto odchylku vydělíme směrodatnou odchylkou.

Výsledkem je číslo bez měrné jednotky.

Například:
- $u_i=0$ znamená, že hodnota odpovídá průměru.
- $u_i=1$ znamená, že hodnota leží jednu směrodatnou odchylku nad průměrem.
- $u_i=-2$ znamená, že hodnota leží dvě směrodatné odchylky pod průměrem.

Momenty směrodatné proměnné označujeme jako normované momenty.

**První obecný moment směrodatné proměnné:**

$$
{}_0m_{u,1}=
\frac{1}{n}\sum_{i=1}^{n}u_i
=
\overline{u}
\tag{35}
$$

Po dosazení definice směrodatné proměnné:

$$
{}_0m_{u,1}
=
\frac{1}{ns_x}
\sum_{i=1}^{n}(x_i-\overline{x})=0
\tag{36}
$$

První obecný moment směrodatné proměnné je tedy roven nule.

Z toho vyplývá, že obecné momenty směrodatné proměnné jsou zároveň centrálními momenty této proměnné:

$$
{}_0m_{u,k}
=
\frac{1}{n}\sum_{i=1}^{n}u_i^k
=
\frac{1}{n}\sum_{i=1}^{n}(u_i-\overline{u})^k
=
{}_{\overline{u}}m_{u,k}
\tag{37}
$$

**Druhý normovaný moment:**

$$
\begin{aligned}
{}_0m_{u,2}
&=\frac{1}{n}\sum_{i=1}^{n}u_i^2\\
&=\frac{1}{n}\sum_{i=1}^{n}
\left(\frac{x_i-\overline{x}}{s_x}\right)^2\\
&=\frac{s_x^2}{s_x^2}=1
\end{aligned}
\tag{38}
$$

Druhý normovaný moment je tedy roven jedné. Rozptyl směrodatné proměnné je roven jedné a její směrodatná odchylka je rovněž rovna jedné.

**Třetí normovaný moment:**

$$
\begin{aligned}
m_{u,3}
&=\frac{1}{n}\sum_{i=1}^{n}u_i^3\\
&=\frac{1}{s_x^3}
\left[
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^3
\right]\\
&=\frac{m_{x,3}}{m_{x,2}\sqrt{m_{x,2}}}
\end{aligned}
\tag{39}
$$

Třetí normovaný moment se používá jako míra šikmosti rozdělení.

- Kladná hodnota znamená kladnou šikmost.
- Záporná hodnota znamená zápornou šikmost.
- Nulová hodnota odpovídá nulové třetí normované momentové charakteristice.

**Čtvrtý normovaný moment:**

$$
\begin{aligned}
m_{u,4}
&=\frac{1}{n}\sum_{i=1}^{n}u_i^4\\
&=\frac{1}{s_x^4}
\left[
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^4
\right]\\
&=\frac{m_{x,4}}{(m_{x,2})^2}
\end{aligned}
\tag{40}
$$

Čtvrtý normovaný moment souvisí se špičatostí rozdělení.

**Co je nejdůležitější si zapamatovat?**

| Normovaný moment | Hodnota / význam |
|---|---|
| 1. normovaný moment | Vždy 0 |
| 2. normovaný moment | Vždy 1 |
| 3. normovaný moment | Míra šikmosti |
| 4. normovaný moment | Míra špičatosti |

### 3.2.1. Příklad – domácnosti a počet dětí

Uvažujeme statistický soubor, který sleduje počet dětí v jednotlivých domácnostech.

Pro každou variantu znaku počítáme její četnost a mocniny hodnot.

| Počet dětí ($x_i$) | Četnost ($n_i$) | $x_i^2$ | $x_i^3$ | $x_i^4$ | $(x_i+1)^4$ |
|---|---:|---:|---:|---:|---:|
| 1 | 3 | 1 | 1 | 1 | 16 |
| 2 | 1 | 4 | 8 | 16 | 81 |
| 3 | 1 | 9 | 27 | 81 | 256 |
| 4 | 3 | 16 | 64 | 256 | 625 |
| 5 | 1 | 25 | 125 | 625 | 1296 |

*Poznámka: Tabulka výše slouží pouze k vysvětlení principu. Při výpočtu podle studijního materiálu se používají jeho konkrétní hodnoty a četnosti.*

V původním příkladu jsou vypočteny následující obecné momenty:

$$
{}_0m_{x,1}=\overline{x}=\frac{13}{9}=1{,}44
$$

$$
{}_0m_{x,2}=\frac{27}{9}=3{,}00
$$

$$
{}_0m_{x,3}=\frac{67}{9}=7{,}44
$$

$$
{}_0m_{x,4}=\frac{183}{9}=20{,}33
$$

Následně se pomocí vztahů mezi obecnými a centrálními momenty získají:

$$
m_{x,2}=3{,}00-1{,}44^2=0{,}93
$$

$$
m_{x,3}
=
7{,}44-3\cdot1{,}44\cdot3
+2\cdot1{,}44^3
\approx -0{,}53
$$

$$
\begin{aligned}
m_{x,4}={}&20{,}33-4\cdot1{,}44\cdot7{,}44\\
&+6\cdot1{,}44^2\cdot3
-3\cdot1{,}44^4
\approx1{,}90
\end{aligned}
$$

Normované momenty:

$$
m_{u,3}
=
\frac{-2{,}53}{\sqrt{0{,}93}\sqrt{0{,}93}\sqrt{0{,}93}}
\approx-2{,}83
$$

$$
m_{u,4}=\frac{1{,}90}{0{,}93^2}\approx2{,}20
$$

### 3.2.2. Výpočet momentů u rozdělení četností

Dosud jsme počítali momenty z jednotlivých pozorování. Pokud však máme k dispozici tabulku rozdělení četností, můžeme výpočty zjednodušit.

Uvažujeme jednotlivé varianty znaku $x_i$, které se v souboru vyskytují s absolutními četnostmi $n_i$.

Celkový rozsah souboru získáme součtem absolutních četností:

$$
n=\sum_{i=1}^{k}n_i
$$

**Vysvětlení symbolů:**
- $k$ – počet různých variant statistického znaku.
- $x_i$ – konkrétní varianta statistického znaku.
- $n_i$ – absolutní četnost dané varianty.
- $n$ – celkový počet pozorování.

Místo toho, abychom každou hodnotu vypisovali tolikrát, kolikrát se v souboru vyskytuje, vynásobíme její mocninu příslušnou četností.

První čtyři obecné momenty potom vypočítáme následovně:

**První obecný moment:**

$$
{}_0m_{x,1}
=
\overline{x}
=
\frac{1}{n}\sum_{i=1}^{k}x_i n_i
\tag{41}
$$

**Druhý obecný moment:**

$$
{}_0m_{x,2}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^2 n_i
\tag{42}
$$

**Třetí obecný moment:**

$$
{}_0m_{x,3}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^3 n_i
\tag{43}
$$

**Čtvrtý obecný moment:**

$$
{}_0m_{x,4}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^4 n_i
\tag{44}
$$

**Jak si to představit?**

Pokud se například hodnota 5 vyskytuje desetkrát, nemusíme ji desetkrát zapisovat. Stačí vypočítat její mocninu a výsledek vynásobit četností 10.

Tímto způsobem výrazně zjednodušíme výpočet momentů u větších statistických souborů.

### 3.2.3. Výpočet momentů u intervalového rozdělení četností

Pokud máme data rozdělena do intervalů, nemáme k dispozici přesné jednotlivé hodnoty pozorování. Proto při výpočtu používáme středy intervalů.

Výsledné momenty jsou v tomto případě pouze přibližné.

Pro zjednodušení výpočtu můžeme zavést pomocnou proměnnou:

$$
v_i=\frac{x_i-a}{h},
\qquad i=1,2,\ldots,k
\tag{45}
$$

**Vysvětlení symbolů:**
- $v_i$ – pomocná proměnná, která usnadňuje výpočty.
- $x_i$ – střed příslušného intervalového rozdělení.
- $a$ – libovolně zvolená konstanta, například předběžný průměr.
- $h$ – délka intervalů.
- $k$ – počet intervalů.

**Proč tento postup používáme?**

Středy intervalů mohou být poměrně velká čísla. Pokud bychom s nimi počítali přímo, výpočty by byly zbytečně složité.

Pomocí proměnné $v_i$ hodnoty převedeme na menší čísla, se kterými se lépe pracuje.

Po zavedení pomocné proměnné vypočítáme obecné momenty:

**První obecný moment:**

$$
{}_0m_{v,1}
=
\overline{v}
=
\frac{1}{n}\sum_{i=1}^{k}v_i n_i
\tag{46}
$$

**Druhý obecný moment:**

$$
{}_0m_{v,2}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^2 n_i
\tag{47}
$$

**Třetí obecný moment:**

$$
{}_0m_{v,3}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^3 n_i
\tag{48}
$$

**Čtvrtý obecný moment:**

$$
{}_0m_{v,4}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^4 n_i
\tag{49}
$$

### 3.2.4. Příklad

V příkladu se pracuje s intervalovým rozdělením příjmů. Pro každý interval máme jeho střed, četnost a pomocnou proměnnou $v_i$.

Pomocná proměnná se vypočítá:

$$
v_i=\frac{x_i-15900}{2800}
$$

Například pro první interval se středem 7500:

$$
v_1=\frac{7500-15900}{2800}=-3
$$

Takto postupujeme u všech intervalů.

Získané součty podle původního příkladu:

$$
\sum v_i n_i=-27
$$

$$
\sum v_i^2 n_i=119
$$

$$
\sum v_i^3 n_i=-123
$$

$$
\sum v_i^4 n_i=599
$$

Celkový rozsah souboru:

$$
n=51
$$

Následně vypočítáme obecné momenty pomocné proměnné:

$$
{}_0m_{v,1}=\overline{v}=\frac{-27}{51}\approx-0{,}53
$$

$$
{}_0m_{v,2}=\frac{119}{51}\approx2{,}33
$$

$$
{}_0m_{v,3}=\frac{-123}{51}\approx-2{,}41
$$

$$
{}_0m_{v,4}=\frac{599}{51}\approx11{,}75
$$

Pro kontrolu můžeme použít Charlierův test:

$$
\frac{1}{n}\sum_{i=1}^{n}(v_i+1)^4
=
{}_0m_{v,4}
+4{}_0m_{v,3}
+6{}_0m_{v,2}
+4{}_0m_{v,1}+1
$$

Po dosazení:

$$
14{,}98\approx14{,}97
$$

Výsledky se přibližně shodují, takže kontrola vychází.

Následně vypočítáme centrální momenty pomocné proměnné:

$$
m_{v,2}
=
2{,}33-(-0{,}53)^2
\approx2{,}05
$$

$$
\begin{aligned}
m_{v,3}={}&-2{,}41
-3(-0{,}53)\cdot2{,}33\\
&+2(-0{,}53)^3
\approx-0{,}22
\end{aligned}
$$

$$
\begin{aligned}
m_{v,4}={}&11{,}75
-4(-0{,}53)(-2{,}41)\\
&+6(-0{,}53)^2\cdot2{,}33
-3(-0{,}53)^4\\
&\approx10{,}33
\end{aligned}
$$

**Převod zpět na původní proměnnou:**

Protože jsme původní hodnoty převedli pomocí vztahu $v_i=(x_i-a)/h$, musíme při interpretaci výsledků přejít zpět k původním jednotkám.

Aritmetický průměr:

$$
\overline{x}=2800\cdot(-0{,}53)+15900
\approx14416
$$

Rozptyl:

$$
s_x^2=2800^2\cdot2{,}05
=16072000
$$

Třetí normovaný moment:

$$
m_{u,3}\approx0{,}34
$$

Čtvrtý normovaný moment:

$$
m_{u,4}\approx2{,}46
$$

*Poznámka: Při ručním přepisu čísel je nutné počítat s tím, že zaokrouhlení mezivýsledků může ovlivnit konečné hodnoty.*

### 3.2.5. Vztahy mezi charakteristikami polohy

Charakteristiky polohy nám pomáhají určit, kde se hodnoty statistického souboru soustřeďují.

Mezi nejdůležitější patří:
- **Aritmetický průměr** $\overline{x}$ – součet všech hodnot vydělený jejich počtem.
- **Medián** $\widetilde{x}$ – prostřední hodnota uspořádaného souboru.
- **Modus** $\hat{x}$ – nejčastěji se vyskytující hodnota.

V symetrickém rozdělení jsou všechny tři charakteristiky stejné:

$$
\overline{x}=\widetilde{x}=\hat{x}
$$

Čím více se rozdělení četností blíží symetrickému rozdělení, tím méně se tyto charakteristiky od sebe odlišují.

### 3.2.6. Vztahy mezi charakteristikami průměrné polohy

U asymetrického rozdělení se aritmetický průměr, medián a modus mohou nacházet na různých místech.

**Záporně zešikmené rozdělení:**

$$
\overline{x}<\widetilde{x}<\hat{x}
\tag{50}
$$

**Kladně zešikmené rozdělení:**

$$
\hat{x}<\widetilde{x}<\overline{x}
\tag{51}
$$

**Jak si to představit?**

- U záporné šikmosti je delší ocas rozdělení vlevo a aritmetický průměr je posunut směrem doleva.
- U kladné šikmosti je delší ocas rozdělení vpravo a aritmetický průměr je posunut směrem doprava.

Pokud rozdělení není příliš asymetrické, platí přibližný vztah:

$$
\overline{x}-\hat{x}
\approx
3(\overline{x}-\widetilde{x})
\tag{52}
$$

Tento vztah vyjadřuje přibližnou závislost mezi modem, mediánem a aritmetickým průměrem u mírně asymetrického rozdělení.

### 3.2.7. Míry variability

Dosud jsme se zabývali především charakteristikami polohy, které nám říkají, kde se hodnoty statistického znaku nacházejí.

Samotná poloha ale nestačí k porovnání dvou statistických souborů.

Dva soubory mohou mít naprosto stejný aritmetický průměr, ale jejich jednotlivé hodnoty mohou být rozloženy velmi odlišně.

Proto potřebujeme také **míry variability**, které vyjadřují, jak moc se jednotlivé hodnoty od sebe navzájem a od charakteristik polohy liší.

Například:
- Soubor A: 9, 10, 11.
- Soubor B: 1, 10, 19.

Oba soubory mají aritmetický průměr 10, ale jejich hodnoty jsou rozptýleny jinak.

Právě tento rozdíl zachycují míry variability.

### 3.2.8. Kvantilové míry variability

Kvantilové míry variability vycházejí z kvantilů a popisují rozptýlení hodnot statistického souboru.

**1. Rozpětí**

Rozpětí představuje rozdíl mezi největší a nejmenší hodnotou souboru.

$$
R_x=x_{\max}-x_{\min}
\tag{53}
$$

Kde:
- $x_{\max}$ – největší hodnota v souboru.
- $x_{\min}$ – nejmenší hodnota v souboru.

Čím větší rozpětí, tím větší je vzdálenost mezi krajními hodnotami.

**2. Kvartilové rozpětí**

Kvartilové rozpětí představuje rozdíl mezi horním a dolním kvartilem.

$$
R_Q=\widetilde{x}_{75}-\widetilde{x}_{25}
\tag{54}
$$

Vyjadřuje rozpětí prostředních 50 % hodnot souboru.

**3. Decilové rozpětí**

$$
\widetilde{x}_{90}-\widetilde{x}_{10}
\tag{55}
$$

Vyjadřuje rozpětí prostředních 80 % hodnot souboru.

**4. Percentilové rozpětí**

$$
\widetilde{x}_{99}-\widetilde{x}_{1}
\tag{56}
$$

Vyjadřuje rozpětí prostředních 98 % hodnot souboru.

**5. Kvartilová odchylka**

$$
Q=
\frac{
(\widetilde{x}_{75}-\widetilde{x})
+
(\widetilde{x}-\widetilde{x}_{25})
}{2}
=
\frac{\widetilde{x}_{75}-\widetilde{x}_{25}}{2}
\tag{57}
$$

Kvartilová odchylka představuje polovinu kvartilového rozpětí.

**6. Decilová odchylka**

$$
\frac{
(\widetilde{x}_{90}-\widetilde{x}_{80})
+
(\widetilde{x}_{80}-\widetilde{x}_{70})
+\cdots+
(\widetilde{x}_{20}-\widetilde{x}_{10})
}{8}
=
\frac{\widetilde{x}_{90}-\widetilde{x}_{10}}{8}
\tag{58}
$$

Decilová odchylka představuje průměrnou šířku jednotlivých osmi desetiprocentních úseků mezi prvním a devátým decilem.

**7. Percentilová odchylka**

$$
\frac{\widetilde{x}_{99}-\widetilde{x}_{1}}{98}
\tag{59}
$$

Percentilová odchylka představuje průměrnou šířku jednotlivých percentilových úseků mezi prvním a devadesátým devátým percentilem.

**8. Momentové míry variability**

Mezi momentové míry variability patří zejména rozptyl, který byl definován jako druhý centrální moment.

V praxi se používá také odhad rozptylu $s^2$, který je definován ve vztahu (2) studijního materiálu.

**9. Momentová míra relativní variability**

$$
c_x=\frac{s_x}{\overline{x}}
\tag{60}
$$

Jedná se o variační koeficient, který vyjadřuje relativní variabilitu sledovaného statistického znaku.

Kde:
- $s_x$ – směrodatná odchylka.
- $\overline{x}$ – aritmetický průměr.

Variační koeficient nám umožňuje porovnávat variabilitu různých souborů, i když mají odlišné měrné jednotky nebo úroveň hodnot.

**10. Výpočet celkového rozptylu z dílčích rozptylů**

Při spojení dílčích skupin můžeme celkový rozptyl vyjádřit pomocí rozptylů jednotlivých skupin a jejich četností.

$$
s_x^2=
\frac{
\sum_{i=1}^{k}s_i^2n_i
}{
\sum_{i=1}^{k}n_i
}
$$

Kde:
- $s_i^2$ – rozptyl i-té skupiny.
- $n_i$ – počet pozorování v i-té skupině.
- $k$ – počet skupin.

Výpočet představuje vážený průměr dílčích rozptylů. Je však třeba rozlišovat tento vztah od úplného rozptylu sloučeného souboru, který musí zohledňovat také rozdíly mezi průměry jednotlivých skupin.

### 3.2.9. Míry šikmosti

Šikmost popisuje, zda je rozdělení hodnot statistického souboru symetrické, nebo zda je vychýlené na jednu stranu.

Rozlišujeme:
- **Symetrické rozdělení** – hodnoty jsou rozloženy přibližně stejně na obě strany od středu.
- **Kladně zešikmené rozdělení** – delší ocas rozdělení směřuje doprava.
- **Záporně zešikmené rozdělení** – delší ocas rozdělení směřuje doleva.

**1. Kvantilová šikmost**

$$
\tau=
\frac{
(x_{\max}-\widetilde{x})
-
(\widetilde{x}-x_{\min})
}{
(x_{\max}-\widetilde{x})
+
(\widetilde{x}-x_{\min})
}
=
\frac{x_{\max}+x_{\min}-2\widetilde{x}}
{x_{\max}-x_{\min}}
\tag{61}
$$

Kde:
- $x_{\max}$ – největší hodnota.
- $x_{\min}$ – nejmenší hodnota.
- $\widetilde{x}$ – medián.

Pokud je rozdělení symetrické, kvantilová šikmost je rovna nule.

**Interpretace:**
- $\tau=0$ – symetrické rozdělení.
- $\tau>0$ – kladná šikmost.
- $\tau<0$ – záporná šikmost.

**2. Percentilová šikmost**

$$
\tau_i=
\frac{
(\widetilde{x}_{100-i}-\widetilde{x})
-
(\widetilde{x}-\widetilde{x}_i)
}{
(\widetilde{x}_{100-i}-\widetilde{x})
+
(\widetilde{x}-\widetilde{x}_i)
}
$$

Po úpravě:

$$
\tau_i=
\frac{
\widetilde{x}_{100-i}
+
\widetilde{x}_i
-
2\widetilde{x}
}{
\widetilde{x}_{100-i}
-
\widetilde{x}_i
}
\tag{62}
$$

Tato míra využívá percentily a medián k určení asymetrie rozdělení.

**3. Výběrová šikmost**

$$
A_3=
\frac{m_{x,3}}{\sqrt{m_{x,2}^{3}}}
=
\frac{
\sum_{i=1}^{k}(x_i-\overline{x})^3n_i
}{
(ns_x^2)^{3/2}
}
\tag{63}
$$

Výběrová šikmost vychází ze třetího centrálního momentu a rozptylu.

- Kladná hodnota znamená kladnou šikmost.
- Záporná hodnota znamená zápornou šikmost.
- Nulová hodnota znamená nulovou momentovou šikmost.

**4. Pearsonova míra šikmosti**

$$
\tau'=\frac{\overline{x}-\hat{x}}{s_x}
\tag{64}
$$

Kde:
- $\overline{x}$ – aritmetický průměr.
- $\hat{x}$ – modus.
- $s_x$ – směrodatná odchylka.

Pearsonova míra šikmosti porovnává rozdíl mezi aritmetickým průměrem a modem vzhledem ke směrodatné odchylce.

**5. Jednoduchá míra šikmosti**

$$
\tau''=\frac{n'-n''}{n}
\tag{65}
$$

Kde:
- $n'$ – počet hodnot menších než aritmetický průměr.
- $n''$ – počet hodnot větších než aritmetický průměr.
- $n$ – celkový počet pozorování.

Tato charakteristika porovnává počty hodnot, které leží pod a nad aritmetickým průměrem.

### 3.2.10. Míry špičatosti

Špičatost popisuje tvar rozdělení a koncentraci hodnot kolem jeho středu.

Pomocí měr špičatosti můžeme porovnávat, jak jsou hodnoty soustředěny kolem středu a jak široké jsou krajní části rozdělení.

**1. Kvantilová špičatost**

První kvantilová míra špičatosti:

$$
K=
\frac{x_{\max}-x_{\min}}
{\widetilde{x}_{75}-\widetilde{x}_{25}}
\tag{66}
$$

Porovnává celkové rozpětí souboru s kvartilovým rozpětím.

Druhá kvantilová míra špičatosti:

$$
K'=
\frac{
\widetilde{x}_{99.5}-\widetilde{x}_{0.5}
}{
\widetilde{x}_{75}-\widetilde{x}_{25}
}
\tag{67}
$$

Třetí kvantilová míra špičatosti:

$$
K''=
\frac{
\widetilde{x}_{99}-\widetilde{x}_{1}
}{
\widetilde{x}_{75}-\widetilde{x}_{25}
}
\tag{68}
$$

Všechny tři charakteristiky porovnávají šířku krajních částí rozdělení s kvartilovým rozpětím.

**2. Výběrová špičatost**

$$
A_4=
\frac{m_{x,4}}{m_{x,2}^2}
=
\frac{
\sum_{i=1}^{k}(x_i-\overline{x})^4n_i
}{
ns_x^4
}
\tag{69}
$$

Kde:
- $m_{x,4}$ – čtvrtý centrální moment.
- $m_{x,2}$ – druhý centrální moment, tedy rozptyl.
- $x_i$ – jednotlivá hodnota statistického znaku.
- $\overline{x}$ – aritmetický průměr.
- $n_i$ – četnost jednotlivých hodnot.
- $n$ – celkový počet pozorování.
- $s_x$ – směrodatná odchylka.

Výběrová špičatost vychází ze čtvrtého normovaného momentu.

Čím vyšší je hodnota čtvrtého normovaného momentu, tím větší je relativní význam čtvrtých mocnin odchylek od průměru.

### 3.2.11. Empirická distribuční funkce

Empirická neboli výběrová distribuční funkce popisuje, jaká část pozorovaných hodnot statistického souboru je menší nebo rovna určité hodnotě $x$.

Označujeme ji:

$$
F_n(x)
$$

Uvažujme uspořádaný statistický soubor:

$$
X_{(1)},X_{(2)},\ldots,X_{(n-1)},X_{(n)}
$$

Hodnoty jsou seřazeny vzestupně, tedy od nejmenší po největší.

Empirickou distribuční funkci definujeme:

$$
F_n(x)=
\begin{cases}
0, & x<X_{(1)}\\
\frac{n_i}{n}, & X_{(i)}\leq x<X_{(i+1)}\\
1, & x\geq X_{(n)}
\end{cases}
$$

**Vysvětlení symbolů:**
- $F_n(x)$ – empirická distribuční funkce.
- $x$ – hodnota, pro kterou zjišťujeme distribuční funkci.
- $n_i$ – počet pozorování menších nebo rovných hodnotě $x$.
- $n$ – celkový počet pozorování.
- $X_{(i)}$ – i-tá hodnota v seřazeném souboru.

**Jak funkce funguje?**

1. Pokud je hodnota $x$ menší než nejmenší pozorování, distribuční funkce je rovna nule.
2. Pokud se nacházíme mezi dvěma pozorovanými hodnotami, funkce udává relativní četnost dosavadních pozorování.
3. Pokud je hodnota $x$ větší nebo rovna největšímu pozorování, distribuční funkce je rovna jedné.

Empirická distribuční funkce je tedy neklesající schodovitá funkce, která začíná na hodnotě nula a postupně dosahuje hodnoty jedna.

**Příklad – ověření rovnoměrného rozdělení**

Uvažujme prvních deset čísel získaných z generátoru náhodných čísel:

$$
0{,}93,\ 0{,}35,\ 0{,}66,\ 0{,}93,\ 0{,}14,
$$

$$
0{,}23,\ 0{,}08,\ 0{,}23,\ 0{,}21,\ 0{,}59
$$

Nejprve čísla uspořádáme vzestupně:

$$
0{,}08,\ 0{,}14,\ 0{,}21,\ 0{,}23,\ 0{,}23,
$$

$$
0{,}35,\ 0{,}59,\ 0{,}66,\ 0{,}93,\ 0{,}93
$$

Následně vytvoříme empirickou distribuční funkci.

| Interval hodnot $x$ | $F_n(x)$ |
|---|---:|
| $x<0{,}08$ | 0 |
| $0{,}08\leq x<0{,}14$ | 0,1 |
| $0{,}14\leq x<0{,}21$ | 0,2 |
| $0{,}21\leq x<0{,}23$ | 0,3 |
| $0{,}23\leq x<0{,}35$ | 0,5 |
| $0{,}35\leq x<0{,}59$ | 0,6 |
| $0{,}59\leq x<0{,}66$ | 0,7 |
| $0{,}66\leq x<0{,}93$ | 0,8 |
| $x\geq0{,}93$ | 1 |

Všimni si, že hodnota 0,23 se vyskytuje dvakrát, proto empirická distribuční funkce přeskočí z hodnoty 0,3 na 0,5.

**Rovnoměrné rozdělení na intervalu (0, 1)**

Pro porovnání empirické distribuční funkce použijeme distribuční funkci rovnoměrného rozdělení:

$$
F_0(x)=
\begin{cases}
0, & x<0\\
x, & 0\leq x<1\\
1, & x\geq1
\end{cases}
$$

U rovnoměrného rozdělení na intervalu od nuly do jedné platí, že distribuční funkce uvnitř tohoto intervalu odpovídá přímo hodnotě $x$.

Porovnáním empirické distribuční funkce $F_n(x)$ s teoretickou distribuční funkcí $F_0(x)$ můžeme posoudit, nakolik pozorovaná data odpovídají rovnoměrnému rozdělení.
