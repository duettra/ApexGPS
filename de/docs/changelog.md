# Versionshinweise

Für Nutzer sichtbare Änderungen, neueste zuerst. Für internes Refactoring / reine Versions-Hochzählungen siehe das private Repo.

---

## 1.41.0 — 9. Juni 2026 — Streckenführung

- **Einer Strecke folgen** — wähle eine gespeicherte oder importierte Strecke, und ApexGPS leitet dich entlang. Wenn du vom Kurs abkommst, warnt dich die App mit einem Ton und Vibration – auch bei ausgeschaltetem Bildschirm – und eine Leiste zeigt die verbleibende Entfernung. Pfeile entlang der Strecke und eine Fahne am Ziel weisen den Weg; tippe auf die Umkehren-Taste, um die Richtung zu wechseln.
- **Zurück zum Start** — tippe während einer Aufzeichnung einmal, um zum Ausgangspunkt zurückgeführt zu werden: entweder den genauen Weg zurückverfolgen oder direkt zurück.
- Behoben: Die Mein-Standort-Taste war hinter der Führungsleiste verborgen.

---

## 1.40.2 — 6. Juni 2026 — Korrektur der Höhenaufzeichnung

- Ein Fehler auf Telefonen ohne Barometer wurde behoben, bei dem Vibrationen (z. B. beim Mountainbiken) die aufgezeichnete Höhe stetig auf unmögliche Werte nach unten ziehen konnten — die Höhe bleibt jetzt an echten GPS-Messungen verankert.
- Physikalisch unmögliche Höhen (unter −500 m oder über 9000 m) werden nicht mehr aufgezeichnet, unabhängig von ihrer Quelle.

---

## 1.40.1 — 5. Juni 2026 — Korrekturen an der Aufzeichnungs-Statistikkarte

- Die Live-Statistikkarte der Aufzeichnung hält ihre Uhr jetzt auch dann aktuell, während eine Aufzeichnung pausiert ist.
- Flüssigere Leistung bei langen Aufzeichnungen — die Live-Statistik wird jetzt nur noch neu berechnet, solange die Karte geöffnet ist.

---

## 1.40.0 — 4. Juni 2026 — Live-Statistikkarte der Aufzeichnung

- **Tippen Sie auf den Aufzeichnungs-Timer, um eine Live-Statistikkarte zu öffnen** — Dauer, Distanz, aktuelle Höhe (mit ihrer Quelle), Gesamt-Aufstieg und die Uhr, alle laufend aktualisiert.
- Pause, Fertig und Löschen sind jetzt klare Symbol-Schaltflächen, jede mit einer Bestätigung.
- Das Aufzeichnungs-Menü und die anderen Karten-Menüs sind jetzt einheitlich: abgerundet, durchscheinend und sie folgen Ihrer In-App-Einstellung der Textgröße.

---

## 1.39.1 — 4. Juni 2026 — Korrekturen für Kartenrückkehr und Anleitung

- Ein gelegentlich **schwarzes Kartenbild** beim Zurückkehren zur Karte aus einem Menü wurde behoben — sie wird jetzt sofort neu gezeichnet, statt leer zu bleiben, bis Sie geschwenkt haben.
- Der Text der Offline-**Anleitung** skaliert jetzt mit der In-App-Einstellung der **Textgröße**, wie der Rest der App.

---

## 1.38.0 — 3. Juni 2026 — Anpassbare Text- und Bediengrößen

- Neuer Schieberegler **Textgröße** unter Einstellungen → Darstellung (50–150 %), der allen In-App-Text zusätzlich zu Ihrer Android-Schrifteinstellung skaliert.
- Neuer Schieberegler **Größe der Kartenbedienelemente** — passen Sie die Schaltflächen auf der Karte, den Kompass und die Aufnahme-Pille in der Größe an; verkleinern Sie sie, um auf einem kleinen Telefon Kartenfläche zurückzugewinnen.
- Die Einstellung der Wegpunkt-Größe ist jetzt ebenfalls ein flüssiger Schieberegler.

---

## 1.37.15 — 2. Juni 2026 — Wegpunkt-Höhe funktioniert offline

- Beim Hinzufügen eines Wegpunkts auf der Karte wird seine **Höhe jetzt aus Ihrer aktuellen GPS-Höhe vorausgefüllt**, sodass es im Flugmodus oder ohne Signal funktioniert. Sie können sie weiterhin bearbeiten oder den genauen Wert später online abrufen.

---

## 1.37.14 — 2. Juni 2026 — Neue Aufzeichnungen starten ohne Aktivität

- Eine neue Aufzeichnung ist nicht mehr standardmäßig „Wandern" — sie startet ohne ausgewählte Aktivität (angezeigt als „Keine"), sodass Sie selbst die richtige auswählen. Bestehende Tracks bleiben unverändert.

---

## 1.37.13 — 1. Juni 2026 — Optimieren zeigt eine Pfad-Vorschau

- Der Optimieren-Dialog zeigt jetzt eine **Vorher/Nachher-Pfad-Vorschau** (blasses Original, kräftiges optimiertes Ergebnis darüber), sodass Sie die Begradigung vor dem Speichern sehen können.

---

## 1.37.12 — 1. Juni 2026 — Optimieren bereinigt Canyon-GPS-Rauschen

- Optimieren **bereinigt den Track jetzt vor dem Vereinfachen** — es glättet verrauschte Höhe und begradigt das GPS-„Gekritzel", das in tiefen Canyons entsteht, während echte Serpentinen erhalten bleiben. Validiert gegen eine Barometer-Uhr auf einer Canyon-Wanderung. Vorschau und Als neu speichern halten Ihr Original weiterhin sicher.

---

