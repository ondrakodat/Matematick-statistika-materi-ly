# 3. Popisná statistika

Popisná statistika se zabývá metodami, pomocí kterých dokážeme charakterizovat vlastnosti statistického souboru. V této kapitole se zaměříme především na **momenty, normované momenty, míry variability, šikmosti a špičatosti a empirickou distribuční funkci**.

Zatímco kvantily představují konkrétní hodnoty statistického znaku, momenty jsou funkcemi všech hodnot daného znaku v souboru. Díky tomu nám poskytují souhrnnou informaci o vlastnostech celého statistického rozdělení.

---

## 3.1. Momenty

**Moment** je statistická charakteristika, která se vypočítává ze všech hodnot sledovaného statistického znaku.

Mějme jednorozměrný statistický soubor o rozsahu \(n\). Jednotlivé hodnoty statistického znaku označíme:

$$
x_1,x_2,\ldots,x_n
$$

K-tý moment kvantitativního statistického znaku obecně definujeme vztahem:

$$
\boxed{
{}_a m_{x,k} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-a)^k
}
\tag{21}
$$

Kde:

- \(x_i\) – jednotlivá pozorování statistického znaku.
- \(n\) – počet všech pozorování.
- \(a\) – konstanta, kolem které moment počítáme.
- \(k\) – stupeň momentu, tedy přirozené číslo.
- \({}_a m_{x,k}\) – k-tý moment znaku \(x\) kolem hodnoty \(a\).

Podle toho, jakou hodnotu zvolíme za konstantu \(a\), rozlišujeme obecné a centrální momenty.

### 3.1.1. Obecné momenty

Pokud za konstantu \(a\) dosadíme nulu, získáme moment kolem počátku, který nazýváme **obecný moment**.

$$
\boxed{
{}_0 m_{x,k} =
\frac{1}{n}\sum_{i=1}^{n}x_i^k
}
\tag{22}
$$

Nejpoužívanější je první obecný moment, který představuje aritmetický průměr.

**První obecný moment:**

$$
\boxed{
{}_0 m_{x,1} =
\frac{1}{n}\sum_{i=1}^{n}x_i
=
\overline{x}
}
\tag{23}
$$

**Druhý obecný moment:**

$$
{}_0 m_{x,2} =
\frac{1}{n}\sum_{i=1}^{n}x_i^2
\tag{24}
$$

**Třetí obecný moment:**

$$
{}_0 m_{x,3} =
\frac{1}{n}\sum_{i=1}^{n}x_i^3
\tag{25}
$$

**Čtvrtý obecný moment:**

$$
{}_0 m_{x,4} =
\frac{1}{n}\sum_{i=1}^{n}x_i^4
\tag{26}
$$

Obecně tedy platí, že u k-tého obecného momentu umocňujeme každou hodnotu statistického znaku na k-tou a následně vypočítáme jejich aritmetický průměr.

### 3.1.2. Centrální momenty

Pokud za konstantu \(a\) dosadíme aritmetický průměr, získáme **centrální momenty**.

Centrální momenty tedy sledují odchylky jednotlivých hodnot od aritmetického průměru.

Obecný vzorec:

$$
\boxed{
{}_x m_{x,k} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^k
}
\tag{27}
$$

Nejdůležitější jsou první čtyři centrální momenty.

**První centrální moment:**

$$
{}_x m_{x,1} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})=0
$$

První centrální moment je vždy roven nule, protože součet odchylek jednotlivých hodnot od aritmetického průměru je nulový.

**Druhý centrální moment – rozptyl:**

$$
\boxed{
{}_x m_{x,2} =
\frac{1}{n}\sum_{i=1}^{n}(x_i-\overline{x})^2
=
s_x^2
}
\tag{28}
$$

Druhý centrální moment představuje rozptyl. Vyjadřuje, jak moc jsou jednotlivé hodnoty rozptýlené kolem aritmetického průměru.

Druhý centrální moment můžeme také vyjádřit pomocí prvních dvou obecných momentů:

$$
\boxed{
{}_x m_{x,2}
=
{}_0 m_{x,2}
-
({}_0 m_{x,1})^2
}
\tag{29}
$$

Jinými slovy: rozptyl získáme jako druhý obecný moment zmenšený o druhou mocninu aritmetického průměru.

**Třetí centrální moment:**

$$
\boxed{
{}_x m_{x,3}
=
{}_0 m_{x,3}
-
3\,{}_0 m_{x,1}\cdot{}_0 m_{x,2}
+
2({}_0 m_{x,1})^3
}
\tag{31}
$$

Třetí centrální moment souvisí s asymetrií statistického rozdělení. Jeho znaménko nám pomáhá určit směr šikmosti.

**Čtvrtý centrální moment:**

$$
\boxed{
{}_x m_{x,4}
=
{}_0 m_{x,4}
-
4\,{}_0 m_{x,1}\cdot{}_0 m_{x,3}
+
6({}_0 m_{x,1})^2\cdot{}_0 m_{x,2}
-
3({}_0 m_{x,1})^4
}
\tag{32}
$$

Čtvrtý centrální moment se využívá při konstrukci míry špičatosti statistického rozdělení.

**Shrnutí centrálních momentů:**

| Moment | Význam |
|---|---|
| První centrální moment | Vždy roven nule. |
| Druhý centrální moment | Rozptyl – variabilita hodnot. |
| Třetí centrální moment | Souvisí se šikmostí. |
| Čtvrtý centrální moment | Souvisí se špičatostí. |

