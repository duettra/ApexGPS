# Wegpunkte

Ein **Wegpunkt** ist ein benannter Punkt auf der Karte — ein Trail-Startpunkt, ein Gipfel, ein guter Foto-Spot, eine Hütte, der Ort, wo das Auto steht. Jeder hat einen Namen, eine Farbe und eines von 32 Symbolen.

## Einen Wegpunkt hinzufügen

### An einem bestimmten Ort (lang auf die Karte drücken)

Lange drücken auf die Karte an dem Punkt, wo der Wegpunkt hinsoll. Ein Dialog fährt hoch mit:

- **Name** — optional. Ohne Eingabe wird „Wegpunkt“ verwendet.
- **Notizen** — optionale Beschreibung.
- **Breitengrad / Längengrad** — vorausgefüllt vom angetippten Punkt; **editierbar**, falls Sie sie anpassen möchten.
- **Höhe (m)** — optional. Leer lassen, wenn unbekannt; ausfüllen, wenn der Wegpunkt eine bestimmte Höhe tragen soll (z. B. eine nachgeschlagene Gipfelhöhe).
- **Symbol** — Auswahl aus 32 Icons.
- **Farbe** — 16-Farben-Palette.
- **Speichern** / **Abbrechen**.

### Durch Eingabe von Koordinaten

Öffnen Sie **Menü → Wegpunkte** → tippen Sie auf den blauen **+**-Button unten rechts. Dasselbe Dialogfenster wie oben, aber die Lat/Lon-Felder starten leer. Geben Sie Koordinaten ein (oder fügen Sie einen `lat, lon`-String in das Breitengrad-Feld ein — die App trennt automatisch in beide Felder).

### Durch Import einer GPX-Datei

Öffnen Sie **Menü → Wegpunkte** → tippen Sie auf den blauen **Ordner-Button** unten rechts. Wählen Sie eine oder mehrere `.gpx`-Dateien. Alle Wegpunkte in den Dateien werden importiert. Duplikate (gleicher Name, innerhalb von ~11 m) werden automatisch übersprungen.

### An Ihrem aktuellen Standort

Schalten Sie GPS ein (Fadenkreuz-Button antippen, wenn das Dreieck nicht sichtbar ist), lange drücken auf das Dreieck selbst (oder sehr nah daran), und der Dialog öffnet sich vorausgefüllt mit Ihrer aktuellen Position.

### Aus einer importierten GPX (über Teilen / Öffnen-mit)

GPX-Dateien, die aus einer anderen App geöffnet werden (WhatsApp-Anhang, Gmail, Dateimanager), importieren ihre Wegpunkte ebenfalls automatisch. Wenn die GPX keinen Namen für einen Wegpunkt enthält (manche Exporter schreiben die Koordinaten ins Name-Feld), erkennt ApexGPS das und zeigt stattdessen „Wegpunkt“.

## Einen Wegpunkt ansehen

Tippen Sie einen Wegpunkt auf der Karte an. Ein Panel fährt von unten herauf mit:

- Symbol + Name.
- Koordinaten (Lat/Lon auf 6 Dezimalstellen).
- Höhe (falls gesetzt).
- Distanz zu Ihrer aktuellen GPS-Position (blau — live).
- Beschreibung (falls eingegeben).
- **Navigieren**-Button (gehende Person, blau) — startet die Luftlinien-Navigation zu diesem Wegpunkt. Siehe unten.
- **Teilen**-Button — sendet den Wegpunkt über WhatsApp / SMS / E-Mail. Der Empfänger erhält einen Text mit Name, Koordinaten, Höhe und zwei Links (ApexGPS App Link + Google Maps). Wenn er auch ApexGPS installiert hat, öffnet der Link-Tap die App direkt mit einer roten Zielscheibe an der Stelle — er kann sie als eigenen Wegpunkt speichern.
- **Bearbeiten**-Button.

Verwerfen durch Nach-unten-Wischen.

## Zu einem Wegpunkt navigieren

Tippen Sie das **Navigieren**-Symbol (gehende Person, primär-gefärbt) im Wegpunkt-Overlay an. Das Overlay schließt sich und:

- Eine **hellblaue gepunktete Linie** zeichnet sich von Ihrer Live-GPS-Position zum Wegpunkt.
- Die untere Leiste wird zu: *„Navigiere · 0,42 km · 045° NO · [Stopp]“* — die Distanz aktualisiert sich live (blau beim Auto-Update), Peilung in Grad + Himmelsrichtung (N, NO, O, SO, S, SW, W, NW).
- Das **DIST**-Feld in der Statusleiste unten zeigt ebenfalls diese Live-Distanz in Blau.
- Stoppt automatisch, wenn Sie **20 Meter** oder näher am Wegpunkt sind („Angekommen“-Meldung).
- Tippen Sie auf **Stopp**, um die Navigation jederzeit manuell zu beenden. Der Wegpunkt bleibt — antippen, um das Overlay wieder zu öffnen.

