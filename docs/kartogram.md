<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

Podstatou kartogramu (*choropleth map*) je znázornění jevu vyjádřeného *relativními* hodnotami, zachyceného za dílčí územní celky. Pro správné srovnání je klíčové, aby data byla *relativní*, tj. v ideálním případě přepočtená na plochu územní jednotky (tzv. pravý kartogram), akceptovatelné je i přepočítání s využitím jiné charakteristiky územní jednotky, např. na počet obyvatel (tzv. nepravý kartogram). Častou a zásadní chybou je použití této kartografické vyjadřovací metody na absolutní data. (Lysák, 2014)

### Nejčastější druhy kartogramu
1.  *Jednoduchý homogenní kartogram* zobrazuje pouze jeden relativní jev, a to změnou barvy nebo rastru
2.  *Jednoduchý kvalifikační kartogram* znázorňuje rozdíl jevu od zvolené střední hodnoty S, pro oblasti s hodnotou jevu větší než S se volí odstíny barvy opačného charakteru než pro jevy s hodnotu menší než S.
3.  *Složený kartogram* zobrazuje hodnoty dvou nebo více jevů, umožňuje jejich vzájemné srovnání, typicky je jeden jev vyjádřen barvou, druhý rastrem

Tvorba kartogramu zahrnuje tři hlavní úkoly:

1.  Tvorba intervalové stupnice, resp. klasifikace vstupních dat do intervalů.
2.  Grafické řešení jejich znázornění v mapě (obvykle pomocí barevné stupnice či rastru).
3.  Návrh správnou legendu.

### Klasifikace vstupních dat
Při klasifikaci vstupních dat (tvorbě intervalové stupnice) je třeba stanovit **počet intervalů a jejich meze** (hranice mezi intervaly).

**Stanovení počtu intervalů**
V kartografické literatuře (Voženílek, 2011) lze nalézt doporučené vzorce pro počet intervalů vycházející pouze z počtu územních jednotek viz níže (*m* znamená počet intervalů, *y* počet statistických jednotek v souboru).

$$
m \approx 1 + 3.3 \log y
$$

$$
m \leq 5 \log y
$$


V praxi se doporučuje použít 4–10 intervalů. Malé množství zna-mená velmi hrubou informaci o rozložení jevu v území, velké množství naopak činí mapu nepřehlednou, zejména z toho důvodu, že je pak pro čtenáře mapy obtížné rozlišit jednotlivé kategorie, mezi jejichž barvou či rastrem jsou pak jen velmi nepatrné rozdíly.

<iframe width="560" height="315" src="https://www.youtube.com/embed/R1Tfla2DieQ?si=tpDmtmJjLlymgdaa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

### Grafický návrh znázornění intervalů v mapě
#### Barevné stupnice
1.  Jednoduchý kartogram
    1.  Homogenní
    2.  Kvalifikační
3.  Složený kartogram
#### Rastrové stupnice

### Tvorba legendy