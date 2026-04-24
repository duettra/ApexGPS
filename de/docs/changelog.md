# Versionshinweise

Für Nutzer sichtbare Änderungen, neueste zuerst. Für internes Refactoring / reine Versions-Hochzählungen siehe das private Repo.

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