Das ist derselbe Gehen-Modus, den auch geteilte Standorte nutzen. Luftlinien-Peilung, keine Abbiegehinweise — beim Wandern abseits der Wege ist das meistens genau das, was man braucht.

Tippen Sie den Wegpunkt während der Navigation jederzeit erneut an, um das Overlay wieder zu öffnen (die Navigation läuft im Hintergrund weiter).

## Einen Wegpunkt bearbeiten

Tippen Sie den Wegpunkt an → **Bearbeiten** im Overlay, oder öffnen Sie **Menü → Wegpunkte** und tippen Sie eine Zeile an.

Dasselbe Dialogfenster wie beim Hinzufügen. Name, Notizen, **Breitengrad**, **Längengrad**, Symbol, Farbe sind alle editierbar. Beim Speichern validiert die App die Koordinaten (Lat ∈ [−90, 90], Lon ∈ [−180, 180], beide müssen Zahlen sein) und zeigt bei Fehler eine rote Fehlermeldung inline.

## Einen Wegpunkt verschieben

**Lange drücken und ziehen** Sie den Wegpunkt auf der Karte. Ziehen Sie ihn zur neuen Position. Beim Loslassen erscheint unten eine Leiste:

- **Verschieben** — bestätigt die neue Position.
- **Abbrechen** — setzt zurück an die ursprüngliche Stelle.

Nichts wird gespeichert, bis Sie Verschieben drücken. Nützlich, falls das Ziehen versehentlich war.

## Die 32 Symbole

Nach Zweck gruppiert, damit Sie sie im Picker gut durchgehen können:

| Gruppe | Symbole |
|---|---|
| **Navigation / generisch** | Flagge · Ort · Stern · Favorit |
| **Outdoor / Wandern** | Gipfel · Sattel · Aussicht · Foto · Wald · Quelle · Wasserfall · Trinkwasser · Zeltplatz · Schutzhütte · Rastplatz · Wegweiser · Ruine |
| **Informativ** | Info · Warnung |
| **Services** | Parken · Tankstelle · Restaurant · Hotel · Krankenhaus · Toiletten |
| **Transport** | Auto · Fahrrad · Fußgänger · Zug · Boot · Flugzeug · Gas |

Alle 32 sind beim Hinzufügen oder Bearbeiten auswählbar. Das Symbol wird mit dem Wegpunkt gespeichert und übersteht Export → Re-Import.

## Die Wegpunkt-Liste (Menü → Wegpunkte)

Jeder Wegpunkt, Anzahl im Titel.

### Filtern

**Filter-Symbol** → zwei Bereiche:

- **Farbe** — auf einen Farbchip tippen, um nur diese Farbe zu zeigen. **Alle** zum Zurücksetzen.
- **Symbol** — scrollbare Liste aller 32 Symbole mit ihren Icons. Eines antippen, um auf Wegpunkte mit diesem Symbol zu filtern.

Aktive Filter färben das Symbol blau.

### Sortieren

**Sortier-Symbol**:

- **Neueste zuerst** — nach Import- / Erstellungsdatum (Standard).
- **Nach Name** — alphabetisch.
- **Nächste zuerst** — nächstgelegen zu Ihrer aktuellen GPS-Position. Zeigt „(kein GPS)“, wenn das Telefon keine zwischengespeicherte Position hat.

### Suchen

Tippen Sie in das Suchfeld, um auf Wegpunkte zu filtern, deren Name ODER Beschreibung Ihren Text enthält.

### Mehrere auswählen

Lange drücken auf einen Wegpunkt in der Liste → Auswahlmodus. Weitere anhaken, dann Bulk-Löschen. Eine Bulk-Farb- oder Symbol-Änderung für Wegpunkte gibt es (noch) nicht — dafür Wegpunkt einzeln bearbeiten.

### Duplikate entfernen

Wenn Sie mit älteren App-Versionen mehrfach dieselbe GPX importiert haben, können gestapelte Duplikate entstehen (gleicher Name an gleichen Koordinaten). Tippen Sie auf das **⋮**-Überlaufmenü → **Duplikate entfernen**. Dabei bleibt die älteste Kopie erhalten; die übrigen werden gelöscht. Die Anzahl wird angezeigt.

## Löschen

Einzeln: Wischen / Papierkorb in einer Zeile, oder Löschen-Button im Bearbeiten-Dialog.

Mehrere: Auswahlmodus + Bulk-Löschen.

Kein Rückgängig. Halten Sie eine [Sicherung](backup.md) bereit, wenn Sie unsicher sind.

## Einen Wegpunkt auf der Karte zeigen

Tippen Sie aus der Listenansicht einen Wegpunkt an → die App navigiert zurück zur Karte und schwenkt zu diesem Wegpunkt. Der Folgen-Modus ist kurz pausiert, damit die Ansicht nicht sofort wieder von der nächsten GPS-Position überschrieben wird.

---

**Verwandt:** [Tracks →](tracks.md) · [Sicherung & Wiederherstellung →](backup.md) · [Die Kartenansicht →](map.md)
