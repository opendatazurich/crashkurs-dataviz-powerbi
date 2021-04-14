# Crashkurs für Power BI Datenvisualisierung
<!-- 
## TODO für neuen Kurs
 -->
<!-- **Tipp für Bilder und Videos**: am einfachstes ist es die Bilder und Videos direkt in das Eingabefeld eines neuen GitHub Issues einzufügen, dadurch wird das Bild/Video direkt auf GitHub hochgeladen und die URL kann ins README kopiert werden. -->
<!-- 
<video preload="none" poster="https://user-images.githubusercontent.com/538415/106586754-1d170d00-6549-11eb-8e7d-d24e0ea4cb13.jpg" src="https://user-images.githubusercontent.com/538415/106586882-3ddf6280-6549-11eb-9db5-9f1ddb7552cc.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="GitHub Upload" src="https://user-images.githubusercontent.com/538415/106586824-2d2eec80-6549-11eb-8348-9ddf62f08607.gif"/></video>
 -->
# Teil 1: Daten finden

Rufe den Open Data Katalog der Stadt Zürich auf «[https://data.stadt-zuerich.ch/](https://data.stadt-zuerich.ch/)». Wir müssen drei Datensätze herunterladen:

1. Glasfasernetz Leistungsdaten der Stadt Zürich
1. Glasfasernetz Gebiete der Stadt Zürich
1. Bruttolastgang der Stadt Zürich

## Glasfasernetz Leistungsdaten

- **Schritt 1:** Suche nach «Zürich Glasfasernetz Leistungsdaten». Gib dazu im Suchfeld beispielsweise den Begriff «Glasfasernetz» und «Leistungsdaten» ein. Während dem Eintippen des Suchbegriffs werden bereits passende Vorschläge angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Zürich Glasfasernetz Leistungsdaten](https://data.stadt-zuerich.ch/dataset/ewz_leistungsdaten_zuerinet)» aus und lese die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. Weiterführende wichtige Informationen sind auch unter *Bemerkungen* zu finden. Beachte, dass die Metadaten und Attributbeschreibungen am Ende der Liste sind und auf der Seite allenfalls heruntergescrollt werden muss, damit diese sichtbar werden.

    <img src="https://user-images.githubusercontent.com/7482996/110360261-cd8f9980-803e-11eb-9357-e6d6e21608a5.png" alt="Suchresultatvorschau"/>
  
  > ***!!!*** Der Datensatz enthält die gemessenen Leistungsdaten (Up- und Downstream) in Bit pro Sekunde (pro «Core Location») im Glasfasernetz der Stadt Zürich. Die Messdaten werden für jede Viertelstunde pro Knotenpunkt, aggregiert (Durchschnitt), ausgewiesen.

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort einen Datensatz aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden. 
  - Es gibt eine Datei pro Monat. Es müssen alle Dateien heruntergeladen und in einen Ordner kopiert werden. Es gibt 39 Dateien bis und mit Januar 2021. (Um diesen Schritt weniger aufwändig zu machen, haben wir für diesen Kurs die [Daten von 2018 bis am 13.04.2021 als Zip-File auf Github](https://github.com/opendatazurich/crashkurs-dataviz-powerbi/raw/main/data_repository/2021_04_13_ewz_leistungsdaten_zuerinet.zip) abgelegt. Sie können also dieses File herunterladen und entzippen. )

## Glasfasernetz Gebiete

- **Schritt 1:** Suche nach «Zürich Glasfasernetz Versorgungszonen». Gib dazu im Suchfeld beispielsweise die Begriffe «Glasfasernetz» und «Versorgungszonen» ein. Während dem Eintippen der Suchbegriffe werden bereits passende Vorschläge angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Zürich Glasfasernetz Versorgungszonen](https://data.stadt-zuerich.ch/dataset/ewz_gebiete_zuerinet)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. 

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Klicke dort auf «ewz_gebiete_zuerinet.json». 
  - Dadurch öffnet sich eine neue Seite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Datei herunter zu laden. 

- **Schritt 3:** Power BI benötigt diese «[GeoJSON-Datei](https://de.wikipedia.org/wiki/GeoJSON)» im «[TopoJSON-Format](https://en.wikipedia.org/wiki/GeoJSON#TopoJSON)». Für die Konvertierung in das TopoJSON Format können wir das Tool «[MapShaper Portal](https://mapshaper.org/)» verwenden. Drücke nach dem Importieren den Button «Export» und wähle das Fileformat «TopoJSON» aus. Lade die Datei mit der Dateierweiterung "topojson" für zukünftige Referenzen herunter.

  <img src="https://user-images.githubusercontent.com/7482996/110362882-27459300-8042-11eb-93ec-7f2021736b0e.png" width=400 alt="MapShaper Import"/> 
  <img src="https://user-images.githubusercontent.com/7482996/110363068-6247c680-8042-11eb-89a1-97c12bf99a8d.png", width=400 alt="MapShaper Export"/>

## Bruttolastgang

- **Schritt 1:** Suche nach «Zürich Viertelstundenwerte zum Bruttolastgang elektrische Energie». Gebe dazu im Suchfeld beispielsweise den Begriff «Bruttolastgang» ein. Beim Eintippen des Suchbegriffs werden bereits passende Vorschläge angezeigt.  

- **Schritt 2:** Wähle das Dataset «[Viertelstundenwerte zum Bruttolastgang elektrische Energie der Stadt Zürich](https://data.stadt-zuerich.ch/dataset/ewz_bruttolastgang_stadt_zuerich)» aus und lies die Metadaten dazu. Besonders wichtig sind dabei die Attributbeschreibungen, welche die Ausprägungen der Informationen im Datensatz beschreiben. Weiterführende wichtige Informationen sind auch unter *Bemerkungen* zu finden. 

  > ***!!!*** Der Bruttolastgang wird basierend auf zahlreichen Messungen zur Einspeisung und zum Verbrauch berechnet. Einzelne Messungen können dabei fehlen und müssen nachträglich nochmals eingepflegt werden.

  - Die Datensätze selber sind unter *Daten und Ressourcen* zu finden. Wähle dort 
  «2020_ewz_bruttolastgang.csv» Datensatz aus und klicke darauf. 
  - Dadurch öffnet sich eine neue Webseite, welche den Downloadlink und eine einfache Datenvorschau beinhaltet.
  - Klicke nun auf den Downloadlink, um die Daten herunter zu laden. 

# Teil 2: Power BI

## Begriffe
### CSV... what?
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

### Median?
Die folgende Abbbildung erklärt den Unterschied zwischen Zentralwert (Median) und Mittelwert (Mean). 
- Der Median von Messwerten ist derjenige Messwert, der genau "in der Mitte" der Liste steht, wenn man die Messwerte der Größe nach sortiert. Falls die Anzahl der Messewerte gerade ist, wird der Mittelwert der beiden in der Mitte stehenden Werte genommen.
- Der Mittelwert ist die Summe aller Messwerte durch die Anzahl der Messwerte.

<img src="https://user-images.githubusercontent.com/7482996/110783095-3dcd3380-8268-11eb-91a5-978d0524eae6.png"/>

## Was ist Power BI?

Power BI ist eine Sammlung von Software-Services, Apps und Konnektoren, die zusammenarbeiten, um deine unzusammenhängenden Datenquellen in kohärente, visuell ansprechende und interaktive Einblicke zu verwandeln. 
Bei deinen Daten kann es sich um eine Excel-Tabelle oder um eine Sammlung von Cloud-basierten und lokalen hybriden Data Warehouses handeln. 
Mit Power BI kannst du dich ganz einfach mit deinen Datenquellen verbinden, visualisieren und entdecken, was wichtig ist, und dies mit jedem teilen, den du möchtest. 
«[[Mehr Info.]](https://docs.microsoft.com/de-CH/power-bi/fundamentals/power-bi-overview)»

Power BI besteht aus verschiedenen Elementen, die eng miteinander verzahnt sind. 
Dies sind die drei Grundkomponenten:
 - Windows-Desktopanwendung namens Power BI Desktop
 - Online-SaaS (Software-as-a-Service) namens Power BI-Service
 - Mobile Power BI-Apps für Windows-, iOS- und Android-Geräte
  <img src="https://docs.microsoft.com/en-US/power-bi/fundamentals/media/power-bi-overview/power-bi-overview-blocks.png"/>


Diese drei Elemente - Power BI Desktop, der Service und die mobilen Apps - sind so entwickelt, dass du Geschäftseinblicke auf die Art und Weise erstellen, teilen und konsumieren kannst, die dir und deiner Rolle am effektivsten dient.

## Power BI Desktop - GUI Intro 

### Query Editor

Hier ist eine sehr kurze Einführung in die Power BI-Schnittstelle. Für eine detaillierte Beschreibung schauen Sie bitte auf die Seite von «[Microsoft](https://docs.microsoft.com/de-CH/power-bi/transform-model/desktop-query-overview)».

- Power BI Desktop verfügt über drei Ansichten:

  - ***Berichtsansicht.*** Hier kannst du mit Hilfe selbst erstellter Abfragen ansprechende Visualisierungen erstellen. Diese Visualisierungen können angeordnet miteiander verknüpft und bei Bedarf auf mehreren Seiten verteilt werden und können für andere Benutzer freigegeben werden.
  - ***Datenansicht.*** Hier kannst du die Daten eines Berichts im Datenmodellformat anzeigen lassen. Du kannst «Measures» hinzufügen und neue Spalten erstellen. 
  - ***Beziehungsansicht.*** Hier kannst du eine grafische Darstellung der Beziehungen abrufen, die im Datenmodell erstellt wurden und diese je nach Bedarf verwalten oder ändern.

  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-view-icons.png"/>

- Der Power Query-Editor kann aufgerufen werden, indem man auf der Registerkarte «Start» auf die Option «Abfragen bearbeiten» klickt.
  
  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-transform.png"/>

- Nach dem Herstellen einer Datenverbindung sieht der Power Query-Editor wie folgt aus:

  1. Im Menüband sind jetzt viele Schaltflächen aktiv, über die man die Daten in der Abfrage interaktiv bearbeiten kann.

  2. Im linken Bereich sind die Abfragen aufgelistet und können ausgewählt, angezeigt und strukturiert werden.
  
  3. Im mittleren Bereich werden die Daten der ausgewählten Abfrage angezeigt und können dort strukturiert werden.
  
  4. Der Bereich Abfrageeinstellungen wird angezeigt. Hier sind die Eigenschaften der Abfrage und die angewendeten Schritte aufgelistet.

  <img src="https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-query-overview/query-overview-with-data-connection.png"/>

- Wenn du mit der Abfrage zufrieden bist, klicke im Dateimenü des Power Query-Editors auf ***Close & Apply*** (Schliessen und anwenden). Mit dieser Aktion werden die Änderungen angewendet und der Editor geschlossen.
    
    <img src="https://user-images.githubusercontent.com/7482996/110667557-a960c380-81ca-11eb-8e93-9326e72af365.png"/>

### Report Builder

  Eine ausführliche Version kannst du auf dem Microsoft Portal finden: «[Erstellen von Berichten](https://docs.microsoft.com/de-CH/power-bi/fundamentals/desktop-getting-started)»

- In der Power BI Desktop-Ansicht Bericht kannst du Visualisierungen und Berichte erstellen. Die Ansicht «Bericht» besteht aus sechs Hauptbereichen:
  
  1. Das Menüband im oberen Bereich, in dem häufige Aufgaben in Verbindung mit Berichten und Visualisierungen angezeigt werden.
  1. Der Canvasbereich, in dem Visualisierungen erstellt und angeordnet werden.
  1. Der Registerkartenbereich **Seiten** am unteren Rand, in dem Berichtsseiten ausgewählt oder hinzugefügt werden können.
  1. Der Bereich **Filter**, in der Datenvisualisierungen gefiltert werden können.
  1. Der Bereich **Visualisierungen**, in dem Visualisierungen hinzugefügt, geändert, angepasst und ein Drillthrough angewendet werden können.
  1. Der Bereich **Felder**, in dem die verfügbaren Felder in den Abfragen angezeigt werden. Diese Felder können in den Canvasbereich, den Bereich **Filter** oder in den Bereich Visualisierungen gezogen werden, um **Visualisierungen** zu erstellen oder zu ändern.

  <img src="https://docs.microsoft.com/de-CH/power-bi/fundamentals/media/desktop-getting-started/designer_gsg_reportview.png"/>

## Datensätze importieren
### Bruttolastgang-Datensätze importieren

1. Daten direkt aus dem csv-Weblink importieren
1. Nullwerte prüfen und entfernen
1. Prüfung auf doppelte Zeitstempel
1. Sortieren nach Zeitstempel, dann nach Status und anschliessend Duplikate entfernen
1. Ändern der Energiedimension nach GWh (für eine bessere Lesbarkeit)
1. Datumsspalte für schnelle Analyse hinzufügen

### Glasfasernetz-Datensätze importieren

1. Heruntergeladene Dateien aus dem Ordner importieren
1. Prüfen der Datenqualität
1. Nullwerte entfernen
1. Doppelte Werte anhand von Zeitstempel und CO entfernen
1. Ändern der Skala auf Gbps (für eine bessere Interpretation)
1. Ausreisser entfernen (>80 Gbps)
1. Datumsspalte für schnelle Analyse hinzufügen
1. Referenzieren einer Tabelle, um eine aggregierte Tabelle zu erstellen, die die Werte aus allen CO's aggregiert. Benenne die neue Tabelle ```Zuerinet ZH```:
  
    <img src="https://user-images.githubusercontent.com/7482996/111188184-10102380-85b5-11eb-8b49-26f8251ddbcd.png"/>
1. Kreieren einer ***groupby action*** mit den folgenden Einstellungen:
  
    <img src="https://user-images.githubusercontent.com/7482996/111187733-92e4ae80-85b4-11eb-97da-c3ed28ae2c0e.png"/>

### Glasfasernetz-Gebiete importieren

1. GeoJSON Datei direkt aus dem csv-Weblink importieren
1. Nur Spalten ```features.properties.name``` und ```features.properties.CO``` auswählen
1. Spalten in ```Gebiet``` und ```CO``` umbenennen

## Kalendertabelle erstellen

1. Verwende ```CALENDARAUTO()``` für eine automatische Kalendertabellenerstellung
1. Verwende das folgende Code-Snippet, um eine detailliertere 15-Minuten-DatumZeit-Tabelle zu erstellen.
    ```
    Time Table = 
    ADDCOLUMNS(
        CROSSJOIN(
            CALENDARAUTO(),
            SELECTCOLUMNS(
                GENERATESERIES(
                    TIME(0,0,0),   
                    TIME(23,45,0),
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
        "MonthID", MONTH([Date]),
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

1. Die Beziehung erscheint automatisch nach dem Anwenden und Schliessen des Dialogs. Andernfalls kann die Beziehung auch manuell durch Ziehen und Ablegen oder über die Schaltfläche «Beziehungen» in der Symbolleiste festgelegt werden. 

    <img src="https://user-images.githubusercontent.com/7482996/112830565-01d10580-9093-11eb-9fad-d29de0772eff.png" alt ="Verbindungen zwischen Tabellen"/>

## Berechnete Spalten & Measures

Der Unterschied zwischen «berechneten Spalten» und «Measures» ist der Kontext der Auswertung. Eine «Measure» wird im Kontext der ausgewerteten Zelle in einem Bericht oder in einer DAX-Abfrage ausgewertet, während eine «berechnete Spalte» auf Zeilenebene innerhalb der Tabelle, zu der sie gehört, berechnet wird. Für eine detaillierte Beschreibung schauen Sie bitte auf die Seite von «[sqlbi](https://www.sqlbi.com/articles/calculated-columns-and-measures-in-dax/)».

  - Beispiel für eine berechnete Spalte:
    
    ```
    Up/Down Ratio CO % = 
      DIVIDE( 'Zuerinet CO'[UPSTREAM (Gb/s)] ,
              'Zuerinet CO'[DOWNSTREAM (Gb/s)]
            )
    ```
  - Beispiele für eine berechnete Measure:
    
    ```
    Median Up/Down Ratio CO % = 
        CALCULATE(
            DIVIDE( MEDIAN('Zuerinet CO'[UPSTREAM (Gb/s)]) ,
                    MEDIAN('Zuerinet CO'[DOWNSTREAM (Gb/s)])
                )
            )
    ```
    ```
    ing. Download (PB) = 
    CALCULATE(
      SUM('Zuerinet CO'[DOWNSTREAM (Gb/s)])
      * 900
      / (8*1000000)
    )
    ```
    ```
    ing. Upload (PB) = 
    CALCULATE(
      SUM('Zuerinet CO'[UPSTREAM (Gb/s)])
      * 900
      / (8*1000000)
    )
    ```

## Berichte erstellen und Untersuchungen durchführen

- Du findest die Berichtsvorlage in diesem Repository unter "[files/PowerBI_template.pbit](https://github.com/opendatazurich/crashkurs-dataviz-powerbi/raw/main/files/PowerBI_template.pbit)". Die Vorlage benötigt den Ordner mit den heruntergeladenen csv-Dateien für die Glasfasernetz Leistungsdaten. z.B. 

<img src="https://user-images.githubusercontent.com/7482996/111190594-89a91100-85b7-11eb-8476-756c879c7b2d.png"/>

- Die Vorlage enthält die folgenden Berichtsseiten:
  
  1. Energieverbrauch über Datum
      <img src="https://user-images.githubusercontent.com/7482996/112823676-e0b7e700-9089-11eb-80f4-8d6aab03bfbb.gif"/>

  1. Internetverbrauch vs. Energieverbrauch über die Zeit
      <img src="https://user-images.githubusercontent.com/7482996/112828530-18c22880-9090-11eb-86f3-8b5ce8966406.gif"/>

  1. Daten als CSV exportieren
      <img src="https://user-images.githubusercontent.com/7482996/112829967-2b3d6180-9092-11eb-8514-f9569cd1e0a3.gif"/>

  1. Visualisierung des Internetverbrauchs jedes Gebiets
      
      ---------
      I. Ribon Plot
      
      <img src="https://user-images.githubusercontent.com/7482996/112862876-841ef100-90b6-11eb-9b2a-0fab8293d678.gif"/>

      ---------
      II. Standortkarte
      
      <img src="https://user-images.githubusercontent.com/7482996/112865065-b4678f00-90b8-11eb-9ac7-00cbbd29109d.gif"/>
      
      ---------
      III. Tabelle
      
      <img src="https://user-images.githubusercontent.com/7482996/113679658-4a567780-96c0-11eb-8264-127c6a1a65a2.gif"/>
      
  1. Untersuchung des Verbrauchs über die Zeit von Woche, Tageszeit, Jahr, Quartal, Monat (wie ändert sich das Energie- oder Internetverbrauchsmuster?)
      <img src="https://user-images.githubusercontent.com/7482996/112869316-4b364a80-90bd-11eb-9574-a5a3e42d16b5.gif"/>


---
***

# Weitere Tutorials

## Power BI selbst lernen

- Präsentation: «[LINK](https://github.com/opendatazurich/crashkurs-dataviz-powerbi/raw/main/files/PowerBI_really_short_intro.pdf)»

- Tutorial: Erstellen von ansprechenden Berichten aus Excel-Arbeitsmappen in Power BI Desktop «[LINK](https://docs.microsoft.com/de-CH/power-bi/create-reports/desktop-excel-stunning-report)»

- Microsoft Dokumentation: Abfrageübersicht in Power BI Desktop «[LINK](https://docs.microsoft.com/de-CH/power-bi/transform-model/desktop-query-overview)»

- Microsoft learn for Power BI: Drei Hauptsammlungen «[LINK](https://docs.microsoft.com/de-CH/learn/powerplatform/power-bi?WT.mc_id=powerbi_landingpage-product-service)»
  - Einstieg in Power BI
  - Der Weg zum Data Analyst
  - Entwickeln mit Power Platform