### 3.1.3. Charlierův test

Při ručních výpočtech momentů může docházet k početním chybám. Proto se používá **Charlierův test**, který slouží ke kontrole správnosti vypočítaných obecných momentů.

Je založen na binomickém rozvoji čtvrté mocniny výrazu:

$$
(x_i+1)^4
=
x_i^4+4x_i^3+6x_i^2+4x_i+1
$$

Po sečtení všech hodnot a vydělení počtem pozorování získáme vztah:

$$
\boxed{
\frac{1}{n}\sum_{i=1}^{n}(x_i+1)^4
=
{}_0m_{x,4}
+
4\,{}_0m_{x,3}
+
6\,{}_0m_{x,2}
+
4\,{}_0m_{x,1}
+
1
}
\tag{33}
$$

**Jak test funguje?**

1. Vypočítáme levou stranu vztahu, tedy průměr čtvrtých mocnin hodnot \(x_i+1\).
2. Vypočítáme pravou stranu pomocí již získaných obecných momentů.
3. Obě strany porovnáme.

Pokud se výsledky přibližně rovnají, výpočet je pravděpodobně správný. Menší rozdíl může vzniknout zaokrouhlováním.

### 3.1.4. Úloha

Zvolíme vlastní statistická data, například:

- Teplotní řadu z meteorologické stanice.
- Hodnoty znečištění ovzduší.
- Denní množství srážek.

Na vybraném souboru následně vypočítáme všechny uvedené momenty a ověříme jejich správnost pomocí Charlierova testu.

---

## 3.2. Normované momenty

Jednotlivé hodnoty statistického znaku jsou vždy vyjádřeny v určitých měrných jednotkách, například v korunách, kilogramech, metrech nebo kusech.

Stejné měrné jednotky mají také odchylky jednotlivých hodnot od aritmetického průměru.

Abychom odstranili závislost na měrných jednotkách, vydělíme odchylku od průměru směrodatnou odchylkou. Tím získáme tzv. **směrodatnou proměnnou**.

### Směrodatná proměnná

$$
\boxed{
u_i =
\frac{x_i-\overline{x}}{s_x}
}
\tag{34}
$$

Kde:

- \(u_i\) – hodnota směrodatné proměnné.
- \(x_i\) – původní hodnota statistického znaku.
- \(\overline{x}\) – aritmetický průměr.
- \(s_x\) – směrodatná odchylka.

Hodnoty směrodatné proměnné jsou bezrozměrná čísla, protože při dělení se odstraní původní měrné jednotky.

### První obecný moment směrodatné proměnné

První obecný moment směrodatné proměnné je její aritmetický průměr:

$$
{}_0m_{u,1}
=
\frac{1}{n}\sum_{i=1}^{n}u_i
=
\overline{u}
$$

Po dosazení definice směrodatné proměnné:

$$
{}_0m_{u,1}
=
\frac{1}{ns_x}
\sum_{i=1}^{n}(x_i-\overline{x})
$$

Protože součet odchylek od aritmetického průměru je nulový, dostáváme:

$$
\boxed{
{}_0m_{u,1}=0
}
\tag{35–36}
$$

První obecný moment směrodatné proměnné je tedy vždy roven nule.

Z toho vyplývá, že obecné momenty směrodatné proměnné jsou zároveň jejími centrálními momenty:

$$
\boxed{
{}_0m_{u,k}
=
{}_u m_{u,k}
}
$$

### Druhý moment směrodatné proměnné

Druhý moment směrodatné proměnné je roven jejímu rozptylu.

$$
{}_0m_{u,2}
=
\frac{1}{n}\sum_{i=1}^{n}u_i^2
$$

Po dosazení:

$$
{}_0m_{u,2}
=
\frac{1}{n}\sum_{i=1}^{n}
\left(
\frac{x_i-\overline{x}}{s_x}
\right)^2
$$

$$
{}_0m_{u,2}
=
\frac{1}{s_x^2}
\cdot
\frac{1}{n}
\sum_{i=1}^{n}(x_i-\overline{x})^2
$$

Protože druhý centrální moment původní proměnné je roven rozptylu \(s_x^2\), dostáváme:

$$
\boxed{
{}_0m_{u,2}=s_u^2=1
}
\tag{37–38}
$$

Rozptyl směrodatné proměnné je tedy vždy roven jedné. Její směrodatná odchylka je rovněž rovna jedné.

### Třetí normovaný moment

Třetí normovaný moment můžeme vyjádřit pomocí třetího a druhého centrálního momentu původní proměnné:

$$
\boxed{
m_{u,3}
=
\frac{{}_x m_{x,3}}{({}_x m_{x,2})^{3/2}}
}
\tag{39}
$$

Tento moment se používá k vyjádření šikmosti statistického rozdělení.

### Čtvrtý normovaný moment

Čtvrtý normovaný moment vypočítáme pomocí čtvrtého centrálního momentu a druhé mocniny rozptylu:

$$
\boxed{
m_{u,4}
=
\frac{{}_x m_{x,4}}{({}_x m_{x,2})^2}
}
\tag{40}
$$

Tento moment se používá k vyjádření špičatosti statistického rozdělení.

**Shrnutí normovaných momentů:**

| Moment | Vlastnost |
|---|---|
| První normovaný moment | Vždy roven 0. |
| Druhý normovaný moment | Vždy roven 1. |
| Třetí normovaný moment | Vyjadřuje šikmost. |
| Čtvrtý normovaný moment | Vyjadřuje špičatost. |

