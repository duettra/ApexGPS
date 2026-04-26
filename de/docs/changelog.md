# Versionshinweise

Für Nutzer sichtbare Änderungen, neueste zuerst. Für internes Refactoring / reine Versions-Hochzählungen siehe das private Repo.

---

## 1.32.2 — 26. Apr. 2026 — Wetter standardmäßig an + vollständige Übersetzungen + Karten-Zurück-Button

- **Wetter ist jetzt von Haus aus aktiviert.** Der Vorhersage-Chip und die Zeile „Wetter hier“ auf Wegpunkten sind ohne vorherige Aktivierung sichtbar. Sie können das Wetter unter **Einstellungen → Wetter** weiterhin ausschalten, falls Sie keine Netzwerk-Aufrufe wünschen — bestehende Installationen behalten Ihre vorherige Einstellung.
- **Vollständige Übersetzungen für die Wetter-Funktion.** Alle Wetter-Texte — der Chip, das Sheet (aktuelles Panel, 24-Stunden-Streifen, Luftfeuchte- / Druck-Trends, 7-Tages-Streifen, Sonnenuntergang / UV / Druck / Taupunkt-Beschriftungen), die Einstellungen-Zeilen und der Anleitungs-Kapitelname — sind jetzt ins Deutsche, Französische, Spanische, Polnische und Arabische übersetzt. Die Wetter-Bedingungen („Leichter Regen“, „Gewitter mit Hagel“, „Teilweise bewölkt“, …) folgen dem standardisierten meteorologischen Vokabular der jeweiligen Sprache.
- **Karten-Menü: Zurück-Button schließt jetzt zuerst eine geöffnete Karte.** Wenn **Neuen Bereich herunterladen** oder **Gespeicherte Offline-Karten** ausgeklappt war, hat der Zurück-Button das Karten-Menü übersprungen und Sie zur Hauptkarte gebracht. Jetzt schließt Zurück zuerst die geöffnete Karte; ein weiterer Druck führt Sie zur Hauptkarte. Das entspricht dem Verhalten anderswo (Einstellungen-Unterseiten, Mehrfachauswahl in den Tracks- / Wegpunkt-Listen).

---

## 1.32.1 — 25. Apr. 2026 — Wetter: kleine Korrekturen

- **Korrekte Sonnen- / Mondsymbole über Mitternacht hinweg.** Der 24-Stunden-Wetterstreifen zeigte bei spätem Öffnen nachts Mond-Glyphen für die Nachmittagsstunden des Folgetages (11:00, 14:00, 17:00). Jede Stunde wählt jetzt ihren eigenen Sonnenauf- / -untergang, sodass Tagstunden immer die Sonnenseite-Symbole zeigen.
- **Wegpunkt-Vorhersage berücksichtigt nun tatsächlich die Höhe.** Wenn ein Gipfel-Wegpunkt fast an derselben Koordinate wie Ihre aktuelle GPS-Position lag, wurde manchmal die zwischengespeicherte Vorhersage für die aktuelle Position für den Wegpunkt zurückgegeben statt einer frischen, höhenbewussten Abfrage. Auf einem 1480-m-Gipfel bedeutete das eine Vorhersage, die ~9 °C zu warm war. Der Cache schlüsselt jetzt zusätzlich nach Höhe, sodass die gespeicherte Höhe des Wegpunkts immer berücksichtigt wird.

---

## 1.32.0 — 25. Apr. 2026 — Wetter: Punktdaten verfeinert, keine Karten-Overlays

Nach 1.31.0 bestanden die Karten-Overlays (Niederschlag, Wolken) den Augen-Test auf Wander-Zoomstufen nicht — sie wirkten wie blockige farbige Quadrate ohne echten Geländebezug, und die untere Steuerleiste (Overlay-Schieberegler + Chip + Tempo / Höhe / Distanz) verschlang zu viel Bildschirm. Diese Version räumt die Karte auf und konzentriert sich auf das Punkt-Sheet, wo die nützlichen Details sitzen.

