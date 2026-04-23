# Tracks

Ein **Track** ist eine aufgezeichnete Strecke — eine Abfolge von GPS-Punkten, als Linie auf der Karte verbunden. Tracks erhalten Sie durch Import von GPX-Dateien (aus GaiaGPS, Strava, Garmin Connect, wikiloc.com oder allem anderen, das GPX exportiert).

**Hinweis:** ApexGPS zeichnet in dieser Version selbst keine neuen Tracks auf. Live-Aufzeichnung ist für eine zukünftige Version geplant.

## Importieren

### Aus einer Datei

Öffnen Sie **Menü → Tracks** → tippen Sie auf den blauen **Ordner-Button** unten rechts. Wählen Sie eine oder mehrere `.gpx`-Dateien aus Ihrem Telefonspeicher (Mehrfachauswahl möglich). Die App navigiert Sie zurück zur Karte und zoomt automatisch auf die importierten Tracks.

### Über das Teilen-Menü (WhatsApp, E-Mail, andere Apps)

Jemand schickt Ihnen eine `.gpx`-Datei? Tippen Sie sie im Chat / der E-Mail / dem Dateimanager an → das System bietet an, sie mit ApexGPS zu öffnen → die App importiert sie automatisch und bringt Sie zur Karte.

### Was wird importiert

- Tracklinien (mit Höhendaten, falls die GPX sie enthält).
- Alle in der GPX-Datei eingebetteten Wegpunkte (jeweils mit Name, Beschreibung und Symbol, auf das nächstliegende Symbol in ApexGPS abgebildet).

**Duplikat-Schutz:** Wenn Sie dieselbe GPX erneut importieren, werden Wegpunkte, die bereits an diesen Koordinaten existieren, nicht erneut hinzugefügt. Tracklinien WERDEN erneut importiert (sie heißen gleich, das Duplikat können Sie manuell löschen).

## Einen Track auf der Karte ansehen

Tippen Sie auf eine Tracklinie auf der Karte. Ein Panel fährt von unten herauf mit:

- Track-Name + Distanz.
- **Höhenprofil** — ein kleines Diagramm. Ziehen Sie Ihren Finger darüber, um den Track entlang zu scrubben; ein Fadenkreuz zeigt, wo dieser Punkt auf der Karte ist.
- **Aufstieg / Abstieg** gesamt.
- **Bearbeiten**-Button → öffnet die Track-Detailansicht.
- **Teilen**-Button → exportiert den Track als `.gpx`-Datei, die Sie beliebig versenden können.
- **Ausblenden**-Button → minimiert das Panel zu einem schmalen Balken unten (damit Sie mit der Track-Auswahl weiterarbeiten können, ohne dass das Panel die Karte verdeckt).
- **Verwerfen** (nach unten wischen) → schließt das Panel.

## Die Track-Liste (Menü → Tracks)

Eine vollständige Liste aller importierten Tracks. Die Anzahl steht im Titel.

### Filtern

Tippen Sie auf das **Filter-Symbol**. Zwei Optionen:

- **Sichtbarkeit** — Alle / Nur sichtbare / Nur ausgeblendete. Tracks, die Sie über den Sichtbarkeits-Schalter ausgeblendet haben, stehen weiter in der Liste, werden aber nicht auf der Karte gezeichnet.
- **Farbe** — 16-Farben-Palette. Tippen Sie auf eine Farbe, um nur Tracks dieser Farbe zu sehen.

Aktiver Filter färbt das Symbol blau. Tippen Sie **Alle** in einem der Abschnitte, um zurückzusetzen.

### Sortieren

Tippen Sie auf das **Sortier-Symbol**:

- **Neueste zuerst** — nach Importdatum (Standard).
- **Nach Name** — alphabetisch.
- **Nächste zuerst** — nächstgelegener Mittelpunkt zu Ihrer aktuellen Position. Nutzt die letzte bekannte GPS-Position Ihres Telefons, funktioniert also auch, wenn Sie in dieser Sitzung noch kein GPS in ApexGPS aktiviert haben. Zeigt „(kein GPS)“, wenn die Standort-Berechtigung fehlt oder keine zwischengespeicherte Position vorhanden ist.
- **Nach Punkten** — Tracks mit den meisten Punkten zuerst (nützlich, um stark detaillierte Tracks von einfachen Routen zu unterscheiden).

### Suchen

Tippen Sie in das Suchfeld, um die Liste auf Tracks zu filtern, deren Name Ihren Text enthält.

### Mehrere auswählen

Lange drücken auf einen Track → Auswahlmodus. Haken Sie die gewünschten an, dann:

- **Bulk-Farbänderung** (Paletten-Symbol) — alle ausgewählten auf eine Farbe setzen.
- **Bulk ein- / ausblenden** (Auge-Symbole) — schnelle Sichtbarkeitssteuerung.
- **Bulk-Löschen** (Papierkorb, rot) — mit Bestätigung.
- **Alle auswählen** — hakt jeden Track in der aktuell gefilterten Ansicht an.

## Aktionen pro Track

Tippen Sie einen Track in der Liste an → die **Track-Detailansicht** öffnet sich.

- **Name** — editierbar.
- **Farbe** — antippen, um die Farbauswahl zu öffnen.
- **Sichtbarkeit** — auf der Karte an- / ausblenden.
- **Höhenprofil** — dasselbe Diagramm wie im Karten-Overlay, aber in voller Größe.
- **Aufstieg / Abstieg** gesamt.
- **Punktanzahl** — wie viele GPS-Punkte den Track ausmachen.
- **Auf Karte anzeigen** — schließt die Detailansicht und zoomt die Karte auf den Track.
- **Optimieren** — vereinfacht den Track, indem redundante Punkte entfernt werden. Nützlich beim Import riesiger, überdetaillierter Exporte. Nicht zerstörungsfrei nur pro Track; re-importieren, um das Original zurückzuholen.
- **Als GPX teilen** — dasselbe wie der Teilen-Button im Karten-Overlay.
- **Löschen** — mit Bestätigung.

## Bulk-Optimierung (für große Sammlungen)

Wenn Sie viele extrem dichte Tracks importiert haben, kann die Karte auf älteren Telefonen träge wirken. **Einstellungen → Daten → Alle Tracks optimieren** führt dieselbe Vereinfachung auf allen Tracks gleichzeitig aus. Die Einstellungs-UI zeigt die Anzahl an, die betroffen wäre.

## Löschen

Einzeln: Wischen / Papierkorb-Symbol in einer Track-Zeile, oder der Löschen-Button in der Detailansicht.

Mehrere: Auswahlmodus + Bulk-Löschen.

Kein Rückgängig. Halten Sie eine [Sicherung](backup.md) bereit, wenn Sie unsicher sind.

---

**Verwandt:** [Wegpunkte →](waypoints.md) · [Die Kartenansicht →](map.md) · [Sicherung & Wiederherstellung →](backup.md)
