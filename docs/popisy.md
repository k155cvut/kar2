# Popis v mapách a jeho tvorba v ArcGIS Pro

Popis v mapách (lidově popisy) je důležitou součástí kartografické vizualizace a slouží zejména ke geografickému ukotvení reality. Jeho úkolem je srozumitelně identifikovat a charakterizovat geografické objekty. Kvalitní popis by měl být:

*   **Čitelný:** správná volba písma, velikosti a barvy.
*   **Srozumitelný:** jasné a stručné texty.
*   **Neinvazivní:** neměl by překrývat důležité prvky mapy.
*   **Jednoznačný:** měl by být zřetelně spojen s popisovaným objektem.

## Tvorba popisů v ArcGIS Pro

ArcGIS Pro nabízí dynamické popisování založené na atributech prvků. To znamená, že se popisy automaticky aktualizují při změnách dat. Hlavní nástroje pro popisování najdeme v panelu **Labeling** a okně **Label Class**. Dynamický popis nad danou vrstvou se zapne volbou *Label* v kontextovém menu vrstvy.

### Přístup k nástrojům pro popisování

1.  Vyberte vrstvu v okně **Contents**.
2.  Na kartě **Feature Layer** klikněte na záložku **Labeling**.
3.  Pro detailní nastavení klikněte pravým tlačítkem myši na vrstvu v okně **Contents** a vyberte **Labeling Properties**. Otevře se okno **Label Class**.

### Základní syntaxe pro popisování pomocí Arcade

Arcade je skriptovací jazyk, který se používá v ArcGIS Pro pro tvorbu dynamických popisů a dalších úloh. Zde je několik příkladů:

*   **Popis z jednoho pole:**

    ```arcade
    $feature.NAME
    ```

    Tento výraz zobrazí hodnotu pole *NAME*.

*   **Spojení více polí:**

    ```arcade
    $feature.ULICE + ", " + $feature.NAZEV
    ```

    Tento výraz spojí hodnoty polí *ULICE* a *NAZEV* s čárkou a mezerou.

*   **Podmíněné popisování:**

    ```arcade
    IF($feature.POC_OBYV > 3000, $feature.NAZEV + " (město)", $feature.NAZEV + " (obec)")
    ```

    Tento výraz zobrazí *(město)* za názvem města, pokud má více než 3000 obyvatel.

!!! note "Použít lze také výrazů jazyka Python, VB Script nebo JavaScript"

### Lišta Labeling

Lišta **Labeling** poskytuje rychlý přístup k základním nastavením popisů:

*   **Zapnutí/vypnutí popisů:** První ikona slouží k aktivaci a deaktivaci popisů pro vybranou vrstvu.
*   **Základní symbologie:** Nastavení barvy a velikosti písma.
*   **Efekt halo:** Přidání obrysu (jinak též halo, framing) kolem textu pro zlepšení čitelnosti.
*   **Pozice popisů:** Základní možnosti umístění popisů.

### Panel Placement Properties (Vlastnosti umístění)

Panel **Placement Properties** (dostupný v okně **Label Class**) nabízí detailní nastavení umístění popisů:

*   **Labeling Engine:** Výběr mezi **Standard Label Engine** (základní algoritmy) a **Maplex Label Engine** (pokročilé algoritmy pro husté popisování a liniové prvky). *Maplex* se doporučuje vždy.

*   **Placement:** Nastavení umístění popisů vzhledem k prvkům (např. nad, pod, vedle, uvnitř polygonu).

*   **Conflict Resolution:** Řešení konfliktů mezi popisy (např. překrývání). Možnosti zahrnují:
    *   **Remove Duplicates:** Odstranění duplicitních popisů.
    *   **Never Remove:** Neodstraňovat žádné popisy (může vést k překrývání).
    *   **Priority Ranking:** Nastavení priority popisů pro různé vrstvy.

*   **Fitting Strategy:** Strategie umisťování popisů (např. zalamování textu, zkracování textu).

*   **Label Orientation:** Orientace popisů (např. vodorovně, podél linie).

!!! tip "Převzetí symboliky z tabulky obsahu"

    Pro vytvoření *tříd* popisu, jež mají být vizuálně odlišné, je možné převzít vytvořenou symboliku z tabulky obsahu. Děje se tak pomocí volby *Class > Create label class from symbology* v hodním panelu *Labeling*.


<figure markdown>
  ![Labeling](../assets/Popisy/layout_panely.png "Rozložení popisovacích funkcí v programu"){ width=800px }
  <figcaption>Rozložení popisovacích funkcí v programu</figcaption>
</figure>


!!! note "Vytvoření popisu vrstvě – praktický návod"

    Popisy lze vytvořit následujícím způsobem. Chcete-li zapnout popis pro vrstvu, v jejím kontextovém menu aktivujte *Label*. Nahoře a vpravo se zpřístupní panely *Labeling*, resp. *Label properties*, které obsahují funkce pro generování a úpravu popisů.

    Pro jednotlivé třídy popisu si nastavte, z jakého atributu se popis vyčítá, vlastnosti písma (tlačítko *Symbol*) a umisťování popisů (tlačítko *Placement properties*). Také zkontrolujte, že máte na záložce *General* v nastavení výkresu definováno referenční měřítko dle skutečného měřítka své mapy.

    Takto vytvořený popis je dynamický – překresluje se při každém pohybu mapou. Trvalý popis ve formě třídy prvků z něj vytvoříte převedením do tzv. anotací pomocí volby *Convert labels to annotation* v kontextovém menu třídy prvků. Pozor ovšem – u vytvořené anotační třídy již nelze měnit font, barvu apod. Ovšem lze tuto třídu editovat jako jakoukoli jinou vrstvu a případně upravovat jednotlivé anotace, otáčet je, přesouvat, mazat apod. Převod do anotací je tedy vhodné provést až ve chvíli, kdy jsme spokojeni s globálním nastavením popisu dané třídy prvků.

    ### Příklad použití Label Engine pro popis linií

    1.  V okně **Label Class** zvolte **Maplex Label Engine**.
    2.  V sekci **Placement** vyberte vhodný styl umístění pro linie (např. **Curved** pro zakřivené linie, **Straight** pro rovné linie).
    3.  V sekci **Fitting Strategy** můžete nastavit zalamování textu nebo opakování popisů podél linie.

    !!! warning "Pozor na kolize anotací navzájem, kolize s mapovým rámem nebo s černými prvky v mapě atd. – popis by vždy měl být dostatečně velký, čitelný, nepřekrývat se s dalšími objekty mapy, nepřekážet"




