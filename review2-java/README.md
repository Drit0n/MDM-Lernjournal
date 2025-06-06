# Review 2 Java

## Beurteiltes Projekt

|       | Bitte ausfüllen |
|-------|-----------------|
| Review von (ZHAW-Kürzel) |        bajraedo    |
| Review durch (ZHAW-Kürzel) |       djeladri     |
| Datum Review, von/bis |    06.05.2025   |

## Review

| Thema                                                                      | Skala | Mängel* | Verbesserungsmöglichkeiten* |
|----------------------------------------------------------------------------|-------|--------|----------------------------|
| Datenquelle klar definiert (Projekt 2: zusätzlich Abgrenzung zu Projekt 1) | 2  | Datenquelle wird klar im Code und in der Doku erwähnt   | Eventuell könnte eine visuelle Darstellung des Datenflusses ergänzt werden                       |
| (Scraping vorhanden)                                                         | --  | --   | --                       |
| (Datensatz vorhanden)                                                        | 2  | Datensatz ist aussagekräftig   | Hinweise zur Datenstruktur in der Doku könnten ergänzt werden                       |
| (Datensatz-Grösse ausreichend, Aufteilung Train/Test, Kennzahlen vorhanden)  | 2  | Es ist ein Datensatz vorhanden, jedoch keine explizite Train/Test-Aufteilung   | Aufteilung der Daten für Evaluation (z. B. 80/20-Split) dokumentieren und automatisieren                       |
| Modell vorhanden                                                           | 	2  | Ein Modell zur Datenklassifikation wurde erfolgreich implementiert   | Beschreibung der Modellparameter und des Trainingsprozesses wäre hilfreich                       |
| App: auf lokalem Rechner gestartet und funktional                          | 2  | App startet lokal über Main-Klasse und ist bedienbar   | GUI ist funktional, aber optisch noch ausbaufähig                       |
| App: mehrere unterschiedliche Testcases durch Reviewer ausführbar          | 1  | Eingaben funktionieren, aber gewisse Szenarien (z. B. leere Eingaben) werden nicht abgefangen   | Input-Validierung erweitern, um Fehlerfälle abzufangen                       |
| Deployment: Falls bereits vorhanden, funktional und automatisiert          | 1  | TODO   | TODO                       |
| Code: Git-Repository vorhanden, Arbeiten mit Branches / Commits            | 2  | Git wird genutzt, aber Branch-Struktur fehlt und Commits sind teilweise unkommentiert   | Branch-Strategie einführen und Commit-Messages standardisieren                       |
| Code: Dependency Management, Dockerfile, Build funktional                  | 2  | Maven-Projekt mit funktionierendem Build, Dockerfile ist vorhanden   | README könnte Build- und Docker-Run-Anleitung genauer beschreiben                       |

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