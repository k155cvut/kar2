<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

# Klasifikace dat (JM)
Při klasifikaci vstupních dat (tvorbě intervalové stupnice) je třeba stanovit **počet intervalů a jejich meze** (hranice mezi intervaly).

### Stanovení počtu intervalů
V kartografické literatuře (Voženílek, 2011) lze nalézt doporučené vzorce pro počet intervalů vycházející pouze z počtu územních jednotek viz níže (*m* znamená počet intervalů, *y* počet statistických jednotek v souboru).

$$
m \approx 1 + 3,3 \log y
$$

$$
m \leq 5 \log y
$$


V praxi se doporučuje použít 4–10 intervalů. Malé množství znamená velmi hrubou informaci o rozložení jevu v území, velké množství naopak činí mapu nepřehlednou, zejména z toho důvodu, že je pak pro čtenáře mapy obtížné rozlišit jednotlivé kategorie, mezi jejichž barvou či rastrem jsou pak jen velmi nepatrné rozdíly. (Lysák, 2014)

<iframe width="560" height="315" src="https://www.youtube.com/embed/R1Tfla2DieQ?si=tpDmtmJjLlymgdaa" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>