---

### 3.2.1. Příklad – domácnosti a počet dětí

V tomto příkladu sledujeme počet dětí v jednotlivých domácnostech.

Pro výpočet momentů vytvoříme tabulku, která obsahuje jednotlivé hodnoty znaku a jejich mocniny.

| Počet dětí \(x_i\) | Četnost \(n_i\) | \(x_i^2\) | \(x_i^3\) | \(x_i^4\) | \((x_i+1)^4\) |
|---:|---:|---:|---:|---:|---:|
| 3 | 3 | 9 | 27 | 81 | 256 |
| 2 | 1 | 4 | 8 | 16 | 81 |
| 1 | 1 | 1 | 1 | 1 | 16 |
| 3 | 3 | 9 | 27 | 81 | 256 |
| 1 | 1 | 1 | 1 | 1 | 16 |
| 1 | 1 | 1 | 1 | 1 | 16 |
| 2 | 2 | 4 | 8 | 16 | 81 |
| 1 | 1 | 1 | 1 | 1 | 16 |
| 0 | 1 | 0 | 0 | 0 | 1 |
| **Součet** | **14** | **30** | **75** | **198** | **739** |

*Poznámka: V původním studijním materiálu je tabulka zapsána jako přehled variant a četností. Pro výpočet momentů je podstatné násobit mocniny hodnot jejich četnostmi.*

V uvedeném příkladu se podle původních výpočtů pracuje s devíti pozorováními a součty:

$$
\sum x_i=13,\qquad
\sum x_i^2=27
$$

$$
\sum x_i^3=67,\qquad
\sum x_i^4=183
$$

**První obecný moment:**

$$
{}_0m_{x,1}
=
\frac{13}{9}
\approx 1{,}44
$$

**Druhý obecný moment:**

$$
{}_0m_{x,2}
=
\frac{27}{9}
=
3
$$

**Třetí obecný moment:**

$$
{}_0m_{x,3}
=
\frac{67}{9}
\approx 7{,}44
$$

**Čtvrtý obecný moment:**

$$
{}_0m_{x,4}
=
\frac{183}{9}
\approx 20{,}33
$$

Nyní vypočítáme centrální momenty.

**Druhý centrální moment:**

$$
{}_x m_{x,2}
=
3-1{,}44^2
$$

$$
\boxed{{}_x m_{x,2}\approx 0{,}93}
$$

**Třetí centrální moment:**

$$
{}_x m_{x,3}
=
7{,}44
-
3\cdot1{,}44\cdot3
+
2\cdot1{,}44^3
$$

$$
\boxed{{}_x m_{x,3}\approx -0{,}53}
$$

**Čtvrtý centrální moment:**

$$
{}_x m_{x,4}
=
20{,}33
-
4\cdot1{,}44\cdot7{,}44
+
6\cdot1{,}44^2\cdot3
-
3\cdot1{,}44^4
$$

$$
\boxed{{}_x m_{x,4}\approx 1{,}90}
$$

Následně vypočítáme třetí a čtvrtý normovaný moment.

**Třetí normovaný moment:**

$$
m_{u,3}
=
\frac{-0{,}53}{0{,}93\sqrt{0{,}93}}
$$

$$
\boxed{m_{u,3}\approx -0{,}59}
$$

**Čtvrtý normovaný moment:**

$$
m_{u,4}
=
\frac{1{,}90}{0{,}93^2}
$$

$$
\boxed{m_{u,4}\approx 2{,}20}
$$

**Důležité:** Při práci s momenty je nutné důsledně rozlišovat obecné, centrální a normované momenty. Každý z nich má jiný účel a používá se v jiné fázi výpočtu.

---

### 3.2.2. Výpočet momentů u rozdělení četností

Pokud máme statistický soubor ve formě tabulky četností, nemusíme každé pozorování vypisovat samostatně.

Uvažujeme jednotlivé varianty znaku:

$$
x_1,x_2,\ldots,x_k
$$

a jejich absolutní četnosti:

$$
n_1,n_2,\ldots,n_k
$$

Celkový rozsah souboru získáme jako součet všech absolutních četností:

$$
\boxed{
n=\sum_{i=1}^{k}n_i
}
$$

Při výpočtu momentů tedy každou mocninu hodnoty znaku násobíme její četností.

**První obecný moment:**

$$
\boxed{
{}_0m_{x,1}
=
\overline{x}
=
\frac{1}{n}\sum_{i=1}^{k}x_i n_i
}
\tag{41}
$$

**Druhý obecný moment:**

$$
\boxed{
{}_0m_{x,2}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^2n_i
}
\tag{42}
$$

**Třetí obecný moment:**

$$
\boxed{
{}_0m_{x,3}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^3n_i
}
\tag{43}
$$

**Čtvrtý obecný moment:**

$$
\boxed{
{}_0m_{x,4}
=
\frac{1}{n}\sum_{i=1}^{k}x_i^4n_i
}
\tag{44}
$$

Kde:

- \(k\) – počet různých variant znaku.
- \(x_i\) – hodnota dané varianty.
- \(n_i\) – absolutní četnost dané varianty.
- \(n\) – celkový počet pozorování.

**Hlavní princip:** Pokud se určitá hodnota vyskytuje například desetkrát, její příspěvek do součtu momentu započítáme desetkrát. Proto ji jednoduše násobíme její četností.

---