## 1.37.11 — 1. Juni 2026 — Zuschneiden: Als neu speichern

- Das **Zuschneiden** von Tracks bietet jetzt **Als neu speichern** (wie Optimieren) — behalten Sie die zugeschnittene Version als separaten Track und lassen Sie das Original unberührt.

---

## 1.37.10 — 1. Juni 2026 — Genauer Aufstieg und Abstieg

- Wild überhöhter **Gesamt-Aufstieg/-Abstieg** auf Telefonen ohne Barometer wurde behoben (eine Canyon-Wanderung zeigte +17.000 m statt ~2.250 m). Der Wert entrauscht die Höhe jetzt vor dem Aufsummieren, so wie Strava und Komoot den Höhengewinn berechnen. Gilt für alle gespeicherten und importierten Tracks.

---

## 1.37.5 — 21. Mai 2026 — GPS-Diagnose-Overlay (optional)

- Neues opt-in **GPS-Diagnose**-Overlay (Einstellungen → Erweitert), das Live-Fix-Qualität, Genauigkeit und Höhenquellen-Detail zeigt — nützlich, um Aufzeichnungen mit schwierigem Signal zu verstehen.

---

## 1.37.0 — 17. Mai 2026 — Barometrischer Höhenmesser und bessere Höhe

- Auf Telefonen mit Barometer nutzt ApexGPS dieses jetzt als **primäre Höhenquelle** — submeter-stabil und frei von GPS-Rauschen und Canyon-Aussetzern.
- Aufstieg/Abstieg nutzt jetzt einen **5-m-Schwellenwert** (der Strava/AllTrails-Standard); bestehende Tracks zeigen kleinere, realistischere Zahlen.
- Dazu eine Reihe von Genauigkeitsverbesserungen für Telefone **ohne** Barometer — mehrere Höhen-Plausibilitätsprüfungen und Glättung, um GPS-Spitzen zu verwerfen, sowie ein optionales GPS-Genauigkeitsfeld in exportierten GPX-Dateien.

---

## 1.36.0 — 17. Mai 2026 — Bessere Canyon-Aufzeichnung

- Die Aufzeichnung **erfasst jetzt mehr Punkte in Canyons und engem Gelände** (Roh-Erfassung mit intelligenteren Dichte-Gattern), sodass Abstiege in tiefen Canyons nicht verloren gehen.
- Neue Option **GPS-Sprünge bereinigen** in Optimieren zum nachträglichen Aufräumen verrauschter Tracks.

---

## 1.35.2 — May 15, 2026 — Zuverlässiger Mülleimer · Mülleimer-Symbol erscheint nur während des Ziehens · Tippen neben Mittelpunkten funktioniert

- **Das Mülleimer-Symbol erscheint jetzt nur beim Ziehen — es taucht im Moment auf, in dem Sie einen Eckpunkt oder Mittelpunkt lange drücken, leuchtet rot beim Darüberziehen und verschwindet beim Loslassen.** Vorher war das Symbol im Mess- und Planungsmodus immer sichtbar, aber die Lang-drücken-und-zum-Löschen-ziehen-Geste war für die meisten Nutzer nicht offensichtlich — sie sahen den Mülleimer, konnten aber nicht herausfinden, wie sie einen Punkt hineinbekommen sollten. Jetzt erscheint der Mülleimer nur, wenn Sie tatsächlich einen Punkt aufgenommen haben, was die Bedienungslogik klar macht.
- **Einen Mittelpunkt auf dem Mülleimer abzulegen löscht ihn jetzt zuverlässig.** Zwei sporadische Fehler behoben: (1) Lose-Lass-Jitter hinterließ die Ablege-Koordinaten manchmal ein paar Pixel außerhalb der Mülleimer-Zone, obwohl das Symbol rot leuchtete — jetzt ist das gerenderte rote Leuchten selbst das Signal, wenn Sie also beim Loslassen Rot sehen, wird der Punkt gelöscht; (2) gelegentlich blieb ein auf den Mülleimer abgelegter Mittelpunkt optisch am Symbol-Bereich stehen, bis die Liste sich das nächste Mal änderte — jetzt springt die Linie bei jedem Abbruch sauber in die ursprüngliche Form zurück.
- **Ein Tipp auf die Linie nahe einem Mittelpunkt-Punkt verzerrt das vorhandene Segment nicht mehr.** Vorher: Wollten Sie auf die Linie tippen, um einen neuen Eckpunkt hinzuzufügen, landeten aber nahe dem Mittelpunkt-Punkt zwischen zwei vorhandenen Eckpunkten, verzerrte sich das vorhandene Segment — Ihr Tipp wurde in ein Fast-null-Ziehen umgewandelt, das einen Eckpunkt genau am Mittelpunkt einfügte. Jetzt wird der Tipp als Tipp erkannt und ein neuer Eckpunkt ans Ende der Liste gesetzt, genau wie beim Tippen an einer beliebigen anderen Stelle auf der Karte.

---

## 1.35.1 — 15. Mai 2026 — Mülleimer-Korrekturen · Streckenplanung beginnt dort, wo Sie getippt haben

