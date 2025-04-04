# Projekt 1 Python

## Übersicht

| | Bitte ausfüllen |
| -------- | ------- |
| Variante | Eigenes Projekt: Bevölkerungsprognose des Kantons Zürich |
| Datenherkunft | HTML (unstrukturiertes HTML mit eingebettetem CSV-Link) |
| Datenherkunft | https://opendata.swiss/de/dataset/zukunftige-bevolkerung-kanton-zurich-und-regionen-nach-geschlecht-und-alter/resource/ad753801-25e7-4bce-b8ab-a704962c95de|
| ML-Algorithmus | Prophet (Time Series Forecasting) |
| Repo URL | https://github.com/drit0n/bev-prog-zh-v2 |

## Dokumentation

### Data Scraping

![alt text](image.png)


![alt text](image-1.png)

ür meine Applikation habe ich mit Scrapy einen Spider (open_data_scraper.py) entwickelt, der den CSV-Link aus der HTML-Struktur von opendata.swiss extrahiert. Dort wird eine CSV-Datei in einer Tabelle mit der Bezeichnung „Download-URL“ eingebettet.

Der Spider ruft den CSV-Link automatisiert ab und lädt die CSV-Daten direkt über pandas von der URL.

Die Daten (Bevölkerungsstatistiken des Kantons Zürich mit Region, Altersgruppe, Jahr und Anzahl) werden nach der Extraktion direkt in eine MongoDB Atlas-Datenbank importiert.

Der MongoDB-Import erfolgt vollautomatisiert über den Scrapy Spider, der die CSV-Daten als DataFrame in MongoDB speichert.

![alt text](image-2.png)

### Training

Nach dem Import in MongoDB wird ein Prophet-Modell pro Kombination von Region und Altersgruppe trainiert.

Ein Skript (model_train.py) liest alle Daten aus MongoDB aus, filtert sie nach Region und Altersgruppe und trainiert Prophet-Modelle. Die trainierten Modelle werden als Pickle-Dateien im Verzeichnis /backend/static/ abgelegt, um sie in der Flask-App performant zu laden.

📌 Alle Modelle werden automatisiert in einem Batch-Prozess erstellt.

📌 Prognosehorizont ist im Frontend einstellbar (5, 10, 15 Jahre).


### ModelOps Automation

Ein zusätzliches Skript (train_and_deploy.py) sorgt dafür, dass nach jedem Scraping- und Importvorgang alle Modelle erneut trainiert und versioniert werden.

Eine GitHub Actions Pipeline (auto_scrape.yml) automatisiert den Scraping-Prozess sowie den Import in MongoDB. Zusätzlich automatisiert ein weiteres Workflow-File (train_model.yml) das Modelltraining und die Bereitstellung der Pickle-Dateien.

📌 Die CI/CD Pipeline sorgt für einen komplett automatisierten Daten- und Modell-Lifecycle.

### Deployment

Das Backend ist als Flask-App mit Blueprint-Architektur modular aufgebaut. Es stellt API-Endpunkte bereit, um Forecast-Daten und Insights zur Bevölkerungsentwicklung pro Region und Altersgruppe an das Frontend zu übermitteln.

Das Frontend basiert auf Flask (Jinja2) und Bootstrap. Nutzer können die Region, Altersgruppe und den Prognosehorizont auswählen. Die App zeigt die Ergebnisse in einer interaktiven Plotly-Grafik und in dynamisch generierten Insight-Boxen an.

Deployment erfolgt als Docker-Container auf Azure App Service. Das Backend-Image wird über ein Dockerfile gebaut und via GitHub Actions automatisiert nach Azure deployed.

MongoDB Atlas dient als produktive Datenquelle, aus der die App bei jeder Anfrage die benötigten Filterdaten und Basisdaten lädt.