- **Karten-Overlays entfernt.** Keine Niederschlag-Radar- oder Wolkendecken-Overlays auf der Basiskarte mehr, kein Zeitschieber. Der Bildschirm **Einstellungen → Wetter** schrumpft auf einen einzigen Hauptschalter.
- **Reicheres Punkt-Sheet.** Das Wetter-Sheet (Tippen auf den Chip oder auf die Zeile „Wetter hier“ eines Wegpunkts) zeigt nun: ein Held-Panel mit Wetter-Emoji, Temperatur, „Gefühlt“; Zeilen für Wind / Luftfeuchte / Taupunkt / Druck / UV / Sonnenuntergang; einen 24-Stunden-Streifen mit stündlichen Wettersymbolen + Temperatur; einen Luftfeuchte-Verlauf (hellblau) und einen Druckverlauf (grün); und einen 7-Tage-Streifen mit Höchst- / Tiefstwert + Symbol. So gestaltet, dass es auf einem typischen Telefon auf einen Bildschirm passt.
- **Wegpunkt-Höhe geht in die Vorhersage.** Wegpunkte mit gespeicherter Höhe geben diese an das Vorhersage-Modell weiter, sodass Gipfel-Vorhersagen die echte Gipfelhöhe nutzen statt der grob gemittelten Modellhöhe. Dasselbe gilt für die Chip-Vorhersage am aktuellen Standort — sie nutzt Ihre GPS-Höhe.
- **Chip stimmt mit Wegpunkt-Karte überein.** Der Chip-Text in der Statusleiste passt nun zu dem, was beim Tippen auf einen Wegpunkt erscheint: Emoji + Temperatur + Wind. Eine dünne Trennlinie wurde zwischen Chip und Tempo / Höhe / Distanz-Zeile eingefügt, sodass sie als ein Panel gelesen werden.

---

## 1.31.0 — 25. Apr. 2026 — Wetter

ApexGPS zeigt nun wandertaugliche Wetterinformationen aus kostenlosen öffentlichen APIs, vollständig opt-in.

- **Vorhersage-Chip in der Statusleiste.** Sobald Sie Wetter unter **Einstellungen → Wetter** aktivieren, zeigt ein kleiner Chip über der Tempo / Höhe / Distanz-Leiste die aktuellen Bedingungen für Ihren GPS-Standort: Temperatur, Wind, Luftfeuchte. Der Chip aktualisiert alle 15 Minuten, solange Sie online sind, und zeigt an, wenn die Daten veraltet sind oder Sie offline gegangen sind (graut aus und ergänzt eine Uhr).
- **Tippen-zum-Erweitern-Sheet.** Tippen Sie auf den Chip (oder die neue „Wetter hier“-Zeile in einem Wegpunkt-Panel) für die volle Aufschlüsselung — aktuelle Werte, die nächsten 24 Stunden als Temperaturlinie + Niederschlagsbalken-Diagramm und ein 7-Tage-Streifen mit Höchst-/Tiefstwerten und Wettersymbolen.
- **Manuelle Aktualisierung.** Ein ↻-Button im Sheet-Header erzwingt eine frische Abfrage, wenn Sie nach einem Flugmodus-Patch wieder verbunden sind.
- **Animierte Karten-Overlays.** Ein neuer Bereich **Overlays** im Karten-Hub fügt zwei unabhängige Schalter hinzu: Niederschlagsradar (animierter farblich kodierter Regen, letzte 2 Stunden plus 30-Minuten-Nowcast) und Wolken-Satellit (geostationäre IR-Wolkenoberseiten). Diese senden Ihren Standort nirgendwohin — es sind reine Kachel-Abfragen, unabhängig vom Wetter-Chip.
- **Datenschutz zuerst.** Die gesamte Funktion ist standardmäßig aus. Vorhersagen kommen von Open-Meteo und Radar von RainViewer; beides sind kostenlose öffentliche APIs, die kein Konto und keinen API-Schlüssel erfordern. Ihr Standort wird nur gesendet, wenn Sie den Chip ausdrücklich aktivieren.

Lesen Sie das vollständige Kapitel unter **Einstellungen → Anleitung → Wetter**.

---

## 1.30.2 — 25. Apr. 2026

