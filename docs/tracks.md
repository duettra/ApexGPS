# Tracks

A **track** is a recorded path — a sequence of GPS points connected as a line on the map. You get tracks three ways: **record** them live during a hike, **import** GPX files (from GaiaGPS, Strava, Garmin Connect, wikiloc.com, or anything else that exports GPX), or **plan** a new route by tapping points on the map.

## Recording

Tap the red **record dot** at the top-left of the map. The dot expands into a live elapsed-time chip (`00:12:43`) and a red breadcrumb line starts drawing your trip on the map as new GPS fixes arrive.

### While recording

- **Tap the timer chip** for a menu:
  - **Pause** — freezes the clock; new fixes stop being added to the breadcrumb until you tap **Resume**.
  - **Finish** — saves the trip as a new Track, opens the track overlay so you can review stats + elevation profile immediately.
  - **Delete** — throws away the current recording without saving.
- The GPS foreground service is started for you when you begin a recording — you don't need to toggle follow-me first.
- **Screen off?** The app relaxes the GPS update cadence to save battery (≈10 s between fixes with screen off vs. 2 s with screen on). No action required — it flips automatically.

### If system location is off

Tapping record when the Android system-wide location toggle is off shows a quick *"System location is off — turn it on to record"* message with a **Settings** shortcut. The recording doesn't start.

### If the app is killed mid-hike

If Android ever kills the app during an active recording (low-memory reclaim, force-stop, reboot), the breadcrumb collected up to that point is **preserved**. Re-open the app and the chip comes back showing elapsed time in a paused state — tap **Resume** to keep going, or **Finish** to save what you've got.

### Activity type

Every recorded track starts tagged as **Hiking**. Open the track's detail screen (Tracks → tap the row) and use the **Activity** picker to change it to Walking / Running / Cycling / Offroading / Paragliding. Imported tracks have no activity tag by default; you can assign one the same way.

### Cropping a recording

Got GPS-warmup noise at the start of your track? Forgot to tap **Finish** and the track now drags halfway to your car? Open the track detail screen and tap **Crop Track**:

- A dialog opens with a mini-map preview of the full track and its elevation profile below.
- Drag the two handles on the elevation chart to set the start and end of the range you want to keep. The mini-map updates live — the kept segment stays in the track's colour, the parts you're dropping fade to grey.
- The **Kept** readout shows the resulting distance and point count.
- Tap **Crop** to commit. A confirmation dialog spells out how many points will drop from each end. **This cannot be undone** — keep a GPX export if you're worried.

Cropping also recomputes the track's distance, bounding box, and elevation profile, so the top-of-screen stats reflect the trimmed track immediately.

## Planning a track

If you want to scout a route before hiking it — tomorrow's walk, a loop you saw on a paper map, a connector between two trails you know — you can sketch it directly on the map and save it as a Track.

Open **menu → Tracks** → tap the blue **+** FAB at the bottom-right (above the import-folder FAB). The app jumps to the map in **planning mode**:

- The top bar changes to `✕  Plan track  ✓ Save`. A small chip below shows your live point count and total distance.
- **Tap anywhere on the map** to drop a numbered teal vertex. Each tap extends the route to the next stop. Vertex 1 is auto-placed at your current location if follow-me is on.
- **Long-press a vertex and drag** to move it. Long-press the small dot between two vertices and drag to insert a new point on that leg.
- **Drag a vertex onto the trash icon** at the top-right (just below the compass) to delete it. The line reconnects through the remaining neighbours. The trash glows red when a vertex is hovering over it.
- Tap the **chart icon** on the right to open the **elevation profile** sheet. The app fetches elevations from Open-Meteo for samples taken every ~100 m along your route, then shows a chart with total ascent and descent. A long route is sampled coarser (capped at ~500 samples) so the fetch never balloons. Cancel and dismiss are both available while loading.
- Tap **✓ Save** in the top bar, name your route, confirm. The new Track lands in your Tracks list (sortable, exportable as GPX, can be compared against a future recording). The map fits the new track's bbox automatically.

To bail out: tap **✕** or hit hardware-back. If you've placed any points, the app asks before discarding.

## Importing

### From a file

Open **menu → Tracks** → tap the blue **folder icon** FAB at the bottom-right. Pick one or more `.gpx` files from your phone's storage (multi-select allowed). The app navigates you back to the map and auto-zooms to fit the imported tracks.

### From a share (WhatsApp, email, another app)

Someone sends you a `.gpx` file? Tap it in the chat / email / file manager → the system offers to open with ApexGPS → the app imports it automatically and takes you to the map.

### What gets imported

- Track lines (with elevation if the GPX has it).
- Any waypoints embedded in the GPX file (each with its name, description, and symbol mapped to ApexGPS's closest match).

**Duplicate protection:** if you re-import the same GPX, waypoints already at those coordinates aren't added again. Track lines ARE imported again (they're named the same, you can delete the duplicate manually).

