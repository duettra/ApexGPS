# Offline-Karten

ApexGPS funktioniert ohne Signal, wenn die Kartenkacheln für das Gebiet bereits auf Ihrem Telefon sind. Das passiert auf zwei Wegen: automatisches Zwischenspeichern und manuelles Vorab-Herunterladen.

## Automatisches Zwischenspeichern

Alles, was Sie mit Signal angesehen haben, wird in den Kachel-Cache Ihres Telefons gespeichert. Besuchen Sie denselben Bereich offline → Kacheln laden sofort aus dem Cache.

Der Cache ist **pro Kartenquelle** — OpenTopoMap und Satellit sind getrennte Speicher. Einen Bereich in OpenTopoMap anzusehen hilft nicht, wenn Sie offline auf Satellit wechseln.

Die Cache-Größe wird unter **Einstellungen → Speicher** mit Aufschlüsselung pro Quelle angezeigt.

## Manuelles Vorab-Herunterladen (empfohlen für Touren)

Bevor Sie irgendwohin ohne Signal aufbrechen, laden Sie die Region bewusst herunter:

### Bereich auswählen

1. Verschieben und zoomen Sie die Karte so, dass der gewünschte Bereich den Bildschirm ausfüllt.
2. **Menü → Karten** → tippen Sie auf **Neuen Bereich herunterladen**.
3. Eine kleine Vorschau-Karte zeigt den aktuellen Bereich. Bewegen Sie sie bei Bedarf, um zu verfeinern.

### Zoombereich festlegen

Ein **Slider** definiert die Zoomstufen, die zwischengespeichert werden. Höherer Zoom = mehr Detail, aber exponentiell mehr Kacheln.

- Für eine **Wochenend-Wanderung**: 10–16 reicht meistens.
- Für eine **längere Tour** / Woche: 10–17 oder 10–18 bei maximalem Detail.
- Zoom 19+ lohnt sich für Outdoor selten — viele Kacheln, wenig mehr Information.

Die UI zeigt die geschätzte **Kachelanzahl** und **MB-Größe**, während Sie den Slider bewegen. Mit Ihrem freien Speicherplatz abgleichen.

### Download starten

Tippen Sie auf **Herunterladen**. Eine Vordergrund-Benachrichtigung erscheint; Sie können die App verlassen, das Telefon sperren, was auch immer — der Download läuft weiter. Der Fortschritt wird live in der Benachrichtigung und auf dem Karten-Hub-Bildschirm angezeigt.

Zum Abbrechen während des Downloads: Gehen Sie zum Karten-Hub → die Download-Karte hat einen **Abbrechen**-Button. (Ein Druck auf die Zurück-Pfeil-Taste bricht NICHT ab — das ist gewollt, damit Sie Tracks durchstöbern können, während Kacheln heruntergeladen werden.)

### Nur aktuelle Kartenquelle

Der Download nutzt die Kartenquelle, die beim Start aktiv ist. Um einen anderen Stil zu cachen, wechseln Sie zuerst die Kartenquelle (Layers-FAB auf der Karte), dann starten.

## Gespeicherte Regionen (Menü → Karten → Gespeicherte Offline-Karten)

Jeder abgeschlossene Download erscheint hier. Tippen Sie eine Region an, um ihre Detailansicht zu öffnen:

- **Name** — editierbar. Der Standard basiert auf dem Land / der Region, die aus dem Begrenzungsrahmen geokodiert wurde.
- **Kartenquelle**, **Zoombereich**, **Kachelanzahl**, **Größe auf der Festplatte**.
- **Auf Karte anzeigen** — schließt die Detailansicht und zoomt auf den Begrenzungsrahmen der Region.
- **Löschen** — gibt den Speicher frei. Mit Bestätigung.

Das Löschen einer gespeicherten Region entfernt ihr Kachelpaket, aber NICHT den allgemeinen Kachel-Cache. Der Bereich kann durch früheres Stöbern weiterhin zwischengespeichert sein.

## Cache-Verwaltung (Menü → Einstellungen → Speicher)

- **Gesamte Cache-Größe** über alle Kartenquellen.
- **Aufschlüsselung pro Quelle** — wie viele MB jeder Stil belegt.
- **Gesamten Cache leeren** — entfernt browse-zwischengespeicherte Kacheln für jede Quelle. Löscht NICHT Ihre gespeicherten Regionen (das sind separate Dateien).
- **[bestimmte Quelle] leeren** — nur den Browse-Cache dieses Stils.

Gespeicherte Offline-Regionen werden separat auf dem Karten-Hub verwaltet, nicht hier.

## Was auf Tour Netzwerk verbraucht

Auch wenn alles zwischengespeichert ist, versuchen manche Dinge weiterhin, das Internet zu erreichen:

- **Kartenstil wechseln**, wenn Sie den neuen Stil für diesen Bereich nicht zwischengespeichert haben — Kacheln bleiben leer.
- **Thunderforest (Outdoors)**-Kacheln werden mit Ihrem API-Schlüssel über HTTPS abgerufen.
- Nichts sonst. Tracks, Wegpunkte und Navigation sind vollständig lokal.

Wenn Ihr Telefon kein Signal hat, erscheint oben der **Offline**-Badge. Das ist das Gerät-Signal, keine App-Wahl.

## Tipps

- **Immer vor einer Tour vorab herunterladen.** Verlassen Sie sich nicht auf den Auto-Cache — er deckt nur ab, was Sie tatsächlich angesehen haben.
- **Zwei Kartenstile** können hilfreich sein: OpenTopoMap für Höhenlinien + Wege, Satellit für visuelle Realität. Beide für kritische Gebiete herunterladen.
- **Höherer Zoom = mehr Speicher, abnehmender Ertrag.** Ab Zoom 17 hilft das zusätzliche Detail selten beim Wegfinden; es sind meist Gebäudeumrisse und Straßenbeschriftungen.
- **Vor großen Downloads freien Platz prüfen.** Eine große Region bei Zoom 18 kann leicht 500 MB überschreiten.

---

**Verwandt:** [Die Kartenansicht →](map.md) · [Einstellungen →](settings.md) · [Sicherung & Wiederherstellung →](backup.md)
