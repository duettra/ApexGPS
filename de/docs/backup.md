# Sicherung & Wiederherstellung

ApexGPS speichert alles **lokal auf Ihrem Telefon**. Es gibt keinen Cloud-Abgleich. Wenn Sie auf Werkseinstellungen zurücksetzen, das Telefon wechseln oder die App deinstallieren, **sind Ihre Tracks, Wegpunkte und heruntergeladenen Offline-Regionen weg** — außer Sie haben vorher eine Sicherung erstellt.

Sicherungen sind manuell, aber einfach. Führen Sie sie regelmäßig durch, wenn Sie Daten haben, die Ihnen wichtig sind.

## Was in einer Sicherung enthalten ist

- **Alle Tracks** (GPX-Daten, Name, Farbe, Sichtbarkeit).
- **Alle Wegpunkte** (Name, Beschreibung, Koordinaten, Höhe, Farbe, Symbol).
- **Alle gespeicherten Offline-Kartenregionen** (die echten Kachelpakete — können groß sein).
- **Alle Einstellungen** (Design, Standard-Kartenquelle, Track-Linienbreite, Wegpunkt-Größe, Rotationssperre, Sichtbarkeit des Notfall-Buttons).

Was **nicht** in einer Sicherung enthalten ist:

- Der **Browse-Kachel-Cache** (automatisch zwischengespeicherte Kacheln aus allgemeiner Nutzung). Nicht gesichert, weil er leicht wiederherstellbar und potenziell riesig ist. Gespeicherte Offline-Regionen werden gesichert; der Browse-Cache nicht.
- Der **Thunderforest-API-Schlüssel** wird mit den Einstellungen gesichert, sodass Sie ihn nicht erneut eingeben müssen.

## Eine Sicherung erstellen

1. **Menü → Einstellungen → Daten → Sicherung**.
2. Optional: Kategorien abwählen, die Sie nicht möchten (gespeicherte Karten sind am größten — weglassen, wenn Sie nur Tracks/Wegpunkte sichern wollen, spart Platz).
3. Tippen Sie auf **Sicherung erstellen**.
4. Die ZIP-Datei wird im privaten Speicher der App erzeugt. Ein Teilen-Dialog öffnet sich — wählen Sie, wohin:
   - **Google Drive / Dropbox / OneDrive** — Cloud-Aufbewahrung.
   - **An sich selbst senden** per E-Mail / Chat.
   - **In Downloads speichern** über einen Dateimanager.

Die ZIP heißt z. B. `apexgps-backup-2026-04-19.zip`. Der Dateiname enthält das Datum.

**Eine Sicherung mit gespeicherten Offline-Regionen kann eine bis zwei Minuten dauern** und produziert eine große ZIP (50–500 MB, je nachdem, wie viele Regionen Sie haben). Die UI zeigt den Fortschritt.

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

Die Wiederherstellung läuft als Streaming-Read — auch bei mehreren hundert MB ZIP sollte es schnell sein. Falls sie mittendrin fehlschlägt, können Teilkategorien schon übernommen worden sein; sicherheitshalber erneut ausführen.

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
