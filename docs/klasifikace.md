<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

# Klasifikace dat (JM)
Při klasifikaci vstupních dat (tvorbě intervalové stupnice) je třeba stanovit **počet intervalů a jejich meze** (hranice mezi intervaly).

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

### Neklasifikovaná data

**Popis**: Každá jednotka (např. okres) je zobrazena unikátní barvou podle přesné hodnoty.

**Výhody**:

-   Plynulý a detailní přechod mezi hodnotami.
-   Precizní zobrazení dat.

**Nevýhody**:

-   Mapa může být složitá a obtížně čitelná pro uživatele.
-   Legenda nemusí být intuitivní.

### Rovnoměrné intervaly *(Equal Interval)*

**Popis**: Data jsou rozdělena do stejně širokých intervalů (např. 0–10, 10–20).

**Výhody**:

-   Intuitivní legenda.
-   Funguje dobře pro normálně rozložená data.

**Nevýhody**:

-   Nevhodné pro asymetricky rozdělená data.
-   Odlehlé hodnoty mohou narušit vizuální přehlednost.
-   Ztráta detailů u nerovnoměrně rozložených dat.

**Použití**: Pro normálně rozložená data.

### Směrodatná odchylka *(Standard Deviation)*

**Popis**: Intervaly jsou určeny na základě průměru a směrodatných odchylek.

**Výhody**:

-   Dobrá vizuální variabilita i u asymetricky rozdělených dat.
-   Jasně ukazuje průměrné, nadprůměrné a podprůměrné hodnoty.

**Nevýhody**:

-   Složitější legenda pro uživatele.
-   Může být matoucí pro neodborné publikum.

**Použití**: Pro normální nebo šikmá data, pokud je důležité ukázat odchylky od průměru.

### Kvantily *(Quantile)*

**Popis**: Každá kategorie obsahuje stejný počet jednotek (např. stejné množství okresů v každé kategorii).

**Výhody**:

-   Atraktivní a vyvážený vzhled mapy.
-   Dobře funguje pro nerovnoměrně rozložená data.

**Nevýhody**:

-   Intervaly nemusí odrážet skutečné rozdělení dat.
-   Potenciál pro matení uživatele (nerovnoměrné intervaly).
-   Je nutné jasně a přesně popsat legendu.

**Použití**: Pro data, kde je cílem zdůraznit nuance bez ohledu na rozložení dat.

### Metoda přirozených zlomů *(Jenks Natural Breaks)*

**Popis**: Algoritmus automaticky hledá přirozené zlomy v datech a určuje intervaly.

**Výhody**:

-   Optimalizované rozdělení dat do kategorií.
-   Vhodné pro data s nepravidelným rozložením.

**Nevýhody**:

-   „Černá skříňka“ – uživatel nemá kontrolu nad rozdělením.
-   Může být obtížné interpretovat legendu.
-   Výsledek závisí na algoritmu, ne na uživateli.

**Použití**: Pokud chcete algoritmu důvěřovat v hledání optimálních bodů.

### Shrnutí metod

| **Metoda**         | **Výhody**                         | **Nevýhody**                     | **Vhodné pro...**            |
|--------------------|------------------------------------|----------------------------------|------------------------------|
| **Neklasifikovaná** | Detailní a přesná data            | Složitá pro čtení                | Detailní vizualizace         |
| **Rovnoměrné int.** | Intuitivní legenda                | Citlivé na odlehlé hodnoty       | Normální rozložení           |
| **Standardní odch.**| Jasná průměrná odchylka           | Složitější legenda               | Normální i nerovnoměrná data |
| **Kvantily**        | Atraktivní vzhled                 | Může být zavádějící              | Nerovnoměrná data            |
| **Přírodní zlomy**  | Optimalizované kategorie          | Málo transparentní proces        | Nepravidelné rozložení       |

<br>

<div style="text-align: center;">
<iframe width="560" height="315" src="https://www.youtube.com/embed/R1Tfla2DieQ?si=tpDmtmJjLlymgdaa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
</div>