### 3.2.3. Výpočet momentů u intervalového rozdělení četností

Při výpočtu momentů z intervalového rozdělení četností používáme středy jednotlivých intervalů místo původních hodnot.

Výsledky jsou proto pouze přibližné, protože přesné hodnoty uvnitř jednotlivých intervalů již neznáme.

Při výpočtu postupujeme podobně jako u běžného rozdělení četností:

- Středy intervalů představují jednotlivé hodnoty znaku.
- Třídní četnosti představují jejich četnosti.

Protože středy intervalů mohou být poměrně velká čísla, zavádíme pomocnou proměnnou \(v_i\), která výpočet zjednodušuje.

### Pomocná proměnná

$$
\boxed{
v_i=\frac{x_i-a}{h}
}
\tag{45}
$$

Kde:

- \(v_i\) – pomocná proměnná.
- \(x_i\) – střed příslušného intervalu.
- \(a\) – vhodně zvolený počátek, například předběžný průměr.
- \(h\) – délka intervalu.

Hodnotu \(a\) vybíráme tak, aby výsledné hodnoty \(v_i\) byly co nejjednodušší.

Po zavedení pomocné proměnné počítáme momenty následujícím způsobem.

**První obecný moment:**

$$
\boxed{
{}_0m_{v,1}
=
\overline{v}
=
\frac{1}{n}\sum_{i=1}^{k}v_i n_i
}
\tag{46}
$$

**Druhý obecný moment:**

$$
\boxed{
{}_0m_{v,2}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^2 n_i
}
\tag{47}
$$

**Třetí obecný moment:**

$$
\boxed{
{}_0m_{v,3}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^3 n_i
}
\tag{48}
$$

**Čtvrtý obecný moment:**

$$
\boxed{
{}_0m_{v,4}
=
\frac{1}{n}\sum_{i=1}^{k}v_i^4 n_i
}
\tag{49}
$$

Po výpočtu momentů pomocné proměnné můžeme získat výsledné charakteristiky původního znaku.

**Aritmetický průměr:**

$$
\boxed{
\overline{x}=a+h\overline{v}
}
$$

**Rozptyl:**

$$
\boxed{
s_x^2=h^2s_v^2
}
$$

**Třetí normovaný moment:**

$$
\boxed{
m_{u,3}=
\frac{{}_v m_{v,3}}{({}_v m_{v,2})^{3/2}}
}
$$

**Čtvrtý normovaný moment:**

$$
\boxed{
m_{u,4}=
\frac{{}_v m_{v,4}}{({}_v m_{v,2})^2}
}
$$

---

### 3.2.4. Příklad výpočtu momentů u intervalového rozdělení

V příkladu použijeme intervalové rozdělení příjmů z předchozí kapitoly.

Délka intervalu je:

$$
h=2800
$$

Jako počátek zvolíme:

$$
a=15900
$$

Pomocnou proměnnou vypočítáme:

$$
v_i=\frac{x_i-15900}{2800}
$$

Pro středy intervalů získáme hodnoty:

| Střed intervalu \(x_i\) | Četnost \(n_i\) | Pomocná proměnná \(v_i\) |
|---:|---:|---:|
| 7 500 | 3 | -3 |
| 10 300 | 12 | -2 |
| 13 100 | 12 | -1 |
| 15 900 | 12 | 0 |
| 18 700 | 7 | 1 |
| 21 500 | 4 | 2 |
| 24 300 | 1 | 3 |
| **Celkem** | **51** | — |

Pro výpočet jednotlivých momentů doplníme mocniny pomocné proměnné vynásobené četnostmi.

| \(v_i\) | \(n_i\) | \(v_i n_i\) | \(v_i^2n_i\) | \(v_i^3n_i\) | \(v_i^4n_i\) |
|---:|---:|---:|---:|---:|---:|
| -3 | 3 | -9 | 27 | -81 | 243 |
| -2 | 12 | -24 | 48 | -96 | 192 |
| -1 | 12 | -12 | 12 | -12 | 12 |
| 0 | 12 | 0 | 0 | 0 | 0 |
| 1 | 7 | 7 | 7 | 7 | 7 |
| 2 | 4 | 8 | 16 | 32 | 64 |
| 3 | 1 | 3 | 9 | 27 | 81 |
| **Součet** | **51** | **-27** | **119** | **-123** | **599** |

Získáme následující obecné momenty pomocné proměnné.

**První obecný moment:**

$$
{}_0m_{v,1}
=
\frac{-27}{51}
$$

$$
\boxed{\overline{v}\approx -0{,}53}
$$

**Druhý obecný moment:**

$$
{}_0m_{v,2}
=
\frac{119}{51}
$$

$$
\boxed{{}_0m_{v,2}\approx 2{,}33}
$$

**Třetí obecný moment:**

$$
{}_0m_{v,3}
=
\frac{-123}{51}
$$

$$
\boxed{{}_0m_{v,3}\approx -2{,}41}
$$

**Čtvrtý obecný moment:**

$$
{}_0m_{v,4}
=
\frac{599}{51}
$$

$$
\boxed{{}_0m_{v,4}\approx 11{,}75}
$$

Následně vypočítáme centrální momenty pomocné proměnné.

**Rozptyl pomocné proměnné:**

$$
{}_v m_{v,2}
=
2{,}33-(-0{,}53)^2
$$

$$
\boxed{{}_v m_{v,2}\approx 2{,}05}
$$

**Třetí centrální moment:**