- **Kompass-Tippen respektiert die Rotationssperre.** Lange auf den Kompass drücken sperrt die Karten-Rotation; im gesperrten Zustand schnappt ein einzelner Tipp auf den Kompass die Karte nicht mehr nach Norden. (Sie müssten erst lange drücken, um zu entsperren, und dann tippen.) Das stellt die Absicht der Sperre wieder her — den Winkel gegen unbeabsichtigte Eingaben einfrieren, einschließlich eines Versehens-Tipps auf den Kompass.
- **Kürzere, weniger störende Hinweise.** Die Meldungen „Gelöscht …“ / „Verschoben …“ / „Angekommen“ / Folgen-gesperrt / Auto-pausiert-Ortung-aus erscheinen nun als kurzer Android-Toast (etwa 2 Sekunden, System-Overlay) statt als 4-Sekunden-Snackbar, die den unteren Kartenrand blockierte. Sie können sofort einen anderen Wegpunkt antippen, nachdem Sie einen gelöscht haben, ohne zu warten.

---

## 1.30.0 / 1.30.1 — 25. Apr. 2026 — Aufzeichnungsqualität

Die erste Wanderung nach 1.29 (4 h 10 Min, 9,98 km) zeigte, dass die Live-Track-Aufzeichnung viel mehr Punkte als nötig speicherte und einen großen falschen Höhenabfall durch eine festsitzende Höhenangabe übernommen hatte. Beides behoben:

- **Leichtere, glattere Aufzeichnungen.** Ein neuer Filter behält einen Fix nur, wenn Sie sich mindestens 5 m bewegt haben, 15 Sekunden vergangen sind oder sich die Höhe um 3 m+ geändert hat. Schlecht genauere Fixes (>25 m) werden direkt verworfen. Beim Test-Hike: ~4600 → ~1500 gespeicherte Punkte, keine sichtbare Änderung der Track-Linie, Distanz unverändert. Weniger Speicher; kleinere GPX-Exporte; derselbe Track.
- **Keine falschen Höhen-Einbrüche mehr.** Manche Android-Geräte liefern aus dem fused location provider dieselbe gecachte Höhe (z. B. `139 m` auf einer Wanderung bei 1200 m) minutenlang. Die Aufzeichnung behandelt diese Werte jetzt als „kein Wert“ statt die falsche Zahl zu persistieren. Das Höhenprofil zeigt eine saubere Lücke über dem fehlerhaften Bereich statt eines Einbruchs auf null, und die Aufstieg- / Abstieg-Werte spiegeln nur echte Höhenänderungen wider.
- **MSL-Höhe auf Android 14+.** Wo verfügbar, nutzt die Aufzeichnung die ehrlichere Mittelmeer-Höhe statt der WGS84-Fallback-Höhe, die dem oben beschriebenen Festsitzen unterworfen ist.

Wenn Sie eine Aufzeichnung vor 1.30.0 mit einer falschen Höhenangabe haben, können Sie sie neu aufzeichnen — die Anzeige im Track verwendet aber die persistierten Punkte. Es gibt keinen Migrationsschritt.

---

## 1.29.0 — 24. Apr. 2026

