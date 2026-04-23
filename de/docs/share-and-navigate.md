# Standort teilen & zu einem Ziel navigieren

## Ihren aktuellen Standort teilen

### Die Kurzfassung

1. GPS muss an sein (Fadenkreuz-Button → blaues Dreieck erscheint).
2. Tippen Sie auf das **blaue Dreieck** auf der Karte.
3. Ein Panel fährt hoch mit Ihren Infos. Tippen Sie auf **Teilen**.
4. Wählen Sie WhatsApp, SMS, E-Mail, was immer. Senden.

### Was das Panel zeigt

```
Höhe 145 m · ±5 m · 19:42
Akku 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717
Google Maps: https://maps.google.com/?q=25.165183,55.409717
```

- **Höhe** — Meter über dem Meeresspiegel vom GPS (entfällt, wenn das Telefon sie nicht ermitteln konnte).
- **±Genauigkeit** — wie sicher das GPS Ihre Position kennt, in Metern. Bäume, Gebäude, enge Täler erhöhen den Wert.
- **Zeit** — wann diese Position ermittelt wurde.
- **Akku** — damit der Empfänger weiß, ob Ihnen der Strom ausgeht.
- Zwei **URLs** — die erste öffnet in ApexGPS (wenn der Empfänger es installiert hat), die zweite in jeder Karten-App.

### Was der Empfänger sieht

Die ausgehende Nachricht fügt vor den Details einen Gruß ein:

```
Hallo, das ist mein aktueller Standort.

Höhe 145 m · ±5 m · 19:42
Akku 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=...
Google Maps: https://maps.google.com/?q=...
```

In WhatsApp und ähnlichen Apps werden beide URLs zu tappbaren Links. In SMS sind sie weiterhin kopierbarer Text.

### Wenn noch keine GPS-Position vorliegt

Das Panel öffnet sich, zeigt aber „GPS wird erfasst…“ und der Teilen-Button ist deaktiviert. Sobald die erste Position verfügbar ist, aktualisiert sich das Panel und der Teilen-Button wird aktiv — Sie müssen nicht schließen und wieder öffnen.

## Einen geteilten Standort empfangen

Jemand schickt Ihnen einen `apexgps.duttra.de/loc?...`-Link.

### Wenn Sie ApexGPS installiert haben

Tippen Sie den Link an → **ApexGPS öffnet sich direkt**, die Karte schwenkt zur Position des Senders, und eine rote Zielscheibe erscheint dort. Unten fährt eine Leiste mit drei Buttons hoch:

- **Navigieren** — startet den Gehen-Modus (siehe unten).
- **Speichern** — fügt diesen Punkt als Wegpunkt hinzu (Sie wählen Name, Farbe, Symbol).
- **Verwerfen** — entfernt die Markierung, tut nichts.

### Wenn Sie ApexGPS nicht haben

Tippen Sie den Link an → öffnet eine einfache Webseite mit einer Kartenvorschau der Position plus:

- **In ApexGPS öffnen**-Button (nur Android; bietet Installation an, falls nicht vorhanden).
- **In Google Maps öffnen**-Button.

## Zu einem geteilten Standort navigieren

Nach dem Tap auf einen geteilten Link tippen Sie **Navigieren** in der unteren Leiste an:

- Eine **hellblaue gepunktete Linie** zeichnet sich von Ihrer Live-Position zum Ziel.
- Die Leiste ändert sich zu: *„Navigiere · 0,42 km · 045° NO · [Stopp]“*.
  - Distanz aktualisiert sich bei jeder GPS-Position, in **Blau** dargestellt als Hinweis auf Auto-Update.
  - **Peilung** in Grad + einer von acht Himmelsrichtungen (N, NO, O, SO, S, SW, W, NW) — laufen Sie in diese Richtung.
  - Dieselbe Distanz erscheint während der Navigation auch im **DIST**-Feld der unteren Statusleiste, in Blau.
- Wenn Sie innerhalb **20 Meter** vom Ziel sind, stoppt die Navigation automatisch mit „Angekommen“.
- **Stopp** beendet die Navigation jederzeit manuell. Die Zielscheibe bleibt; Sie können erneut **Navigieren** oder sie als Wegpunkt **Speichern**.

Das ist Luftlinien-Peilung — keine Abbiegehinweise. Beim Wandern abseits der Wege ist das meistens genau das, was man braucht; in der Stadt öffnen Sie lieber den Google-Maps-Link für Straßenrouting.

### Funktioniert auch mit eigenen Wegpunkten

