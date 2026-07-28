# Filament-Galerie einrichten (Alles-in-GitHub-Variante)

Dateien in diesem Ordner:

- `index.html` – die fertige Galerie-Seite
- `filamente.csv` – deine Bestandsliste (Beispielinhalt, zum Anpassen)
- diese Anleitung

Alles liegt in einem einzigen GitHub-Repo: kein Google-Konto, kein separates Veröffentlichen. Bestand ändern = Datei auf github.com bearbeiten und committen.

## 1. GitHub-Repo anlegen

Auf github.com (kostenloser Account reicht) ein neues, öffentliches Repository anlegen, z. B. `benchy-galerie`.

## 2. Dateien hochladen

Die drei Dateien aus diesem Ordner per Drag & Drop im Browser hochladen ("Add file" → "Upload files"), plus einen Ordner `bilder/` mit den Fotos deiner Benchys.

## 3. GitHub Pages aktivieren

Im Repo: Settings → Pages → unter "Branch" `main` auswählen → Save. Nach ca. 1 Minute ist die Seite erreichbar unter `https://deinname.github.io/benchy-galerie/`.

## 4. CSV-Link eintragen

Der Rohdaten-Link zu deiner CSV-Datei sieht so aus:

```
https://raw.githubusercontent.com/deinname/benchy-galerie/main/filamente.csv
```

Diesen Link in `index.html` bei

```js
const CSV_URL = "PASTE_YOUR_GOOGLE_SHEET_CSV_LINK_HERE";
```

einsetzen, Datei speichern und wieder hochladen (überschreiben).

## 5. Tabelle befüllen

`filamente.csv` enthält die Spalten `Name, Material, FarbHex, Bild, AufLager`. Bei `Bild` den Pfad zum jeweiligen Foto eintragen, z. B. `bilder/sonnengelb.jpg` (relativ zur Seite) oder eine volle URL. Bei `AufLager` `ja` oder `nein` – nur `ja`-Zeilen werden angezeigt.

## 6. In Strato einbinden

Homepage-Baukasten: Inhaltselemente → **Embed-Widget** → Zahnrad-Symbol → als Embed-Code:

```html
<iframe src="https://deinname.github.io/benchy-galerie/" width="100%" height="900" frameborder="0"></iframe>
```

Speichern – fertig.

## Bestand aktualisieren

Ab jetzt: auf github.com die Datei `filamente.csv` öffnen (Stift-Symbol = "Edit"), Zeile ändern (z. B. `ja` → `nein`), unten "Commit changes" klicken. Änderung ist innerhalb weniger Minuten live, ganz ohne erneutes Hochladen der Seite selbst.

## Alternative: Google Sheets statt CSV im Repo

Falls du lieber in einer Tabellen-Oberfläche statt im Text-Editor pflegst: Google Sheet anlegen, Spalten wie oben, über "Datei → Im Web veröffentlichen → CSV" einen Link erzeugen und diesen statt des GitHub-Links bei `CSV_URL` eintragen. Funktioniert genauso, braucht aber zusätzlich ein Google-Konto und den Veröffentlichen-Schritt – daher als Standard nicht nötig.