- **Live-Track-Aufzeichnung.** Tippen Sie auf den roten Punkt oben links auf der Karte, um die Aufzeichnung Ihrer aktuellen Tour zu starten. Ein Live-Timer `HH:MM:SS` ersetzt den Punkt; Tap für **Pause / Fertig / Löschen**. Ihr Pfad zeichnet sich als rote Linie auf der Karte, während Sie sich bewegen. Bei **Fertig** wird die Aufzeichnung als neuer Track gespeichert und das Overlay öffnet sich automatisch, damit Sie Distanz, Aufstieg und Höhenprofil sofort prüfen können.
- **Track zuschneiden.** In der Track-Detailansicht öffnet **Track zuschneiden** einen Dialog mit Mini-Karten-Vorschau und zwei ziehbaren Griffen im Höhendiagramm. Schneiden Sie einen schlechten Anfang (noch kein GPS-Fix) oder ein versehentliches Ende (vergessen, Fertig zu tippen) ab, ohne den Rest des Tracks zu verlieren. Destruktiv — ein Bestätigungsschritt nennt genau, wie viele Punkte entfallen.
- **Aktivitäts-Tag pro Track.** Die Track-Detailansicht hat ein neues Dropdown **Aktivität**: Wandern · Spazieren · Laufen · Radfahren · Offroad · Gleitschirmfliegen. Aufzeichnungen starten standardmäßig als Wandern; importierte Tracks ohne Tag.
- **Höhe am Wegpunkt.** Das Wegpunkt-Dialogfenster hat ein neues optionales Feld **Höhe (m)** — ausfüllen, wenn Sie eine Höhe für einen bekannten Gipfel / Pass / o. ä. mitführen möchten. Leer = keine Höhe gespeichert (wie heute bei importierten Wegpunkten ohne Höhendaten).
- **Track-Details + Wegpunkt-Bearbeitung überarbeitet.** Gruppierte Karten, Abschnitts-Überschriften, Icons in jeder Zeile, aktivitätsspezifisches Icon am Aktivitäts-Chip, rot umrandetes **Löschen** passend zur destruktiven Aktion, neue Statistik **Punkte** im Track-Bildschirm. Das Wegpunkt-Dialogfenster ist kompakter — das ganze Formular passt auf den meisten Telefonen über die System-Navigationsleiste, ohne zu scrollen.
- **Prozess-Tod-Wiederherstellung.** Beendet Android die App mitten in einer Aufzeichnung (Low-Memory, Force-Stop), bleibt die Breadcrumb erhalten. Nach dem erneuten Öffnen kommt die Aufzeichnung im pausierten Zustand zurück — fortsetzen, beenden oder verwerfen.
- **Energiesparen: adaptive GPS-Rate.** Während einer Aufzeichnung bei ausgeschaltetem Bildschirm verlangsamt sich die GPS-Abfragerate von 2 s auf 10 s, um Akku zu sparen. Sobald Sie das Telefon entsperren, geht es zurück auf 2 s für live-glatte Aufzeichnung. Vollautomatisch.
- **System-Ortung-Schutz.** Tippen auf Aufnahme bei deaktivierter Android-System-Ortung zeigt jetzt eine Meldung mit einer **Einstellungen**-Abkürzung statt still eine tote Aufzeichnung zu starten.
- **No-Fix-Hinweis.** Tippen Sie auf Aufnahme, bevor GPS einen Fix erfasst hat, erscheint eine kurze Meldung *„GPS wird erfasst…"*, die erklärt, warum die Breadcrumb noch nicht gestartet ist. Die Aufzeichnung beginnt, sobald der erste Fix eintrifft.
- **Entfernt:** der optionale Notfall-Button. Der Bereich oben links gehört nun dem Aufnahme-Chip.

---

## 1.28.0 — 24. Apr. 2026

- **Arabisch ergänzt.** العربية schließt sich Deutsch, Französisch, Spanisch und Polnisch neben Englisch an. Sechs UI-Sprachen in **Einstellungen → Darstellung → Sprache**.
- **Wegpunkt-Panel jetzt übersetzt.** Tippen auf einen Wegpunkt zeigte bisher „Elev 145 m · Dist 0,42 km" auf Englisch — unabhängig von der App-Sprache. Jetzt schaltet es mit um (z. B. „Höhe 145 m · Dist 0,42 km").
- **Zahlen bleiben in allen Sprachen westliche Ziffern.** Koordinaten, Distanzen, Höhen, Richtungen — immer `25.165`, `145`, `0.42`. Konsistent mit Google Maps / WhatsApp.

---

## 1.27.0 — 23. Apr. 2026

- **Fünf UI-Sprachen.** Deutsch, Französisch, Spanisch, Polnisch und Englisch. Auswahl in **Einstellungen → Darstellung → Sprache**, oder „Systemsprache" für die Telefon-Sprache.
- **Offline-Anleitung in Ihrer Sprache.** Alle 11 Kapitel des Anwenderhandbuchs (Einstellungen → Über → Anleitung) sind übersetzt.
- **Sprache übersteht Wiederherstellung aus Sicherung.** Die gewählte Sprache ist in der ZIP enthalten.
- **Statusleiste auch übersetzt.** TEMPO / HÖHE / DIST wechseln mit der Sprache.

---

## 1.26.2 — 22. Apr. 2026