$$
{}_v m_{v,3}
=
-2{,}41
-
3(-0{,}53)\cdot2{,}33
+
2(-0{,}53)^3
$$

$$
\boxed{{}_v m_{v,3}\approx 1{,}00}
$$

**Čtvrtý centrální moment:**

$$
{}_v m_{v,4}
=
11{,}75
-
4(-0{,}53)(-2{,}41)
+
6(-0{,}53)^2\cdot2{,}33
-
3(-0{,}53)^4
$$

$$
\boxed{{}_v m_{v,4}\approx 10{,}33}
$$

Nyní přejdeme zpět k původní proměnné \(x\).

**Aritmetický průměr:**

$$
\overline{x}
=
h\overline{v}+a
$$

$$
\overline{x}
=
2800\cdot(-0{,}53)+15900
$$

$$
\boxed{\overline{x}\approx 14416}
$$

**Rozptyl:**

$$
s_x^2=h^2s_v^2
$$

$$
s_x^2=2800^2\cdot2{,}05
$$

$$
\boxed{s_x^2\approx 16072000}
$$

**Třetí normovaný moment:**

$$
m_{u,3}
=
\frac{1{,}00}{2{,}05\sqrt{2{,}05}}
$$

$$
\boxed{m_{u,3}\approx 0{,}34}
$$

**Čtvrtý normovaný moment:**

$$
m_{u,4}
=
\frac{10{,}33}{2{,}05^2}
$$

$$
\boxed{m_{u,4}\approx 2{,}46}
$$

Výsledky nám ukazují, že pomocí pomocné proměnné můžeme výrazně zjednodušit výpočty, aniž bychom změnili výsledné normované charakteristiky.

---

### 3.2.5. Vztahy mezi charakteristikami polohy

Mezi základní charakteristiky polohy patří:

- Aritmetický průměr.
- Medián.
- Modus.

V symetrickém rozdělení se všechny tři charakteristiky nacházejí ve stejném bodě:

$$
\boxed{
\overline{x}=\tilde{x}=\hat{x}
}
$$

Kde:

- \(\overline{x}\) – aritmetický průměr.
- \(\tilde{x}\) – medián.
- \(\hat{x}\) – modus.

Čím více se rozdělení četností blíží symetrickému rozdělení, tím méně se tyto charakteristiky od sebe odlišují.

### 3.2.6. Vztahy mezi charakteristikami průměrné polohy

U asymetrických rozdělení se aritmetický průměr, medián a modus zpravidla nacházejí na různých místech.

**Záporně zešikmené rozdělení (levostranné):**

$$
\boxed{
\overline{x}<\tilde{x}<\hat{x}
}
$$

**Kladně zešikmené rozdělení (pravostranné):**

$$
\boxed{
\hat{x}<\tilde{x}<\overline{x}
}
$$

U mírně asymetrického rozdělení, které není extrémně nesouměrné, bývá vzdálenost mezi mediánem a aritmetickým průměrem přibližně třetinou vzdálenosti mezi modem a aritmetickým průměrem.

$$
\boxed{
\overline{x}-\tilde{x}
\approx
\frac{\overline{x}-\hat{x}}{3}
}
$$

Tento vztah je orientační a používá se především pro mírně asymetrická rozdělení.

---

### 3.2.7. Míry variability

Dosud jsme se zabývali především mírami polohy, které nám umožňují porovnávat úroveň hodnot statistického znaku ve dvou nebo více souborech.

Samotná míra polohy však nestačí. Dva zcela odlišné statistické soubory mohou mít stejný aritmetický průměr nebo medián.

Proto potřebujeme sledovat také to, jak moc se jednotlivé hodnoty odlišují od míry polohy a jak moc se liší navzájem.

Tyto odlišnosti označujeme jako **variabilitu neboli měnlivost**.

Příklad:

- Soubor A: 28, 29, 30, 31, 32.
- Soubor B: 10, 20, 30, 40, 50.

Oba soubory mají stejný aritmetický průměr:

$$
\overline{x}_A=\overline{x}_B=30
$$

Přesto jsou hodnoty v souboru B výrazně více rozptýlené. Soubor B má tedy vyšší variabilitu.

---

### 3.2.8. Kvantilové míry variability

Kvantilové míry variability vycházejí z kvantilů a popisují rozsah, ve kterém se nacházejí určité části statistického souboru.

**Variační rozpětí**

Vyjadřuje rozdíl mezi největší a nejmenší hodnotou souboru:

$$
\boxed{
R_x=x_{\max}-x_{\min}
}
\tag{53}
$$

**Kvartilové rozpětí**

Vyjadřuje rozsah prostředních 50 % pozorování:

$$
\boxed{
R_Q=\tilde{x}_{75}-\tilde{x}_{25}
}
\tag{54}
$$

**Decilové rozpětí**

Vyjadřuje rozsah mezi prvním a devátým decilem:

$$
\boxed{
R_D=\tilde{x}_{90}-\tilde{x}_{10}
}
\tag{55}
$$

**Percentilové rozpětí**

Vyjadřuje rozsah mezi prvním a devadesátým devátým percentilem:

$$
\boxed{
R_P=\tilde{x}_{99}-\tilde{x}_{1}
}
\tag{56}
$$

### Kvartilová odchylka

Kvartilová odchylka představuje polovinu kvartilového rozpětí:

$$
Q=
\frac{
(\tilde{x}_{75}-\tilde{x})+
(\tilde{x}-\tilde{x}_{25})
}{2}
$$

