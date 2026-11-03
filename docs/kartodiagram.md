# Kartodiagram
Kartodiagram (angl. *diagram map*) je metoda tematické kartografie, která využívá diagramy proměnlivé velikosti k vyjádření kvantitativních charakteristik geografických jevů. Používá se především pro znázornění **absolutních hodnot** (např. počtu obyvatel, objemu produkce nebo intenzity dopravy). Velikost diagramu odpovídá hodnotě zobrazovaného jevu, případně může diagram vyjadřovat také jeho vnitřní strukturu.

## Základní typy kartodiagramů

**Podle geometrie:**

- **Bodový (figurální)** – diagram je umístěn v konkrétním bodě (např. počet obyvatel města).
- **Plošný** – diagram se vztahuje k územní jednotce a obvykle se umísťuje do jejího středu (např. počet obyvatel kraje).
- **Liniový (stuhový)** – šířka linie nebo pásu vyjadřuje velikost jevu (např. intenzitu dopravy).

**Podle množství vyjádřených parametrů:**

- **Jednoduchý kartodiagram** – vyjadřuje velikost jediného jevu, 
- **Strukturní** – vyjadřuje pouze vnitřní strukturu jevu, velikost všech digramů je stejná (např. kruhový výsečový diagram).
- **Součtový** – vyjadřuje vnitřní strukturu jevu a jeho celkovou hodnotu (např. kruhový výsečový diagram).
- **Srovnávací** – sestava dvou a více kartodiagramů umožňující srovnání vybraného jevu, nejčastěji se využívá pro srovnání vývoje v čase či se zvolenou střední hodnotou.



    <figure markdown>
     ![Dělení kartodiagramů dle složitosti (množství vyjádřených parametrů) dle Miklína (2018)](../assets/Uloha3/kartodiagram_Miklin.png "Dělení kartodiagramů dle složitosti (množství vyjádřených parametrů) dle Miklína (2018)"){ width=800px }
    <figcaption>Dělení kartodiagramů dle složitosti (množství vyjádřených parametrů) dle Miklína (2018)</figcaption>
    </figure>   

### Zásady tvorby kartodiagramů

- Zvolit vhodný typ diagramu a funkční stupnici podle charakteru dat.
- Zajistit čitelnost i nejmenších diagramů a omezit jejich vzájemné překrývání.
- Při překryvu kruhových diagramů umisťovat menší diagramy nad větší.
- Používat přehlednou legendu vysvětlující velikost diagramů a případně jejich vnitřní strukturu.

## Hodnotové (diagramové) měřítko
 **Hodnotové (diagramové) měřítko** je funkce (zobrazení), která zobrazuje hodnotu jevu do velikosti znaku. Velikostí znaku se rozumí např. výška, plocha či objem znaku / diagramu. Hodnotové měřítko má nejčastěji podobu srovnávacího obrazce neboli tzv.velikostní stupnice. Zvolený obrazec / symbol může nabývat podoby figurálního znaku , plošného geometrického obrazce či pseudoprostorového geometrického obrazce. Podle typu symbolu pak rozlišujeme parametr, pomocí kterého kódujeme hodnotu jevu (figurální symbol-výška, geometrický symbol-plocha, pseudoprostorový symbol-objem). Díky hodnotovému měřítku může uživatel mapy odvozovat a srovnávat hodnoty zobrazeného jevu v mapě. 

Rozlišujeme dvě základní podoby diagramového měřítka:

- **Plynulá / funkční stupnice** – každé hodnotě jevu je přiřazen diagram s uečitou hodnotou parametru. Z velikostní stupnice lze vyčíst velikost znaku pro každou hodnotu jevu. 
- **Intervalová stupnice** – hodnoty jsou rozděleny do intervalů, jimž odpovídají předem stanovené velikosti diagramů. Velikosti diagramů jsou odvozeny pro střední hodnoty intervalu.


### Tvorba hodnotového měřítka
Při tvorbě mapy v prostředí ArcGIS software nelze automaticky vygenerovat plynulou / funkční stupnici. Software automaticky generuje pouze jednoduché diagramové měřítko, v rámci něhož jsou uvedeny pouze vybrané (zaokrouhlené) hodnoty jevu. Použití zjednodušené verze je samozřejmě přípustné, vhodnější je však využít klasické formy plynulé / funkční stupnice.

Pro tvorbu plynulé / funkční stupnice lze využít tyto nástroje:

-   Webový nástroj [**Value-scale generator**](https://radiat.pythonanywhere.com/)
-   Python toolbox pro ArcGIS **ValueScale.pyt** (viz Shares, složka ``\K155\Public\155KAR2\ULOHA_3_TEM_KART\ValueScale``)

    **pozn. toolbox byl odvozen z webového nástroje Value-scale generator pro potřeby předmětu 155KAT2*


    <figure markdown>
     ![Srovnání klasické podoby funkční / plynulé stupnice (vlevo) vs zjednodušené verze diagramového měřítka z ArcGIS (vpravo)](../assets/Uloha3/DiagramoveMeritko_plynule_srovnani.png "Srovnání klasické podoby funkční / plynulé stupnice (vlevo) vs zjednodušené verze diagramového měřítka z ArcGIS (vpravo)"){ width=600px }
    <figcaption>Srovnání klasické podoby funkční / plynulé stupnice (vlevo) vs zjednodušené verze diagramového měřítka z ArcGIS (vpravo)</figcaption>
    </figure>   




## Použité zdroje

- Bláha, J, D.: Vybrané okruhy z geografické kartografie. Ústí nad Labem: UJEP, 2017. ISBN: 978-80-7561-092-8.
- Jaroš, J., Lysák, J.: Kartodiagram. In: Moderní geoinformační metody ve výuce GIS, 2014. Dostupné z: [https://drive.google.com/file/d/1q4zpn4ZXQr7XSeBQT3GEvf9cmv6tOsEx/view](https://drive.google.com/file/d/1q4zpn4ZXQr7XSeBQT3GEvf9cmv6tOsEx/view)
- KAŇOK, Jaromír (1999). Cartogram and Cartodiagram – Determination of Objective Scale. *Geografie*, 104(4), 268–281. https://doi.org/10.37040/geografie1999104040268
- KAŇOK, Jaromír a Vít VOŽENÍLEK (2008). Kartodiagramy. GeoBusiness, s. 36–39. Dostupné z: [https://www.dibavod.cz/data/gis_kartografie/kart_kardiogramy.pdf](https://www.dibavod.cz/data/gis_kartografie/kart_kardiogramy.pdf)
- Miklín, J., R. Dušek, L. Krtička a O. Kaláb: Tvorba map. Ostrava: Ostravská univerzita, 2018. ISBN: 978-80-7599-017-4. Dostupné z: [https://tvorbamap.osu.cz/ke-stazeni/](https://tvorbamap.osu.cz/ke-stazeni/)
- VEVERKA, Bohuslav a Růžena ZIMOVÁ (2004). *Topografická a tematická kartografie 10*. Praha: ČVUT.
- Voženílek V.: Aplikovaná kartografie I.: tematické mapy, 2. vydání. Olomouc: Univerzita Palackého, 2001. ISBN: 80-244-0270-X.
- Voženílek, V. a kol.: Metody tematické kartografie – vizualizace prostorových jevů. Olomouc: Univerzita Palackého, 2011. ISBN: 978-80-244-2790-4.
- GISKA – GIS a kartografie…: Kartografie [online]. Dostupné z: [http://giska.cz/kartografie/](http://giska.cz/kartografie/) [cit. 14. 11. 2025].



--------------






