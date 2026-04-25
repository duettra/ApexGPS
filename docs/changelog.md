# Changelog

User-visible changes, newest first. For internal refactoring / version-bump-only builds see the private repo.

---

## 1.30.2 — Apr 25, 2026

- **Compass tap respects the rotation lock.** Long-press the compass to lock the map's rotation; while locked, a single tap on the compass no longer snaps the map back to north. (You'd have to long-press again to unlock first, then tap.) This restores the lock's intent — freezing the angle against accidental input, including a stray tap on the compass itself.
- **Shorter, less intrusive notifications.** The "Deleted …" / "Moved …" / "Arrived" / follow-locked / auto-paused-location-off messages now show as a brief Android Toast (about 2 seconds, system overlay) instead of a 4-second snackbar that blocked the bottom of the map. You can tap another waypoint immediately after deleting one without waiting.

---

## 1.30.0 / 1.30.1 — Apr 25, 2026 — Recording quality

First post-1.29 hike (4 h 10 min, 9.98 km) revealed that the live track recording was storing far more points than necessary and had absorbed a large false elevation drop from a stuck altitude reading. Both fixed:

- **Lighter, smoother recordings.** A new filter only keeps a fix if you've moved at least 5 m, 15 seconds have elapsed, or the elevation changed by 3 m+. Wild fixes with accuracy worse than 25 m are dropped outright. On the test hike: ~4600 → ~1500 points stored, no visible change to the trail line, distance accuracy unchanged. Less storage; smaller GPX exports; the same trail.
- **No more false elevation ditches.** Some Android devices' fused location provider gets stuck and reports the same cached altitude (e.g. `139 m` on a hike at 1200 m) for minutes at a time. The recording now treats those readings as "no value" rather than persisting the wrong number. The elevation profile shows a clean gap across the bad window instead of a dip to zero, and the climb / descent stats reflect only real altitude changes.
- **MSL altitude on Android 14+.** Where available, the recording uses the more honest mean-sea-level altitude reading instead of the WGS84 fallback that's prone to the stuck-cache behaviour above.

If you have a recording from before 1.30.0 with a wrong elevation reading, you can re-record it — but the on-track display in the app will use the persisted points. There's no migration step.

---

## 1.29.0 — Apr 24, 2026