- **Thunderforest-API-Schlüssel jetzt verschlüsselt gespeichert.** Der Schlüssel, den Sie unter **Einstellungen → Erweitert** einfügen, liegt nun in einem Android-Keystore-gestützten Tresor, nicht im Klartext. Existierende Schlüssel wandern beim ersten Start automatisch. Sicherungen, die Ihre Einstellungen einschließen, tragen den Schlüssel weiter in der ZIP (nötig für Portabilität) — ein neuer roter Warnhinweis im Sicherungsdialog weist darauf hin, die ZIP privat zu halten.
- **Sicherheit bei der Wiederherstellung erhöht.** Die Wiederherstellung weist jetzt ZIPs mit Directory-Traversal-Versuchen zurück, begrenzt Einträge auf 100 000, pro Eintrag auf 500 MB und die gesamte entpackte Größe auf 2 GB. Manipulierte / fehlerhafte Sicherungen können Ihren Speicher nicht mehr füllen oder aus dem Sicherungsverzeichnis ausbrechen.
- **Abbrechen-Button bei der Sicherung.** Während eine Sicherung läuft, können Sie nun unter dem beschäftigten Button **Abbrechen** drücken, um ohne Warten zu stoppen.
- **Fortschritt beim GPX-Import.** Ein `Importiere GPX…`-Snackbar wird während großer Importe gezeigt, sodass die App bei großen Ladevorgängen nicht mehr eingefroren wirkt.
- **Standort-Dienst auf Android 14+ zuverlässiger.** Der GPS-Vordergrund-Dienst startet nun korrekt auf Android 14 und 15 (zuvor in einigen Randfällen stillschweigend abgebrochen). Wake-Lock-Umfang eingeschränkt — sollte den Akkuverbrauch bei langen Tracking-Sessions reduzieren.
- **Kachel-Vorschau-Fix + Hintergrund-Hygiene.** Die Offline-Karten-Detailvorschau lädt nun, ohne die UI zu blockieren. Intern: Der Kachel-Download-Dienst kann nicht mehr beim Herunterfahren ANR auslösen. Release-Builds lassen keine Debug-Log-Ausgaben mehr durch.
- **Entfernt:** der Buy-me-a-coffee-Link in Einstellungen → Über. ApexGPS bleibt kostenlos ohne Werbung, Tracking oder Cloud.
- **Intern (für interessierte Nutzer):** Die Room-DB liefert jetzt explizite Migrationen (1→2→3); Upgrades erhalten Ihre Tracks und Wegpunkte auch bei Schema-Änderungen. Downgrade-Wipe bleibt bestehen — das Sideloaden einer älteren APK über eine neuere hinweg setzt die DB zurück.

---

## 1.26.1 — 22. Apr. 2026

- **Detailansicht gespeicherter Offline-Karte — verzerrte Vorschau korrigiert.** Die Kartenvorschau unter **Menü → Gespeicherte Offline-Karten → [Region antippen]** malte Kacheln über die eigenen Grenzen hinaus, sodass sie die Statistikzeilen und den „Auf Karte anzeigen“-Button überlappten. Die Vorschau wird jetzt sauber auf das 1,6:1-Rechteck zugeschnitten.
- **In-App-„Online lesen“-Link** in Einstellungen → Über zeigt nun auf `apexgps.duttra.de/docs/` (die gerenderte Anleitung) statt auf die rohe GitHub-Tree-Ansicht.
- **Buy me a coffee.** Neuer Support-Bereich in **Einstellungen → Über**. ApexGPS bleibt kostenlos ohne Werbung und Tracking — wenn es Ihnen nützt, hilft ein kleines Trinkgeld, neue Features voranzubringen.

---

## 1.26.0 — 21. Apr. 2026