- **Der Mülleimer funktioniert jetzt auch bei gedrehter Karte.** Vorher schlug das Ziehen eines Mess-Pins oder Planungs-Punkts auf das Mülleimer-Symbol oben rechts stillschweigend fehl, wenn die Karte um irgendeinen Winkel gedreht war — das Symbol leuchtete nicht rot und das Loslassen löschte nichts. Der Trefferpunkt liest jetzt die rohen Finger-Koordinaten statt des internen Rahmens der gedrehten Karte, sodass der Mülleimer in jeder Ausrichtung funktioniert.
- **Das Löschen des ersten Mess-Pins im Folgemodus zerstört nicht mehr den nächsten Pin.** Beim Messen mit aktivem Folgemodus folgt der erste Pin (Pin A) automatisch Ihrer Live-Position. Ihn in den Mülleimer zu ziehen schlug auf verwirrende Weise fehl: A schien beim nächsten GPS-Fix zurückzukehren, und der Pin, den Sie direkt danach gesetzt hatten (B), verschwand stillschweigend. Jetzt bleibt A nach dem Mülleimer-Ziehen für den Rest der Mess-Sitzung weg, und B + alle anderen Pins bleiben an Ort und Stelle. Schalten Sie den Mess-Modus aus und wieder an, um A erneut an Ihrer aktuellen Position zu setzen.
- **Die Streckenplanung setzt Punkt 1 nicht mehr automatisch an Ihrer aktuellen Position.** Planung ist ein bewusster Arbeitsablauf auf einem Kartenbereich — die meisten Nutzer schwenken in den Bereich, den sie planen möchten, und wechseln dann in den Planungsmodus. Das automatische Setzen von Punkt 1 an der GPS-Position überraschte Nutzer, die abgelegene Routen planten. Die Planung beginnt jetzt leer; der erste Tipp setzt Punkt 1 genau dort, wo Sie tippen, egal wohin Sie die Karte geschwenkt haben.

---

## 1.35.0 — 14. Mai 2026 — Sichtbare Tracks & Wegpunkte teilen · Energiesparmodus bei hoher Geschwindigkeit · GPX aus Messenger-Apps

- **Alles, was auf der Karte sichtbar ist, mit einem Tipp teilen.** Ein neues **Teilen-Symbol** sitzt oben links auf der Karte, direkt links neben dem ☰-Menü. Tippen Sie es an und ein Blatt öffnet sich, das jeden sichtbaren Track + Wegpunkt im aktuellen Ausschnitt auflistet. Hakeln Sie ab, was Sie möchten, tippen Sie auf **Teilen**, wählen Sie WhatsApp / E-Mail / Drive — das ganze Bündel geht als einzelne `.gpx`-Datei raus, benannt nach dem Bereich, den Sie gerade anschauten (z. B. `ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx`). Zwei weitere Einstiegspunkte nutzen dasselbe Blatt: eine **Sichtbare Tracks & Wegpunkte teilen**-Karte im Karten-Menü (verwendet den Ausschnitt, den Sie beim Öffnen des Menüs hatten), und ein **Teilen**-Symbol in der oberen Leiste der Listen Tracks / Wegpunkte, wenn Sie per Langdruck mehrere Einträge auswählen — bündelt die ausgewählten Elemente direkt ohne zusätzliches Blatt.
- **Energiesparmodus bei hoher Geschwindigkeit.** Ein neuer Schalter in **Einstellungen → Erweitert** (standardmäßig an) reduziert die GPS-Abtastung von einmal pro Sekunde auf einmal alle 10 Sekunden, wenn Sie schneller als 36 km/h unterwegs sind — Auto, Zug, schnelles E-Bike. Straßentracks werden weiterhin sauber aufgezeichnet; die Spur-Genauigkeit ist beim Fahren reduziert. Spart auf der Autobahn-Etappe einer Reise grob die Hälfte des GPS-Akkuverbrauchs ohne sichtbaren Verlust der Routenform. Bei Bedarf abschalten, um volle Abtastung bei Geschwindigkeit zu erhalten.
- **`.gpx`-Anhänge aus WhatsApp / Telegram / Signal / Outlook per Antippen öffnen.** Vorher fielen Anhänge aus diesen Apps auf den System-Texteditor zurück, weil sie die Datei als generisches `application/xml` statt als kanonischen GPX-MIME-Typ ankündigen. ApexGPS akzeptiert nun auch diese generischen Typen — tippen Sie einen `.gpx`-Anhang in einer beliebigen Messenger-App einmal an und das System-„Öffnen mit"-Menü zeigt ApexGPS als erstklassige Option.
- **Rezept-Modus für Offline-Karten-Sicherungen (plattformübergreifend).** Einstellungen → Daten → Sicherung ersetzt das einzelne Häkchen „Gespeicherte Kartenregionen" durch eine Drei-Wege-Auswahl: **Nicht einschließen** / **Rezept** (klein — listet auf, welche Regionen neu heruntergeladen werden sollen, funktioniert plattformübergreifend mit dem iOS-Port) / **Vollständige Kacheln** (das alte Verhalten — bettet die rohen Kachelpakete ein, groß aber offline wiederherstellbar, nur Android). Eine Rezept-Sicherung ist selbst für ein Dutzend Regionen etwa 80 KB; das Wiederherstellen fügt Platzhalter-Zeilen in **Karten → Gespeicherte Offline-Karten** mit einer **Herunterladen**-Schaltfläche ein, um die eigentlichen Kacheln bei Bedarf zu holen.
- **Kostenpflichtiger Kartenstil blendet sich ohne Schlüssel aus.** Der Eintrag **Outdoors (Thunderforest)** verschwindet jetzt sowohl aus dem Kartenstil-Picker als auch aus dem Picker für Offline-Region-Download, bis Sie unter **Einstellungen → API-Schlüssel** einen API-Schlüssel eingefügt haben. Vorher fiel die Auswahl ohne Schlüssel stillschweigend auf OpenTopoMap zurück, ohne Erklärung. Schlüssel einfügen → der Eintrag erscheint in beiden Menüs wieder.

---

## 1.34.2 — 14. Mai 2026 — Kostenpflichtige Kachelquellen ohne Schlüssel ausblenden