- **Live track recording.** Tap the red dot at the top-left of the map to start recording your current trip. A live `HH:MM:SS` timer replaces the dot; tap it for **Pause / Finish / Delete**. Your path draws as a red line on the map as you move. On **Finish** the recording is saved as a new Track and the overlay opens automatically so you can review distance, ascent, and elevation profile right away.
- **Crop Track.** On the track detail screen, **Crop Track** opens a dialog with a mini-map preview and two draggable handles on the elevation chart. Trim a bad start (no GPS fix yet) or a stray tail (forgot to hit Finish) without losing the rest of the track. Destructive — a confirmation step tells you exactly how many points you'll drop.
- **Activity tag per track.** The Track detail screen has a new **Activity** picker: Hiking · Walking · Running · Cycling · Offroading · Paragliding. Recordings default to Hiking; imported tracks start unset.
- **Waypoint elevation.** The waypoint edit sheet has a new optional **Elev (m)** field — fill it in when you want to carry an altitude for a known summit / pass / etc. Blank = no elevation stored (same as today's imported waypoints without elevation data).
- **Track detail + waypoint edit refreshed.** Grouped Cards, section overlines, icons on every row, activity-specific icon on the Activity chip, red-outlined **Delete** to match the destructive action, new **Points** stat on the track screen. Waypoint edit is tighter — the whole form now fits above the system nav bar on most phones without scrolling.
- **Process-death recovery.** If Android ever kills the app mid-recording (low memory, force-stop), the breadcrumb is preserved. Re-open the app and the recording comes back in a paused state — resume, finish, or discard.
- **Battery saver: adaptive GPS cadence.** While recording with the screen off, GPS fix cadence relaxes from 2 s to 10 s to save battery. The moment you unlock the phone it's back to 2 s for live smoothness. Fully automatic.
- **System-location guard.** Tapping record when your Android system-wide location toggle is off now shows a message with a **Settings** shortcut instead of silently starting a dead recording.
- **No-fix hint.** If you tap record before GPS has acquired a fix, a short *"Acquiring GPS fix…"* notice tells you why the breadcrumb hasn't started yet. Recording begins as soon as the first fix lands.
- **Removed:** the opt-in panic button. The top-left area now belongs to the record chip.

---

## 1.28.0 — Apr 24, 2026

- **App now available in Arabic.** العربية joins German, French, Spanish, and Polish alongside English. All six languages in **Settings → Appearance → Language**. Every screen, every menu, the offline User Guide, the website — all translated.
- **Waypoint-overlay labels now translated.** Tapping a waypoint on the map used to show "Elev 145 m · Dist 0.42 km" in English regardless of the app language. Now it switches with the UI language (e.g. "Höhe 145 m · Dist 0.42 km" in German, "ارتفاع 145 م · مسافة 0.42 كم" in Arabic).
- **Numbers stay in Western digits in every language.** Coordinates, distances, altitudes, bearings — all render as `25.165`, `145`, `0.42`, etc. regardless of UI language. Matches the convention used by Google Maps, WhatsApp, and every modern Arabic app.
- **On the compass and in shared coordinates**, N/E/S/W stay Latin — international GPS/aviation convention.
- **Map tile labels (place names)** continue to reflect OpenStreetMap's native-script data for each region — Arabic for Arab-world areas, Latin elsewhere. Independent of the UI language.

---

## 1.27.0 — Apr 23, 2026

- **App now available in four new languages.** German, French, Spanish, and Polish, alongside English. Every screen, every dialog, every menu — all translated. Pick your language in **Settings → Appearance → Language**, or leave it on *System default* to follow your phone\'s language.
- **Translated user guide.** All 11 chapters of the in-app User Guide (Settings → About → User Guide) are translated into the same four languages. Offline and online — the "View online" link at the bottom of the guide takes you to the matching language version at `apexgps.duttra.de/<lang>/docs/`.
- **Language survives a backup restore.** Your chosen language is included in the Settings category of the backup ZIP. Restore on a new phone and you land in the right language without having to find the picker again.
- **Stats bar now translated too.** The SPEED / ELEV / DIST labels at the bottom of the map (and km/h / m units) now switch with the UI language. German shows TEMPO / HÖHE / DIST, Spanish shows VEL / ALT / DIST, and so on.
- **Italian and Arabic are next.** Italian follows the same pattern as French. Arabic adds right-to-left layout, which needs a dedicated visual audit before it ships.

---

## 1.26.2 — Apr 22, 2026

- **Thunderforest API key now encrypted at rest.** The key you paste in **Settings → Advanced** is now stored in an Android-Keystore-backed vault, not plaintext. Existing keys migrate automatically on first launch. Backups that include your settings will carry the key in the ZIP (needed for portability) — a new red warning appears in the backup dialog when this applies, so you know to keep the ZIP private.
- **Backup restore is safer.** Restore now rejects ZIPs attempting directory traversal, caps entries at 100 000, per-entry size at 500 MB, and total uncompressed size at 2 GB. Crafted / malformed backups can't fill your storage or escape the backup directory any more.
- **Cancel button on backup.** While a backup is running you can now hit **Cancel** under the busy button to abort without waiting.
- **GPX import progress.** A `Importing GPX…` snackbar is shown while large imports are in progress, so the app no longer appears frozen during a big load.
- **Location service more reliable on Android 14+.** The GPS foreground service now starts correctly on Android 14 and 15 (previously silently killed in some edge cases). Wake-lock scope tightened — should improve battery drain during long tracking sessions.
- **Tile preview fix + background hygiene.** The saved-offline-maps detail preview now loads without blocking the UI. Internal: tile download service can no longer ANR on shutdown. Release builds no longer leak debug log output.
- **Removed:** the Buy-me-a-coffee link in Settings → About. ApexGPS remains free with no ads, no tracking, no cloud.
- **Internal (for curious users):** Room DB now ships with explicit migrations (1→2→3); upgrades preserve your tracks and waypoints even if a schema bump lands. Downgrade wipe still applies — sideloading an older APK over a newer one will reset the DB.

---

## 1.26.1 — Apr 22, 2026

- **Saved offline map detail — fixed skewed preview.** The map preview on **Menu → Saved offline maps → [tap a region]** was painting tiles past its own bounds, overlapping the stat rows and the "Show on Map" button. The preview now clips correctly to its 1.6:1 rectangle.
- **In-app "View online" link** in Settings → About now points at `apexgps.duttra.de/docs/` (the rendered user guide) instead of the raw GitHub tree view.
- **Buy me a coffee.** New Support section in **Settings → About**. ApexGPS stays free with no ads and no tracking — if it's useful to you, a small tip helps keep new features coming.

---

## 1.26.0 — Apr 21, 2026

- **Offline User Guide.** The full 10-chapter guide is now bundled inside the app — open **Settings → About** and tap any chapter to read without an internet connection. Links between chapters work in-app; taps on external links open your browser.
- **Load sample data.** New button in **Settings → Data** loads 3 example waypoints (Summit / Viewpoint / Trailhead) and 3 tracks of different lengths and elevation profiles. Lets you try every feature of the app without needing your own GPX files. Safe to delete later — they're just normal tracks/waypoints after import.
- **Navigate auto-enables GPS.** Tapping Navigate on a shared location or waypoint now turns live location on automatically if it was off. No more "Acquiring GPS…" stall when you actually wanted to start navigating.
- **Map panning unlocks follow-me again.** A regression from earlier 1.2x builds: under continuous GPS updates the map kept snapping back to your position every second even after you'd dragged it. Drag the map → camera unlocks (FAB turns mid-blue) as before; your triangle keeps updating in place.
- **Waypoint symbols that used to crash.** Importing a GPX that contained Viewpoint / Saddle / Waterfall / Picnic / Drinking water / Guidepost / Ruins / Toilets symbols could crash the app on render. Fixed — all 32 symbols render correctly now.

---

## 1.25.x — Apr 21, 2026

- **Import GPX from the Tracks list** (top-right folder icon). Same for the Waypoints list. The map's Import FAB is gone — list screens own imports now.
- **Add waypoint by coordinates** — blue "+" in the Waypoints list opens the full waypoint edit sheet with empty Lat/Lon fields. Type coords or paste a `lat, lon` string into Latitude (auto-splits).
- **Edit a waypoint's coordinates.** Lat and Lon are now editable in the waypoint edit sheet, with inline validation (lat ∈ [-90, 90], lon ∈ [-180, 180]).
- **Follow-me FAB moved to the bottom** of the map's right-hand column — closest to your thumb. Layers is above it, Measure above that.

---

## 1.24.x — Apr 19, 2026

- **Full-screen navigation compass.** While navigating to a target, tap the 🧭 icon on the nav strip to open a big analog compass: distance / ETA / speed / elevation up top, a rotating dial with the blue needle pointing at the target, and lat/lon/bearing/accuracy below. Drag down to minimise. See [Share → The navigation compass](share-and-navigate.md#the-navigation-compass-full-screen).
- **Share a waypoint.** Waypoint overlay now has a Share button next to Navigate and Edit. Sends the waypoint via any messaging app; recipients with ApexGPS open the link directly as a shared location they can Save.
- **Cleaner nav strip + stats bar.** The nav strip now shows bearing + ETA (bearing in blue — it updates live), distance lives in the stats bar's DIST field. No more duplicate numbers stacked on top of each other.
- Needle on the compass emerges smoothly from the centre pivot (subtle visual polish).

## 1.23.0 — Apr 19, 2026

- **Navigate to any waypoint** straight from the waypoint overlay. Tap the walking-person icon next to Edit — same light-blue dotted line + live distance/bearing + auto-stop at 20 m as shared-location navigation. See [Waypoints → Navigate to a waypoint](waypoints.md#navigate-to-a-waypoint).

## 1.22.2 — Apr 19, 2026

- **User guide link** in Settings → About. Opens this documentation in your browser.

## 1.21.0 — Apr 19, 2026

- **Follow-me: pan freely.** Dragging the map no longer fights the GPS — the triangle keeps updating, but the map stays where you put it. Tap the location button to re-center. Long-press to turn GPS off instantly. Three visible states (off / locked / unlocked) so you always know what the map is doing.
- **Compass-to-north animates smoothly** instead of snapping. Less jolting when rotating back to north.

## 1.20.0 — Apr 19, 2026

- **Navigate to a shared location.** When someone shares a location with you via an `apexgps.duttra.de` link, tap the Navigate button on the bottom bar to draw a light-blue dotted line from your position to theirs with live distance and bearing. Auto-stops when you're within 20 m. See [Share → Navigate to a shared location](share-and-navigate.md#navigate-to-a-shared-location).
- **Visual cue for shared locations.** A red bullseye marker appears at the shared spot so you can see exactly where it is on the map. [Save] it as a waypoint or [Dismiss] to clear.

## 1.19.0 — Apr 19, 2026

- **Waypoints list: filter + sort.** Filter by colour or symbol, sort by date / name / nearest. Matches what Tracks already had. See [Waypoints → The Waypoints list](waypoints.md#the-waypoints-list-menu--waypoints).
- **Share message format cleaner** — labelled URLs (`ApexGPS:` / `Google Maps:`) with a blank line above for readability.

## 1.18.x — Apr 19, 2026

- **Share your current location.** Tap the blue position triangle on the map → info panel with elevation, accuracy, time, battery → Share via WhatsApp, SMS, email, etc. Full flow in [Share & navigate](share-and-navigate.md).
- **App Links.** Shared locations from ApexGPS open directly in the app on devices that have it installed, complete with a red marker at the spot.
- **Web fallback** — if the recipient doesn't have ApexGPS, the shared link opens a web page with a map preview + a button to open in Google Maps.

## 1.17.6 — Apr 18, 2026

- **Maps hub** redesign. Downloading a new area and browsing saved offline maps now live on one screen as expandable cards. See [Offline maps](offline-maps.md).
- Rotation black-corner fix (when you rotate the map, no more black triangles at the edges).

## 1.16.0 — Apr 17, 2026

- **Settings** reorganised into sub-screens (Appearance / Storage / Data / API Keys / About) with inline help.
- **Waypoint size** setting (Small / Normal / Large / XL) in Appearance.
- **Start with rotation locked** option — if you hate accidental map rotations, lock it at launch.

## 1.15.0 and earlier

- Core app: GPX import, tracks list, waypoints with 32 symbols, offline map downloads, compass + rotation, distance measurement, backup/restore to ZIP, track optimization.

---

*For bug-report-level detail or developer context, see the [private code repo](mailto:sandwalker.one@proton.me) — contact the developer for access.*
