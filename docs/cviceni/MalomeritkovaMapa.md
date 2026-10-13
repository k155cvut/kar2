# Úloha 1 – Maloměřítková přehledná mapa

## Zadání

V této úloze bude vaším úkolem vyrobit přehlednou mapu zadané obce s rozšířenou působností (ORP) na papír formátu A3. Mapa bude obecně zeměpisného typu a bude obsahovat základní polohopis (komunikace, sídla, lesní plochy) a členění ORP do nižších správních celků (obce, obce s pověřeným obecním úřadem – OPOÚ).

**Stručný postup**

-   z [webové služby](https://ags.cuzk.cz/arcgis2/rest/services/dmr5g/ImageServer "https://ags.cuzk.cz/arcgis2/rest/services/dmr5g/ImageServer") nad daty dig. modelu reliéfu DMR5G vyseparujte rastr terénu;
-   z něj pomocí Classify připravte hypsometrickou mapu;
-   doplňte mapu o vybrané prvky polohopisu z datové sady DATA200 (silnice a železnice);
-   z datové sady DATA200 vyberte sídla a připravte vrstvu intravilánů;
-   malé obce budou značeny pouze plochou správního území, větší i ploškou sídla;
    z ArcČR500 připravte vrstvu OPOÚ a obcí, postačí bodové.
    
!!! note "Databáze ArcČR je k dispozici na disku S: ve složce data\\ArcGIS\\ArcČR500 4.2.gdb*. *DATA200 jsou tamtéž."

Výsledkem by měla být přehledná mapa ORP, která bude obsahovat hypsometricky zpracovaný výškopis (postačí členění po 100 m; barvy potlačeny pomocí zprůhlednění), základní polohopis a členění ORP na OPOÚ (barevně) a polohu jednotlivých obcí. Mapu jsme doplnili o layout s *Map frame*, ustavili měřítko, ve kterém budou data zobrazena, které zároveň slouží jako referenční měřítko výkresu. 

K úloze proběhne výklad na cvičení, zde připojujeme níže jen stručný výtah.

Mapu s potlačeným výškopisným hypsometrickým podkladem a správním členěním vyznačeným pomocí polygonů s barevnými lemovkami **doplňte o další polohopis**. Konkrétně o silnice a železnice (vrstvy RoadL a RailrdL ve složce TRANS datové sady DATA200). Dále z vrstvy POP > BuiltUpA vyberte ty plošky, které jsou většího charakteru než drobné obdélníčky, ty budou symbolizovat významnější sídla. Vybrat se dají atributovým dotazem na velikost plošky, např. `SHAPE_Area > 1600000`. Tím zůstanou jen polygony větších sídel. Barevné řešení necháváme na Vašem uvážení, pozor ale, aby nedocházelo ke kolizi s podkladovou hypsometrií nebo lemovkami OPOÚ a aby byly vrstvy dobře rozlišitelné.

**Doplňte popis k polygonům sídel a – odpovídající barvou – k plochám obcí s pověřeným obecním úřadem**. Jednotlivé běžné obce není třeba popisovat.

Popisy lze vytvořit následujícím způsobem. Chcete-li zapnout popis pro vrstvu, v jejím kontextovém menu aktivujte *Label features*. Nahoře a vpravo se zpřístupní panely *Label properties*, které obsahují funkce pro generování a úpravu popisů.

Podrobnější návod k vytvoření popisu je na [samostatné záložce](../popisy.md) nahoře. Pozor na kolize anotací navzájem, kolize s mapovým rámem nebo s černými prvky v mapě atd. – popis by vždy měl být čitelný, nekolidovat s dalšími objekty mapy, nepřekážet.

Mapu je potřeba nakonec **doplnit o kompoziční prvky** (výklad k nim viz přednáška). Existují čtyři základní kompoziční prvky (mimo mapového pole), jež musí mapa vždy obsahovat – název mapy, měřítko, legenda a tiráž. Ostatní jsou nepovinné (včetně směrovky – pokud je mapa orientována k severu, směrovka je nadbytečná). V souvislosti s tímto apeluji nepoužívat pro mapy obdobné jako v této úloze Křovákovo zobrazení, resp. systém JTSK. Ten je vytvořen pro specifické katastrální účely a pro SMD, ve svém případě použijte spíše UTM či ETRS89 (oboje v zóně 33 – EPSG kód 326333 pro UTM nebo 3045 pro ETRS89) nebo některé  kuželové zobrazení (např. Lambertovo, Albersovo, kde upravíte střední poledník tak, aby procházel zhruba Vaším územím; v tomto viz KAR1).

Všechny kompoziční prvky lze nalézt v menu *Insert \> Text / Scale bar / Legend*.

**Název mapy** by měl být věcný, výstižný, např.  
ADMINISTRATIVNÍ ČLENĚNÍ ORP CHRUDIM V ROCE 2024  
Název odráží věcné, prostorové a časové vymezení jevu. Používá se zpravidla bezpatkový font (Arial/Helvetica/Tahoma apod.)

**Měřítko mapy** může být grafické nebo číselné. Grafické postačí v případě, že je měřítko nezaokrouhlené na rozumnou hodnotu. Lepší je "méně než více", tedy zdobná měřítka rozdělená na velké množství dílků jsou zbytečná, zcela postačí jedna linie s díly např. 0 a 10 km. 

**Legenda** musí splňovat několik náležitostí, zejména:

-   shodnou velikost znaků v mapě a legendě;  
-   shodnou barevnou a formální vizualizaci;  
-   kopmpletnost – vše co je v mapě, musí být i v legendě a naopak (vč. stupnic);  
-   popis v jednotném čísle.

Umisťuje se do volného prostoru v blízkosti mapy.  

**Tiráž** je text, informující o tvůrci mapy a dalších datech. Měla by obsahovat jméno nebo organizaci tvůrce, datum, použitá podkladová data a příp. další náležitosti. Příkladem může být

!!! quote "Vytvořil Tomáš Janata  <br />v rámci předmětu Kartografie 2  <br />na Stavební fakultě ČVUT v Praze  <br />říjen 2024  <br />použitá data: ArcČR 500, DATA200"

Tiráž postačí menším písmem někde v dolním rohu mapy nikoli kurzívou ani jinak zvýrazněně.

Vytištěnou mapu na formát A3 přiložte k technické zprávě. **Dbejte na kvalitní barevný tisk** a na to, aby nebyly uříznuté okraje (většina tiskáren má jistou "netisknutelnou oblast" listu někde mezi 3 až 5 mm, tedy pro jistotu oblast 5 mm od okraje papíru pro mapový obsah vůbec nevyužívejte.



!!! warning "K odevzdání"

    #### **Technická zpráva bude obsahovat:**

    -   číslo zadání;
    -   název zadané ORP;
    -   stručně postup a použitá data;
    -   jako přílohu vyhotovenou mapu;
    -   dále závěr – s uvedením vlastního zhodnocení práce s informačními a výpočetními zdroji;
    -   bibliografické odkazy na použitou literaturu a zdroje, zpracované podle normy pro bibliografické citace (ČSN ISO 690, ČSN ISO 690-2).

    Technickou zprávu je třeba v požadovaném termínu nahrát do Moodlu (PDF) a v tištěné podobě odevzdat vyučujícímu.
