# 04_Recomender_Systems

Binder Badge zum starten des Jupyter Notebooks (Recommender_Systems.ipynb) via myBinder: [![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/tristii/04_Recomender_Systems/main?labpath=Recommender_Systems.ipynb)

In der Umgebung von mybinder können Sie das Übungsbeispiel ausführen lassen, eigene Lösungen codieren (bestehenden Code modifizieren), um das Übungsbeispiel mit dem erwartenden Ergebnis zu reproduzieren.

## Dokumentation zur Übungsaufgabe: 
Aufgebaut ist die Übungsaufgabe in jeweils in Beschreibungsabschnitt was explizit gemacht werden soll. Die jeweilige darunterliegende Zelle stellt den Code Bereich dar, in der dieser Aufgabenabschnitt codiert wird und ggf. den dazugehörigen Output nach der Ausführung (SHIFT + Enter) der jeweiligen Codezelle darstellt.

! Um das zu erwartendee Ergebnis (Output) der Lösung im Übungsbeispiel nicht zu verlieren bzw. zu überschreiben, können Sie nach der Beschreibung der jeweiligen Teil-Aufgabe eine Zwischenzeile(neue Zeile) einfügen, in der Sie Ihre Lösung codieren um danach Ihren Code mit dem darunter liegenden Mustercode + dessen Output vergleichen/überprüfen zu können. 

**Vorgehensweise im Übungsbeispiel:**

Fallbeispiel: In diesem Notebook geht es daraum ein einfaches funktionierendes Empfehlungssystem zu erstellen, dass Items empfiehlt, die möglichst ähnlich zu einem bestimmten Item sind. In unserem Fall wird es sich um Filme handeln. Denkt aber bitte daran, dass dies kein ausgeklügeltes reales Empfehlungssystem ist; es sagt uns einfach nur, welche Filme sich in ihren Eigenschaften ähneln. Netflix und Co. beziehen das Nutzerverhalten und viel mehr Eigenschaften für ihre Empfehlungen.

**1. Libraries**
* notwendige Libraries müssen importiert werden (pandas, numpy, matplotlib.pyplot, seaborn) für die Datenverarbeitung und Datenvisualisierung

**2. Rohdaten**
* Rohdaten (Movie_Id_Titles.csv; U.data.csv) einlesen und DataFrames erstellen
* Deskriptive Statistiken anzeigen und analysieren mit der head() Funktion
* DataFrames (beide Tabellen) zusammenführen mit pd.merge()

**3. Explorative Datenanalyse**

mittels Plots aus der Seaborn und Pandas Library können die Daten visualisiert werden, um sie besser analysieren zu können. 
* Dataframe für die Bewertungen ("ratings") erstellen. Dabei werden die durchschnittliche Bewertung und die Anzahl an Bewertungen betrachtet.
* Hinzufügen der Spalte Anzahl an Bewertungen ("number of ratings") 
* Visualisierung der durchschnittlichen Bewertungen + die Anzahl der Bewertungen mithilfe von Histogrammen
* Jointplot zu gegenüberstellen von den durchschnittlichen Bewertungen + die Anzahl der Bewertungen


**4. Ähnliche Filme empfehlen**
*Erstellen einer Matrix. Diese wird die User-IDs (Spalte: user_id) auf der einen Achse und die Filmtitel (Spalte: title) auf der anderen Achse tragen. Jede Zelle beinhaltet dann die Bewertung, die ein Nutzer einem Film gegeben hat
* Ausgabe der am häufigsten bewerteten Filme
* Auswahl der 2 Filme: "Star Wars" und "Liar Liar"
* corrwith() anwenden, um Korrelationen zwischen den beiden Panda Series der oben genannten Filme zu erhalten
* NaN Werte entfernen und aus den Series DataFrames erstellen
* DataFrame nach den Korrelationen sortieren, dann sollten wir die ähnlichsten Filme erhalten, dabei muss beachtet werden, dass viele Nutzer Star Wars gesehen haben (der bekannteste Film) und andere Filme nur von einzelnen Nutzern gesehen wurden
* Da zu wenige Bewertungen nicht aussagekräftig genug sind, werden nur Filme mit mehr als 100 Bewertungen in Betracht gezogen, um eine sinnvolle Empfehlung zu erhalten 
