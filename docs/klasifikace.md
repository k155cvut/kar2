<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

# Klasifikace dat
**Data** z principu tvoří základ každé datové vizualizace. Bez nich či bez hlubšího porozumění datům, bez znalosti jejich původu či způsobu sběru, není možné správně pracovat. Dvě hlavní kategorie představují data **kvalitativní** a **kvantitativní**. Kvantitativní data lze měřit v číslech, např. vzdálenost, cena, čas. Kvalitativní data jsou vyjádřena nečíselnou informací (např. pohlaví nebo pocity obyvatel města).

V rámci **kvalitativních dat** lze dále rozlišit **ordinální** a **nominální** (nemají vnitřní pořadí, např. druhy stromů). U ordinálních dat záleží na pořadí, ale rozdíly mezi hodnotami nejsou definovány, např. výzkum veřejného mínění s možnostmi: souhlasím – spíše souhlasím – nevím – spíše nesouhlasím – nesouhlasím. Pořadí je zřejmé, avšak nelze tvrdit, že rozdíl mezi prvními dvěma možnostmi je stejný jako mezi poslední dvojicí.

**Kvantitativní data** mohou být **spojitá** (dále dělitelná, např. teplota) či **diskrétní** (celá čísla, nelze dělit, např. počet dětí). Spojitá data lze rozlišovat také dle toho, zda jsou měřena na **intervalové** či **poměrové** stupnici. U in**tervalových stupnic** je možné zjistit rozdíl, ale nikoliv podíl dvou hodnot, jelikož nulová hodnota je konvenční. Nelze se tedy ptát, kolikrát je jedna hodnota větší než druhá (např. teplota ve °C, nelze tvrdit, kolikrát tepleji bude zítra než dnes). U **poměrové stupnice** se nachází nulová hodnota na místě, které odpovídá absenci sledovaného znaku (např. váha).

Při klasifikaci vstupních dat za účelem tvorby intervalové stupnice je třeba stanovit **počet intervalů a jejich meze** (hranice mezi intervaly).

## Stanovení počtu intervalů
V kartografické literatuře (Voženílek, 2011) lze nalézt doporučené vzorce pro počet intervalů vycházející pouze z počtu územních jednotek viz níže (*m* znamená počet intervalů, *y* počet statistických jednotek v souboru).

$$
m \approx 1 + 3,3 \log y
$$

$$
m \leq 5 \log y
$$


V praxi se doporučuje použít 4–10 intervalů. Malé množství znamená velmi hrubou informaci o rozložení jevu v území, velké množství naopak činí mapu nepřehlednou, zejména z toho důvodu, že je pak pro čtenáře mapy obtížné rozlišit jednotlivé kategorie, mezi jejichž barvou či rastrem jsou pak jen velmi nepatrné rozdíly. (Lysák, 2014)

## Klasifikační metody
V praxi se obvykle využívá některého z klasifikačních algoritmů, které jsou v ArcGIS Pro implementovány a výsledek automatického zpracování se následně ručně upraví. Je proto vhodné rozumět tomu, jak jednotlivé algoritmy pracují. (Lysák, 2014)

### Neklasifikovaná data

**Popis**:

Každá jednotka (např. okres) je zobrazena unikátní barvou podle přesné hodnoty.

**Výhody**:

-   Plynulý a detailní přechod mezi hodnotami.
-   Precizní zobrazení dat.

**Nevýhody**:

-   Mapa může být složitá a obtížně čitelná pro uživatele.
-   Legenda nemusí být intuitivní.

### Manual

**Popis**:

Manuálně vymezené intervaly představují ruční klasifikaci, při které tvůrce mapy nastaví hranice intervalů dle analýzy dat a vlastního uvážení.

### Equal Interval

**Popis**:

Data jsou rozdělena do stejně širokých intervalů (např. 0–10, 10–20). Algoritmus v datech nejprve nalezne minimum a maximum a poté rozdělí rozpětí mezi těmito hodnotami do stejně velkých intervalů.

**Výhody**:

-   Intuitivní legenda.
-   Funguje dobře pro normálně rozložená data.

**Nevýhody**:

-   Nevhodné pro asymetricky rozdělená data.
-   Odlehlé hodnoty mohou narušit vizuální přehlednost.
-   Ztráta detailů u nerovnoměrně rozložených dat.

### Defined Interval

**Popis**:

Zatímco v předchozím případě jsme zadávali počet intervalů a program dopočítával jejich šířku, zde zadáváme šířku intervalu a počet je závislý na tom, kolikrát se zadaný interval vejde mezi minimum a maximum.

### Standard Deviation

**Popis**:

Intervaly jsou určeny na základě průměru a směrodatných odchylek. Tento algoritmus je mimochodem do značné míry podobný *Defined Intervals*. Oba algoritmy dělí data do intervalů o zadané velikosti, ale v případě *Standard Deviation* nevolíme velikost intervalů libovolně, ale vybíráme z násobků směrodatné odchylky vypočtené z klasifikovaných dat.

**Výhody**:

-   Dobrá vizuální variabilita i u asymetricky rozdělených dat.
-   Jasně ukazuje průměrné, nadprůměrné a podprůměrné hodnoty.

**Nevýhody**:

-   Složitější legenda pro uživatele.
-   Může být matoucí pro neodborné publikum.

### Quantile

**Popis**:

Každá kategorie obsahuje stejný počet jednotek (např. stejné množství okresů v každé kategorii).

**Výhody**:

-   Atraktivní a vyvážený vzhled mapy.
-   Dobře funguje pro nerovnoměrně rozložená data.

**Nevýhody**:

-   Intervaly nemusí odrážet skutečné rozdělení dat.
-   Potenciál pro matení uživatele (nerovnoměrné intervaly).
-   Je nutné jasně a přesně popsat legendu.

### Jenks Natural Breaks

**Popis**:

Algoritmus (*metoda přirozených zlomů*) automaticky hledá přirozené zlomy v datech a určuje intervaly.

**Výhody**:

-   Optimalizované rozdělení dat do kategorií.
-   Vhodné pro data s nepravidelným rozložením.

**Nevýhody**:

-   „Černá skříňka“ – uživatel nemá kontrolu nad rozdělením.
-   Může být obtížné interpretovat legendu.
-   Výsledek závisí na algoritmu, ne na uživateli.

### Shrnutí vybraných metod

| **Metoda**         | **Výhody**                         | **Nevýhody**                     | **Vhodné pro...**            |
|--------------------|------------------------------------|----------------------------------|------------------------------|
| **Neklasifikovaná** | Detailní a přesná data            | Složitá pro čtení                | Detailní vizualizace         |
| **Rovnoměrné int.** | Intuitivní legenda                | Citlivé na odlehlé hodnoty       | Normální rozložení           |
| **Standardní odch.**| Jasná průměrná odchylka           | Složitější legenda               | Normální i nerovnoměrná data |
| **Kvantily**        | Atraktivní vzhled                 | Může být zavádějící              | Nerovnoměrná data            |
| **Přírodní zlomy**  | Optimalizované kategorie          | Málo transparentní proces        | Nepravidelné rozložení       |

### Videa

<div style="text-align: center;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/nRqdTBKwYeU?si=sY67dSf2T12y_fXc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>

<br>

<div style="text-align: center;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/R1Tfla2DieQ?si=tpDmtmJjLlymgdaa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>