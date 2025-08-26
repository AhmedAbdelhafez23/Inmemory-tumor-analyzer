In-Memory-Datenverarbeitung zur Tumorerkennung mit LaserBase-Daten

Dieses Projekt entstand im Rahmen einer Belegarbeit im Fach In-Memory-Datenbanken im Wintersemester 2024/2025. Ziel war es, medizinische Messdaten – sogenannte Spektraldaten – effizient zu verarbeiten und auszuwerten, um den Tumorstatus von Proben zu bestimmen.

Ziel des Projekts

Im Mittelpunkt steht die Analyse von Messwerten, die mithilfe eines Laser-basierten Messverfahrens gewonnen wurden. Jede Probe enthält Werte für verschiedene Wellenlängen, die in einer CSV-Datei gespeichert sind. Die Aufgabe bestand darin, herauszufinden, ob eine Probe als "Tumorfrei" (N) oder "Tumorbefallen" (T) gilt.

Vorgehensweise

Zur Lösung der Aufgabe wurden zwei verschiedene Ansätze verfolgt:

Python-basierte Datenverarbeitung
Mithilfe von Pandas und NumPy wurden die Referenzdaten aus einer Datei eingelesen, bereinigt und gruppiert. Für jede Gruppe wurde ein Durchschnittswert berechnet, wobei die sogenannte Leave-One-Out-Methode zur Anwendung kam. Die eigentlichen Testdaten wurden dann mit diesen Referenzwerten verglichen.

SQL-basierte Verarbeitung
Zusätzlich wurde eine alternative Umsetzung entwickelt, bei der die gesamte Analyse direkt in einer SQL-Datenbank (SQLite) durchgeführt wurde. Dabei kamen verschachtelte Abfragen, statistische Kennzahlen wie Varianz und Standardabweichung sowie Filter zur Erkennung und Entfernung von Ausreißern zum Einsatz.

Beide Methoden liefern am Ende eine Klassifikation jeder Messreihe und bewerten, ob die Wellenlängenergebnisse im erwarteten Bereich liegen.

Testdaten und Ergebnisermittlung

Drei Testdateien mit realen Messwerten wurden analysiert. Für jede Datei wurde entschieden, ob die Probe tumorfrei oder tumorverdächtig ist. Als Entscheidungskriterium galt: Wenn mindestens 70 % der gemessenen Werte in den Toleranzbereich passen, gilt die Probe als tumorfrei.

Die Ergebnisse wurden in neuen CSV-Dateien gespeichert, die für jede Testdatei sowohl die Bewertung einzelner Wellenlängen als auch die Gesamtauswertung enthalten.

Warum dieses Projekt?

Die Analyse medizinischer Daten erfordert oft hohe Genauigkeit und schnelle Verarbeitung großer Datenmengen. Durch den Einsatz von In-Memory-Techniken, paralleler Verarbeitung und strukturierter Datenmodellierung zeigt dieses Projekt, wie man diese Anforderungen mit modernen Technologien umsetzen kann.

Fazit

Das Projekt demonstriert, wie In-Memory-Verarbeitung und SQL miteinander kombiniert werden können, um medizinische Diagnosedaten effizient zu analysieren. Die entwickelte Lösung ist erweiterbar und bietet eine solide Grundlage für die zukünftige Verarbeitung von tausenden Proben im Rahmen klinischer Anwendungen.

Inmemory-tumor-analyzer/
├── 📂 data_original/           # Ursprüngliche bereitgestellte CSV-Dateien
│   ├── LaserBase.csv
│   ├── LaserBaseTest1.csv
│   ├── LaserBaseTest2.csv
│   ├── LaserBaseTest3.csv
│   └── Klassifikation_Ergebnisse.csv
│
├── 📂 src/                     # Eigenentwickelte Quellcodes zur Datenverarbeitung
│   ├── daten_verarbeitung.py
│   ├── sql_verarbeitung.py
│   └── utils.py (optional für Hilfsfunktionen)
│
├── 📂 results/                 # Ergebnisse der Verarbeitung (generierte CSVs)
│   ├── Test1.csv_results.csv
│   ├── Test2.csv_results.csv
│   ├── Test3.csv_results.csv
│   ├── Test1.csv_analyse.csv
│   ├── Test2.csv_analyse.csv
│   ├── Test3.csv_analyse.csv
│   ├── LaserBaseTest1.csv_vergleich.csv
│   ├── LaserBaseTest2.csv_vergleich.csv
│    ├── LaserBaseTest2.csv_vergleich.csv │   
│
├── 📂 docs/                    #Screenshots oder Abbildungen
│   └── Belegarbeit.pdf            # 🧾 Ausformulierte Belegarbeit (Endversion)
│    └──Screenshots
│
├── README.md                  # 🔹 Projektbeschreibung

