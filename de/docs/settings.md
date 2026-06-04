# Einstellungen

**Menü → Einstellungen** ist in fünf Unterbildschirme gegliedert: Darstellung, Speicher, Daten, API-Schlüssel, Erweitert. Jeder hat einen ⓘ Info-Button neben den Gruppenüberschriften, der erklärt, was das Feature tut.

## Darstellung

### Design
- **System** (Standard) — folgt der Dunkel-/Hell-Einstellung Ihres Telefons.
- **Hell** — immer hell.
- **Dunkel** — immer dunkel.

### Standardkarte
Der Kartenstil, der beim Start der App verwendet wird. Sechs Optionen; siehe [Die Kartenansicht → Kartenlayer](map.md) für Details zu jedem. Sie können jederzeit während der Sitzung über den Layer-Button auf der Karte wechseln.

### Textgröße
Slider, 50 %–150 % in 10-%-Schritten. Skaliert **den gesamten App-Text** — Menüs, Listen, die Statusleiste, Dialoge. Wirkt *zusätzlich* zur System-Schriftgröße Ihres Telefons statt sie zu ersetzen, überschreibt also keine systemweite Bedienhilfen-Einstellung; ApexGPS wird nur relativ dazu größer oder kleiner. Standard ist 100 %. Nützlich, wenn eine große System-Schrift die Menüs überlaufen lässt oder wenn Sie speziell in ApexGPS größeren Text möchten.

### Größe der Kartenbedienelemente
Slider, 50 %–150 % (gleiche Schritte wie Textgröße). Ändert die Größe der Bedienelemente auf der Karte (die Hauptschaltflächen, den Kompass und die Aufnahme-Leiste). Verkleinern Sie sie, um auf einem kleinen Telefon Platz zurückzugewinnen, wenn die Elemente die Karte überladen; vergrößern Sie sie für leichteres Tippen mit Handschuhen. Die Schaltflächen werden nie kleiner als eine bequeme Tippfläche. Standard ist 100 %.

### Wegpunkt-Größe
Slider, 50 %–200 %. Ein Multiplikator auf die automatische zoom-abhängige Größe — Marker schrumpfen bei niedrigem Zoom und wachsen bei hohem Zoom, damit sie lesbar bleiben; diese Einstellung schiebt den gesamten Bereich nach oben oder unten. Standard ist 100 %. (Vor 1.38.0 war dies eine Auswahl Klein/Normal/Groß/XL; jetzt ein Slider für feinere Abstufung.)

### Linienbreite Tracks
Slider von dünn bis dick. Dickere Linien sind bei vielen überlappenden Tracks besser sichtbar; dünnere Linien sehen bei hohem Zoom sauberer aus. Standard ist eine mittlere Breite.

### Beim Start Rotation sperren
- **Aus** (Standard) — Zwei-Finger-Drehgesten funktionieren vom ersten Moment an.
- **An** — Rotation ist beim Start gesperrt; Sie müssen den Kompass lange drücken, um zu entsperren. Nützlich, wenn Sie die Karte oft versehentlich drehen und den zusätzlichen Schritt zum Zurückdrehen hassen.

## Speicher

### Cache-Nutzung
Gesamtgröße des Browse-Kachel-Caches + Aufschlüsselung pro Kartenquelle.

### Cache-Größe für Kartenkacheln
Wählen Sie, wie viel Speicherplatz für automatisch zwischengespeicherte Kartenkacheln genutzt wird: **250 MB**, **500 MB** (Standard), **1 GB**, **2 GB**. Der neue Wert greift sofort beim nächsten Kachel-Abruf — kein App-Neustart nötig. Gespeicherte Offline-Regionen werden separat abgelegt und nicht gegen dieses Limit gerechnet; das Ändern der Cache-Größe löscht also nie eine bewusst heruntergeladene Region.

### Cache leeren
- **Alle leeren** — entfernt Browse-zwischengespeicherte Kacheln aus jedem Stil. Löscht NICHT Ihre gespeicherten Offline-Regionen.
- **[bestimmte Quelle] leeren** — Leerung pro Stil. Nützlich, wenn ein Stil besonders viel Platz belegt (z. B. ist Satellitenbild schwerer als Höhenlinienkarte).

Der Browse-Kachel-Cache baut sich wieder auf, während Sie Bereiche mit Signal ansehen. Das Leeren betrifft nicht Daten, die Sie explizit über den Karten-Hub-Download gespeichert haben.

## Daten

### Sichern
Eine ZIP mit Tracks, Wegpunkten, gespeicherten Offline-Regionen und Einstellungen erstellen. Toggles ermöglichen es, Kategorien auszuschließen. Gespeicherte Offline-Regionen haben einen **Drei-Wege-Modus**: **Nicht einschließen** (überspringen) / **Rezept** (klein — nur die Anweisungen, jede Region neu herunterzuladen, funktioniert plattformübergreifend zwischen Android und iOS) / **Vollständige Kacheln** (das alte Verhalten — bettet die rohen Kachelpakete ein, groß, aber offline wiederherstellbar, nur Android). Siehe [Sicherung & Wiederherstellung](backup.md).

