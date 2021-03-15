# Crashkurs für Power BI Datenvisualisierung
<!-- 
## TODO für neuen Kurs
 -->
<!-- **Tipp für Bilder und Videos**: am einfachstes ist es die Bilder und Videos direkt in das Eingabefeld eines neuen GitHub Issues einzufügen, dadurch wird das Bild/Video direkt auf GitHub hochgeladen und die URL kann ins README kopiert werden. -->
<!-- 
<video preload="none" poster="https://user-images.githubusercontent.com/538415/106586754-1d170d00-6549-11eb-8e7d-d24e0ea4cb13.jpg" src="https://user-images.githubusercontent.com/538415/106586882-3ddf6280-6549-11eb-9db5-9f1ddb7552cc.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="GitHub Upload" src="https://user-images.githubusercontent.com/538415/106586824-2d2eec80-6549-11eb-8348-9ddf62f08607.gif"/></video>
 -->
# Teil 1: Daten finden

Rufe den Open Data Katalog der Stadt Zürich auf unter: «[https://data.stadt-zuerich.ch/](https://data.stadt-zuerich.ch/)». Wir müssen drei Datensätze herunterladen

1. Glasfasernetz Leistungsdaten der Stadt Zürich
1. Glasfasernetz Gebiete der Stadt Zürich
1. Bruttolastgang der Stadt Zürich

## [Daten] Glasfasernetz Leistungsdaten

- **Schritt 1:** Suche nach Zürich Glasfasernetz Leistungsdaten. Gebe dazu im Suchfeld beispielsweise den Begriff «Glasfasernetz» und «Leistungsdaten» ein. Beim Eintippen des Suchbegriffs werden bereits passende Vorschläge zu auf dem Katalog vorkommenden Daten angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Zürich Glasfasernetz Leistungsdaten](https://data.stadt-zuerich.ch/dataset/ewz_leistungsdaten_zuerinet)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. Weiterführende wichtige Informationen sind auch unter *Bemerkungen* zu finden. 
    ```
    Der Datensatz enthält die gemessenen Leistungsdaten (Up- und Downstream) in Bit pro Sekunde (pro «Core Location») sim Glasfasernetz der Stadt Zürich. Die Messdaten werden für jede Viertelstunde pro Knotenpunkt, aggregiert (Durchschnitt), ausgewiesen.
    ```
  <img src="https://user-images.githubusercontent.com/7482996/110360261-cd8f9980-803e-11eb-9357-e6d6e21608a5.png" alt="Suchresultatvorschau"/>

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort einen Datensatz aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden. 
  - Es gibt ein File pro Monat. Es wäre besser, alle Datei herunterlanden und in einem Folder kopieren. Wir werden bis Januar 2021 39 Files haben. 

## [Daten] Glasfasernetz Gebiete

- **Schritt 1:** Suche nach Zürich Glasfasernetz Versorgungszonen. Gebe dazu im Suchfeld beispielsweise den Begriff «Glasfasernetz» und «Versorgungszonen» ein. Beim Eintippen des Suchbegriffs werden bereits passende Vorschläge zu auf dem Katalog vorkommenden Daten angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Zürich Glasfasernetz Versorgungszonen](https://data.stadt-zuerich.ch/dataset/ewz_gebiete_zuerinet)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. 

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort den «ewz_gebiete_zuerinet.json» aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden. 

- **Schritt 3:** Power BI würde diese «[GeoJSON-Datei](https://de.wikipedia.org/wiki/GeoJSON)» im «[TopoJSON-Format](https://en.wikipedia.org/wiki/GeoJSON#TopoJSON)» benötigen. Zur Konvertierung in Topojson können wir das «[MapShaper Portal](https://mapshaper.org/)» verwenden. Wählen Sie nach dem Importieren die Option "Export", wählen Sie «TopoJSON» aus und laden Sie die Datei herunter. Geben Sie die Dateierweiterung "topojson" für zukünftige Referenzen an. 

  <img src="https://user-images.githubusercontent.com/7482996/110362882-27459300-8042-11eb-93ec-7f2021736b0e.png" width=400 alt="MapShaper Import"/> 
  <img src="https://user-images.githubusercontent.com/7482996/110363068-6247c680-8042-11eb-89a1-97c12bf99a8d.png", width=400 alt="MapShaper Export"/>

## [Daten] Bruttolastgang

- **Schritt 1:** Suche nach Zürich Viertelstundenwerte zum Bruttolastgang elektrische Energie. Gebe dazu im Suchfeld beispielsweise den Begriff «Bruttolastgang» ein. Beim Eintippen des Suchbegriffs werden bereits passende Vorschläge zu auf dem Katalog vorkommenden Daten angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Viertelstundenwerte zum Bruttolastgang elektrische Energie der Stadt Zürich](https://data.stadt-zuerich.ch/dataset/ewz_bruttolastgang_stadt_zuerich)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. Weiterführende wichtige Informationen sind auch unter *Bemerkungen* zu finden. 

  > ***!!!*** Der Bruttolastgang wird basierend auf zahlreichen Messungen zur Einspeisung und zum Verbrauch berechnet. Einzelne Messungen können dabei fehlen und müssen nachträglich nochmals eingepflegt werden.

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort 
  «2020_ewz_bruttolastgang.csv» Datensatz aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden. 

<!-- ## [Daten] Hundebestand
Zur Beantwortung der Fragestellung benötigen wir die dazu relevanten Daten. Wir müssen uns zuerst auf die Suche machen:

- **Schritt 1:** Rufe den Open Data Katalog der Stadt Zürich auf unter: [https://data.stadt-zuerich.ch/](https://data.stadt-zuerich.ch/)
- **Schritt 2:** Suche nach Hundebestand pro Stadtquartier und Jahr. Gebe dazu im Suchfeld beispielsweise den Begriff «Hunde» und «Stadtquartier» ein. Beim Eintippen des Suchbegriffs werden bereits passende Vorschläge zu auf dem Katalog vorkommenden Daten angezeigt.  
<img src="https://user-images.githubusercontent.com/2479732/103986721-847caf80-518b-11eb-839c-95953ead6f67.png" alt="Suchresultatvorschau"/>
- **Schritt 3:** 
  - Wähle das Dataset «[Hundebestand der Stadt Zürich](https://data.stadt-zuerich.ch/dataset/sid_stapo_hundebestand)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. Hier sehen wir beispielsweise, dass es Angaben zu Hundehaltenden und Hunden gibt. Bereits in der ersten Attributbeschreibung zur technischen Identifikationsnummer der hundehaltenden Personen (`HALTER_ID`) erfahren wir eine sehr wichtige Information: ein Record (eine Zeile) im Datensatz entspricht einem Hund. Wenn demnach der gleiche Hundehaltende zwei Hunde hat, so kommt seine ID im Datensatz zweimal vor. Dank der Beschreibung können wir ebenfalls sicher sein, dass die Stadtquartiere in den Daten vorkommen. Weiterführende wichtige Informationen sind auch unter *Bemerkungen* zu finden. 
  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort den aktuellsten Datensatz (2020) aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden.
  
  <video preload="none" poster="https://user-images.githubusercontent.com/538415/105815933-e888db80-5fb3-11eb-9074-58310dfb5f96.jpg" src="https://user-images.githubusercontent.com/2479732/105727018-ee86aa00-5f2a-11eb-8f33-90a597fd2658.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="01_hundebestand_download" src="https://user-images.githubusercontent.com/2479732/103988953-3669ab00-518f-11eb-99ab-0ca362d5cb0c.gif"/></video>

- **Schritt 4:** Suche nach einem Datensatz, der die Anzahl Kleinkinder pro Stadtquartier und Jahr beinhaltet. Da für die Definition eines Kleinkindes das Alter relevant ist, suchen wir also einen Datensatz, welcher das Alter der Bevölkerung nach Stadtquartier und Jahr beinhaltet. Gib daher im Suchfeld beispielsweise die Begriffe «Alter» und «Stadtquartier» ein. Als [Suchresultat](https://data.stadt-zuerich.ch/dataset?q=alter+stadtquartier&sort=score+desc%2C+date_last_modified+desc) erscheinen nun aber 35 Datensätze. Wir sollte daher noch einen besseren Begriff wählen. Verwende daher die Begriffe «Altersjahr» und «Stadtquartier», dadurch sind es nur noch 8 [Resultate](https://data.stadt-zuerich.ch/dataset?q=altersjahr+stadtquartier&sort=score+desc%2C+date_last_modified+desc).

- **Schritt 5:** Für unsere Fragestellung ist der Datensatz «[Bevölkerung nach Stadtquartier, Herkunft, Geschlecht und Alter, seit 1993](https://data.stadt-zuerich.ch/dataset/bev_bestand_jahr_quartier_alter_herkunft_geschlecht_od3903)» am geeignetsten. Er beinhaltet zwar mehr Informationen als wir benötigen (die Herkunft oder das Geschlecht interessieren uns eigentlich weniger), aber wir werden sie in einem späteren Schritt mit Excel herausfiltern.
 
- **Schritt 6:** Lies nun auch wieder die Metadaten zum Datensatz und gehe gleich wie in **Schritt 3** vor, um den Datensatz auf Deinen Computer herunter zu laden.

- **Schritt 7:** Du hast nun die beiden für unsere Fragestellung relevanten Datensätze gefunden und heruntergeladen. Sie heissen `20200306_hundehalter.csv` (Hunde) und `BEV390OD3903.csv`(Bevölkerungsdaten). Kopiere diese beiden Datensätze nun aus dem Downloadverzeichnis Deines Computers und lege sie in ein Verzeichnis, wo Du an den noch folgenden Schritten weiter arbeiten kannst. 

Damit ist unser erster Teil zum Thema «Daten finden» beendet. Solltest Du später einmal für eine andere Fragestellung auf dem [Open Data Katalog der Stadt Zürich](https://data.stadt-zuerich.ch) nicht fündig werden, können auch viele andere Open Data Quellen konsultiert werden. Auf nationaler Ebene werden unter [opendata.swiss](https://opendata.swiss) sämtliche offenen Verwaltungsdaten von verschiedenen Bundesstellen, anderen Kantonen und Städten angeboten.  -->

# Teil 2: Power BI

## CSV... what?
Eines der Grundprinzipien von Open Data ist, dass die Datensätze in **nicht-proprietären Formaten** veröffentlicht werden sollen. Sprich, für die Verwendung der Daten sollen die AnwenderInnen nicht auf kommerzielle Software angewiesen sein. Damit soll allen die gleiche Möglichkeit gegeben werden, mit den Daten arbeiten zu können. Das Excelformat (.xls oder .xlsx) ist ein Beispiel eines proprietären Datenformats, weil es zur Verwendung Excel erfordert.

Das Standardformat für tabellarische Daten ist daher [CSV](https://de.wikipedia.org/wiki/CSV_(Dateiformat)). CSV steht für **C**omma-**s**eparated **v**alues (komma-getrennte Werte).

**CSV-Beispiel:** 

CSV-Dateien haben meistens auf der ersten Zeile eine Spaltenüberschrift und auf den nachfolgenden Zeilen dann die kommaseparierten Werte.
<pre>
"zeitpunkt","bruttolastgang","status"
"2020-01-01T00:15",66546.656045,"E"
"2020-01-01T00:30",66018.362440,"E"
"2020-01-01T00:45",65272.630020,"E"
"2020-01-01T01:00",64385.925397,"E"
"2020-01-01T01:15",63578.900426,"E"
"2020-01-01T01:30",63105.155989,"E"
"2020-01-01T01:45",62287.860786,"E"
"2020-01-01T02:00",61283.998490,"E"
</pre>

Werte zwischen Anführungszeichen sind entweder Texte oder Datumswerte.
Wo keine Anführungszeichen stehen, handelt es sich um numerische Werte.
Die Kodierung für Unicode-Zeichen ist dabei standardmässig [UTF-8](https://de.wikipedia.org/wiki/UTF-8).
Der angezeigte CSV-Auszug oben repräsentiert die folgende Tabelle in Excel:

![Darstellung Excel](https://user-images.githubusercontent.com/2479732/104014716-cc173180-51b3-11eb-9440-3d87d2fb6128.png)
## Median?

<img src="https://user-images.githubusercontent.com/7482996/110783095-3dcd3380-8268-11eb-91a5-978d0524eae6.png"/>


## Power BI Desktop - kurze GUI Intro 

### Query Editor

Hier ist eine sehr kurze Einführung in die Power BI-Schnittstelle. Für eine detaillierte Beschreibung schauen Sie bitte auf die Seite von «[Microsoft](https://docs.microsoft.com/de-CH/power-bi/transform-model/desktop-query-overview)».

- Power BI Desktop verfügt über drei Ansichten:

  - ***Berichtsansicht.*** Hier entwerfen Sie mithilfe selbst erstellter Abfragen ansprechende Visualisierungen, ordnen diese wie gewünscht und bei Bedarf auf mehreren Seiten an und geben Sie für andere Benutzer frei
  - ***Datenansicht.*** Hier können Sie die Daten Ihres Berichts im Datenmodellformat anzeigen und Measures hinzufügen, neue Spalten erstellen und Beziehungen verwalten
  - ***Beziehungsansicht.*** Hier können Sie eine grafische Darstellung der Beziehungen abrufen, die in Ihrem Datenmodell eingerichtet wurden, und diese je nach Bedarf verwalten oder ändern.

  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-view-icons.png"/>

- Sie können den Power Query-Editor aufrufen, indem Sie auf der Registerkarte Start auf die Option Abfragen bearbeiten klicken.
  
  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-transform.png"/>

- Nach dem Herstellen einer Datenverbindung sieht der Power Query-Editor wie folgt aus:

  1. Im Menüband sind jetzt viele Schaltflächen aktiv, über die Sie die Daten in der Abfrage interaktiv bearbeiten können.

  1. Im linken Bereich sind die Abfragen aufgelistet und können ausgewählt, angezeigt und strukturiert werden.
  
  1. Im mittleren Bereich werden die Daten der ausgewählten Abfrage angezeigt und können dort strukturiert werden.
  
  1. Der Bereich Abfrageeinstellungen wird angezeigt. Hier sind die Eigenschaften der Abfrage und die angewendeten Schritte aufgelistet.

  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-with-data-connection.png"/>

- Wenn Sie mit Ihrer Abfrage zufrieden sind, klicken Sie im Dateimenü des Power Query-Editors auf ***Close & Apply*** (Schliessen und anwenden). Mit dieser Aktion werden die Änderungen angewendet und der Editor geschlossen.
    
    <img src="https://user-images.githubusercontent.com/7482996/110667557-a960c380-81ca-11eb-8e93-9326e72af365.png"/>

### Report Builder

  Sie könnten längere Version auf dem Microsoft Portal finden: «(Erstellen von Berichten)[https://docs.microsoft.com/de-CH/power-bi/fundamentals/desktop-getting-started]»

- In der Power BI Desktop-Ansicht Bericht können Sie Visualisierungen und Berichte erstellen. Die Ansicht Bericht besteht aus sechs Hauptbereichen:
  
  1. Das Menüband im oberen Bereich, in dem häufige Aufgaben in Verbindung mit Berichten und Visualisierungen angezeigt werden.
  1. Der Canvasbereich, in dem Visualisierungen erstellt und angeordnet werden.
  1. Der Registerkartenbereich „Seiten“ am unteren Rand, in dem Sie Berichtsseiten auswählen oder hinzufügen können.
  1. Der Bereich **Filter**, in dem Sie Datenvisualisierungen filtern können.
  1. Der Bereich **Visualisierungen**, in dem Sie Visualisierungen hinzufügen, ändern oder anpassen und einen Drillthrough anwenden können.
  1. Der Bereich **Felder**, in dem die verfügbaren Felder in Ihren Abfragen angezeigt werden. Sie können diese Felder in den Canvasbereich, den Bereich **Filter** oder in den Bereich Visualisierungen ziehen, um **Visualisierungen** zu erstellen oder zu ändern.

  <img src="https://docs.microsoft.com/de-CH/power-bi/fundamentals/media/desktop-getting-started/designer_gsg_reportview.png"/>

## Bruttolastgang-Datensätze in Power BI laden

1. Daten direkt aus dem csv-Weblink importieren
1. Nullwerte prüfen und entfernen
1. Prüfung auf doppelte Zeitstempel
1. Sortieren nach Zeitstempel, dann nach Status und anschliessend Duplikate entfernen
1. ändern Sie die Energiedimension in GWh (später leichter zu lesen)
1. Datumsspalte für schnelle Analyse hinzufügen

## Glasfasernetz-Datensätze in Power BI laden

1. Heruntergeladene Daten aus dem Ordner importieren
1. prüfen Sie die Qualität der Daten
1. Nullwerte entfernen
1. doppelte Werte anhand von Zeitstempel und CO entfernen
1. ändern Sie die Skala auf Gbps für eine bessere Interpretation
1. Ausreisser entfernen (>80 Gbps)
1. Datumsspalte für schnelle Analyse hinzufügen
1. Referenzieren Sie die Tabelle, um eine aggregierte Tabelle zu erstellen, die die Werte aus allen COs aggregiert. Benennen Sie die neue Tabelle in ```Zuerinet ZH``` um.
  
    <img src="https://user-images.githubusercontent.com/7482996/111188184-10102380-85b5-11eb-8b49-26f8251ddbcd.png"/>
1. Create a groupby action with the information below:
  
    <img src="https://user-images.githubusercontent.com/7482996/111187733-92e4ae80-85b4-11eb-97da-c3ed28ae2c0e.png"/>

## Glasfasernetz-gebiete GeoJSON in Power BI laden

1. GeoJSON Datei direkt aus dem csv-Weblink importieren
1. Nur Spalten ```features.properties.name``` und ```features.properties.CO``` auswählen
1. Spalten in ```Gebiet``` und ```CO``` umbenennen

## Create Calendar Table

1. Verwenden Sie ```CALENDARAUTO()``` für eine magische Kalendertabellenerstellung
1. Verwenden Sie den folgenden Code-Snippet, um eine detailliertere 15-Minuten-DatumZeit-Tabelle zu erstellen.
    ```
    Time Table = 
    ADDCOLUMNS(
        CROSSJOIN(
            CALENDARAUTO(),
            SELECTCOLUMNS(
                GENERATESERIES(
                    TIME(0,0,0),   
                    TIME(23,59,59),
                    TIME(0,15,0)
                    ),
                    "Time" , [Value] 
            )
        ),
        "Year", YEAR([Date]),
        "Quarter", QUARTER([Date]),
        "YearQuarter", FORMAT([Date],"yyyy")&"-Q"&QUARTER([Date]),
        "YearMonth", FORMAT([Date],"yyyy-mmm"),
        "Month", FORMAT([Date],"mmm"),
        "Day", DAY([Date]),
        "WeekDay", FORMAT([Date],"ddd"),
        "WeekDayID", WEEKDAY([Date],2),
        "Weekend", IF(WEEKDAY([Date],2)>5,"Weekend","Workday"),
        "WeekTime", WEEKDAY([Date],2)+(HOUR([Time])*60+MINUTE([Time]))/1440,
        "StartofWeek", [Date] - WEEKDAY([Date],2) + 1,
        "StartofMonth", DATE(YEAR([Date]),MONTH([Date]),1),
        "StartofQuarter", DATE(YEAR([Date]),QUARTER([Date])*3-2,1),
        "DateTime", [Date]+[Time]
    )
    ```

## Beziehungen einstellen

1. Die Beziehung würde automatisch nach dem Anwenden und Schliessen erscheinen. Andernfalls kann die Beziehung auch manuell durch Ziehen und Ablegen oder über die Schaltfläche "Beziehungen" in der Symbolleiste festgelegt werden. 

    <img src="https://user-images.githubusercontent.com/7482996/110663918-39047300-81c7-11eb-9780-27f02f094b04.png" alt ="Verbindungen zwischen Tabellen"/>

## Berechnete Spalten und Measures

  - Beispiel für eine berechnete Spalte:
    
    ```
    Up/Down Ratio ZH % = 
      DIVIDE( zurinet_csv[UPSTREAM (Gb/s)] ,
              zurinet_csv[DOWNSTREAM (Gb/s)]
            )
    ```
  - Beispiel für eine berechnete Measure:
    
    ```
    Median Up/Down Ratio ZH % = 
        CALCULATE(
            DIVIDE( MEDIAN(zurinet_csv[UPSTREAM (Gb/s)]) ,
                    MEDIAN(zurinet_csv[DOWNSTREAM (Gb/s)])
                )
            )
    ```

## Berichte erstellen und Untersuchungen durchführen

- Sie finden die Berichtsvorlage in diesem Repository unter "files/PowerBI_template.pbit". Die Vorlage benötigt den Ordrner mit den heruntergeladenen Glassfasser csv-Dateien. z.B. 

  <img src="https://user-images.githubusercontent.com/7482996/111190594-89a91100-85b7-11eb-8476-756c879c7b2d.png"/>

- Die Vorlage enthält die folgenden Berichtsseiten:
  
  1. Energieverbrauch über die Zeit
  1. Internetverbrauch vs. Energieverbrauch über die Zeit
  1. Visualisierung des Internetverbrauchs jedes Gebiets
  1. Untersuchen Sie den Verbrauch über die Zeit von Woche, Tageszeit, Jahr, Quartal, Monat (Wie ändert sich das Energie- oder Internetverbrauchsmuster?)


---
***

# Weitere Tutorials

### Datawrapper
Datawrapper hat eine Reihe von [Tutorials](https://academy.datawrapper.de/) und [Schulungsunterlagen](https://www.datawrapper.de/training-materials/), die die einzelnen Diagramm- und Karten-Typen erklären und wie damit Visualisierungen erstellt werden können.

Beispiele:

- [Let’s build a stacked bar chart](https://www.datawrapper.de/training-materials/#exercise-1)
- [How to create a grouped column chart](https://academy.datawrapper.de/article/21-how-to-create-a-grouped-column-chart)
- [How to choose the best interpolation for your colors (choropleth map)](https://academy.datawrapper.de/article/117-color-palette-for-your-map)

### Programmierung (R, Python, SPARQL)
- [Data analysis with Python](https://csmastersuh.github.io/data_analysis_with_python_2020/)
- [Information Visualization (Python)](https://infovis.fh-potsdam.de/tutorials/).
- [Getting started with data visualization in R using ggplot2](https://www.storybench.org/getting-started-data-visualization-r-using-ggplot2/)
- [Rddj - Hand-curated, high quality resources for doing data journalism with R.](https://rddj.info/)
- [Einführung in Wikidata](https://www.wikidata.org/wiki/Wikidata:Tours), siehe dazu auch das [Trainingsmaterial von Open Data Zürich zu Wikidata](https://github.com/opendatazurich/wikidata-training).
