# Úloha 2 – Plán města v kartografickém software OCAD

## Zadání

V měřítku 1 : 10 000 vyhotovte v programu OCAD mapovou kresbu autorského originálu plánu zadaného města. Plán bude zpracován podle kartografických zásad ve vytvořeném znakovém klíči.

Plán výřezu města bude na listu A4 zabírat plochu 200×200 mm, zbytek listu využijte pro legendu, tiráž, měřítko a název mapy. Nezapomeňte, že i legenda podléhá kartografickým zásadám.


#### Podkladové rastrové soubory

-   podkladový soubor s výřezem mapy uložte např. ve formátu PNG nebo TIFF a stáhněte ze vhodného zdroje (mapy.cz či jiné webové mapy) nebo použijte sken tištěného plánu města.

Jako podklad mpžete využít také WMS službu ZTM5 na adrese [https://ags.cuzk.cz/arcgis1/services/ZTM/ZTM5/MapServer/WMSServer](https://ags.cuzk.cz/arcgis1/services/ZTM/ZTM5/MapServer/WMSServer).

####  Mapový soubor se znakovým klíčem

-   Využijte šablonu pojmenovanou City Map, kterou vhodně upravíte.

!!! tip "Vybírat můžete obecně z měst nad 5 tisíc obyvatel, např. z přehledu níže"

    <style>
        .city-columns {
            display: flex;
            flex-wrap: wrap;
        }

        .city-column {
            flex: 1;
            font-size: 0.8em; 
            font-weight: bold;
            color: grey;
            box-sizing: border-box;
            min-width: 150px;
            height: fit-content;
        }

        ul {
            list-style-type: none;
            padding: 0;
            margin: 0;
        }
    </style>

    <div class="city-columns">
    <div class="city-column">
        <ul>
            <li>Aš</li>
            <li>Benešov</li>
            <li>Beroun</li>
            <li>Bílina</li>
            <li>Blansko</li>
            <li>Bohumín</li>
            <li>Boskovice</li>
            <li>Brandýs n. L. – St. Boleslav</li>
            <li>Brno</li>
            <li>Bruntál</li>
            <li>Břeclav</li>
            <li>Čáslav</li>
            <li>Čelákovice</li>
            <li>Česká Lípa</li>
            <li>Česká Třebová</li>
            <li>České Budějovice</li>
            <li>Český Krumlov</li>
            <li>Český Těšín</li>
            <li>Děčín</li>
            <li>Dobříš</li>
            <li>Domažlice</li>
            <li>Dvůr Králové nad Labem</li>
            <li>Frenštát pod Radhoštěm</li>
            <li>Frýdek-Místek</li>
            <li>Frýdlant nad Ostravicí</li>
            <li>Havířov</li>
            <li>Havlíčkův Brod</li>
            <li>Hlinsko</li>
            <li>Hlučín</li>
            <li>Hodonín</li>
            <li>Holešov</li>
            <li>Hradec Králové</li>
            <li>Hranice</li>
            <li>Humpolec</li>
            <li>Cheb</li>
            <li>Chodov</li>
        </ul>
    </div>
    <div class="city-column">
        <ul>
            <li>Chomutov</li>
            <li>Chotěboř</li>
            <li>Chrudim</li>
            <li>Ivančice</li>
            <li>Jablonec nad Nisou</li>
            <li>Jaroměř</li>
            <li>Jeseník</li>
            <li>Jičín</li>
            <li>Jihlava</li>
            <li>Jindřichův Hradec</li>
            <li>Jirkov</li>
            <li>Kadaň</li>
            <li>Karlovy Vary</li>
            <li>Karviná</li>
            <li>Kladno</li>
            <li>Klášterec nad Ohří</li>
            <li>Klatovy</li>
            <li>Kolín</li>
            <li>Kopřivnice</li>
            <li>Kralupy nad Vltavou</li>
            <li>Krnov</li>
            <li>Kroměříž</li>
            <li>Krupka</li>
            <li>Kuřim</li>
            <li>Kutná Hora</li>
            <li>Kyjov</li>
            <li>Lanškroun</li>
            <li>Liberec</li>
            <li>Litoměřice</li>
            <li>Litomyšl</li>
            <li>Litovel</li>
            <li>Litvínov</li>
            <li>Louny</li>
            <li>Lovosice</li>
            <li>Lysá nad Labem</li>
            <li>Mariánské Lázně</li>
        </ul>
    </div>
    <div class="city-column">
        <ul>
            <li>Mělník</li>
            <li>Milovice</li>
            <li>Mladá Boleslav</li>
            <li>Mohelnice</li>
            <li>Moravská Třebová</li>
            <li>Most</li>
            <li>Náchod</li>
            <li>Neratovice</li>
            <li>Nové Město na Moravě</li>
            <li>Nové Město nad Metují</li>
            <li>Nový Bor</li>
            <li>Nový Jičín</li>
            <li>Nymburk</li>
            <li>Olomouc</li>
            <li>Opava</li>
            <li>Orlová</li>
            <li>Ostrava</li>
            <li>Ostrov</li>
            <li>Otrokovice</li>
            <li>Pardubice</li>
            <li>Pelhřimov</li>
            <li>Písek</li>
            <li>Plzeň</li>
            <li>Poděbrady</li>
            <li>Praha</li>
            <li>Prachatice</li>
            <li>Prostějov</li>
            <li>Přelouč</li>
            <li>Přerov</li>
            <li>Příbram</li>
            <li>Rakovník</li>
            <li>Rokycany</li>
            <li>Roudnice nad Labem</li>
            <li>Rožnov pod Radhoštěm</li>
            <li>Rumburk</li>
            <li>Rychnov nad Kněžnou</li>
        </ul>
    </div>
    <div class="city-column">
        <ul>
            <li>Říčany</li>
            <li>Slaný</li>
            <li>Sokolov</li>
            <li>Strakonice</li>
            <li>Studénka</li>
            <li>Sušice</li>
            <li>Svitavy</li>
            <li>Šternberk</li>
            <li>Šumperk</li>
            <li>Tábor</li>
            <li>Tachov</li>
            <li>Teplice</li>
            <li>Tišnov</li>
            <li>Trutnov</li>
            <li>Třebíč</li>
            <li>Třinec</li>
            <li>Turnov</li>
            <li>Uherské Hradiště</li>
            <li>Uherský Brod</li>
            <li>Uničov</li>
            <li>Ústí nad Labem</li>
            <li>Ústí nad Orlicí</li>
            <li>Valašské Meziříčí</li>
            <li>Varnsdorf</li>
            <li>Velké Meziříčí</li>
            <li>Veselí nad Moravou</li>
            <li>Vlašim</li>
            <li>Vrchlabí</li>
            <li>Vsetín</li>
            <li>Vysoké Mýto</li>
            <li>Vyškov</li>
            <li>Zábřeh</li>
            <li>Zlín</li>
            <li>Znojmo</li>
            <li>Žatec</li>
            <li>Žďár nad Sázavou</li>
        </ul>
    </div>
    </div>



## Pokyny pro zpracování

!!! tip "Mnoho užitečných informací k OCADu a kartografii jako takové naleznete na webu [kartografie.fsv.cvut.cz](http://kartografie.fsv.cvut.cz/)"

Při zpracování plánu využijte vhodných dat, např. OpenStreetMap, není nutné většinu polohopisu vektorizovat. Postup připojení dat OSM do OCADu byl vykládán na cvičení. Je třeba použít 64bitový OCAD z důvodu kompatibility s ODBC databázovým rozhraním. Pro ergonomičtější práci v softwaru doporučuji vypnout kontextové menu (v *Options* \> *OCAD Preferences* hned první zaškrtávátko, dále lze v sekci *Select* nastavit jen objekty zcela uvnitř výběru). 

V krátkosti další postup možného zpracování úlohy pro ty, kteří nestihnou výklad na cvičení:

-   upravit data OSM (např. v ArcGIS) na vhodný rozsah (o trochu více než požadované 2×2 km – pozor, abyste nepracovali v systému Web Mercator, kde platí zkreslení délek a ploch), převést do metrického souř. systému (ideálně ne S-JTSK, lépe např. UTM);
-   jednotlivě připojovat SHP soubory ze zrcadla OSM do OCAD a nastavit symboliku (doporučené pořadí – plochy a linie první, např. *Railways*, *Roads*, *Landuse*, *Waterways*, *Water_A*, později i budovy a bodové prvky – *Buildings*, *Pois* atd.);
-   pro import použijte *File \> Import*, vyberte příslušný SHP, databázový typ je *MS Access 2010*, primární klíč *osmid*, layer information na *do not import* a spusťte import;
-   vyrobte si liniový symbol dostatečně široký (1–2 mm) pro mapový rám a vyznačte zájmovou oblast 2×2 km;
-   pro symbolizování vrstev je vhodné využít atribut FCLASS (v prostředí OCAD výběr pomocí SQL Query,  např. <br />`[FCLASS] IN ('residential', 'living_street')` vybere všechny běžné ulice v rezidenční zástavbě, <br />`[FCLASS] = 'secondary'` vybere silnice II. tříd apod.; u budov je namísto *FCLASS* použit *TYPE*;
-   strukturu OpenStreetMap můžete pročíst v [OSM Wiki](https://wiki.openstreetmap.org/wiki/Main_Page);
-   nezapomeňte vytvořit bodové symboly pro body zájmu (úřad, hotel, divadlo, policie apod.) a odlišit budovy 'veřejné' od 'obyčejných';
-   před aplikací popisů nezapomeňte, aby ulice a další popisované prvky měly dostatečnou šíři a aby použité fonty měly dostatečnou
    velikost (např. písmena vysoká 1 mm opravdu nebudou k přečtení);
-   popis ulic můžete vyrobit pomocí funkce *Database* \> *Add text from Database records*: vyberte dataset ulic, text field je *NAME*, podmínka dle požadované symbolizace, např. `[FCLASS] = 'secondary'`, vyberte příslušný symbol s požadovaným textem (lze využít/upravit symboly předdefinované s písmenem S v ikoně), nezapomeňte změnit
    *Replace* na *Add new objects*, jinak vám písma nahradí kresbu ulic;
-   písma je možno upravit, aby byly zarovnané na linii středem, nikoli patkou (v nastavení symbolu sekce *Paragraph \> Alignment*);
-   doplňte popisy i k objektům mimo ulice a náměstí (POI, areály, městské čtvrtě, řeka, žel. stanice apod.);
-   ořežte kresbu mimo mapový rám např. pomocí *Object \> Crop objects* nebo ručně, příp. vymaskujte polygony bílé barvy;
-   doplňte kompoziční řešení (např. dle zaslaných příkladových map), tedy název mapy, měřtko, tiráž a legendu;
-   legendu lze vygenerovat pomocí *Layout \> Add map legend*, nagenerují se buď všechny symboly nebo jen ty, které jsou v mapě použité (lze zvolit), pro popis položek se přebírají názvy symbolů, které je vhodné před generováním legendy upravit (česky, v jednotném čísle, s malým prvním písmenem, dostatečně konkrétně); chcete-li vygenerovat legendu jen pro určité symboly, lze je v okně se symboly označit, pak vybrat pravým tl. *Select \> Invert*, čímž se vybere zbytek, a volbou *Hide* nastavit skrytí; v dialogu tvorby legendy se pak odškrtne hodnota *Also show hidden symbols* a legenda se vygeneruje jen pro Vámi vybranou sadu symbolů;
-   nezapomeňte na vhodnou hierarchizaci legendy (tematické prvky do popředí, prvky podobých kategorií k sobě).



!!! warning "K odevzdání"

    ### **Požadované výstupy:**

    -   **Mapový soubor OCD** se zpracovanou kresbou plánu v elektronické formě v systému Moodle – jako OCD soubor s názvem cislozadani_prijmeni.ocd;
    -   **Vytištěný plán** v měřítku 1 : 10 000 na papír A4 jako součást technické zprávy.

    **Technická zpráva** bude obsahovat:

    -   číslo zadání, zvolené město;
    -   stručně údaje o hlavních bodech postupu;
    -   výstupy – název výsledného souboru + vytištěný plán 1 : 10 000;
    -   shrnutí, vlastní zkušenosti/problémy, názory.