Po zjednodušení:

$$
\boxed{
Q=\frac{\tilde{x}_{75}-\tilde{x}_{25}}{2}
}
\tag{57}
$$

### Decilová odchylka

Decilová odchylka je osmina decilového rozpětí:

$$
\boxed{
D=\frac{\tilde{x}_{90}-\tilde{x}_{10}}{8}
}
\tag{58}
$$

### Percentilová odchylka

Percentilová odchylka je rozdíl mezi 99. a 1. percentilem vydělený 98:

$$
\boxed{
P=\frac{\tilde{x}_{99}-\tilde{x}_{1}}{98}
}
\tag{59}
$$

### Momentové míry variability

Mezi momentové míry variability patří především rozptyl a směrodatná odchylka.

**Rozptyl:**

$$
\boxed{
s_x^2=
\frac{1}{n}
\sum_{i=1}^{n}(x_i-\overline{x})^2
}
$$

**Směrodatná odchylka:**

$$
\boxed{
s_x=\sqrt{s_x^2}
}
$$

Rozptyl vyjadřuje průměrnou čtvercovou odchylku od aritmetického průměru. Směrodatná odchylka je jeho druhou odmocninou a má stejné měrné jednotky jako původní statistický znak.

### Momentová míra relativní variability

Pro porovnání variability souborů s různými průměry můžeme využít variační koeficient:

$$
\boxed{
c_x=\frac{s_x}{\overline{x}}
}
\tag{60}
$$

Často jej vyjadřujeme také v procentech:

$$
\boxed{
c_x=\frac{s_x}{\overline{x}}\cdot100\,\%
}
$$

Variační koeficient vyjadřuje relativní velikost směrodatné odchylky vzhledem k aritmetickému průměru.

Čím vyšší je variační koeficient, tím vyšší je relativní variabilita souboru.

**Pozor:** Variační koeficient je vhodný především pro znaky s kladným a nenulovým průměrem, u kterých má poměr směrodatné odchylky k průměru smysluplnou interpretaci.

### Výpočet celkového rozptylu z dílčích rozptylů

Pokud je soubor rozdělen do několika dílčích skupin, můžeme celkový rozptyl vypočítat jako vážený průměr dílčích rozptylů pouze za předpokladu, že jednotlivé skupiny mají stejný průměr.

$$
\boxed{
s_x^2=
\frac{\sum_{i=1}^{k}s_i^2n_i}
{\sum_{i=1}^{k}n_i}
}
$$

Kde:

- \(s_i^2\) – rozptyl i-té skupiny.
- \(n_i\) – počet pozorování v i-té skupině.
- \(k\) – počet skupin.

Pokud mají skupiny různé průměry, je nutné zohlednit také rozdíly mezi skupinovými průměry a celkovým průměrem. Samotný vážený průměr dílčích rozptylů by pak nestačil.

---

### 3.2.9. Míry šikmosti

Míry šikmosti popisují asymetrii statistického rozdělení. Umožňují zjistit, zda jsou hodnoty rozloženy symetricky, nebo zda má rozdělení delší ocas na jedné straně.

Rozlišujeme několik způsobů výpočtu šikmosti.

### Kvantilová šikmost

Kvantilová šikmost je definována vztahem:

$$
\boxed{
\tau=
\frac{
(x_{\max}-\tilde{x})-(\tilde{x}-x_{\min})
}{
(x_{\max}-\tilde{x})+(\tilde{x}-x_{\min})
}
}
\tag{61}
$$

Po úpravě:

$$
\boxed{
\tau=
\frac{x_{\max}+x_{\min}-2\tilde{x}}
{x_{\max}-x_{\min}}
}
$$

Kde:

- \(x_{\max}\) – největší hodnota.
- \(x_{\min}\) – nejmenší hodnota.
- \(\tilde{x}\) – medián.

V symetrickém rozdělení je kvantilová šikmost rovna nule:

$$
\tau=0
$$

### Percentilová šikmost

Percentilová šikmost využívá kvantily místo krajních hodnot:

$$
\boxed{
\tau_i=
\frac{
(\tilde{x}_{100-i}-\tilde{x})-
(\tilde{x}-\tilde{x}_i)
}{
(\tilde{x}_{100-i}-\tilde{x})+
(\tilde{x}-\tilde{x}_i)
}
}
\tag{62}
$$

Po úpravě:

$$
\boxed{
\tau_i=
\frac{
\tilde{x}_{100-i}+\tilde{x}_i-2\tilde{x}
}{
\tilde{x}_{100-i}-\tilde{x}_i
}
}
$$

Tato míra porovnává vzdálenosti dolního a horního kvantilu od mediánu.

### Výběrová šikmost

Výběrová šikmost vychází ze třetího centrálního momentu a rozptylu:

$$
\boxed{
A_3=
\frac{{}_x m_{x,3}}{({}_x m_{x,2})^{3/2}}
}
\tag{63}
$$

Při rozdělení četností můžeme vztah zapsat:

$$
A_3=
\frac{
\sum_{i=1}^{k}(x_i-\overline{x})^3n_i
}{
n s_x^3
}
$$

Interpretace:

- \(A_3=0\) – nulová šikmost.
- \(A_3>0\) – kladná, pravostranná šikmost.
- \(A_3<0\) – záporná, levostranná šikmost.

### Pearsonova míra šikmosti

Pearsonova míra šikmosti využívá rozdíl mezi aritmetickým průměrem a modem:

