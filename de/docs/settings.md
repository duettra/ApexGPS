# Einstellungen

**Menü → Einstellungen** ist in vier Unterbildschirme gegliedert: Darstellung, Speicher, Daten, API-Schlüssel. Jeder hat einen ⓘ Info-Button neben den Gruppenüberschriften, der erklärt, was das Feature tut.

## Darstellung

### Design
- **System** (Standard) — folgt der Dunkel-/Hell-Einstellung Ihres Telefons.
- **Hell** — immer hell.
- **Dunkel** — immer dunkel.

### Standardkarte
Der Kartenstil, der beim Start der App verwendet wird. Sechs Optionen; siehe [Die Kartenansicht → Kartenlayer](map.md) für Details zu jedem. Sie können jederzeit während der Sitzung über den Layer-Button auf der Karte wechseln.

### Linienbreite Tracks
Slider, 4–24 dp. Dickere Linien sind bei vielen überlappenden Tracks besser sichtbar; dünnere Linien sehen bei hohem Zoom sauberer aus. Standard ist etwa 6 dp.

### Wegpunkt-Größe
Klein / Normal / Groß / XL. Das ist ein Multiplikator auf die automatische zoom-abhängige Größe — Marker schrumpfen bei niedrigem Zoom und wachsen bei hohem Zoom, damit sie lesbar bleiben; diese Einstellung schiebt den gesamten Bereich nach oben oder unten. Standard ist Normal (1,0×).

### Beim Start Rotation sperren
- **Aus** (Standard) — Zwei-Finger-Drehgesten funktionieren vom ersten Moment an.
- **An** — Rotation ist beim Start gesperrt; Sie müssen den Kompass lange drücken, um zu entsperren. Nützlich, wenn Sie die Karte oft versehentlich drehen und den zusätzlichen Schritt zum Zurückdrehen hassen.

### Notfall-Button
- **Aus** (Standard) — kein Notfall-Button auf der Karte.
- **An** — zeigt ein rotes ⚠ Symbol oben links auf der Karte (als Spiegelung des Kompasses oben rechts). Tap → öffnet das Standort-teilen-Panel und startet GPS bei Bedarf automatisch. Siehe [Teilen → Notfall-Button](share-and-navigate.md#notfall-button-optional).

## Speicher

### Cache-Nutzung
Gesamtgröße des Browse-Kachel-Caches + Aufschlüsselung pro Kartenquelle.

### Cache leeren
- **Alle leeren** — entfernt Browse-zwischengespeicherte Kacheln aus jedem Stil. Löscht NICHT Ihre gespeicherten Offline-Regionen.
- **[bestimmte Quelle] leeren** — Leerung pro Stil. Nützlich, wenn ein Stil besonders viel Platz belegt (z. B. ist Satellitenbild schwerer als Höhenlinienkarte).

Der Browse-Kachel-Cache baut sich wieder auf, während Sie Bereiche mit Signal ansehen. Das Leeren betrifft nicht Daten, die Sie explizit über den Karten-Hub-Download gespeichert haben.

## Daten

### Sichern
Eine ZIP mit Tracks, Wegpunkten, gespeicherten Offline-Regionen und Einstellungen erstellen. Optionale Toggles ermöglichen es, Kategorien auszuschließen (gespeicherte Karten sind am größten — oft für schnelle „nur meine Tracks“-Sicherungen weggelassen). Siehe [Sicherung & Wiederherstellung](backup.md).

### Wiederherstellen
Eine existierende `apexgps-backup-*.zip` öffnen. **Zusammenführen** (zu vorhandenen hinzufügen) oder **Ersetzen** (vorhandene überschreiben) wählen. Siehe [Sicherung & Wiederherstellung → Zusammenführen vs. Ersetzen](backup.md#zusammenführen-vs-ersetzen).

### Alle Tracks optimieren
Führt die Douglas-Peucker-Vereinfachung auf jedem importierten Track durch. Reduziert die Punktanzahl, ohne die Form sichtbar zu verändern. Nützlich, wenn Sie viele stark detaillierte GPX-Dateien importiert haben und die Karte auf einem älteren Telefon träge wirkt. Die Gesamtanzahl der betroffenen Tracks wird angezeigt.

Einzelne Tracks können auch einzeln aus der Track-Detailansicht optimiert werden.

### Beispieldaten laden
Importiert 3 Beispiel-Wegpunkte (Gipfel / Aussicht / Wanderparkplatz) und 3 Tracks unterschiedlicher Länge und Höhenprofile (5 km / 12 km / 25 km, mit realistischem Aufstieg von +260 m bis +3030 m). Nützlich, um das Verhalten der App ohne eigene GPX-Dateien auszuprobieren. Nach dem Import sind es ganz normale Tracks/Wegpunkte — jederzeit löschbar.

## API-Schlüssel

### Thunderforest
Erforderlich, um den **Outdoors (Thunderforest)**-Kachelstil zu nutzen. Kostenloser „Hobby“-Plan: 150 000 Kachelabrufe pro Monat, keine Kreditkarte. Registrieren Sie sich unter [thunderforest.com](https://www.thunderforest.com/), kopieren Sie Ihren API-Schlüssel, fügen Sie ihn hier ein → **Speichern**.

Ohne Schlüssel zeigt der Outdoors-Stil einen Platzhalter; die anderen fünf Stile funktionieren ohne jeden Schlüssel.

## Über

**Einstellungen → Über** zeigt die App-Version, Attributionen und Kontakt-E-Mail — außerdem die **Anleitung**: antippbare Einträge für jedes Kapitel dieser Dokumentation, in der App gebündelt, sodass die vollständige Anleitung offline funktioniert. Tippen Sie ein Kapitel an → ein Reader öffnet sich und rendert das Kapitel in der App. Kapitelübergreifende Links innerhalb der Seiten werden befolgt; die Zurück-Pfeil-Taste kehrt zur Kapitelliste zurück. Ein **„Online lesen“**-Link unten öffnet dieselbe Dokumentation unter [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) im Browser. Für Hilfe: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

---

**Verwandt:** [FAQ →](faq.md) · [Sicherung & Wiederherstellung →](backup.md)
