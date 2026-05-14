# Sicherung & Wiederherstellung

ApexGPS speichert alles **lokal auf Ihrem Telefon**. Es gibt keinen Cloud-Abgleich. Wenn Sie auf Werkseinstellungen zurücksetzen, das Telefon wechseln oder die App deinstallieren, **sind Ihre Tracks, Wegpunkte und heruntergeladenen Offline-Regionen weg** — außer Sie haben vorher eine Sicherung erstellt.

Sicherungen sind manuell, aber einfach. Führen Sie sie regelmäßig durch, wenn Sie Daten haben, die Ihnen wichtig sind.

## Was in einer Sicherung enthalten ist

- **Alle Tracks** (GPX-Daten, Name, Farbe, Sichtbarkeit, Aktivitäts-Tag).
- **Alle Wegpunkte** (Name, Beschreibung, Koordinaten, Höhe, Farbe, Symbol).
- **Alle gespeicherten Offline-Kartenregionen** — siehe [Rezept vs. Vollständige Kacheln](#rezept-vs-vollständige-kacheln) unten für zwei Wege, diese zu sichern.
- **Alle Einstellungen** (Design, Standard-Kartenquelle, Track-Linienbreite, Wegpunkt-Größe, Rotationssperre, Energiesparmodus usw.).

Was **nicht** in einer Sicherung enthalten ist:

- Der **Browse-Kachel-Cache** (automatisch zwischengespeicherte Kacheln aus allgemeiner Nutzung). Nicht gesichert, weil er leicht wiederherstellbar und potenziell riesig ist.
- Der **Thunderforest-API-Schlüssel** wird mit den Einstellungen gesichert, sodass Sie ihn nicht erneut eingeben müssen.

## Eine Sicherung erstellen

1. **Menü → Einstellungen → Daten → Sicherung**.
2. Wählen Sie aus, was eingeschlossen werden soll — es gibt Häkchen für Tracks / Wegpunkte / Einstellungen plus eine **Drei-Wege-Auswahl für Offline-Kartenregionen** (siehe unten).
3. Tippen Sie auf **Sicherung erstellen**.
4. Die ZIP-Datei wird im privaten Speicher der App erzeugt. Ein Teilen-Dialog öffnet sich — wählen Sie, wohin:
   - **Google Drive / Dropbox / OneDrive** — Cloud-Aufbewahrung.
   - **An sich selbst senden** per E-Mail / Chat.
   - **In Downloads speichern** über einen Dateimanager.

Die ZIP heißt z. B. `apexgps-backup-2026-05-14.zip`. Der Dateiname enthält das Datum.

### Rezept vs. Vollständige Kacheln

Für gespeicherte Offline-Kartenregionen wählen Sie **einen von drei Modi**:

| Modus | Größe | Verhalten | Plattformübergreifend? |
|---|---|---|---|
| **Nicht einschließen** | am kleinsten | Region-Zeilen werden überhaupt nicht gesichert. | n.a. |
| **Rezept** | ~80 KB gesamt | Jede Region wird als kurze „Anweisungs-Karte" gesichert — Name, Bounding-Box, Zoom-Bereich, Kachelquelle. Beim Wiederherstellen erscheinen die Regionen unter **Karten → Gespeicherte Offline-Karten** markiert mit *„Noch nicht heruntergeladen · X Kacheln"*, mit einer **Herunterladen**-Schaltfläche, um die tatsächlichen Kacheln vom Kachelserver zu holen. | **Ja** — funktioniert zwischen Android und iOS. |
| **Vollständige Kacheln** | 50–500 MB | Das echte MBTiles-Paket jeder Region wird in die ZIP eingebettet. Beim Wiederherstellen sind die Regionen sofort offline nutzbar; kein erneuter Download nötig. | **Nur Android.** iOS kann die eingebetteten Pakete (noch) nicht lesen. |

**Wählen Sie Rezept** für geräteübergreifende Umzüge (Telefonwechsel, Sicherung mit einem iOS-Freund teilen oder eine „für alle Fälle"-Sicherung, die Sie für immer auf Drive aufheben). Der erneute Download ist über WLAN schnell und nutzt Ihre aktuellsten Kacheln.

**Wählen Sie Vollständige Kacheln**, wenn Sie ausdrücklich eine in einem Schritt offline wiederherstellbare Sicherung nur auf Android wollen — nützlich vor einer Reise, bei der Sie Ihr Telefon zurücksetzen und am Ziel kein WLAN haben könnten.

**Eine Vollständige-Kacheln-Sicherung zu erstellen kann eine bis zwei Minuten dauern** und produziert eine große ZIP. Die UI zeigt den Fortschritt.

## Eine Sicherung wiederherstellen

### Der einfache Weg

Tippen Sie in einem Dateimanager / Google Drive / Gmail-Anhang auf eine `apexgps-backup-*.zip`-Datei. Android bietet Apps an, die sie öffnen können; wählen Sie ApexGPS. Die App öffnet sich direkt zu Einstellungen → Daten mit einem Wiederherstellungs-Dialog.

### Über Einstellungen

1. **Menü → Einstellungen → Daten → Wiederherstellen**.
2. ZIP aus dem Dateiauswahl-Dialog wählen.
3. Modus wählen (siehe unten).
4. Bestätigen.

### Zusammenführen vs. Ersetzen

Beide Modi arbeiten die ZIP Kategorie für Kategorie ab.

| Modus | Was passiert |
|---|---|
| **Zusammenführen** | Neue Einträge aus der Sicherung werden zu dem HINZUGEFÜGT, was bereits in Ihrer App ist. Tracks mit gleichem Namen werden nicht kollabiert — Sie können Duplikate bekommen; nutzen Sie **Einstellungen → Daten → Alle optimieren** oder Einzellöschungen zum Aufräumen. |
| **Ersetzen** | Jede Kategorie in der Sicherung ERSETZT, was Sie aktuell haben. Wenn die Sicherung Tracks enthält, werden alle vorhandenen Tracks zuerst gelöscht. Kategorien, die Sie beim Erstellen der Sicherung abgewählt haben, werden beim Wiederherstellen NICHT berührt. |

**Faustregel:**

- Neues Telefon → **Ersetzen** (Sie wollen den exakten Stand vom alten Telefon).
- Eine Wegpunkt-Sammlung aus der Sicherung eines Freundes holen → **Zusammenführen** (eigene Daten behalten, seine hinzufügen).

Die Wiederherstellung läuft als Streaming-Read — auch bei mehreren hundert MB ZIP sollte es schnell sein. Während sie läuft, erscheint unter der Wiederherstellen-Schaltfläche ein Fortschrittsbalken + Beschriftung („Stelle Track N von M wieder her…" / „Stelle Wegpunkt N von M wieder her…"), damit Sie sehen, wie weit es noch geht. Falls sie mittendrin fehlschlägt, können Teilkategorien schon übernommen worden sein; sicherheitshalber erneut ausführen.

### Rezept-Modus-Wiederherstellung — die Regionen zurückladen

Wenn die Sicherung den **Rezept**-Modus für Offline-Karten verwendet hat, ist die Wiederherstellung sofort fertig, aber Sie sehen die Regionen unter **Karten → Gespeicherte Offline-Karten** markiert mit *„Noch nicht heruntergeladen · X Kacheln"* mit einer **Herunterladen**-Schaltfläche. Antippen, um die Kacheln vom Kachelserver neu zu holen. Wenn die Region Thunderforest-Kacheln nutzt und Sie Ihren API-Schlüssel noch nicht eingefügt haben, zeigt die App einen einmaligen Toast, der Sie auffordert, ihn zuerst unter **Einstellungen → API-Schlüssel** hinzuzufügen; sobald der Schlüssel da ist, erneut auf Herunterladen tippen.

### Wiederherstellung über App-Versionen hinweg

Eine v2-Sicherung (erstellt mit dieser Version oder neuer) lässt sich auf älteren App-Versionen nicht öffnen und zeigt *„Sicherungsformat v2 ist neuer, als diese App unterstützt. Bitte aktualisieren Sie ApexGPS."* — zuerst aktualisieren, dann wiederherstellen. Ältere v1-Sicherungen lassen sich weiterhin auf der aktuellen App ohne Extra-Schritt wiederherstellen.

## Auf ein neues Telefon umziehen

1. **Auf dem alten Telefon:** Sicherung mit allen Kategorien erstellen. An sich selbst per E-Mail senden / auf Drive speichern.
2. **Auf dem neuen Telefon:** ApexGPS installieren, öffnen, Berechtigungen erteilen, in E-Mail / Drive einloggen.
3. **ZIP auf das neue Telefon laden**, antippen → mit **Ersetzen** wiederherstellen.

Fertig. Ihre Tracks, Wegpunkte, gespeicherten Karten und Einstellungen sind alle da.

## Schutz vor Werkszurücksetzung / Deinstallation

Androids Auto-Backup stellt bei Neuinstallation *einen Teil* Ihrer Einstellungen wieder her (Design, Standard-Kartenquelle, API-Schlüssel, Linienbreite, Wegpunkt-Größe, Rotationssperre) aus Google Drive. Das umfasst NICHT Tracks, Wegpunkte oder Offline-Regionen — nur leichte Einstellungen.

**Der einzige zuverlässige Weg, Ihre Wanderdaten über eine Neuinstallation hinweg zu bewahren, ist eine ZIP-Sicherung.** Erstellen Sie eine vor jedem Telefonwechsel oder größeren OS-Update.

---

**Verwandt:** [Einstellungen →](settings.md) · [Tracks →](tracks.md) · [Wegpunkte →](waypoints.md)