$$
\boxed{
\tau=
\frac{\overline{x}-\hat{x}}{s_x}
}
\tag{64}
$$

Kde:

- \(\overline{x}\) – aritmetický průměr.
- \(\hat{x}\) – modus.
- \(s_x\) – směrodatná odchylka.

### Jednoduchá míra šikmosti

Jednoduchá míra šikmosti vychází z počtu hodnot, které jsou menší a větší než aritmetický průměr.

$$
\boxed{
\tau=
\frac{n_1-n_2}{n}
}
\tag{65}
$$

Kde:

- \(n_1\) – počet hodnot menších než aritmetický průměr.
- \(n_2\) – počet hodnot větších než aritmetický průměr.
- \(n\) – celkový počet pozorování.

**Shrnutí šikmosti:**

| Hodnota šikmosti | Význam |
|---|---|
| Kladná | Pravostranně zešikmené rozdělení. |
| Záporná | Levostranně zešikmené rozdělení. |
| Nulová | Rozdělení je z hlediska dané míry symetrické. |

---

### 3.2.10. Míry špičatosti

Míry špičatosti popisují tvar statistického rozdělení, zejména jeho vrchol a chování krajních hodnot.

Rozlišujeme kvantilovou a výběrovou špičatost.

### Kvantilová špičatost

První způsob výpočtu využívá variační rozpětí a kvartilové rozpětí:

$$
\boxed{
K=
\frac{x_{\max}-x_{\min}}
{\tilde{x}_{75}-\tilde{x}_{25}}
}
\tag{66}
$$

Druhá varianta využívá 0,5. a 99,5. percentil:

$$
\boxed{
K=
\frac{\tilde{x}_{99{,}5}-\tilde{x}_{0{,}5}}
{\tilde{x}_{75}-\tilde{x}_{25}}
}
\tag{67}
$$

Třetí varianta využívá 1. a 99. percentil:

$$
\boxed{
K=
\frac{\tilde{x}_{99}-\tilde{x}_{1}}
{\tilde{x}_{75}-\tilde{x}_{25}}
}
\tag{68}
$$

Tyto charakteristiky porovnávají rozsah krajních hodnot s rozsahem prostředních 50 % pozorování.

### Výběrová špičatost

Výběrová špičatost vychází ze čtvrtého centrálního momentu a druhé mocniny rozptylu:

$$
\boxed{
A_4=
\frac{{}_x m_{x,4}}{({}_x m_{x,2})^2}
}
\tag{69}
$$

Při rozdělení četností lze vztah zapsat:

$$
A_4=
\frac{
\sum_{i=1}^{k}(x_i-\overline{x})^4n_i
}{
n s_x^4
}
$$

Čtvrtý normovaný moment je citlivý na vzdálené hodnoty, protože odchylky od průměru umocňuje na čtvrtou.

**Důležité rozlišení:** Ve studijním materiálu je špičatost definována jako čtvrtý normovaný moment, jehož hodnota u normálního rozdělení je 3. Někdy se používá také excesní špičatost, která vznikne odečtením tří:

$$
\boxed{
\text{Excesní špičatost}=A_4-3
}
$$

Proto je nutné vždy vědět, kterou variantu špičatosti používáme.

---

### 3.2.11. Empirická distribuční funkce

**Empirická distribuční funkce** je výběrovou obdobou teoretické distribuční funkce. Udává, jaká část pozorování ve statistickém souboru má hodnotu menší nebo rovnou zadané hodnotě \(x\).

Označujeme ji:

$$
F_n(x)
$$

Nejprve musíme všechny hodnoty statistického souboru seřadit vzestupně:

$$
X_{(1)}\leq X_{(2)}\leq\cdots\leq X_{(n)}
$$

Empirická distribuční funkce je definována po částech:

$$
\boxed{
F_n(x)=
\begin{cases}
0, & x<X_{(1)},\\[6pt]
\frac{i}{n}, & X_{(i)}\leq x<X_{(i+1)},\\[6pt]
1, & x\geq X_{(n)}.
\end{cases}
}
$$

Kde:

- \(F_n(x)\) – hodnota empirické distribuční funkce.
- \(n\) – počet pozorování.
- \(X_{(i)}\) – i-tá hodnota seřazeného souboru.
- \(i\) – pořadové číslo pozorování.

### Příklad – ověření rovnoměrného rozdělení

Máme prvních deset čísel získaných generátorem náhodných čísel:

$$
0{,}93;\ 0{,}35;\ 0{,}66;\ 0{,}93;\ 0{,}14;
$$

$$
0{,}23;\ 0{,}08;\ 0{,}23;\ 0{,}21;\ 0{,}59
$$

Nejprve čísla seřadíme vzestupně:

$$
\begin{aligned}
&0{,}08;\ 0{,}14;\ 0{,}21;\ 0{,}23;\ 0{,}23;\\
&0{,}35;\ 0{,}59;\ 0{,}66;\ 0{,}93;\ 0{,}93
\end{aligned}
$$

Počet pozorování:

$$
n=10
$$

Nyní vytvoříme empirickou distribuční funkci.