- **Offline-Anleitung.** Die vollständige 10-Kapitel-Anleitung ist jetzt in der App gebündelt — öffnen Sie **Einstellungen → Über** und tippen Sie ein Kapitel an, um es ohne Internetverbindung zu lesen. Links zwischen Kapiteln funktionieren in der App; Taps auf externe Links öffnen Ihren Browser.
- **Beispieldaten laden.** Ein neuer Button in **Einstellungen → Daten** lädt 3 Beispiel-Wegpunkte (Gipfel / Aussicht / Wanderparkplatz) und 3 Tracks unterschiedlicher Länge und Höhenprofile. Damit können Sie jedes Feature ausprobieren, ohne eigene GPX-Dateien zu brauchen. Nach dem Import sind es ganz normale Tracks/Wegpunkte — später löschbar.
- **Navigieren aktiviert GPS automatisch.** Ein Tap auf Navigieren bei einem geteilten Standort oder Wegpunkt schaltet die Live-Position jetzt automatisch ein, falls sie aus war. Kein „GPS wird erfasst…“-Stau mehr, wenn Sie eigentlich navigieren wollten.
- **Kartenverschieben entsperrt Folgen-Modus wieder.** Eine Regression aus früheren 1.2x-Builds: Unter kontinuierlichen GPS-Updates sprang die Karte jede Sekunde zurück, auch nachdem Sie sie gezogen hatten. Karte ziehen → Kamera entsperrt sich (FAB wird mittelblau) wie zuvor; Ihr Dreieck aktualisiert sich weiter an Ort und Stelle.
- **Wegpunkt-Symbole, die früher abstürzten.** Der Import einer GPX mit Aussicht / Sattel / Wasserfall / Rastplatz / Trinkwasser / Wegweiser / Ruine / Toiletten-Symbolen konnte die App beim Rendern zum Absturz bringen. Behoben — alle 32 Symbole rendern jetzt korrekt.

---

## 1.25.x — 21. Apr. 2026

- **GPX-Import aus der Track-Liste** (Ordner-Symbol oben rechts). Ebenso aus der Wegpunkt-Liste. Der Import-FAB der Karte ist weg — Import läuft nun über die Listen-Ansichten.
- **Wegpunkt über Koordinaten hinzufügen** — blaues „+“ in der Wegpunkt-Liste öffnet das volle Wegpunkt-Dialogfenster mit leeren Lat/Lon-Feldern. Koordinaten eingeben oder einen `lat, lon`-String in den Breitengrad einfügen (automatische Trennung).
- **Wegpunkt-Koordinaten bearbeiten.** Lat und Lon sind nun im Wegpunkt-Dialog editierbar, mit Inline-Validierung (Lat ∈ [-90, 90], Lon ∈ [-180, 180]).
- **Folgen-FAB an den unteren Rand verschoben** in der rechten Spalte der Karte — am nächsten zum Daumen. Layers darüber, Messen darüber.

---

## 1.24.x — 19. Apr. 2026