Derselbe Gehen-Modus startet auch ab einem beliebigen Wegpunkt auf der Karte. Wegpunkt antippen → **Navigieren**-Symbol (gehende Person) im Overlay → das Wegpunkt-Overlay schließt sich und die Navigationsleiste übernimmt. Details in [Wegpunkte → Zu einem Wegpunkt navigieren](waypoints.md#zu-einem-wegpunkt-navigieren).

## Der Navigationskompass (Vollbild)

Während Sie zu einem Ziel navigieren, erscheint links neben Stopp ein kleines **Kompass-Symbol** 🧭 auf der Navigationsleiste. Antippen, um eine Vollbild-Kompassansicht zu öffnen. Ziehen Sie das Sheet nach unten, um zurück zur Leiste zu minimieren.

### Layout

Obere Datenzeile: **Distanz** (blau) · **Ankunft** · **Tempo** · **Höhe**.

Zentrales Analog-Ziffernblatt:
- Äußerer Ring mit Strichen alle 15° (größere Striche alle 30°).
- **N / O / S / W**-Beschriftungen auf der Scheibe.
- Ein kleines **rotes Dreieck** markiert den geographischen Norden auf der Scheibe.
- Eine **blaue Nadel** (Dreieck) zeigt in der realen Welt zum Ziel.
- **Zentrumsplakette** zeigt die aktuelle Telefon-Ausrichtung (`245°`), oder den Buchstaben **S** mit einer *„Simulierte Richtung“*-Überschrift, wenn der Kompasssensor unzuverlässig ist (Metall in der Nähe, starke Magnete, Kalibrierungs-Achten-Bewegung erforderlich).

Untere Datenzeile: **Breite · Länge · Peilung° + Himmelsrichtung · ±Genauigkeit**.

Ganz unten: **Navigation beenden** (volle Breite, beendet die Navigation komplett).

### Nutzung

Das Kompass-Ziffernblatt **rotiert mit der Orientierung Ihres Telefons**, sodass das rote Dreieck immer zum realen Norden zeigt, egal wie Sie das Telefon halten. Richten Sie die Oberkante des Telefons in Richtung der blauen Nadel, um das Ziel vor sich zu haben.

Wenn der Sensor zuverlässig arbeitet, zeigt die Plakette die Richtung in Grad; ansonsten fällt sie auf ein stilisiertes „S“ und die Beschriftung *Simulierte Richtung* zurück — als Hinweis darauf, dass die Richtung driften könnte.

### Was passiert mit der unteren Statusleiste?

Während der Kompass offen ist, wird die übliche TEMPO / HÖHE / DIST-Statusleiste am unteren Kartenrand **ausgeblendet** — das obere Panel des Kompasses zeigt diese Werte bereits in großer Schrift, eine Duplikation wäre laut. Die Statusleiste erscheint sofort wieder, wenn Sie den Kompass nach unten ziehen.

### Was die Navigationsleiste zeigt, wenn der Kompass geschlossen ist

Wenn der Kompass minimiert ist, zeigt die Navigationsleiste unten:

> *Navigiere · **045° NO** · ANK 12 min · 🧭 · Stopp*

Die Peilung und die Himmelsrichtung sind in **Blau**, weil sie sich bei jeder GPS-Position aktualisieren. ANK ist eine Schätzung basierend auf Ihrer aktuellen Geh- / Fortbewegungsgeschwindigkeit — zeigt `--`, wenn Sie stehen. Die Distanz erscheint nicht mehr in der Leiste; sie steht im **DIST**-Feld der Statusleiste unten (während der Navigation ebenfalls blau).

## Notfall-Button (optional)

**Was er ist:** ein rotes ⚠ Symbol oben links auf der Karte, als Spiegelung des Kompasses oben rechts. Ein Tap → öffnet sofort das Standort-teilen-Panel.

**Aktivieren:** Einstellungen → Darstellung → Notfall-Button → auf **An** stellen. Standardmäßig versteckt, weil die meisten Nutzer ihn nicht brauchen.

**Was passiert beim Drücken:**

- Öffnet dasselbe Standort-teilen-Panel wie ein Tap auf das blaue Dreieck.
- **Startet GPS automatisch**, wenn es nicht schon läuft, damit Sie im echten Notfall keinen „GPS wird erfasst…“-Stau haben.
- Teilt nicht direkt — Sie müssen weiterhin auf **Teilen** im Panel tippen. Das ist gewollt: Ein versehentlicher Druck in der Tasche soll nicht ohne Bestätigung Ihren Standort an jemanden senden.

Es ist eine **Abkürzung**, kein eigenes Feature. Denken Sie an „Überspringe das Dreieck-Suchen, bring mich direkt zum Teilen-Dialog“.

---

**Verwandt:** [Die Kartenansicht →](map.md) · [Einstellungen →](settings.md) · [FAQ →](faq.md)
