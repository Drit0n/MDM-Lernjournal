# Review 1 Python

## Beurteiltes Projekt

|       | Bitte ausfüllen |
|-------|-----------------|
| Review von (ZHAW-Kürzel) |      Mansan      |
| Review durch (ZHAW-Kürzel) |      DJELADRI      |
| Datum Review, von/bis |  25.03.2025    |

## Review

| Thema                                                                      | Skala | Mängel* | Verbesserungsmöglichkeiten* |
|----------------------------------------------------------------------------|-------|--------|----------------------------|
| Datenquelle klar definiert (Projekt 2: zusätzlich Abgrenzung zu Projekt 1) | 2  | Datenquelle ist klar definiert und nachvollziehbar   | Allenfalls könnte je nach anwendungsbedarf featue engineering betrieben werden, sofern nicht vorhanden.                     |
| Scraping vorhanden                                                         | 2  | Web Scraping ist grundsätzlich vorhanden  | Verbesserung der Fehlerbehandlung bei fehlgeschlagenem Scrape möglich.                       |
| Scraping automatisiert                                                     | 1  | Scraping nicht vollständig automatisiert   | Automatisierung über Scheduler (z. B. CRON, GitHub Actions) denkbar.                       |
| Datensatz vorhanden                                                        | 2  | Datensatz vorhanden und wird verwendet   | Kurze Erläuterung zur Datenstruktur/Datenmenge im UI oder Doku wünschenswert. Arbeiten mit Dokstrings sind wichtig für das verständnis                       |
| Erstellung Datensatz automatisiert, Verwendung Datenbank                   | 1  | Automatisierung nicht transparent, keine klare DB-Anbindung   | Einbindung einer Datenbank (z. B. MongoDB) zur Persistenz könnte das System robuster machen.                       |
| Datensatz-Grösse ausreichend, Aufteilung Train/Test, Kennzahlen vorhanden  | 1  | Keine klare Info zu Aufteilung/Grösse/Validierung sichtbar   | TODO                       |
| Modell vorhanden                                                           | 2  | Modell ist integriert   | Beschreibung des verwendeten Modells (z. B. ARIMA, Prophet etc.) könnte ergänzt werden.                       |
| Modell-Versionierung vorhanden (ModelOps)                                  | 0  | 	Keine Versionierung vorhanden   | Modellversionierung über MLflow oder manuelle Verwaltung sinnvoll.                       |
| App: auf lokalem Rechner gestartet und funktional                          | 2  | Funktionalität gegeben (auch online überprüfbar)   | TODO                       |
| App: mehrere unterschiedliche Testcases durch Reviewer ausführbar          | 1  | Eingabemöglichkeiten etwas eingeschränkt   | Könnte durch erweiterte User-Inputs (z. B. Zeitbereich, weitere Währungen) verbessert werden                       |
| Deployment: Falls bereits vorhanden, funktional und automatisiert          | 1  | Deployment ist in Azure aufrufbar, aber nicht automatisiert   | CI/CD-Prozess könnte dokumentiert oder via GitHub Actions automatisiert werden                     |
| Code: Git-Repository vorhanden, Arbeiten mit Branches / Commits            | 0  | Keine .gitignore, API-Key hardcodiert, keine Docker-Nutzung   | Verwendung von .env-Dateien für API-Keys, .gitignore für Sicherheit, Dockerisierung zur Portabilität.                      |
| Code: Dependency Management, Dockerfile, Build funktional                  | 1  | 	App vollständig in app.py, keine Trennung in Module  | Empfehlung: Trennung in Routen, Logik, Daten, Modell etc. zur besseren Wartbarkeit und Fehlerdiagnose.                       |

\* wenn fehlend: mögliche Schwierigkeiten und Lösungen besprechen

## Skala

| Skala |                 |
|-------|-----------------|
| 0     | fehlt           |
| 1     | mit Lücken      |
| 2     | alles vorhanden |
| 3     | übertroffen     |

## Hinweise

Der Projekt-Review fliesst nicht in die Beurteilung der Leistungsnachweise ein, soll aber dem Studierenden dazu dienen, bis zur Abgabe noch Verbesserungsmöglichkeiten zu erkennen. Der Review *des fremden Projektes* muss als Teil des *eigenen* Lernjournals abgegeben werden.