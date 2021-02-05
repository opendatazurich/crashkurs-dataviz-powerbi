# Kurs-Template

**A template for the documentation of a course**

This template is based on our [dataviz crash course](https://github.com/opendatazurich/crashkurs-dataviz).

## TODO für neuen Kurs

- [ ] Im `_config.yml` die Werte anpassen (insbesondere `title` und `description`)
- [ ] Kurs-Inhalt in README.me erfassen, Überschrift 1 und 2 (in Markdown mit `#` und `##` markiert) wird als Navigation auf der Seite zur Verfügung gestellt (auf Geräte mit kleinem Bildschirm ist das ausgeblendet). **HINWEIS:** Die erste Überschrift ist absichtlich nicht in der Navigation, das ist für den Haupttitel des Kurses (dies kann in der Datei `assets/js/main.js` angepasst werden, falls nötig).
- [ ] In den Settings "GitHub Pages" aktivieren (mit Branch `main` und `root`): ![GitHub Pages in den Settings](https://user-images.githubusercontent.com/538415/106585645-d674e300-6547-11eb-8556-39a3fa540547.png)

**Tipp für Bilder und Videos**: am einfachstes ist es die Bilder und Videos direkt in das Eingabefeld eines neuen GitHub Issues einzufügen, dadurch wird das Bild/Video direkt auf GitHub hochgeladen und die URL kann ins README kopiert werden.

<video preload="none" poster="https://user-images.githubusercontent.com/538415/106586754-1d170d00-6549-11eb-8e7d-d24e0ea4cb13.jpg" src="https://user-images.githubusercontent.com/538415/106586882-3ddf6280-6549-11eb-9db5-9f1ddb7552cc.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="GitHub Upload" src="https://user-images.githubusercontent.com/538415/106586824-2d2eec80-6549-11eb-8348-9ddf62f08607.gif"/></video>

# Teil 1: Daten finden
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

Damit ist unser erster Teil zum Thema «Daten finden» beendet. Solltest Du später einmal für eine andere Fragestellung auf dem [Open Data Katalog der Stadt Zürich](https://data.stadt-zuerich.ch) nicht fündig werden, können auch viele andere Open Data Quellen konsultiert werden. Auf nationaler Ebene werden unter [opendata.swiss](https://opendata.swiss) sämtliche offenen Verwaltungsdaten von verschiedenen Bundesstellen, anderen Kantonen und Städten angeboten. 

# Teil 2: Excel

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
Der angezeigte CSV-Auszug oben repräsentiert die folgende Tabelle:

![Darstellung Excel](https://user-images.githubusercontent.com/2479732/104014716-cc173180-51b3-11eb-9440-3d87d2fb6128.png)

## CSV-Datensätze in Excel laden

Vielleicht fragst Du Dich unterdessen, wozu der ganze Exkurs über CSV dienlich sein soll...(?)
Leider ist es so, dass viele Datennutzende bereits zu diesem Zeitpunkt scheitern, wenn sie noch nie mit CSV gearbeitet haben und eine CSV-Datei in Excel öffnen wollen.
Daher zeigen wir Euch in diesem Abschnitt, wie man vorgehen sollte, wenn man mit CSV-Datensätzen in Excel arbeiten möchte.

**Wie es NICHT funktioniert:**
Ein Doppelklicken auf eine CSV-Datei - wie in unten gezeigter Animation gezeigt - funktioniert leider in den meisten Fällen nicht.
Obwohl man gemäss des im Beispiel angezeigten Icons der Datei das Gefühl hätte, dass dies so möglich sein sollte. Folgendes geschieht jedoch stattdessen: 

<video src="https://user-images.githubusercontent.com/2479732/105727214-25f55680-5f2b-11eb-8d62-e1d64c5bbd65.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="02_excelissue" src="https://user-images.githubusercontent.com/2479732/104017881-32528300-51b9-11eb-8d15-39debf3c426a.gif"/></video>

Die CSV-Datei wird zwar in Excel geöffnet, es findet dabei jedoch keine Trennung der einzelnen Attribute in Spalten statt (vgl. mit der oben gezeigten Tabelle).
Mit der hier gezeigten Vorgehensweise sind alle Werte in eine Spalte (hier Spalte A) eingefügt worden. Damit lässt sich nicht bequem weiterarbeiten.

## Datenauswertung mit Excel 
Excel ist bezüglich Datenanalyse selbstverständlich nicht allererste Sahne.
Fortgeschrittenere Datennutzende verwenden in der Regel eher Statistiktools wie **[R](https://www.r-project.org/)** (siehe dazu Ressourcen, wie [Rddj](https://rddj.info/) oder [RStudio Education](https://education.rstudio.com/blog/2020/05/remote-roundup/)) oder **[Python](https://www.python.org/)** (siehe dazu Ressourcen, wie [Data analysis with Python](https://csmastersuh.github.io/data_analysis_with_python_2020/ ) oder [Information Visualization](https://infovis.fh-potsdam.de/tutorials/)). 

### Anzahl Kleinkinder nach Stadtquartier
Beginnen wir zuerst einmal damit herauszufinden, wie viele Kleinkinder es pro Stadtquartier am 31.12.2019 gab.

- **Schritt 1:** Gehe zum Menu **Einfügen**, klicke aufs **PivotChart-Icon** und wähle **PivotChart und PivotTable**.

- **Schritt 2:** Mit dem Pop-Up **PivotTable erstellen** wirst Du aufgefordert, den Tabellenbereich der analysiert werden soll auszuwählen. Sofern Du alle Daten des aktiven Arbeitsblattes betrachten möchtest, musst Du hier nichts anpassen. Als weitere Option kannst Du auswählen, ob die PivotTable in ein bestimmtes oder in ein neues Arbeitsblatt eingefügt werden soll. Klicke danach auf **OK**.

- **Schritt 3:** Im neuen Arbeitsblatt erscheinen nun die noch leeren PivotTable- und PivotChart-Flächen. Auf der rechten Seite siehst Du die PivotTable-Felder, welche Du **interaktiv** per drag & drop in vier Bereiche ziehen kannst. 
  - a) **WERTE**: hier werden die zu aggregierenden Wertefelder definiert. In unserem Fall ist das die **Anzahl Personen** aus der wirtschaftlichen Wohnbevölkerung (`AnzBestWir`) .
  - b) **ZEILEN**: hier werden die Felder eingefügt, welche als Zeilen dargestellt werden sollen. In unserem Fall also die **Stadtquartiere** (`QuartLang`). Die Stadtquartiere können mit ihren Namen oder mit ihren offiziellen IDs (`QuartSort`oder `QuartCd`) angezeigt werden.
  - c) **SPALTEN**: hier könnten weitere Ausprägungen ausgewählt werden, wie z.B. das Geschlecht oder die Herkunft. Für unsere Fragestellung sind diese Felder jedoch nicht relevant. Deshalb bleibt dieser Bereich leer.
  - d) **FILTER**: hier können für Attribute gewisse Werte aus den Daten gefiltert werden. So müssen wir nun das für uns relevante **Jahr** (`StichtagDatJahr`), also **2019**, auswählen. Ausserdem betrachten wir ja lediglich die Kleinkinder. Wir definieren sie hier als jene Personen in der **Alterskategorie** (`AlterV05Kurz`) **0-4**. Also der Kinder die jünger als 5 Jahre alt sind. Man könnte die Definition selbstverständlich auch anders festlegen.
  
  <video preload="none" poster="https://user-images.githubusercontent.com/538415/105816425-94cac200-5fb4-11eb-80a2-fdfe0a96d2a1.jpg" src="https://user-images.githubusercontent.com/2479732/105727578-897f8400-5f2b-11eb-952d-3d28126196c3.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="05_bevbest_pivot" src="https://user-images.githubusercontent.com/2479732/104037207-ac443580-51d4-11eb-8458-4ee22822d42d.gif"/></video>
  
- **Schritt 4:** Damit haben wir nun bereits die erforderliche Tabelle und eine simple Grafik der Anzahl Kleinkinder pro Stadtquartier Ende 2019. Benenne das Arbeitsblatt wieder, z.B. mit `BevBest_Pivot`.

### Vergleich zur Anzahl Hunde und Kleinkinder
Damit wir die Resultate der Anzahl Hunde und Anzahl Kleinkinder pro Stadtquartier vergleichen können, kopieren wir am einfachsten die Resultate der Pivot-Tabellen in ein neues Arbeitsblatt.

- **Schritt 1:** Füge ein neues Arbeitsblatt (mit Klick auf das Plus-Zeichen unten rechts neben den anderen Arbeitsblättern) hinzu. Gib ihm einen Namen. In unserem Beispiel `Vgl_Kleinkinder_Hunde`.

- **Schritt 2:** Kopiere die Werte der Anzahl Kleinkinder pro Stadtquartier und füge sie ins neue Arbeitsblatt ein. 

- **Schritt 3:** Mache das gleiche mit den Werten zur Anzahl Hunde pro Stadtquartier und füge sie mit etwas Abstand rechts ins neue Arbeitsblatt ein. 

<video preload="none" poster="https://user-images.githubusercontent.com/538415/105816678-e410f280-5fb4-11eb-96f2-552408ac88ca.jpg" src="https://user-images.githubusercontent.com/2479732/105728266-3f4ad280-5f2c-11eb-92e2-092bca21b723.mp4" controls="controls" muted="muted" style="max-height:640px;"><img alt="07_results" src="https://user-images.githubusercontent.com/2479732/104167948-86e64000-53fd-11eb-9a1a-152601170a01.gif"/></video>

# Anhänge

## CSV-Datei
Die CSV-Datei, auf der dieser Kurs basiert, kann von GitHub heruntergeladen werden: [ZIP-Datei mit den verlinkten CSVs](https://github.com/opendatazurich/kurs-template/raw/main/files/beispiel.csv).
[![Excel-Datei](https://user-images.githubusercontent.com/538415/104441265-bb8c0000-5593-11eb-91ac-daf61d617bc1.png)](https://github.com/opendatazurich/kurs-template/raw/main/files/beispiel.csv)

## Tutorials

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
