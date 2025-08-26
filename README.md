# Inmemory-tumor-analyzer
Effizientes In-Memory-Tumorerkennung auf Basis spektraler Wellenlängendaten. Die Analyse erfolgt mit Python und optimierten SQL-Abfragen zur Klassifikation biologischer Gewebeproben.

 Inmemory-tumor-analyzer/
├── imdb1.py # Python-Skript für die Datenverarbeitung
├── imdb2.py # SQL-basierte Version mit SQLite
├── data/
│ ├── LaserBase.csv # Referenzdaten
│ ├── LaserBaseTest1.csv
│ ├── LaserBaseTest2.csv
│ ├── LaserBaseTest3.csv
├── results/
│ ├── Test1_results.csv
│ └── Test2_results.csv
│ └── Test3_results.csv
├── screenshots/ # Für Dokumentation (z. B. Jupyter-Ausgabe)

# 🎯 LaserBase: Tumordetektion mit In-Memory-Datenverarbeitung

Dieses Projekt wurde im Rahmen der Belegarbeit „In-Memory-Datenbanken“ im Wintersemester 2024/25 entwickelt. Ziel ist die Klassifizierung von spektroskopischen Messdaten zur Unterscheidung zwischen tumorfreiem und tumorbefallenem Gewebe auf Basis effizienter In-Memory-Datenverarbeitung.

## 🔬 Motivation

In der medizinischen Forschung, insbesondere der Onkologie, ist eine schnelle und präzise Analyse großer Datenmengen entscheidend. Diese Anwendung zeigt, wie moderne In-Memory-Techniken wie Pandas, kombiniert mit SQL-Optimierungen, dazu beitragen können, Tumorerkennung effizient durchzuführen.

## ⚙️ Projektstruktur

### `3.1 Datenaufbereitung`
- Bereinigen der Referenzdaten (z. B. Konvertierung von Dezimalzeichen, Entfernen von Ausreißern)
- Berechnung der Durchschnittswerte pro Wellenlänge mit der **Leave-One-Out (LOO)** Methode
- Parallelisierte Verarbeitung zur Erhöhung der Performance

### `3.2 Tumortests`
- Vergleich von Testdaten mit Referenzdaten
- Klassifikation jedes Wertes als „N“ (tumorfrei) oder „T“ (tumorbefallen)
- Gesamtauswertung einer Testprobe basierend auf dem Anteil der „N“-Klassifikationen

### `3.3 Relationale Datenbankabfragen`
- Transformation der Logik in SQL zur Analyse großer Testdatenmengen
- Ausreißereliminierung durch Standardabweichung
- Schwellenwertbasierte Aggregation (z. B. 70 %-Regel)
- Index-Erstellung zur Optimierung der Abfragen

## 💾 Technologie-Stack

- **Python (Pandas, NumPy, concurrent.futures)**
- **SQLite / MS Access (relationale Abfragen)**
- **CSV-Datenimport**
- **Jupyter / IDLE / PyCharm** (für Entwicklung und Test)

## 🗃️ Dateien (Beispiel)

- `LaserBase.csv` – Referenzmessdaten (Gewebeproben)
- `LaserBaseTest1.csv`, `Test2.csv`, `Test3.csv` – neue Messproben
- `IMDB1.py`, `IMDB2.py` – Python-Skripte zur Analyse
- `IMDB.accdb` – relationale SQL-Abfragen in MS Access

## 📈 Ergebnisse

- Laufzeit je Test < 1 Sekunde
- Zuverlässige Identifikation aller Proben als tumorbefallen (T)
- Kombinierter Einsatz von In-Memory-Analyse und relationaler Aggregation ermöglicht Skalierung für große Datenmengen

## 🧪 Ausführung

1. Referenzdaten & Testdaten ins Projektverzeichnis legen
2. `IMDB1.py` ausführen: In-Memory-Testanalyse
3. `IMDB2.py` oder `.accdb` öffnen: SQL-basierte Analyse

## 📚 Quelle

Diese Implementierung basiert auf der Belegarbeit [In-Memory-Datenbanken WS24/25] und orientiert sich an der Fallstudie LaserBase (Kapitel 3).

---




© 2025 Ahmed Abdelhafez
