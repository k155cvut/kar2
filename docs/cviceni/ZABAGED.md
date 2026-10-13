# Úloha 4 – Tvorba mapy z dat ZABAGED, generalizace dat

## Zadání 
Vytvořte topografickou mapu v měřítku 1 : 25 000 z dat ZABAGED pomocí symbolizace jednotlivých vrstev. Jedná se o různé výřezy v severní části Čech. Máte k dispozici všechny vrstvy ZABAGED, mimo jiné:

-   ***ArealUceloveZastavby*** (plocha)
-   BazinaMocal (plocha)
-   **BudovaBlokBudov** (plocha)
-   **Cesta** (linie)
-   ElektrickeVedeni (linie)
-   HraniceSpravniJednotkyKU (linie)
-   *Hrbitov* (plocha)
-   *Chmelnice* (plocha)
-   KrizSloup (bod)
-   KulnaSklenikFoliovnik (plocha)
-   *LesniPudaSeStromy* (plocha)
-   *LesniPudaSKrovinatymPorostem* (plocha)
-   MohylaPomnikNahrobek (bod)
-   ParkovisteOdpocivka (bod)
-   *OkrasnaZahradaPark* (plocha)
-   *OrnaPuda_Ostatni* (plocha)
-   *OvocnySadZahrada* (plocha)
-   Pesina (linie)
-   **SilniceDalnice** (linie)
-   SilniceNeevidovana (linie)
-   *Skladka* (plocha)
-   *TrvalyTravniPorost* (plocha)
-   Ulice (linie)
-   *UsazovaciNadrzOdkaliste* (plocha)
-   *Vinice* (plocha)
-   *VodniPlocha* (plocha)
-   **VodniTok** (linie)
-   ZeleznicniTrat (linie)
-   ZeleznicniVlecka (linie)
-   ZeleznicniStanice (bod)
-   ZeleznicniZastavka (bod)

**Tučně** vyznačené vrstvy mají atributy využitelné pro symbolizaci. *Kurzívou* vyznačené tvoří topologický plošný základ mapy.

Mapa by měla být ve výsledku vizuálně podobná běžným topografickým mapám, které znáte (ZTM, TM, příp. jiné bězné mapy). Měla pokrýt papír o velikosti A4 (využijte rám 200×287 mm). Data jsou v S-JTSK, ale mapu vytvořte v ETRS89 (EPSG kód 3045). V písmech Esri je možné najít mnoho znaků, využitelných pro některé z objektů. Znaky pro případné zbylé objekty vytvořte dle vlastního návrhu nebo importujte pomocí SVG (např. [SVGrepo](https://www.svgrepo.com)); využijte zkušenosti s prací s existujícími topografickými mapami, u nichž se můžete inspirovat. Pro začátek jsem Vám připravil projekt s některými vrstvami již symbolizovanými.

**Je vhodné projít si v první fázi data a podívat se na jejich strukturu.** Např. vrstva Chmelnice nemá žádné atributy použitelné při symbolizaci, naproti tomu vrstva SilniceDalnice má mnoho typů od 3. třídy po dálnici, které je vhodné graficky odlišit, jako je to v konvenčních topografických mapách běžné. Tučně vyznačené vrstvy je možné/vhodné atributově členit. Vrstva ArealUceloveZastavby obsahuje mnoho typů objektů, které, byť vyznačeny plochou, mohou být přeznačeny bodovou značkou (kostel, vodojem apod.), nebo i značkou plošnou (hřiště, zeměd. areál apod.). 

!!! note "Takové vrstvy, které mají kromě plošné/liniové realizace i bodovou vrstvu (centroid), jsou označeny v datech příponou *_c*"

Informace o struktuře dat ZABAGED, jednotlivých atributech apod. naleznete v [KATALOGU OBJEKTŮ ZABAGED](https://geoportal.cuzk.cz/Dokumenty/ZABAGED_katalog/CS/){target="_blank"}. Atributy v dodaných datech se mohou jmenovat v některých případech odlišně, ale nabývají příslušných textových hodnot, příp. kódů.



### JEDNODUCHÁ GENERALIZACE

V rámci úlohy si vyzkoušíme některé **generalizační algoritmy**. Máte dodána data pro měřítko 5 tisíc (i teoreticky větší), ale vytváříte mapu měřítka menšího. Je tedy vhodné:

-   aplikovat cenzální výběr na vodní toky a drobné komunikace, příp. některé bodové vrstvy, např. kóty, dále pominout objekty plošně natolik malé, že nebude možné je v měřítku vhodně zobrazit;
-   zblokovat budovy do ploch intravilánů pomocí funkce *Aggregate Polygons* nebo *Delineate Built-Up Areas*;
-   příp. použít další vhodné algoritmy dle ukázky na cvičení.

Není třeba využít všech vrstev ZABAGED (mnohé mohou být po ořezu i prázdné) – uvažte, co má s ohledem na měřítko smysl.


### GENEROVÁNÍ POPISŮ

K mapě s hotovým polohopisem v závěru připojte popis. Mnoho objektů ZABAGED obsahuje atribut *JMENO*, který obsahuje text pro vytvoření popisů. Je také vhodné využít datové sady GeoNames, protože objekty jako sídla, pomístní názvy, orografické celky atp. své názvy v ZABAGED nemají, protože v ZABAGED není odpovídající datová vrstva.

Podobně jako při symbolizaci polohopisu, také texty by měly mít různý charakter (font, řez, velikost, barvu) na základě prvků, které popisují. Klasifikaci GeoNames proveďte podle typů objektů. Vytvoříte-li v tabulce obsahu kategorie, lze je pak převzít na kartě Labels pro vytvoření tříd popisu. 

Podrobnější návod k vytvoření popisu je na [samostatné záložce](../popisy.md) nahoře.

Pozor na kolize anotací navzájem, kolize s mapovým rámem nebo s černými prvky v mapě atd.


### GENEROVÁNÍ VRSTEVNIC

V úloze je možné pracovat s [Image službou nad DMR 5G](https://ags.cuzk.cz/arcgis2/rest/services/dmr5g/ImageServer){target="_blank"} (s rozlišením 2 metry), ze které je možné provést export (viz 1. úloha) a využít jako výškový rastr pro generování vrstevnic.

Pomocí funkce *Contour* vytvořte nad tímto rastrem povrchu vrstevnice s rozestupem 10 m. Každou pátou vrstevnici zvýrazněte (pro běžné použijte hnědou linii 0,16 mm, pro zvýrazněné 0,3 mm). Popis vrstevnic by se řešil obdobně jako u GeoNames, ve vlastnostech *Placement properties* je přímo i styl *Contour placement*, přizpůsobený pro vrstevnice. Pro tuto mapu ale popis vrstevnic řešit nemusíte.

Nezapomeňte mapu doplnit jednoduchým textovým polem, ve kterém bude alespoň název s měřítkem.
Tiráž ani legendu vytvářet nebudete. Ověřte si, že exportujete skutečně v měřítku 1 : 25 000. Rám mapy bude trochu menší než oblast polygonu v zadání, v rámci oblasti se tedy libovolně umístěte. Pozor na okrajové anotace, aby je rám neřezal.



!!! warning "K odevzdání"

    **Mapa vytvořená z vektorových dat ZABAGED (formát PDF)** plus všechna zdrojová dat ve formě MPKX balíčku. Odevzdává se prostřednictvím Moodle. Soubory k odevzdání (do jednoho archívu):

    -   MPKX soubor,
    -   PDF export s mapovým obrazem.

    Technickou zprávu není nutné zpracovat.