- **Vollbild-Navigationskompass.** Während Sie zu einem Ziel navigieren, tippen Sie auf das 🧭-Symbol auf der Nav-Leiste, um einen großen Analog-Kompass zu öffnen: Distanz / Ankunft / Tempo / Höhe oben, ein rotierendes Ziffernblatt mit der blauen Nadel zum Ziel und Lat/Lon/Peilung/Genauigkeit unten. Zum Minimieren nach unten ziehen. Siehe [Teilen → Der Navigationskompass](share-and-navigate.md#der-navigationskompass-vollbild).
- **Wegpunkt teilen.** Das Wegpunkt-Overlay hat jetzt einen Teilen-Button neben Navigieren und Bearbeiten. Sendet den Wegpunkt über jede Messaging-App; Empfänger mit ApexGPS öffnen den Link direkt als geteilten Standort, den sie speichern können.
- **Aufgeräumtere Nav-Leiste + Statusleiste.** Die Nav-Leiste zeigt jetzt Peilung + Ankunft (Peilung in Blau — aktualisiert sich live), Distanz steht im DIST-Feld der Statusleiste. Keine doppelten Zahlen übereinander mehr.
- Nadel am Kompass tritt sanft aus der Mittelplakette heraus (subtile visuelle Politur).

## 1.23.0 — 19. Apr. 2026

- **Zu einem beliebigen Wegpunkt navigieren** direkt aus dem Wegpunkt-Overlay. Tippen Sie auf das Gehende-Person-Symbol neben Bearbeiten — dieselbe hellblaue gepunktete Linie + Live-Distanz/-Peilung + Auto-Stopp bei 20 m wie bei geteilten Standorten. Siehe [Wegpunkte → Zu einem Wegpunkt navigieren](waypoints.md#zu-einem-wegpunkt-navigieren).

## 1.22.2 — 19. Apr. 2026

- **Anleitungs-Link** in Einstellungen → Über. Öffnet diese Dokumentation im Browser.

## 1.21.0 — 19. Apr. 2026

- **Folgen-Modus: frei verschieben.** Das Ziehen der Karte kämpft nicht mehr gegen das GPS — das Dreieck aktualisiert sich weiter, aber die Karte bleibt, wo Sie sie hinziehen. Tippen Sie auf den Standort-Button, um zu re-zentrieren. Lange drücken, um GPS sofort auszuschalten. Drei sichtbare Zustände (aus / gesperrt / entsperrt), damit Sie immer wissen, was die Karte tut.
- **Kompass-zu-Norden animiert sanft** statt zu springen. Weniger holprig beim Zurückdrehen.

## 1.20.0 — 19. Apr. 2026

- **Zu einem geteilten Standort navigieren.** Wenn Ihnen jemand einen Standort über einen `apexgps.duttra.de`-Link teilt, tippen Sie den Navigieren-Button in der unteren Leiste, um eine hellblaue gepunktete Linie von Ihrer Position zu seiner zu ziehen, mit Live-Distanz und Peilung. Stoppt automatisch bei 20 m Näherung. Siehe [Teilen → Zu einem geteilten Standort navigieren](share-and-navigate.md#zu-einem-geteilten-standort-navigieren).
- **Visueller Hinweis für geteilte Standorte.** Eine rote Zielscheibe erscheint am geteilten Punkt, damit Sie genau sehen, wo er auf der Karte ist. [Speichern] als Wegpunkt oder [Verwerfen] zum Löschen.

## 1.19.0 — 19. Apr. 2026

- **Wegpunkt-Liste: Filter + Sortierung.** Nach Farbe oder Symbol filtern, nach Datum / Name / nächster sortieren. Entspricht dem, was Tracks bereits hatten. Siehe [Wegpunkte → Die Wegpunkt-Liste](waypoints.md#die-wegpunkt-liste-menü--wegpunkte).
- **Teile-Nachrichtenformat aufgeräumt** — beschriftete URLs (`ApexGPS:` / `Google Maps:`) mit einer Leerzeile darüber für bessere Lesbarkeit.

## 1.18.x — 19. Apr. 2026

- **Aktuellen Standort teilen.** Das blaue Positions-Dreieck auf der Karte antippen → Info-Panel mit Höhe, Genauigkeit, Zeit, Akku → Teilen über WhatsApp, SMS, E-Mail usw. Ganzer Ablauf unter [Teilen & Navigieren](share-and-navigate.md).
- **App Links.** Aus ApexGPS geteilte Standorte öffnen sich auf Geräten mit installierter App direkt in der App, komplett mit roter Markierung am Punkt.
- **Web-Fallback** — wenn der Empfänger ApexGPS nicht hat, öffnet der geteilte Link eine Webseite mit Kartenvorschau + einem Button „In Google Maps öffnen“.

## 1.17.6 — 18. Apr. 2026

- **Karten-Hub**-Redesign. Neue Region herunterladen und gespeicherte Offline-Karten durchstöbern leben nun auf einem Bildschirm als ausklappbare Karten. Siehe [Offline-Karten](offline-maps.md).
- Rotation-Schwarze-Ecken-Fix (beim Drehen der Karte keine schwarzen Dreiecke mehr an den Rändern).

## 1.16.0 — 17. Apr. 2026

- **Einstellungen** in Unterbildschirme reorganisiert (Darstellung / Speicher / Daten / API-Schlüssel / Über) mit Inline-Hilfe.
- **Wegpunkt-Größe**-Einstellung (Klein / Normal / Groß / XL) unter Darstellung.
- **Beim Start Rotation sperren** — falls Sie versehentliche Kartendrehungen hassen, beim Start sperren.

## 1.15.0 und früher

- Kern-App: GPX-Import, Track-Liste, Wegpunkte mit 32 Symbolen, Offline-Karten-Downloads, Kompass + Rotation, Distanzmessung, Sicherung/Wiederherstellung als ZIP, Track-Optimierung.

---

*Für fehlerbericht-genaue Details oder Entwicklerkontext siehe das [private Code-Repo](mailto:sandwalker.one@proton.me) — Entwickler für Zugriff kontaktieren.*