## Viewing a track on the map

Tap a track line on the map. A panel slides up from the bottom with:

- Track name + distance.
- **Elevation profile** — a little chart. Drag your finger across it to scrub along the track; a crosshair shows where on the map that point is.
- **Ascent / descent** totals.
- **Edit** button → opens the track detail screen.
- **Share** button → exports the track as a `.gpx` file you can send to anyone.
- **Hide** button → minimises the panel to a thin bar at the bottom (so you can keep working with the track selection without the panel covering the map).
- **Dismiss** (swipe down) → closes the panel.

## The Tracks list (menu → Tracks)

A full list of every track you've imported. Count in the title.

### Filter

Tap the **filter icon**. Three options:

- **Visibility** — All / Visible only / Hidden only. Tracks you've hidden via the visibility toggle still exist in the list but don't draw on the map.
- **Color** — 16-colour palette. Tap a colour chip to see only tracks of that colour.
- **Activity** — six chips (Hiking / Walking / Running / Cycling / Offroading / Paragliding) plus a **No activity** chip for tracks you haven't tagged yet. Combine with the others to isolate, say, only hiking tracks coloured blue.

Active filter turns the icon blue. Tap **Any** in any section to clear that section.

### Sort

Tap the **sort icon**. Five keys, and **re-tapping the active key flips the direction** (the active row shows the directional name + `✓`):

- **Newest first** / **Oldest first** — by import / creation date (newest is the default).
- **By name** → **Name (A→Z)** / **Name (Z→A)** — alphabetical.
- **Nearest first** / **Farthest first** — closest centre-point to your current location. Uses your phone's last-known GPS fix so it works even if you haven't turned on GPS in ApexGPS this session. Shows "(no GPS)" if location permission is denied or there's no cached fix.
- **By points** → **Most points** / **Fewest points** — useful for picking out heavily-detailed tracks vs simple routes.
- **By activity** → **Activity (A→Z)** / **Activity (Z→A)** — alphabetical by activity type. Tracks with no activity tag sink to the bottom in A→Z and float to the top in Z→A — chosen so "what activities have I tagged?" is the readable view.

Tapping a different key resets to that key's natural direction (newest / A→Z / nearest / most / A→Z); re-tap to flip.

### Search

Type into the search box to filter the list to tracks whose name contains your text.

### Select multiple

Long-press a track → selection mode. Tick the ones you want, then:

- **Bulk colour change** (palette icon) — set all selected to one colour.
- **Bulk show / hide** (eye icons) — quickly control visibility.
- **Bulk delete** (trash icon, red) — with confirmation.
- **Select all** — tick every track currently in the filtered view.

## Per-track actions

Tap a track in the list → it opens the **Track detail** screen.

- **Name** — **tap the title in the top bar to rename**.
- **Colour** — tap to open colour picker.
- **Visibility** — show / hide on the map.
- **Elevation profile** — the same chart as the map overlay, but full-size. If the track was imported without per-point altitude (some GPX exporters strip it), the chart area shows a **Tap to fetch from terrain** card instead. One tap pulls altitudes from the same worldwide terrain model the waypoint and planning fetches use (~30 m accuracy, no account required); you'll see an `X / Y` progress count and a Cancel button while it loads. When it finishes, the chart renders against the fetched values and a **Save / Discard** bar appears so you can preview the result and back out if it looks wrong.
- **Ascent / descent** totals.
- **Point count** — how many GPS samples make up this track.
- **Top-bar icons:** **share** (export as GPX) and **show on map** (closes the detail and zooms the map to fit the track).
- **Action row below the chart** — three buttons:
  - **Crop Track** — open the cropping dialog (see [Cropping a recording](#cropping-a-recording) above).
  - **Optimize Track (N pts)** — simplify the track by dropping redundant points. Useful for importing huge overly-detailed exports. The dialog asks for a target point count; on confirm the simplified track renders in the chart + stats panel beneath a small dialog summary (`3214 → 500 points · 12.40 → 12.30 km`). **Save** persists; **Discard** (or hardware-back) drops the preview without touching your track.
  - **Delete Track** (red) — with confirmation.

## Bulk optimize (for heavy libraries)

If you've imported many extremely dense tracks, the map can feel sluggish on older phones. **Settings → Data → Optimize all tracks** runs the same simplification across every track at once. There's a count in the Settings UI so you know how many will be touched.

## Deleting

Single: swipe / tap the trash icon on any track row, or use the Delete button on the detail screen.

Multiple: selection mode + bulk delete.

There's no undo. Keep a [backup](backup.md) if you're nervous.

---

**Related:** [Waypoints →](waypoints.md) · [The map screen →](map.md) · [Backup & restore →](backup.md)
