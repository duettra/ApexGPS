# Die Kartenansicht

Alles dreht sich um diese Ansicht. Hier ist, was jedes Bedienelement tut.

## Gesten

| Geste | Wirkung |
|---|---|
| Ein-Finger-Ziehen | Karte verschieben. |
| Pinchen | Hinein- / Herauszoomen. |
| Zwei-Finger-Drehen | Karte rotieren. |
| Einfacher Tap auf einen Track | Track-Overlay öffnen (Höhenprofil, Scrubber). |
| Einfacher Tap auf einen Wegpunkt | Wegpunkt-Overlay öffnen (Name, Beschreibung, Bearbeiten). |
| Einfacher Tap auf das blaue Dreieck (Ihre Position) | **Standort teilen**-Panel öffnen. |
| Lange drücken auf leere Karte | Wegpunkt an diesem Punkt hinzufügen. |

## Oben rechts: der Kompass

Ein rundes Symbol mit roter Nadel. Immer sichtbar. Die Nadel zeigt immer zum geographischen Norden, egal wie die Karte gedreht ist — dient also auch als permanenter Norden-Indikator.

- **Tippen** — dreht die Karte sanft zurück auf Nord-oben.
- **Lange drücken** — schaltet die Rotationssperre um. Wenn das Symbol **blau** ist, werden Zwei-Finger-Drehgesten ignoriert; die Karte bleibt in ihrer aktuellen Ausrichtung. Nochmal lange drücken zum Entsperren.

Eine Option „Beim Start sperren“ finden Sie unter **Einstellungen → Darstellung → Beim Start Rotation sperren** für Nutzer, die die Karte nie drehen möchten.

## Rechte Spalte: die Aktions-Buttons

Von oben nach unten:

### Distanz messen
Das **Lineal-Symbol**. Antippen, um den Messmodus zu starten. Wenn der Folgen-Modus an ist, wird Pin A automatisch an Ihrer aktuellen Position gesetzt (oder in die Warteschlange aufgenommen, bis Ihr erster GPS-Fix eintrifft, mit einem „GPS wird erfasst…"-Toast — kein zweiter Tap nötig); andernfalls auf die Karte tippen, um Pin A zu setzen. Auf die Karte tippen, um weitere Pins zu setzen. Eine Linie verbindet die Pins und die untere Statusleiste zeigt die Gesamtdistanz. Während Messmodus und Folgen-Modus beide aktiv sind, verfolgt Pin A weiterhin Ihre Live-GPS-Position. **Ziehen Sie einen Pin auf das Mülleimer-Symbol** (oben rechts, direkt unter dem Kompass), um ihn zu löschen. Erneut auf das Lineal-Symbol tippen zum Beenden.

### Kartenlayer
Das **Layer-Symbol**. Bis zu sechs Stile zur Auswahl: OpenTopoMap (Wander-Fokus), OSM Standard (klar und allgemein), ESRI Topo (Standard bei Neuinstallationen), ESRI Reliefschattierung, Satellit, Outdoors (Thunderforest — benötigt einen kostenlosen API-Schlüssel aus Einstellungen → API-Schlüssel; der Eintrag ist ausgeblendet, bis ein Schlüssel gespeichert ist).

Der gewählte Stil wird über App-Neustarts hinweg gespeichert.

### Folgen-Modus (Fadenkreuz)
Drei Zustände — die Farbe des Buttons zeigt, welcher aktiv ist:

| Zustand | Farbe | Verhalten |
|---|---|---|
| **Aus** | Grau | GPS aus, kein blaues Dreieck auf der Karte. |
| **An, gesperrt** | Blau (gefüllt) | GPS an, Dreieck sichtbar, Karte zentriert alle paar Sekunden auf Sie. |
| **An, entsperrt** | Gedämpftes Blau | GPS an, Dreieck aktualisiert sich weiter, aber die Karte bleibt, wo Sie sie hingezogen haben. |

- Tap aus **Aus** → GPS an + Kamera auf Sie gesperrt.
- Tap aus **Gesperrt** → GPS aus.
- **Karte ziehen** während gesperrt → wechselt automatisch zu entsperrt. Dreieck aktualisiert sich weiter; Karte hält ihre Position.
- Tap aus **Entsperrt** → re-zentriert + sperrt wieder.
- **Lange drücken** in jedem An-Zustand → schaltet GPS sofort aus (überspringt die Re-Zentrierungs-Animation).

### Wo ist der Import-Button (+) hin?

Seit **v1.25.2** hat die Karte keinen eigenen Import-FAB mehr — GPX-Import findet nun in den Listen-Ansichten Tracks und Wegpunkte statt. Siehe [Tracks](tracks.md#importieren) oder [Wegpunkte](waypoints.md#einen-wegpunkt-hinzufügen).

## Oben links

- **☰ Menü** — Navigationsschublade (Tracks, Wegpunkte, Karten, Einstellungen).
- **Teilen-Symbol** — Ein-Tap-Abkürzung, um jeden sichtbaren Track + Wegpunkt im aktuellen Kartenausschnitt als einzelne `.gpx`-Datei zu exportieren. Öffnet das **Sichtbaren Bereich teilen**-Sheet mit einer Häkchen-Liste pro Eintrag. Siehe [Sichtbaren Bereich teilen](share-and-navigate.md#alles-teilen-was-gerade-sichtbar-ist-sichtbaren-bereich-teilen).
- **Aufnahme-Chip** — ein roter Punkt in einem dunklen Kreis. Antippen, um die Aufzeichnung Ihrer aktuellen Tour zu starten. Während der Aufzeichnung erweitert er sich zu einem Live-Timer `00:00:00`; Tap auf den Timer für **Pause / Fertig / Löschen**. Ihr Pfad wird als rote Linie auf der Karte gezeichnet, während Sie sich bewegen. Bei **Fertig** wird die Aufzeichnung als neuer Track gespeichert und das Overlay öffnet sich direkt, damit Sie sie sofort ansehen können. Siehe [Tracks → Aufzeichnung](tracks.md#aufzeichnung).

## Untere Statusleiste

Drei Werte:

- **TEMPO** — aktuelle km/h laut GPS.
- **HÖHE** — aktuelle Höhe in Metern.
- **DIST** — kontextabhängig:
  - Im **Messmodus**: Gesamtlänge der Messlinie.
  - Während **Navigation zu einem geteilten Standort**: Live-Distanz zum Ziel (blau gezeigt, wenn sich auto-aktualisierend).
  - Ansonsten: leer.

## Offline-Indikator

Wenn Ihr Gerät keine Netzverbindung hat, erscheint oben in der Leiste ein kleines rotes **„Offline“**-Symbol. Zwischengespeicherte Kacheln werden weiter angezeigt; Kacheln, die Sie noch nicht gesehen haben, laden erst wieder, wenn Sie online sind. Siehe [Offline-Karten](offline-maps.md), um Regionen vorab herunterzuladen.

---

**Verwandt:** [Tracks →](tracks.md) · [Wegpunkte →](waypoints.md) · [Standort teilen →](share-and-navigate.md)
