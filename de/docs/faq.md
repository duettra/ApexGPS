# FAQ & Fehlerbehebung

## „Mein blaues Dreieck erscheint nicht“

Drei mögliche Gründe:

1. **GPS ist nicht an.** Tippen Sie auf den Fadenkreuz-Button in der rechten Spalte. Geht von grau → blau. Siehe [Die Kartenansicht → Folgen-Modus](map.md#folgen-modus-fadenkreuz).
2. **Die Standort-Berechtigung ist nicht erteilt.** Gehen Sie in die Einstellungen Ihres Telefons → Apps → ApexGPS → Berechtigungen → Standort → **Nur bei Nutzung zulassen**, **Genau**. Öffnen Sie dann ApexGPS erneut.
3. **Noch keine GPS-Position.** Drinnen, in der Nähe hoher Gebäude oder in engen Tälern kann die erste Erfassung 30 Sekunden oder länger dauern. Wenn möglich, nach draußen gehen.

## „Die Karte zieht ständig zu mir zurück“

Das ist der gesperrte Folgen-Modus. Ziehen Sie die Karte einmal — der Fadenkreuz-Button wird heller blau und die Karte bleibt, wo Sie sie hinziehen. Das Dreieck aktualisiert sich weiter; nur die Kamera hört auf, Sie zu verfolgen. Zum Re-Zentrieren: Fadenkreuz-Button antippen.

Siehe [Die Kartenansicht → Folgen-Modus](map.md#folgen-modus-fadenkreuz).

## „Wie schalte ich GPS ganz aus?“

**Lange drücken** auf den Fadenkreuz-Button. GPS stoppt, das Dreieck verschwindet, Akku gespart.

Tap-zum-Umschalten aus dem gesperrten Zustand schaltet ebenfalls aus, aber ein Langes-Drücken überspringt die Re-Zentrierungs-Animation — nützlich, wenn Sie weggezogen haben und nicht möchten, dass die Karte vor dem Ausschalten zurückspringt.

## „Jemand hat mir einen Standort-Link geschickt — wie sehe ich ihn an?“

Wenn der Link wie `https://apexgps.duttra.de/loc?lat=...&lon=...` aussieht, tippen Sie ihn direkt in Ihrer Nachricht an. Mit installiertem ApexGPS öffnet er sich in der App mit einer roten Zielscheibe. Ohne ApexGPS öffnet sich eine Webseite mit Kartenvorschau + einem Link zur Installation.

Andere Karten-Links (Google-Maps-URLs usw.) öffnen sich in Ihrer bevorzugten Karten-App — sie binden nicht in ApexGPS ein.

Siehe [Teilen → Einen geteilten Standort empfangen](share-and-navigate.md#einen-geteilten-standort-empfangen).

## „Kann ich beim Wandern einen neuen Track aufzeichnen?“

Nicht in dieser Version. Live-Track-Aufzeichnung (Ihre Strecke beim Laufen) ist für eine zukünftige Version geplant. Derzeit kommen Tracks durch Import von GPX-Dateien (von einer anderen App oder von jemand anderem).

## „Wie viel Speicher belegt die App?“

Die App selbst ist klein (~10 MB). Der Speicherverbrauch wächst durch:

- **Browse-Kachel-Cache** — Kacheln aus den Bereichen, die Sie angesehen haben. Siehe **Einstellungen → Speicher** für die Größe.
- **Gespeicherte Offline-Regionen** — Kacheln, die Sie explizit über den Karten-Hub vorab heruntergeladen haben. Können groß sein (50–500 MB pro Region je nach Zoomstufen).
- **Tracks + Wegpunkte** — winzig, meist unter 1 MB auch bei hunderten Einträgen.

Browse-Cache leeren über Einstellungen → Speicher → Leeren. Gespeicherte Regionen löschen über Karten-Hub → Region antippen → Löschen.

## „Die Karte ist beim Zoomen / Verschieben langsam“

Ein paar Dinge zum Ausprobieren:

1. **Zu viele Tracks geladen.** Track-Liste → nach Sichtbarkeit filtern → die heute nicht benötigten ausblenden. Oder alte Importe bulk-löschen.
2. **Stark detaillierte Tracks.** **Einstellungen → Daten → Alle Tracks optimieren** nutzen, um zu vereinfachen — die Punktanzahl sinkt ~90 % ohne sichtbare Änderung.
3. **Niedriger Zoom mit vielen Wegpunkten.** Wegpunkte clustern sich bei niedrigem Zoom automatisch (ein einzelner Punkt mit Anzahl) — ein Cluster antippen, um hineinzuzoomen. Wenn Ihr Telefon trotzdem noch kämpft, ist die Cluster-Schwelle im Code fest; erwägen Sie stattdessen, Tracks auszublenden.
4. **Altes Telefon.** ApexGPS richtet sich an modernes Android. Bei einem Gerät vor 2020 sind einige Leistungseinbußen mit 500+ Tracks gleichzeitig unvermeidbar.

## „Ich sehe die neue Version nicht im Play Store“

Sie sind Closed-Testing-Tester und haben gerade eine Update-Benachrichtigung erhalten. Falls sie nicht erscheint:

1. Play Store → Profilsymbol (oben rechts) → **Apps und Gerät verwalten** → **Verfügbare Updates** → aktualisieren. Wenn ApexGPS erscheint, **Aktualisieren** antippen.
2. Weiterhin nichts? Öffnen Sie den Tester-Einladungslink erneut (den Sie zum Testbeitritt genutzt haben). Dann Play Store erzwungen stoppen, neu öffnen, ApexGPS suchen.
3. Weiterhin nichts? **Einstellungen → Apps → Google Play Store → Speicher → Cache leeren**. Play Store neu öffnen, erneut suchen.
4. Googles CDN-Rollout dauert 2–24 Stunden nach „Auto-veröffentlicht“. Wenn Sie gerade erst vom Update erfahren haben, ein paar Stunden warten.

## „Kann ich ApexGPS ohne Standort-Berechtigung nutzen?“

Größtenteils ja. Sie können GPX-Dateien importieren, Tracks ansehen, Routen planen, Distanzen messen, Wegpunkte verwalten und Kartenregionen vorab herunterladen — alles ohne Standort. Was verloren geht:

- Live-Positions-Dreieck.
- Folgen-Modus / Nach-nächste-sortieren.
- Standort-teilen-Feature (kein Standort zu teilen).
- Navigation-zu-Ziel (kein „Sie“ als Startpunkt).

## „Sendet die App meinen Standort irgendwohin?“

Nein. ApexGPS führt keine Netzwerk-Anfragen mit Ihrem Standort durch. Die einzige ausgehende Netzwerkaktivität ist das Abrufen von Kartenkacheln, was vom Durchsuchen einer Karte nicht zu unterscheiden ist — Kachel-Server sehen eine IP + Kachelkoordinaten, nichts über Sie. Siehe die [Datenschutzerklärung](/privacy.html).

Das Teilen über den Teilen-Button ist vollständig nutzerinitiiert — Sie wählen die App (WhatsApp usw.) und den Empfänger.

## „Das Android-Telefon meines Freundes öffnet den geteilten Link im Browser, nicht in ApexGPS“

Der Link verlinkt nur auf Geräten direkt in ApexGPS, auf denen die von Google ausgestellte App-Links-Verifizierung abgeschlossen ist. Frische Installationen brauchen manchmal einen ersten App-Start, bevor die Verifizierung greift. Bitten Sie Ihren Freund:

1. ApexGPS einmal öffnen, Standort-Berechtigung erteilen, schließen.
2. Ihren geteilten Link erneut antippen.

Jetzt sollte er sich direkt in der App öffnen. Falls er weiterhin im Browser öffnet, bietet Android möglicherweise einen Auswahl-Dialog — er kann „Immer in ApexGPS öffnen“ aus dem Dialog wählen.

## „Kann ich eine ApexGPS-Sicherung auf dem iPhone wiederherstellen?“

Nein. ApexGPS ist nur für Android. Das Sicherungsformat ist app-spezifisch.

## „Wo liegen meine Daten physisch?“

Auf Ihrem Telefon, im privaten App-Speicher von ApexGPS (`/data/data/com.apexgps.app/` bei gerootetem Zugriff — ansonsten nicht direkt erreichbar). Tracks + Wegpunkte in einer SQLite-Datenbank; Einstellungen in einer Preferences-Datei; Kacheln als Bilddateien auf der Festplatte.

Nichts wird irgendwohin hochgeladen. Zum Sichern nutzen Sie [Sicherung & Wiederherstellung](backup.md).

---

**Immer noch stecken geblieben?** [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me) — Fehlerberichte willkommen.
