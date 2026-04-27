# Tracks

Ein **Track** ist eine aufgezeichnete Strecke — eine Abfolge von GPS-Punkten, als Linie auf der Karte verbunden. Tracks erhalten Sie auf drei Arten: durch **Live-Aufzeichnung** direkt in ApexGPS, durch **Import** von GPX-Dateien (aus GaiaGPS, Strava, Garmin Connect, wikiloc.com oder allem anderen, das GPX exportiert) oder durch **Planung** einer neuen Strecke per Antippen auf der Karte.

## Aufzeichnung

Tippen Sie auf den roten **Aufnahme-Punkt** oben links auf der Karte. Der Punkt erweitert sich zu einem Live-Zeit-Chip (`00:12:43`) und eine rote Breadcrumb-Linie zeichnet Ihre Tour auf der Karte, sobald neue GPS-Fixes eintreffen.

### Während der Aufzeichnung

- **Tap auf den Timer-Chip** für ein Menü:
  - **Pause** — hält die Uhr an; neue Fixes werden nicht mehr zur Breadcrumb hinzugefügt, bis Sie **Fortsetzen** tippen.
  - **Fertig** — speichert die Tour als neuen Track und öffnet das Track-Overlay, damit Sie Statistiken und Höhenprofil sofort prüfen können.
  - **Löschen** — verwirft die aktuelle Aufzeichnung ohne zu speichern.
- Der GPS-Vordergrund-Dienst wird automatisch gestartet, wenn Sie eine Aufzeichnung beginnen — Sie müssen den Folgen-Modus nicht vorher aktivieren.
- **Bildschirm aus?** Die App verlangsamt die GPS-Abfragerate, um Akku zu sparen (≈10 s zwischen Fixes bei ausgeschaltetem Bildschirm gegenüber 2 s bei eingeschaltetem). Keine Aktion erforderlich — es wechselt automatisch.

### Wenn die Systemortung aus ist

Tippen auf Aufnahme bei deaktivierter Android-System-Ortung zeigt die kurze Meldung *„Systemortung ist aus — aktivieren, um aufzuzeichnen"* mit einer **Einstellungen**-Abkürzung. Die Aufzeichnung beginnt nicht.

### Wenn die App während der Wanderung beendet wird

Falls Android die App während einer aktiven Aufzeichnung beendet (Low-Memory-Reclaim, Force-Stop, Neustart), bleibt die bis dahin gesammelte Breadcrumb **erhalten**. Öffnen Sie die App erneut und der Chip kehrt mit der bisherigen verstrichenen Zeit in pausiertem Zustand zurück — tippen Sie **Fortsetzen**, um weiterzumachen, oder **Fertig**, um das Bisherige zu speichern.

### Aktivitätstyp

Jeder aufgezeichnete Track startet mit dem Tag **Wandern**. Öffnen Sie die Track-Detailansicht (Tracks → Zeile antippen) und verwenden Sie das Dropdown **Aktivität**, um ihn auf Spazieren / Laufen / Radfahren / Offroad / Gleitschirmfliegen zu ändern. Importierte Tracks haben standardmäßig keinen Aktivitäts-Tag; Sie können ihn auf dieselbe Weise zuweisen.

### Zuschneiden einer Aufzeichnung

GPS-Warmlauf-Rauschen am Anfang Ihres Tracks? Vergessen, **Fertig** zu tippen, und der Track zieht sich jetzt halbwegs zum Auto? Öffnen Sie die Track-Detailansicht und tippen Sie auf **Track zuschneiden**:

- Ein Dialog öffnet sich mit einer Mini-Karten-Vorschau des gesamten Tracks und dem Höhenprofil darunter.
- Ziehen Sie die beiden Griffe im Höhendiagramm, um Start und Ende des Bereichs festzulegen, den Sie behalten möchten. Die Mini-Karte aktualisiert sich live — der behaltene Abschnitt bleibt in der Track-Farbe, die entfallenden Teile werden grau.
- Die Anzeige **Behalten** zeigt die resultierende Distanz und Punktzahl.
- Tippen Sie **Zuschneiden**, um zu bestätigen. Ein Bestätigungsdialog nennt genau, wie viele Punkte an jedem Ende entfallen. **Dies kann nicht rückgängig gemacht werden** — behalten Sie einen GPX-Export, wenn Sie unsicher sind.

Das Zuschneiden berechnet auch Distanz, Bounding-Box und Höhenprofil neu, damit die Statistiken oben im Bildschirm sofort den gekürzten Track widerspiegeln.

## Eine Strecke planen

Wenn Sie eine Route vor der Wanderung planen möchten — die morgige Tour, eine Schleife von einer Papierkarte, eine Verbindung zwischen zwei bekannten Wegen — können Sie sie direkt auf der Karte skizzieren und als Track speichern.

Öffnen Sie **Menü → Tracks** → tippen Sie auf den blauen **+**-Knopf unten rechts (über dem Importordner-Knopf). Die App wechselt zur Karte im **Planungsmodus**:

- Die obere Leiste ändert sich zu `✕  Strecke planen  ✓ Speichern`. Ein kleiner Chip darunter zeigt die aktuelle Punktzahl und Gesamtdistanz.
- **Tippen Sie irgendwo auf die Karte**, um einen nummerierten türkisfarbenen Punkt zu setzen. Jeder Tipp verlängert die Route zum nächsten Stopp. Punkt 1 wird automatisch an Ihrer aktuellen Position gesetzt, wenn Folgemodus aktiv ist.
- **Lange auf einen Punkt drücken und ziehen**, um ihn zu verschieben. Lange auf den kleinen Punkt zwischen zwei Stopps drücken und ziehen, um einen neuen Punkt auf diesem Abschnitt einzufügen.
- **Ziehen Sie einen Punkt auf das Mülleimer-Symbol** oben rechts (direkt unter dem Kompass), um ihn zu löschen. Die Linie verbindet sich neu durch die verbleibenden Nachbarn. Der Mülleimer leuchtet rot, wenn ein Punkt darüber schwebt.
- Tippen Sie auf das **Diagramm-Symbol** rechts, um das **Höhenprofil** zu öffnen. Die App fragt Höhen von Open-Meteo für Stichproben alle ~100 m entlang Ihrer Route ab und zeigt dann ein Diagramm mit Aufstieg und Abstieg. Eine lange Strecke wird gröber abgetastet (max. ~500 Stichproben), damit der Abruf nie aufgebläht wird. Während des Ladens stehen Abbruch und Schließen zur Verfügung.
- Tippen Sie auf **✓ Speichern** oben, benennen Sie Ihre Route, bestätigen Sie. Der neue Track erscheint in Ihrer Track-Liste (sortierbar, als GPX exportierbar, gegen eine spätere Aufzeichnung vergleichbar). Die Karte passt sich automatisch an die neue Streckenausdehnung an.

Zum Abbrechen: tippen Sie auf **✕** oder drücken Sie die Hardware-Zurück-Taste. Wenn Sie Punkte gesetzt haben, fragt die App vor dem Verwerfen.

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