- **Der Stil „Outdoors (Thunderforest)" blendet sich nun vollständig aus, bis Sie einen API-Schlüssel eingefügt haben.** Vorher fiel die Auswahl ohne Schlüssel stillschweigend auf OpenTopoMap zurück, ohne Erklärung — Sie tippten Outdoors an, sahen OpenTopoMap-Kacheln und fragten sich, warum. Der Kartenstil-Picker und der Picker zum Download einer Offline-Region lassen den Outdoors-Eintrag weg, bis unter **Einstellungen → API-Schlüssel → Thunderforest** ein Schlüssel gespeichert ist. Schlüssel einfügen → Outdoors erscheint sofort wieder in beiden Menüs.

---

## 1.34.1 — 13. Mai 2026 — Sicherungsformat v2 (Offline-Regions-Rezepte, plattformübergreifend)

- **Sicherungen können die schweren Kachelpakete jetzt überspringen und stattdessen ein „Rezept" speichern.** Einstellungen → Daten → Sicherung ersetzt das einzelne Häkchen „Gespeicherte Kartenregionen" durch eine Drei-Wege-Auswahl: **Nicht einschließen** / **Rezept** (klein — listet auf, welche Regionen neu heruntergeladen werden sollen, funktioniert plattformübergreifend mit dem iOS-Port) / **Vollständige Kacheln** (groß — das alte Verhalten, nur Android). Eine Rezept-Sicherung ist selbst für ein Dutzend Regionen etwa 80 KB; die entsprechende Vollständige-Kacheln-Sicherung könnte 50–500 MB groß werden. Eine Rezept-Sicherung wiederherstellen und die Liste der gespeicherten Karten füllt sich mit Zeilen, die mit „Noch nicht heruntergeladen · X Kacheln" markiert sind, plus einer **Herunterladen**-Schaltfläche — antippen, um vom ursprünglichen Kachelserver neu zu laden (nutzt Ihren aktuellen Cache + frische Kachelabrufe für den Rest).
- **Eine auf Android erstellte Sicherung kann nun auf iOS wiederhergestellt werden und umgekehrt — bis auf die Vollständige-Kacheln-Pakete.** Tracks, Wegpunkte, Einstellungen und Regions-Rezepte gehen sauber hin und her. Der Vollständige-Kacheln-Modus bleibt Android-only, weil iOS keinen MBTiles-Consumer mitliefert, aber der Rezept-Modus deckt die praktischen Bedürfnisse der meisten Nutzer ab (auf dem neuen Telefon neu aufbauen, einen kurzen Neudownload für die wichtigen Regionen akzeptieren).
- **Beim Wiederherstellen eines Outdoors-Stil-Rezepts werden Sie aufgefordert, zuerst den API-Schlüssel zu setzen.** Wenn ein wiederhergestelltes Rezept auf Thunderforest zielt und Sie keinen Schlüssel gespeichert haben, zeigt das Antippen von **Herunterladen** einen einmaligen Toast, der Sie zu **Einstellungen → Erweitert → Thunderforest-API-Schlüssel** lenkt; sobald der Schlüssel hinterlegt ist, startet der Download normal.

---

## 1.34.0 — 13. Mai 2026 — Größenanpassung · Wassersport · Live-Wiederherstellungsfortschritt · Korrekte Pluralformen

