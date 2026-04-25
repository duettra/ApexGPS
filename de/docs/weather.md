# Wetter

ApexGPS kann aktuelle Bedingungen, eine stündliche Vorschau und eine 7-Tages-Aussicht für jeden Punkt anzeigen, an dem Sie interessiert sind. Alles ist Opt-in.

## Wetter aktivieren

Öffnen Sie **Einstellungen → Wetter** und aktivieren Sie **Wetter anzeigen**. Sobald aktiviert:

- Ein kleiner Chip erscheint über der Statusleiste und zeigt die Bedingungen an Ihrem aktuellen GPS-Standort.
- Beim Tippen auf einen Wegpunkt erscheint im Wegpunkt-Panel eine Zeile „Wetter hier“.
- Tippen auf eine der beiden Oberflächen öffnet ein Sheet mit der vollständigen Aufschlüsselung.

Standard ist **aus**, damit die App Ihren Standort nicht ohne Ihr Einverständnis an einen Drittanbieter sendet. Wenn Sie es aktivieren, wird Ihr Breitengrad/Längengrad bei jeder Vorhersage-Abfrage an Open-Meteo (eine kostenlose öffentliche Wetter-API) gesendet.

## Was der Chip anzeigt

Der Chip wechselt zwischen einigen Zuständen:

| Zustand | Sieht aus wie | Bedeutung |
|---|---|---|
| Aktuell | `☼ 24° · 12 km/h NO` | Aktualisiert in den letzten 15 Minuten. |
| Älter | `… · vor 32 Min.` | Älter als 15 Minuten, aber wahrscheinlich noch genau. |
| Veraltet / offline | `⚠ … · vor 2 Std.` (ausgegraut) | Älter als eine Stunde oder keine Verbindung. Tippen Sie zum manuellen Aktualisieren. |

Der Chip verschwindet nicht, wenn Wetter aktiviert ist — er ändert nur sein Aussehen, um Ihnen zu zeigen, wie verlässlich die Daten sind.

## Das Vorhersage-Sheet

Tippen Sie auf den Chip (oder auf die „Wetter hier“-Zeile bei einem Wegpunkt), um das vollständige Sheet zu öffnen. Von oben nach unten:

- **Jetzt** — großes Wetter-Emoji + Temperatur, „gefühlt“ und je eine Zeile für Wind / Luftfeuchte + max. Niederschlag / Taupunkt + UV / Druck + Sonnenuntergang.
- **Nächste 24 Stunden** — acht Symbole alle 3 Stunden (Sonnen- oder Mondseite je nach lokalem Sonnenauf- und -untergang für diese Stunde) mit der stündlichen Temperatur.
- **Druckverlauf** (grün) — 24-Stunden-Liniendiagramm, hilfreich, um eine herannahende Front zu erkennen.
- **Luftfeuchte-Verlauf** (hellblau) — 24-Stunden-Liniendiagramm.
- **Nächste 7 Tage** — eine Reihe von Wochentag-Symbolen mit Höchst-/Tiefstwert des Tages.

Im Sheet-Header gibt es einen Aktualisieren-Button (↻), der den Cache umgeht und frische Daten abruft. Wenn Sie offline sind, bleiben die vorherigen Daten auf dem Bildschirm und der Veraltet-Indikator des Chips bleibt sichtbar.

## Höhenbewusste Vorhersagen auf Gipfeln

Wenn ein Wegpunkt eine gespeicherte Höhe hat (manuell eingegeben, vom GPS gesetzt oder aus einer GPX mit `<ele>` importiert), wird diese Höhe an Open-Meteo gesendet, damit das Modell weiß, dass es sich um einen Gipfel handelt und nicht um einen Talpunkt bei derselben Lat/Lon. Dasselbe gilt für den Chip: Er verwendet Ihre GPS-Höhe. Auf einem 1500 m hohen Gipfel korrigiert dies die Vorhersage-Temperatur typischerweise um ~9 °C im Vergleich zu einer reinen Koordinaten-Abfrage.

## Automatische Aktualisierung

Wenn Wetter aktiviert ist, aktualisiert der Chip alle 15 Minuten, solange die App geöffnet und online ist. Sind Sie im Flugmodus, behält der Chip die letzten bekannten Daten und einen „Veraltet“-Indikator, bis Sie wieder verbunden sind.

## Datenquellen

Die Vorhersagen kommen von **[Open-Meteo](https://open-meteo.com)**, einer kostenlosen öffentlichen API, die ECMWF, GFS, ICON und andere erstklassige globale Modelle kombiniert. Kostenlos für den persönlichen Gebrauch, kein Konto, kein API-Schlüssel.

## Einschränkungen

- **Konvektiver Regen in trockenen Regionen** ist für jedes Modell schwer vorherzusagen. Erwarten Sie gelegentliche Aussetzer bei Sturzflut-Gewittern in Regionen wie den emiratischen Hajar-Bergen. Die Wahrscheinlichkeit ist ehrlich darüber, aber lokalisierte Ereignisse können neben dem Raster liegen.
- **Unwetter-Warnungen** sind nicht Teil dieser Funktion. ApexGPS sendet keine Push-Nachrichten bei nahenden Stürmen.
- **Routen-Wetter** wird nicht unterstützt — Vorhersagen sind Punkt-Abfragen, nicht „Wie wird das Wetter entlang dieses Pfades in 2 Stunden“. Sie können einzelne Wegpunkte entlang einer Route antippen, um stichprobenartig zu prüfen.
