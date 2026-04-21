---
title: Changelog — ApexGPS
permalink: /docs/changelog/
---

# Changelog

User-visible changes, newest first. For internal refactoring / version-bump-only builds see the private repo.

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

## 1.22.0 — Apr 19, 2026

- **Panic button** (opt-in). A red ⚠ chip at the top-left of the map. Tap → opens the Share location panel instantly and auto-starts GPS if needed. Enable in **Settings → Appearance → Panic button**. See [Share → Panic button](share-and-navigate.md#panic-button-optional).

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