- **Wegpunkt-Symbole sind standardmäßig etwa 25 % größer.** „Normal" (1,0×) rendert jetzt in der Größe, die früher „Groß" hatte. Wenn die Wegpunkte zu klein wirken, gibt es weiterhin Klein / Normal / Groß / XL — Einstellungen → Darstellung → Wegpunkt-Größe. Bestehende Einstellung wird beibehalten; möglicherweise eine Stufe niedriger wählen, da die ganze Skala größer geworden ist.
- **Schnitt-Schieberegler — die runden Griffe funktionieren jetzt überall.** Vorher reagierte nur die senkrechte Linie jedes Griffs; ein Tipp auf den runden Knopf unten löste oft nichts aus, weil die Trefferfläche nicht ganz nach unten reichte. Behoben — beide runden Griffe lassen sich jetzt überall auf dem Kreis plus einem kleinen Bereich darunter greifen.
- **Neue Aktivitätsart: Wassersport.** Wählbar über Trackdetails → Aktivität, um Paddel-, Segel-, Surf-, Kajak- oder andere Wassersport-Sitzungen zu markieren. Gleiches Wellen-Symbol wie der Wasserfall-Wegpunkt.
- **Wiederherstellen einer Sicherung zeigt jetzt Live-Fortschritt.** Eine große Sicherung (hunderte Tracks, tausende Wegpunkte) blockierte die App früher minutenlang auf einem Spinner ohne Hinweis — leicht mit einem Absturz zu verwechseln. Die Schaltfläche „Wiederherstellen" sitzt jetzt über einem Fortschrittsbalken + Beschriftung („Stelle Track N von M wieder her…" / „Stelle Wegpunkt N von M wieder her…"), die pro Track und alle 100 Wegpunkte tickt.
- **Polnisch und Arabisch zeigen jetzt korrekt pluralisierte Zähltexte.** 13 Zeichenketten mit Zählwerten („X Tracks", „Y Wegpunkte", „vor Z Minuten" usw.) routen jetzt durch echte Pluralregeln. Polnisch erhält alle 4 Formen, Arabisch alle 6. Englisch / Deutsch / Französisch / Spanisch waren bereits grammatikalisch korrekt; die zugrundeliegende Mechanik verläuft jetzt konsistent durch denselben Pfad.

---

## 1.33.8 — 10. Mai 2026 — Messwerkzeug & Routenplaner: Erst-Pin-Warteschlange

- **Tippen Sie auf das Messwerkzeug oder den Planer-FAB, bevor Ihr GPS-Fix bereit ist, fällt der erste Punkt nun automatisch, sobald Ihre Position eintrifft.** Bisher hinterließ ein Tap, während GPS noch warmlief, einen leeren Start — Sie mussten manuell auf die Karte tippen, um Pin A zu setzen. Jetzt zeigt die App „GPS wird erfasst…" am Schalter und reiht den Erst-Punkt-Auto-Place in die Warteschlange ein; sobald der Fix eintrifft, erscheint Pin A an Ihrer aktuellen Position und der Live-Tracker übernimmt normal. Spiegelt dasselbe Warteschlangen-Verhalten, das der Aufnahme-FAB in 1.33.7 bekommen hat. Manuelles Antippen zum Setzen eines Pins bricht die Warteschlange währenddessen ab, sodass Sie keinen Tap verlieren.

---

## 1.33.7 — 10. Mai 2026 — Toleranter GPX-Import · Datenschutz unter Über · Auto-Start der Aufzeichnung

- **Imports von GPX-Dateien mit fehlerhaften Koordinaten brechen nicht mehr komplett ab.** Ein Track-Punkt oder Wegpunkt mit einem fehlerhaften `lat` / `lon`-Wert brach bisher den ganzen Import ab. Die App überspringt jetzt den fehlerhaften Punkt und importiert den Rest weiter — ein schlechter Punkt in einer 10 000-Punkt-Wanderung verliert die Datei nicht mehr. Harte Obergrenzen (10 000 Tracks, 100 000 Wegpunkte, 500 000 Punkte pro Track) lösen weiterhin Fehler aus, um Out-of-Memory zu verhindern.
- **Datenschutzerklärung direkt unter Einstellungen → Über.** Eine neue Zeile „Datenschutzerklärung" sitzt unter der Anleitung; antippen, um die Erklärung in der App zu lesen, kein Internet nötig. Derselbe Inhalt wird unter `apexgps.duttra.de/privacy.html` (die Play-Store-Datenschutz-URL) gespiegelt für alle, die ihn vor der Installation lesen möchten.
- **Tippen Sie auf Aufnahme, bevor Ihr erster GPS-Fix eintrifft, und die Aufzeichnung startet automatisch, sobald der Fix kommt.** Vorher startete ein Tap auf Aufnahme, bevor irgendein Fix empfangen war, sofort einen leeren Breadcrumb-Track — wenn Sie auf Stopp tippten, bevor ein Fix eintraf, speicherten Sie einen Track mit null Punkten. Jetzt sagt der Toast „GPS wird erfasst…" und die Aufzeichnung feuert automatisch in dem Moment, in dem der erste nicht-null-Fix eintrifft — kein zweiter Tap nötig.

---

## 1.33.6 — 9. Mai 2026 — Mülleimer-Ablegezone wieder zuverlässig nach Wiederherstellen

- **Mülleimer-Ablegezone in Routenplanung und Messwerkzeug funktioniert wieder zuverlässig, nachdem die App minimiert und über „Letzte Apps" wieder geöffnet wurde.** Eine versteckte Schwachstelle führte dazu, dass die Geste „Wegpunkt über den Mülleimer ziehen, um ihn zu löschen" nach dem Lösen und Wiederanhängen des App-Fensters (Minimieren → aus „Letzte Apps" antippen) stillschweigend nicht mehr funktionierte. Die Begrenzung der Ablegezone blieb auf den Koordinaten vor dem Minimieren stehen, während die Kartenposition weiter aktualisiert wurde, sodass Ablegevorgänge nicht erkannt wurden. Der Treffertest liest die Begrenzung jetzt bei jedem Drag-Ereignis frisch (und nur, wenn das Mülleimer-Symbol tatsächlich am Fenster angehängt ist) — damit funktioniert die Ablegezone über beliebig viele Wiederherstellungszyklen hinweg. Kein App-Neustart als Workaround mehr nötig.
- **Intern: Build-Aufräumarbeiten für die Play-Store-Produktionsprüfung.** UI-Abhängigkeit (`androidx.activity:activity-compose` 1.9.3 → 1.10.1) aktualisiert, um die in der 1.33.5-Prüfung gemeldeten Vitals-Warnungen („Edge-to-Edge wird möglicherweise nicht für alle Nutzer angezeigt") zu beheben — reine Aufräumarbeit, kein Verhalten geändert. Extraktion nativer Debug-Symbole für Release-Builds aktiviert (heute ohne Effekt, da die einzigen nativen Bibliotheken im AAB von Google bereits ohne Symbole ausgeliefert werden — aktiviert sich automatisch, falls künftig eine Abhängigkeit Symbole mitliefert).

---

## 1.33.5 — 7. Mai 2026 — Anpassbarer Karten-Cache + Begleit-Wanderung auf neuen Installationen

- **Wählen Sie, wie viel Speicherplatz für den Karten-Cache reserviert wird.** Unter Einstellungen → Offline-Cache stehen jetzt vier Voreinstellungen zur Auswahl: 250 MB / 500 MB (Standard) / 1 GB / 2 GB. Der neue Wert greift sofort — kein Neustart nötig. Gespeicherte Offline-Regionen werden separat abgelegt und nicht mitgezählt; das Ändern dieses Werts löscht also keine bewusst heruntergeladene Region.
- **Eine Begleit-Wanderung bei jeder Neuinstallation.** Eine reale Aufzeichnung der **Watzmann-Überschreitung** (Berchtesgaden) — Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, ~22,6 km Rundtour / +2250 m / etwa 10–12 h Gehzeit — wird beim ersten Öffnen der App automatisch importiert. Dazu kommen drei markante Wegpunkte (Trailhead Wimbachbrücke, DAV-Watzmannhaus, Watzmann-Mittelspitze). Bestehende Installationen bleiben unberührt. Wenn Sie die Beispieldaten löschen und später zurückhaben möchten, importiert sie **Einstellungen → Daten → Beispieldaten laden** auf Knopfdruck erneut.

---

## 1.33.4 — 5. Mai 2026 — Berechtigungs-Aufräumarbeiten für den Play-Store-Eintrag

- **Saubererer Berechtigungs-Eintrag im Play Store.** Eine veraltete „USB-Speicher"-Berechtigung wurde entfernt, die nie genutzt wurde — die App speichert Kartenkacheln im eigenen internen Speicher, nicht auf USB-/Wechselspeicher. Die Berechtigungs-Übersicht im Play Store zeigt jetzt vier Einträge weniger; auf Ihrem Telefon ändert sich nichts.

---

## 1.33.3 — 4. Mai 2026 — Korrekte Höhe über dem Meeresspiegel + aufgeräumter Track-Bildschirm + Folgemodus-Korrektur

- **Die Höhe in der Statusleiste zeigt jetzt echte Meter über dem Meeresspiegel.** Auf den meisten Android-Telefonen meldet der GPS-Chip die Höhe relativ zum *Ellipsoid* — einem glatten mathematischen Modell der Erde — nicht zum tatsächlichen Ozean. Im Persischen Golf sind das etwa 30 m Abweichung; an der Corniche von Abu Dhabi wurden rund **−27 m** statt null angezeigt. Die App nutzt jetzt den Mittelwasser-Wert des Geräts, sofern verfügbar (Android 14+ auf unterstützender Hardware), und greift auf eine mitgelieferte globale Geoid-Korrektur zurück (1°-EGM96-Raster, ~128 KB), wenn das Gerät ihn nicht liefert (das Vivo X300 Pro ist eines davon). Der Meeresspiegel zeigt jetzt weltweit **+0 m bis ein paar Meter**, unabhängig vom Telefon. Dieselbe Korrektur wird auf den Standort-Teilen-Text und die an die Wettervorhersage übergebene Höhe angewendet.
- **Die Geschwindigkeit in der Statusleiste bleibt bei 0 km/h, wenn Sie stillstehen.** Vorher ließ GPS-Jitter im Stillstand die Geschwindigkeitsanzeige auf 1–3 km/h springen, obwohl keine echte Bewegung stattfand. Die Anzeige zeigt jetzt null, bis Sie die vom Telefon gemeldete Geschwindigkeits-Genauigkeitsschwelle überschreiten — die Aufzeichnung selbst nutzt weiterhin den Rohwert, sodass langsame echte Bewegung nicht verdeckt wird.
- **Sauberere Aufzeichnungen in Canyons und bebauten Gebieten.** Drei neue Abwehrmaßnahmen gegen Multipath-Höhenspitzen (wenn eine Wand das GPS-Signal reflektiert): Der Aufzeichnungsfilter verwirft jetzt Höhenwerte mit schlechter vertikaler Genauigkeit, lehnt harte Sprünge über 50 m gegenüber dem vorherigen guten Fix unabhängig von der verstrichenen Zeit ab und hält sein Raten-Gatter auch nach langen Strecken ohne Höhe scharf. Eine Wadi-Hijr-Canyon-Spur vom 3. Mai hatte acht Ein-Sekunden-Höhensprünge von 70–300 m durch den vorherigen Filter geschmuggelt; die neuen Schichten fangen sie ab.
- **Track-Detailbildschirm — einfacheres Layout.** Das Stift-Symbol in der Symbolleiste ist weg — **tippen Sie auf den Track-Namen** in der Symbolleiste, um ihn umzubenennen. Eine einzelne Zeile mit drei Schaltflächen sitzt unter dem Höhendiagramm: **Zuschneiden · Track optimieren (X Pkt.) · Track löschen**. Der vorherige Schaltflächenstapel über die volle Breite und das Drei-Punkte-Überlaufmenü sind beide entfernt; alles passt auf einen Telefonbildschirm ohne Scrollen.
- **Optimieren ist jetzt Vorschau-dann-Speichern.** Das Bestätigen der Optimierung im Dialog übernahm sie früher sofort ohne Rückgängig. Jetzt rendert der vereinfachte Track im Diagramm + in der Statistikkarte unter einem kleinen Dialog, der `3214 → 500 Punkte · 12,40 → 12,30 km` zeigt. **Speichern** schreibt ihn; **Verwerfen** (oder Hardware-Zurück) verwirft ihn. Keine DB-Änderungen, bis Sie Speichern.
- **Folgemodus-FAB: einmal tippen zum erneuten Sperren.** Ein Fehler, bei dem das Schwenken der Karte (was den Folgemodus-FAB dimmte) und das anschließende Antippen **zwei Taps** erforderte, damit der FAB wieder kräftig blau wurde — die Neuzentrierungs-Animation wurde als fortgesetztes Nutzer-Schwenken fehlinterpretiert. Jetzt sperrt und zentriert ein Tap erneut, wie es immer hätte sein sollen.

---

## 1.33.2 — 30. Apr. 2026 — Aufgefrischtes Karten-Aussehen + Fehlerbehebungs-Runde

- **Aufgeräumterer, modernerer Kartenbildschirm.** Die obere Leiste, die FABs Ebenen / Messen / Folgemodus, die Aufnahme-Schaltfläche, die Statusleiste und der Wetter-Chip sind jetzt durchscheinend — die Karte scheint schwach dahinter durch, sodass der Bildschirm weniger eingerahmt wirkt. Die Karte selbst reicht jetzt randlos vom obersten bis zum untersten Bildschirmrand.
- **Modernisierte Menüs.** Das Hamburger-Menü (oben rechts) und der Ebenen-Kachelquellen-Picker erscheinen jetzt als abgerundete Popup-Karten mit vorangestellten Symbolen statt der flachen Rechtecke von früher. Die Tippziele sind größer; die aktive Kachelquelle ist mit fettem Namen + Häkchen markiert.
- **Arabisch / Persisch / Urdu — überall westliche Ziffern.** Distanzen, Höhen, Koordinaten, Benachrichtigungszeiten beim Standort-Teilen und die stündliche Uhr im Wetter-Sheet erscheinen nicht mehr als ostarabische Ziffern (`٣٫٤ كم`) — sie lesen sich als `3.4 km`, unabhängig von der Telefonsprache. Dies war eine langjährige Inkonsistenz in den Diagramm-Beschriftungen und einigen Benachrichtigungs-Buildern.
- **Arabische Diagramme: Wisch-Gesten in die richtige Richtung.** Die Höhendiagramme in Track-Detail und Planung hatten in Arabisch invertiertes Wischen — das Berühren des visuellen linken Randes sprang ans Ende der Route. Jetzt folgt das Wischen Ihrem Finger korrekt, unabhängig von der Sprache.
- **Hardware-Zurück aus der Höhen-Vorschau Speichern / Verwerfen verwirft jetzt die Vorschau**, statt stillschweigend wegzunavigieren und den nicht gespeicherten Abruf zu verlieren. Die Vorschauleiste spiegelt das „Sind Sie sicher?"-Muster des Planungsmodus.
- **Sicherung → Wiederherstellung bewahrt jetzt Startzeit, Stoppzeit und Aktivitäts-Tag Ihrer aufgezeichneten Tracks.** Importierte GPX-Tracks waren bereits abgedeckt (sie tragen diese Felder ohnehin nicht); aufgezeichnete Tracks verloren alle drei still bei jeder Wiederherstellung. Wenn Sie seit Einführung der Aktivitäts-Markierung eine Sicherung wiederhergestellt und bemerkt haben, dass Ihre Wanderungen / Fahrten ihre Abzeichen verloren — das ist der Grund. Erstellen Sie jetzt eine frische Sicherung, und die nächste Wiederherstellung behält sie.
- **Übersetzungsvervollständigung (de / fr / es / pl / ar).** Elf Zeichenketten rund um den Höhen-Abruf-Ablauf („Höhe wird abgerufen…", „Speichern", „Verwerfen", „Höhe konnte nicht abgerufen werden" usw.) und der Diagramm-Wisch-Tooltip („Diagramm berühren zum Erkunden") sind jetzt übersetzt. Vorher waren diese auf nicht-englischen Telefonen nur auf Englisch.
- **Diverse Feinschliffe.** Mehrere „Track gespeichert" / „GPS wird erfasst"-Statusmeldungen erscheinen jetzt als schnelle Toasts (~2 s, blockieren die Karte nicht) statt als untere Snackbars (~4 s, blockierten Taps). Der Startpfad des Aufzeichnungs- / Folgemodus-Dienstes wurde gegen eine seltene Race-Condition gehärtet, die eine „Dienst nicht gestartet"-Warnung loggen konnte. Der Höhen-Abruf der Streckenplanung ist auf langen Routen schneller (die Netzwerkverbindungen pro Stapel werden jetzt wiederverwendet).

---

## 1.33.1 — 28. Apr. 2026 — Sortier-Feinschliff + Höhenabruf für alte Tracks + ESRI-Standard

- **Eine Sortierzeile erneut antippen, um die Richtung umzukehren.** In den Listen Tracks und Wegpunkte kehrt das Antippen der **aktiven** Sortierzeile jetzt die Reihenfolge um — `Neueste zuerst` wird zu `Älteste zuerst`, `Name (A→Z)` zu `Name (Z→A)`, `Nächste zuerst` zu `Entfernteste zuerst`, `Meiste Punkte` zu `Wenigste Punkte`. Die aktive Zeile zeigt den Richtungsnamen plus ein `✓`. Das Antippen einer anderen Zeile wählt die natürliche Richtung dieses Schlüssels; erneutes Antippen kehrt sie dann um. Kein separater Auf-/Absteigend-Schalter — hält das Menü kompakt.
- **Tracks nach Aktivität sortieren und filtern.** Die Track-Liste erhält einen fünften Sortierschlüssel: **Aktivität** (alphabetisch — Gleitschirmfliegen, Laufen, Offroad, Radfahren, Spazieren, Wandern). Tracks ohne zugewiesene Aktivität sinken in A→Z nach unten (und steigen in Z→A nach oben), sodass Sie sehen, was noch markiert werden muss. Das Filter-Menü erhält ebenfalls einen Abschnitt **Aktivität** — sechs Chips für die Aktivitätsarten plus einen „Keine Aktivität"-Chip —, sodass Sie „zeig mir nur meine Wander-Tracks" oder „zeig mir alles, was ich noch nicht markiert habe" isolieren können.
- **Antippen, um die Höhe für Tracks ohne Höhendaten abzurufen.** GPX-Dateien aus manchen Quellen tragen keine Höhe pro Punkt, sodass die Track-Detailansicht früher ein leeres Höhendiagramm zeigte. Jetzt: Wenn ein Track keine Höhe hat, wird der Diagrammbereich durch eine Karte **Antippen, um aus dem Gelände abzurufen** ersetzt. Ein Tipp holt die Höhe aus einem weltweiten Geländemodell (etwa 30 m Genauigkeit, kein Konto erforderlich) für jeden Punkt Ihres Tracks. Während des Ladens sehen Sie eine `X / Y`-Fortschrittszählung und eine Abbrechen-Schaltfläche. Nach Abschluss rendert das Diagramm gegen die neuen Höhen — aber sie sind **noch nicht gespeichert**: Eine Leiste Speichern / Verwerfen erscheint, damit Sie das Ergebnis in der Vorschau prüfen und bei falschem Aussehen abbrechen können.
- **ESRI Topo ist die neue Standard-Basiskarte auf neuen Installationen.** Bestehende Installationen bleiben unberührt — was auch immer Sie unter **Einstellungen → Kartenstil** gewählt hatten, bleibt. Für jemanden, der die App zum ersten Mal installiert, öffnet sich die Karte auf ESRI Topo statt OpenTopoMap. ESRIs Kacheln rendern sauberere Beschriftungen bei Wander-Zoomstufen, besonders auf Displays der iPhone-Klasse. Die Reihenfolge im Picker in den Einstellungen bleibt unverändert; das Zurückwechseln ist ein Tipp.
- **Planung: leichter, einen Eckpunkt zu greifen, zuverlässigeres Mülleimer-Ablegen.** Die Tippziele auf den Planungs-Eckpunkten und Mittelpunkt-Griffen bekamen eine echte ~28dp kreisförmige Trefferfläche (vorher das nackte Symbol-Rechteck — Finger-Fehlgriffe waren auf dichten Routen häufig). Die Mülleimer-Ablegezone bekam einen kleinen Toleranzrand an jeder Kante, und die Prüfung „haben Sie auf dem Mülleimer abgelegt?" nutzt jetzt die tatsächliche Position des Markers beim Drag-Ende statt eines manchmal veralteten „schwebt darüber"-Flags. Nettoeffekt: Der Mülleimer „hört nicht mehr auf zu funktionieren" nach ein paar Eckpunkten, und das Greifen des richtigen Eckpunkts auf einem langen Plan ist zuverlässig.

---

## 1.33.0 — 27. Apr. 2026 — Eine Strecke auf der Karte planen

- **Neu: Streckenplanung.** Skizzieren Sie eine Route, indem Sie Punkte auf der Karte antippen, und speichern Sie sie als normalen Track — nützlich, um die morgige Wanderung auszukundschaften, eine auf einer Papierkarte entdeckte Verbindung zu markieren oder einfach die Runde zu zeichnen, an die Sie sich erinnern. Öffnen Sie **Menü → Tracks** und tippen Sie auf die neue **+**-Schaltfläche (über der Import-Ordner-Schaltfläche). Die Karte öffnet sich im Planungsmodus: Antippen, um nummerierte türkise Stopps hinzuzufügen, einen Stopp lange drücken, um ihn zu ziehen, den kleinen Punkt zwischen zwei Stopps lange drücken, um einen neuen einzufügen. Ziehen Sie einen beliebigen Stopp auf das **Mülleimer-Symbol** (oben rechts, unter dem Kompass), um ihn zu löschen — die Linie verbindet sich durch die verbleibenden Nachbarn neu. Der Mülleimer leuchtet rot, wenn ein Stopp darüber schwebt.
- **Höhenprofil für geplante Routen.** Tippen Sie während der Planung auf das **Diagramm-Symbol** rechts, um ein echtes Höhendiagramm für Ihren Entwurf zu sehen. Die App tastet Ihre Route etwa alle 100 m ab und fragt Open-Meteo nach der Geländehöhe an jedem Abtastpunkt, dann zeigt sie Gesamt-Aufstieg und -Abstieg. Lange Routen werden gröber abgetastet, damit der Abruf schnell bleibt; Sie sehen während des Ladens eine `X / Y`-Fortschrittszählung und eine Abbrechen-Schaltfläche.
- **Den Plan speichern.** Tippen Sie auf **✓ Speichern** in der oberen Leiste, benennen Sie Ihre Route, bestätigen Sie — der geplante Track landet in Ihrer Track-Liste, als GPX exportierbar, mit einer künftigen Aufzeichnung vergleichbar. Wenn Sie das Höhenprofil geladen hatten, trägt der gespeicherte Track die dichten abgetasteten Punkte; falls nicht, nur die Stopps, die Sie angetippt haben (mit Höhe, die Sie bei Bedarf später ausfüllen können).

---

## 1.32.4 — 27. Apr. 2026 — Korrektur des Zuschneide-Dialogs für Arabisch

- **Der Track-Zuschneide-Dialog funktioniert jetzt in Arabisch.** Vorher zeigte das Öffnen des Zuschneide-Dialogs eines Tracks in Arabisch keinen sichtbaren Track, bis Sie die Schieberegler nach innen zogen. Behoben: Der Koordinatenrahmen des Diagramms und die Schieberegler-Drag-Handler bleiben jetzt unabhängig vom Gebietsschema konsistent.

---

## 1.32.3 — 27. Apr. 2026 — Höhe für Wegpunkte mit einem Tipp

- **Höhe aus dem Gelände abrufen.** Wenn Sie einen Wegpunkt bearbeiten, hat das Feld Höhe (m) jetzt rechts ein kleines Download-Symbol. Tippen Sie es an und die App füllt die Höhe aus einem weltweiten Geländemodell (etwa 30 m Genauigkeit) anhand des von Ihnen eingegebenen Breiten- / Längengrads aus. Nützlich, wenn Sie einen Wegpunkt von Hand eingeben oder nachdem Sie einen an eine neue Stelle gezogen haben. Das Symbol ist ausgegraut, bis Sie gültige Koordinaten eingegeben haben; es zeigt einen kurzen Spinner während des Abrufs und eine kurze Meldung „Höhe konnte nicht abgerufen werden", falls Sie offline sind. Was auch immer Sie bereits in das Feld eingegeben hatten, wird ersetzt — Sie haben es ausdrücklich angefordert.

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