| Interval hodnot \(x\) | Empirická distribuční funkce |
|---|---:|
| \(x<0{,}08\) | 0 |
| \(0{,}08\leq x<0{,}14\) | 0,1 |
| \(0{,}14\leq x<0{,}21\) | 0,2 |
| \(0{,}21\leq x<0{,}23\) | 0,3 |
| \(0{,}23\leq x<0{,}35\) | 0,5 |
| \(0{,}35\leq x<0{,}59\) | 0,6 |
| \(0{,}59\leq x<0{,}66\) | 0,7 |
| \(0{,}66\leq x<0{,}93\) | 0,8 |
| \(x\geq0{,}93\) | 1 |

Všimni si, že hodnota 0,23 se v souboru vyskytuje dvakrát. Proto se empirická distribuční funkce při této hodnotě zvýší z 0,3 na 0,5.

Obecně platí, že empirická distribuční funkce je neklesající schodovitá funkce. Při každém výskytu nové hodnoty se její hodnota zvýší o příslušnou četnost dělenou celkovým počtem pozorování.

### Porovnání s rovnoměrným rozdělením

V příkladu chceme ověřit, zda lze získaná čísla považovat za výběr z rovnoměrného rozdělení na intervalu \(\langle 0,1\rangle\).

Teoretická distribuční funkce rovnoměrného rozdělení na tomto intervalu je:

$$
\boxed{
F(x)=
\begin{cases}
0, & x<0,\\[4pt]
x, & 0\leq x<1,\\[4pt]
1, & x\geq1.
\end{cases}
}
$$

Následně porovnáváme empirickou distribuční funkci s teoretickou distribuční funkcí.

Pokud se obě funkce dostatečně podobají, může to naznačovat, že data pocházejí z rovnoměrného rozdělení. Samotné grafické porovnání však není formálním důkazem; pro statistické ověření bychom použili vhodný test dobré shody.

V MATLABu lze deset náhodných čísel vygenerovat příkazem:

```matlab
X = rand(10,1)
```

---

## Shrnutí kapitoly 3 – Popisná statistika

Popisná statistika nám umožňuje charakterizovat statistický soubor pomocí několika základních skupin statistických charakteristik.

### 1. Momenty

Momenty jsou funkcemi všech hodnot statistického znaku.

| Druh momentu | Význam |
|---|---|
| Obecný moment | Počítá se kolem nuly. |
| Centrální moment | Počítá se kolem aritmetického průměru. |
| Normovaný moment | Je bezrozměrný a využívá směrodatnou odchylku. |

Nejdůležitější momenty:

- První obecný moment = aritmetický průměr.
- První centrální moment = 0.
- Druhý centrální moment = rozptyl.
- Třetí normovaný moment = šikmost.
- Čtvrtý normovaný moment = špičatost.

### 2. Variabilita

Variabilita vyjadřuje, jak moc se jednotlivé hodnoty odlišují od středu statistického souboru.

Mezi hlavní charakteristiky patří:

- Variační rozpětí.
- Kvartilové rozpětí.
- Decilové rozpětí.
- Percentilové rozpětí.
- Rozptyl.
- Směrodatná odchylka.
- Variační koeficient.

### 3. Šikmost

Šikmost popisuje asymetrii statistického rozdělení.

- Kladná šikmost – pravostranné rozdělení.
- Záporná šikmost – levostranné rozdělení.
- Nulová šikmost – rozdělení je z hlediska dané míry symetrické.

### 4. Špičatost

Špičatost popisuje tvar rozdělení a jeho chování v okolí středu a v krajních částech.

Nejčastěji se počítá pomocí čtvrtého normovaného momentu.

### 5. Empirická distribuční funkce

Empirická distribuční funkce vyjadřuje podíl pozorování, která mají hodnotu menší nebo rovnou zadané hodnotě.

Její průběh je schodovitý a neklesající.

---

## Nejdůležitější vzorce kapitoly 3

| Charakteristika | Vzorec |
|---|---|
| Obecný moment | \(\displaystyle {}_0m_{x,k}=\frac{1}{n}\sum x_i^k\) |
| Centrální moment | \(\displaystyle {}_xm_{x,k}=\frac{1}{n}\sum(x_i-\overline{x})^k\) |
| Rozptyl | \(\displaystyle s_x^2=\frac{1}{n}\sum(x_i-\overline{x})^2\) |
| Směrodatná proměnná | \(\displaystyle u_i=\frac{x_i-\overline{x}}{s_x}\) |
| Třetí normovaný moment | \(\displaystyle A_3=\frac{{}_xm_{x,3}}{({}_xm_{x,2})^{3/2}}\) |
| Čtvrtý normovaný moment | \(\displaystyle A_4=\frac{{}_xm_{x,4}}{({}_xm_{x,2})^2}\) |
| Variační rozpětí | \(\displaystyle R_x=x_{\max}-x_{\min}\) |
| Kvartilové rozpětí | \(\displaystyle R_Q=\tilde{x}_{75}-\tilde{x}_{25}\) |
| Variační koeficient | \(\displaystyle c_x=\frac{s_x}{\overline{x}}\) |
| Kvantilová šikmost | \(\displaystyle \tau=\frac{x_{\max}+x_{\min}-2\tilde{x}}{x_{\max}-x_{\min}}\) |
| Kvartilová špičatost | \(\displaystyle K=\frac{x_{\max}-x_{\min}}{\tilde{x}_{75}-\tilde{x}_{25}}\) |

**Hlavní myšlenka kapitoly:** Zatímco míry polohy nám říkají, kde se nachází střed statistického souboru, momenty a další charakteristiky nám umožňují pochopit, jak jsou hodnoty rozptýlené, zda jsou symetrické a jaký tvar má jejich rozdělení.