### Wiederherstellen
Eine existierende `apexgps-backup-*.zip` öffnen. **Zusammenführen** (zu vorhandenen hinzufügen) oder **Ersetzen** (vorhandene überschreiben) wählen. Siehe [Sicherung & Wiederherstellung → Zusammenführen vs. Ersetzen](backup.md#zusammenführen-vs-ersetzen).

### Alle Tracks optimieren
Führt die Douglas-Peucker-Vereinfachung auf jedem importierten Track durch. Reduziert die Punktanzahl, ohne die Form sichtbar zu verändern. Nützlich, wenn Sie viele stark detaillierte GPX-Dateien importiert haben und die Karte auf einem älteren Telefon träge wirkt. Die Gesamtanzahl der betroffenen Tracks wird angezeigt.

Einzelne Tracks können auch einzeln aus der Track-Detailansicht optimiert werden.

### Beispieldaten laden
Eine reale Aufzeichnung der **Watzmann-Überschreitung** (Berchtesgaden): Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, ~22,6 km Rundtour / +2250 m / etwa 10–12 h Gehzeit. Drei markante Wegpunkte mit echten Koordinaten: Trailhead Wimbachbrücke (628 m), DAV-Watzmannhaus (1930 m), Watzmann-Mittelspitze (Hauptgipfel, 2713 m). Beim ersten Start einer Neuinstallation automatisch importiert; mit dieser Schaltfläche können Sie die Daten bei Bedarf erneut importieren, falls Sie sie gelöscht haben und zurückhaben möchten. Nach dem Import sind es ganz normale Tracks/Wegpunkte — jederzeit löschbar.

## API-Schlüssel

### Thunderforest
Erforderlich, um den **Outdoors (Thunderforest)**-Kachelstil zu nutzen. Kostenloser „Hobby“-Plan: 150 000 Kachelabrufe pro Monat, keine Kreditkarte. Registrieren Sie sich unter [thunderforest.com](https://www.thunderforest.com/), kopieren Sie Ihren API-Schlüssel, fügen Sie ihn hier ein → **Speichern**.

**Ohne Schlüssel wird der Outdoors-Stil ausgeblendet** — sowohl im Kartenstil-Picker als auch im Picker zum Download einer Offline-Region — damit Sie ihn nicht versehentlich wählen und OpenTopoMap-Fallback-Kacheln sehen. Schlüssel einfügen → der Eintrag erscheint in beiden Menüs wieder. Die anderen fünf Stile funktionieren ohne jeden Schlüssel.

## Erweitert

### Energiesparmodus bei hoher Geschwindigkeit
Wenn Sie sich schneller als **36 km/h** (≈22 mph) bewegen — beim Fahren, im Zug, auf einem schnellen E-Bike — senkt die App ihre GPS-Abtastrate auf einen Fix alle **10 Sekunden** statt einen pro Sekunde. Straßenförmige Tracks werden weiterhin sauber aufgezeichnet; die Spur-Genauigkeit ist beim Fahren reduziert. Spart auf der Autobahn-Etappe einer Autofahrt etwa die Hälfte des GPS-Stromverbrauchs ohne sichtbaren Verlust der Routengeometrie. Ausschalten, wenn Sie bei hoher Geschwindigkeit volle Abtastung brauchen (z. B. Rallye-Telemetrie).

## Über

**Einstellungen → Über** zeigt die App-Version, Attributionen und Kontakt-E-Mail — außerdem die **Anleitung**: antippbare Einträge für jedes Kapitel dieser Dokumentation, in der App gebündelt, sodass die vollständige Anleitung offline funktioniert. Tippen Sie ein Kapitel an → ein Reader öffnet sich und rendert das Kapitel in der App. Kapitelübergreifende Links innerhalb der Seiten werden befolgt; die Zurück-Pfeil-Taste kehrt zur Kapitelliste zurück. Ein **„Online lesen“**-Link unten öffnet dieselbe Dokumentation unter [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) im Browser. Für Hilfe: [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

Unter der Anleitung öffnet eine **Datenschutzerklärung**-Zeile denselben In-App-Reader auf dem Datenschutz-Kapitel — kein Internet nötig, um zu lesen, welche Daten die App erhebt (nichts über das hinaus, was auf Ihrem Telefon ist) und wie sie genutzt werden. Derselbe Inhalt wird unter [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) gespiegelt für alle, die ihn vor der Installation lesen möchten.

---

**Verwandt:** [FAQ →](faq.md) · [Sicherung & Wiederherstellung →](backup.md)
