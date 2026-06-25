# Changelog

User-visible changes, newest first. For internal refactoring / version-bump-only builds see the private repo.

---

## 1.42.1 — June 25, 2026 — Accurate weather on peaks

- **Current-location weather now uses your altitude.** Previously the chip for your live position could show a too-warm, valley-level forecast — your elevation wasn't being sent to the weather model (on a mountain this could be off by ~9 °C). Tapped waypoints were already correct; now your live location matches.
- **Faster first weather.** The forecast appears almost immediately when you open the map instead of waiting for a full GPS lock, then sharpens to your exact location and elevation once your position settles.
- **Tidier refreshing.** Weather refreshes when you open the forecast, when you tap refresh, and automatically every 15 minutes while you have a live signal — and never makes network calls while you're offline.

---

## 1.42.0 — June 17, 2026 — Adjustable waypoint clustering

- **Control how waypoints cluster** — a new *Waypoint clustering* slider in **Settings → Appearance** lets you choose how aggressively nearby waypoints collapse into a numbered badge when you zoom out: **Off** (always show every pin), **Low**, **Medium**, or **Default**. Lower settings show individual pins sooner as you zoom in.
- The new default is **Medium**, which keeps busy maps tidy while still showing individual pins at hiking zoom levels. Slide it to **Off** if you'd rather never group your waypoints.

---

## 1.41.2 — June 16, 2026 — Smoother compass

- **Smoother navigation compass** — the needle now glides instead of jumping in steps, at any speed.
- **Calibration hint** — when the compass is unreliable it now tells you to calibrate: wave your phone in a figure-8 (clear of metal). Works anytime, even while navigating.

---

## 1.41.1 — June 16, 2026 — Accuracy & navigation polish

- **Realistic elevation gain for imported tracks** — tracks imported from another device (e.g. a GPS watch) used to show wildly inflated total ascent. They now report a realistic figure, matching what the same hike records on your phone.
- **Smarter Optimize** — the Optimize dialog now suggests the right level of detail for you (you can still override it), keeps a track equally smooth whether it's short or long, and works on shorter recordings too — not just huge imports.
- **Better waypoint compass** — points the correct way while driving (it follows your direction of travel from GPS, instead of the in-car compass which metal throws off), moves more smoothly, and the arrival time (ETA) turns green when you're closing in and red **"away"** when you're heading away from the target.

---

## 1.41.0 — June 9, 2026 — Track Guidance

- **Follow a track** — pick any saved or imported track and ApexGPS guides you along it. If you drift off course it alerts you with a beep and a vibration, even with the screen off, and a bar shows how far you have left to go. Arrows along the route and a flag at the destination show the way; tap the reverse button to flip direction.
- **Back to start** — while recording, one tap guides you back to where you began: either retrace your exact path, or head straight back.
- Fixed the follow-me (recenter) button being hidden behind the guidance bar.

---

## 1.40.2 — June 6, 2026 — Elevation recording fix

- Fixed a bug on phones without a barometer where vibration (e.g. mountain biking) could drag a recording's elevation steadily downward to impossible values — elevation now stays anchored to genuine GPS readings.
- Physically impossible elevations (below −500 m or above 9000 m) can no longer be recorded, whatever their source.

---

## 1.40.1 — June 5, 2026 — Recording stats card fixes

- The live recording stats card now keeps its clock current even while a recording is paused.
- Smoother performance on long recordings — the live stats now recompute only while the card is open.

---

## 1.40.0 — June 4, 2026 — Live recording stats card

- **Tap the recording timer to open a live stats card** — duration, distance, current elevation (with its source), total ascent, and the clock, all updating as you go.
- Pause, Finish, and Delete are now clear icon buttons, each with a confirmation.
- The recording menu and the other map menus now match: rounded, translucent, and they follow your in-app Text size setting.

---

## 1.39.1 — June 4, 2026 — Map-return and User Guide fixes

- Fixed an occasional **black map** when returning to the map from a menu — it now redraws immediately instead of staying blank until you panned.
- The offline **User Guide** text now scales with the in-app **Text size** setting, like the rest of the app.

---

## 1.38.0 — June 3, 2026 — Adjustable text and control sizes

- New **Text size** slider in Settings → Appearance (50–150%) that scales all in-app text on top of your Android font setting.
- New **Map controls size** slider — resize the on-map buttons, compass, and record pill; shrink them to reclaim map area on a small phone.
- The waypoint-size setting is now a smooth slider too.

---

## 1.37.15 — June 2, 2026 — Waypoint elevation works offline

- Adding a waypoint on the map now **pre-fills its elevation from your current GPS altitude**, so it works in flight mode or with no signal. You can still edit it, or fetch the precise value later when online.

---

## 1.37.14 — June 2, 2026 — New recordings start with no activity

- A new recording no longer defaults to "Hiking" — it starts with no activity selected (shown as "None"), so you choose the right one yourself. Existing tracks are unchanged.

---

## 1.37.13 — June 1, 2026 — Optimize shows a path preview

- The Optimize dialog now shows a **before/after path preview** (faint original, bold optimized result on top) so you can see the straightening before you save.

---

## 1.37.12 — June 1, 2026 — Optimize cleans canyon GPS noise

- Optimize now **cleans the track before simplifying** — it smooths noisy altitude and straightens the GPS "scribble" you get in deep canyons, while preserving real switchbacks. Validated against a barometer watch on a canyon hike. Preview and Save-as-new still keep your original safe.

---

## 1.37.11 — June 1, 2026 — Crop: Save as new

- Track **Crop** now offers **Save as new** (like Optimize) — keep the cropped version as a separate track and leave the original untouched.

---

## 1.37.10 — June 1, 2026 — Accurate ascent and descent

- Fixed wildly inflated **total ascent/descent** on phones without a barometer (one canyon hike showed +17,000 m instead of ~2,250 m). The figure now denoises the elevation before adding it up, the way Strava and Komoot compute gain. Applies to all stored and imported tracks.

---

## 1.37.5 — May 21, 2026 — GPS Diagnostics overlay (optional)

- New opt-in **GPS Diagnostics** overlay (Settings → Advanced) showing live fix quality, accuracy, and altitude-source detail — useful for understanding tricky-signal recordings.

---

## 1.37.0 — May 17, 2026 — Barometric altimeter and better elevation

- On phones with a barometer, ApexGPS now uses it as the **primary altitude source** — sub-metre stable and free of GPS noise and canyon dropouts.
- Ascent/descent now uses a **5 m threshold** (the Strava/AllTrails standard); existing tracks will show smaller, more realistic numbers.
- Plus a series of accuracy improvements for phones **without** a barometer — multiple altitude sanity-checks and smoothing to reject GPS spikes, and an optional GPS-accuracy field in exported GPX.

---

## 1.36.0 — May 17, 2026 — Better canyon recording

- Recording now **captures more points in canyons and tight terrain** (raw capture with smarter density gates), so deep-canyon descents aren't lost.
- New **Clean GPS jumps** option in Optimize for tidying noisy tracks after the fact.

---

## 1.35.2 — May 15, 2026 — Reliable recycle-bin · Trash icon now appears only while dragging · Tapping near midpoints works

- **The recycle-bin icon is now drag-only — it appears the moment you long-press a vertex or midpoint, glows red on hover, and disappears on release.** Before, the icon was always visible in measure and planning modes but the long-press-drag-to-delete gesture wasn't obvious to most users — they saw the bin but couldn't figure out how to get a point into it. Now the bin appears only when you've actually picked up a point, making the affordance clear.
- **Dropping a midpoint on the recycle-bin now reliably deletes it.** Two intermittent bugs fixed: (1) release-position jitter sometimes left the drop-coordinates a few pixels outside the trash zone even when the icon was glowing red — now the rendered red glow itself is the signal, so if you see red on release, the point deletes; (2) on a few occasions a midpoint dropped on the trash would stay visually parked at the icon area until the next list change — now the line cleanly snaps back to the original shape on every abort.
- **Tapping the line near a midpoint dot no longer warps the existing segment.** Before, if you tried to tap the line to add a new vertex but landed near the midpoint dot between two existing vertices, the existing segment would distort — your tap got hijacked into a near-zero drag that inserted a vertex right at the midpoint. Now the tap is recognised as a tap and a new vertex is added to the end of the list, exactly like tapping anywhere else on the map.

---

## 1.35.1 — May 15, 2026 — Recycle-bin fixes · Track planning starts where you tapped

- **The recycle-bin trash now works when the map is rotated.** Before, dragging a measure pin or planning vertex onto the top-right trash icon silently failed if the map had been rotated by any amount — the icon wouldn't glow red and dropping wouldn't delete. The hit-test now reads raw finger coordinates instead of the rotated map's internal frame, so the trash works at any orientation.
- **Deleting the first measure pin in follow-me mode no longer destroys the next pin.** When measuring with follow-me on, the first pin (pin A) auto-tracks your live location. Trashing it used to fail in a confusing way: A appeared to come back on the next GPS fix, and the pin you'd put right after it (B) silently disappeared. Now trashing A keeps A gone for the rest of the measure session, and B + every other pin stay put. Toggle measure mode off and on to re-seed A at your current location.
- **Track planning no longer auto-places vertex 1 at your current location.** Planning is a deliberate map-area workflow — most users pan to the area they want to plan in, then enter plan mode. Auto-seeding vertex 1 at your GPS location surprised users planning remote routes. Planning now starts empty; the first tap places vertex 1 exactly where you tapped, wherever you've panned the map.

---

## 1.35.0 — May 14, 2026 — Share visible tracks & waypoints · Battery saver at speed · GPX from chat apps

- **Share everything visible on the map with one tap.** A new **share icon** sits in the top-left of the map, just to the left of the ☰ menu. Tap it and a sheet opens listing every visible track + waypoint inside your current viewport. Tick what you want, tap **Share**, pick WhatsApp / email / Drive — the whole bundle goes out as a single `.gpx` file named after the area you were viewing (e.g. `ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx`). Two more entry points use the same sheet: a **Share visible** card on the Maps menu (uses the viewport you had open when you opened the menu), and a **share** icon in the top bar of Tracks / Waypoints lists when you long-press to select multiple — bundles the selected items directly with no extra sheet.
- **Battery saver at high speed.** A new toggle in **Settings → Advanced** (default on) reduces GPS sampling from once-a-second to once-every-10-seconds when you're moving faster than 36 km/h — driving, on a train, on a fast e-bike. Road tracks still record cleanly; lane-level accuracy is reduced during driving. Cuts roughly half the GPS battery drain on the highway leg of a road trip with no visible loss of route shape. Toggle off if you need full sampling at speed.
- **Tap-to-open `.gpx` files from WhatsApp / Telegram / Signal / Outlook.** Before, attachments from these apps fell back to the system text viewer because they advertise the file as generic `application/xml` instead of the canonical GPX MIME type. ApexGPS now also accepts those generic types — single-tap a `.gpx` attachment in any messaging app and the system "Open with" menu shows ApexGPS as a first-class option.
- **Recipe-mode offline-map backups (cross-platform).** Settings → Data → Backup replaces the single "Saved map regions" checkbox with a three-way picker: **None** / **Recipe** (small — lists which regions to re-download, works cross-platform with the iOS port) / **Full tiles** (the old behaviour — embeds the raw tile bundles, large but offline-restorable, Android-only). A recipe backup is around 80 KB even for a dozen regions; restoring one drops placeholder rows in **Maps → Saved offline maps** with a **Download** button to fetch the actual tiles on demand.
- **Paid map style hides itself without a key.** The **Outdoors (Thunderforest)** entry now disappears from the map-style picker and from the Download Offline Region picker until you've pasted an API key under **Settings → API Keys**. Before, picking it without a key silently fell through to OpenTopoMap with no explanation. Paste a key → the entry reappears in both menus.

---

## 1.34.2 — May 14, 2026 — Hide paid tile sources without a key

- **The "Outdoors (Thunderforest)" style now hides itself entirely until you've pasted an API key.** Before, picking it without a key silently fell through to OpenTopoMap with no explanation — you tapped Outdoors, saw OpenTopoMap tiles, and wondered why. The map-style picker and the Download Offline Region picker both omit the Outdoors entry until **Settings → API Keys → Thunderforest** has a saved key. Paste a key → Outdoors reappears immediately in both menus.

---

## 1.34.1 — May 13, 2026 — Backup format v2 (offline-region recipes, cross-platform)

- **Backups can now skip the heavy tile bundles and store a "recipe" instead.** Settings → Data → Backup replaces the single "Saved map regions" checkbox with a three-way picker: **None** / **Recipe** (small — lists which regions to re-download, works cross-platform with the iOS port) / **Full tiles** (large — the old behaviour, Android-only). A recipe backup is around 80 KB even for a dozen regions; the equivalent full-tile backup could be 50–500 MB. Restore a recipe-mode backup and the saved-maps list fills with rows marked "Not downloaded yet · X tiles" plus a **Download** button — tap it to re-download from the original tile server (uses your current cache + a brand-new tile fetch for the rest).
- **A backup made on Android can now be restored on iOS and vice versa — for everything except full-tile bundles.** Tracks, waypoints, settings, and region recipes all round-trip cleanly. The full-tile bundle mode is still Android-only because iOS doesn't ship an MBTiles consumer, but the recipe mode covers most users' practical needs (rebuild on the new phone, accept a short re-download for the regions you care about).
- **Restoring an Outdoors-style recipe nudges you to set the API key first.** If a restored recipe targets Thunderforest and you don't have a key saved, tapping **Download** shows a one-time toast directing you to **Settings → Advanced → Thunderforest API key**; once the key is there, the download starts normally.

---

## 1.34.0 — May 13, 2026 — Sizing polish · Water Sports · Live restore progress · Plural correctness

- **Waypoint markers are about 25% larger by default.** "Normal" (1.0×) now renders at the size the prior "Large" did. If your waypoints feel too small, the picker still has Small / Normal / Large / XL — open Settings → Appearance → Waypoint size and switch back to Normal (existing setting kept; you may want to step down one notch since the whole ladder is bigger now).
- **Crop track sliders — the round handles work from any point now.** Before, only the vertical line of each crop handle was draggable; tapping the round knob at the bottom often did nothing because the touch area didn't extend all the way down. Fixed — both round handles now grab from anywhere on the circle plus a small slop band below.
- **New activity type: Water sports.** Pick it from Track details → Activity to tag paddle, sail, surf, kayak, or any other water session. Same wave-and-water-surface icon as the Waterfall waypoint symbol.
- **Restoring a backup now shows live progress.** A large backup (hundreds of tracks, thousands of waypoints) used to lock the app on a spinner for several minutes with no indication it was working — easy to mistake for a crash and force-close. The Restore button now sits above a progress bar + "Restoring track N of M…" / "Restoring waypoint N of M…" caption that ticks per track and every 100 waypoints, so you can see the import is healthy and how far it has to go.
- **Polish & Arabic now show correctly-pluralised count labels.** 13 strings that show counts ("X tracks", "Y waypoints", "Z minutes ago", "saved 12.4 km · 4,200 points kept", etc.) finally route through proper plural rules. Polish gets its full 4-form set (1 trasa / 2 trasy / 5 tras / 1,5 trasy); Arabic gets all 6 (zero / one / two / few / many / other). English / German / French / Spanish were already grammatically correct but the underlying machinery now routes through the same path for consistency.

---

## 1.33.8 — May 10, 2026 — Measure tool & route planner first-pin queue

- **Tap the measure tool or planner FAB before your GPS fix is ready and the first point now auto-drops as soon as your location lands.** Previously, tapping while GPS was still warming up left an empty start — you had to tap the map manually to drop pin A. Now the app shows "Acquiring GPS fix…" on the toggle and queues the first-point auto-place; once the fix arrives, pin A appears at your current location and the live tracker takes over normally. Mirrors the same queue behaviour the recording FAB got in 1.33.7. Manually tapping to drop a pin meanwhile cancels the queue, so you never lose a tap.

---

## 1.33.7 — May 10, 2026 — Tolerant GPX import · Privacy in About · Recording auto-start

- **Imports of GPX files with malformed coordinates no longer fail outright.** A track-point or waypoint with a malformed `lat` / `lon` value used to abort the entire import. The app now skips the bad point and keeps importing the rest — one bad point in a 10,000-point hike no longer loses the file. Hard upper limits (10K tracks, 100K waypoints, 500K points per track) still throw to prevent out-of-memory.
- **Privacy policy directly under Settings → About.** A new "Privacy policy" row sits beneath User Guide; tap it to read the policy in-app, no internet needed. The same content is mirrored at `apexgps.duttra.de/privacy.html` (the Play Store privacy URL) for anyone who wants to read it before installing.
- **Tap Record before your first GPS fix and the recording auto-starts when the fix arrives.** Previously, tapping Record before any fix had been received started an empty-breadcrumb track immediately — if you tapped Stop before any fix arrived, you'd save a track with zero points. Now the toast says "Acquiring GPS fix…" and the recording auto-fires the moment the first non-null fix lands — no second tap needed.

---

## 1.33.6 — May 9, 2026 — Trash drop-zone reliability fix

- **Track-planning and measure-tool trash drop-zone now works reliably after the app is minimised and resumed from Recents.** A latent issue made the "drag a vertex over the trash bin to delete it" gesture silently stop working after the app's window detached and reattached (minimise → tap from Recents). The drop-zone bounds got stuck at their pre-minimise coordinates while the live map position kept updating, so drops never registered. The hit-test now reads bounds fresh on every drag event (and only when the trash icon is actually attached to the window), so the drop-zone keeps working through any number of resume cycles. No app-restart workaround needed any more.
- **Internal: build cleanups for the Play Store production review.** Bumped a UI dependency (`androidx.activity:activity-compose` 1.9.3 → 1.10.1) to resolve the "edge-to-edge may not display for all users" Vitals warnings flagged on the 1.33.5 review — pure cleanup, no behavior change. Native debug-symbol extraction enabled for release builds (no-op today since the only native libs in the AAB ship pre-stripped by Google, but auto-activates if a future dep ever ships symbols).

---

## 1.33.5 — May 7, 2026 — Adjustable map-tile cache + welcome hike on first install

- **Choose how much disk to allow for the map cache.** Settings → Offline cache now has four presets: 250 MB / 500 MB (default) / 1 GB / 2 GB. The new cap takes effect immediately — no restart. Saved offline regions are stored separately and aren't counted, so changing this value never deletes a region you've explicitly downloaded.
- **A welcome hike on every fresh install.** A real recording of the **Watzmann Traverse** (Berchtesgaden, Germany) — Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, ~22.6 km loop / +2250 m / about 10–12 h on the move — is auto-imported the first time you open the app. Three landmark waypoints come along (Wimbachbrücke trailhead, DAV Watzmannhaus, Watzmann-Mittelspitze). Existing installs are untouched. If you delete the samples and want them back later, **Settings → Data → Load sample data** re-imports them on demand.

---

## 1.33.4 — May 5, 2026 — Permissions tidy-up for the Play Store listing

- **Cleaner permissions on the Play Store page.** Removed a leftover "USB storage" permission declaration that was never used — the app caches map tiles in its own internal storage, not on USB / shared storage. The Play permissions summary now shows four fewer entries; nothing changes on your phone.

---

## 1.33.3 — May 4, 2026 — Correct sea-level elevation + cleaner track screen + follow-me bug fix

- **Stats-bar elevation now reads true sea-level metres.** On most Android phones the GPS chip reports altitude relative to the *ellipsoid* — a smooth math model of Earth — not the actual ocean. In the Persian Gulf that's about 30 m off; standing on Abu Dhabi corniche showed roughly **−27 m** instead of zero. The app now uses the device's mean-sea-level value when available (Android 14+ on supporting hardware) and falls back to a bundled global geoid correction (1° EGM96 grid, ~128 KB) on devices that don't supply it (Vivo X300 Pro is one). Sea level now reads **+0 m to a couple of metres**, anywhere in the world, regardless of phone. Same correction is applied to the share-location text and the elevation passed to the weather forecast.
- **Stats-bar speed pins to 0 km/h when you're standing still.** Previously, GPS jitter at standstill would spike the speed reading to 1–3 km/h despite no actual movement. The display now shows zero until you exceed your phone's reported speed-accuracy floor — the recording itself still uses the raw value, so slow legitimate motion isn't masked.
- **Cleaner recordings in canyons and built-up areas.** Three new defenses against multipath altitude spikes (where a wall reflects the GPS signal): the recording filter now drops altitude readings whose vertical-accuracy is poor, rejects hard jumps over 50 m vs the previous good fix regardless of the elapsed time, and keeps its rate gate sharp even after long no-altitude stretches. A May-3 Wadi Hijr canyon trace had eight one-second altitude jumps of 70–300 m slip through the previous filter; the new layers catch them.
- **Track detail screen — simpler layout.** The toolbar's pencil icon is gone — **tap the track name** in the toolbar to rename. A single row of three buttons sits below the elevation chart: **Crop · Optimize Track (X pts) · Delete Track**. The previous full-width button stack and the 3-dot overflow menu are both removed; everything fits on one phone screen without scrolling.
- **Optimize is now preview-then-save.** Confirming the optimization in the dialog used to commit immediately with no undo. Now the simplified track renders in the chart + stats card underneath a small dialog that shows `3214 → 500 points · 12.40 → 12.30 km`. **Save** writes it; **Discard** (or hardware-back) drops it. No DB changes until you Save.
- **Follow-me FAB: tap once to re-lock.** A bug where panning the map (which dimmed the follow-me FAB) and then tapping it required **two taps** to make the FAB go solid blue — the recenter animation was being misread as a continued user pan. Now one tap re-locks and recenters, as it should always have.

---

## 1.33.2 — Apr 30, 2026 — Refreshed map look + bug-fix sweep

- **Cleaner, more modern map screen.** The top bar, Layers / Measure / Follow-me FABs, the Record button, the stats bar, and the weather chip are now translucent — the map shows through faintly behind them so the screen feels less boxed-in. The map itself now extends edge-to-edge from the very top to the very bottom of the screen.
- **Modernised menus.** The hamburger menu (top-right) and the Layers tile-source picker now appear as rounded popup cards with leading icons, instead of the flat rectangles they were before. Tap targets are larger; the active tile source is marked with a bold name + checkmark.
- **Arabic / Persian / Urdu — Western digits everywhere.** Distances, elevations, coordinates, share-location notification times, and the weather sheet's hourly clock no longer render as Eastern-Arabic numerals (`٣٫٤ كم`) — they read as `3.4 km` regardless of phone language. This was a long-standing inconsistency in the chart labels and a few notification builders.
- **Arabic charts: scrub gestures in the right direction.** The track-detail and planning elevation charts had inverted scrubbing in Arabic — touching the visual left edge jumped to the end of the route. Now the scrub follows your finger correctly regardless of language.
- **Hardware-back from the elevation Save / Discard preview now discards the preview** instead of silently navigating away and dropping the unsaved fetch. The preview bar mirrors the planning-mode "are you sure?" pattern.
- **Backup → restore now preserves your recorded tracks' start time, stop time, and activity tag.** Imported GPX tracks were already covered (they don't carry these fields anyway); recorded tracks were silently losing all three on every restore. If you've restored a backup since the activity-tagging feature shipped and noticed your hikes / rides lost their badges — that's why. Take a fresh backup now and the next restore will keep them.
- **Translation completion (de / fr / es / pl / ar).** Eleven strings around the elevation-fetch flow ("Fetching elevation…", "Save", "Discard", "Couldn't fetch elevation", etc.) and the chart scrub tooltip ("Touch chart to explore") are now translated. Previously these were English-only on non-English phones.
- **Misc tightening.** Several "Track saved" / "Acquiring GPS fix" status messages now appear as quick toasts (~2 s, don't block the map) instead of bottom snackbars (~4 s, blocked taps). The recording / follow-me service start path was hardened against a rare race that could log a "service didn't start" warning. Track planning's elevation fetch is faster on long routes (the per-batch network connections are now reused).

---

## 1.33.1 — Apr 28, 2026 — Sort polish + fetch elevation for old tracks + ESRI default

- **Re-tap a sort row to flip the direction.** In the Tracks and Waypoints lists, tapping the **active** sort row now reverses the order — `Newest first` flips to `Oldest first`, `Name (A→Z)` flips to `Name (Z→A)`, `Nearest first` flips to `Farthest first`, `Most points` flips to `Fewest points`. The active row shows the directional name plus a `✓`. Tapping a different row picks that key's natural direction; re-tapping then flips it. No separate asc / desc switch — keeps the menu compact.
- **Sort and filter your tracks by activity.** The Tracks list gains a fifth sort key: **Activity** (alphabetical — Cycling, Hiking, Offroading, Paragliding, Running, Walking). Tracks with no activity assigned sink to the bottom in A→Z (and float to the top in Z→A) so you can spot what still needs tagging. The filter menu also gains an **Activity** section — six chips for the activity types plus a "No activity" chip — so you can isolate "show me only my hiking tracks" or "show me everything I haven't tagged yet."
- **Tap to fetch elevation for tracks that don't have any.** GPX files from some sources don't carry per-point altitude, so the track detail used to show an empty elevation chart. Now: if a track has no elevation, the chart area is replaced with a **Tap to fetch from terrain** card. One tap pulls altitude from a worldwide terrain model (about 30 m accuracy, no account required) for every point of your track. While loading you'll see an `X / Y` progress count and a Cancel button. When it finishes, the chart renders against the new altitudes — but they're **not saved yet**: a Save / Discard bar appears so you can preview the result and back out if it looks wrong.
- **ESRI Topo is the new default basemap on fresh installs.** Existing installs are untouched — whatever you'd picked under **Settings → Map style** sticks. For someone installing the app for the first time, the map opens on ESRI Topo instead of OpenTopoMap. ESRI's tiles render cleaner labels at hiking zooms, especially on iPhone-class displays. The picker order in Settings is unchanged; switching back is one tap.
- **Planning: easier to grab a vertex, more reliable trash drop.** Touch targets on the planning vertices and midpoint handles got a real ~28dp circular hit-area (was the bare icon rect — finger-misses were common on dense routes). The trash drop-zone got a small slop margin on every edge, and the "did you drop on the trash?" check now uses the marker's actual position at drag-end, not a sometimes-stale "is hovering" flag. Net effect: the trash bin no longer "stops working" after a few vertices, and grabbing the right vertex on a long plan is reliable.

---

## 1.33.0 — Apr 27, 2026 — Plan a track on the map

- **New: track planning.** Sketch a route by tapping points on the map and save it as a regular Track — useful for scouting tomorrow's hike, marking a connector you spotted on a paper map, or just drawing the loop you remember. Open **menu → Tracks** and tap the new **+** button (above the import-folder button). The map opens in planning mode: tap to add numbered teal stops, long-press a stop to drag it, long-press the small dot between two stops to insert a new one. Drag any stop onto the **trash icon** (top-right, below the compass) to delete it — the line reconnects through the remaining neighbours. The trash glows red when a stop is hovering over it.
- **Elevation profile for planned routes.** While planning, tap the **chart icon** on the right to see a real elevation chart for your draft. The app samples your route every ~100 m and asks Open-Meteo for the terrain altitude at each sample, then shows total ascent and descent. Long routes are sampled coarser so the fetch stays quick; you'll see a `X / Y` progress count and a Cancel button while it loads.
- **Save the plan.** Tap **✓ Save** in the top bar, name your route, confirm — the planned track lands in your Tracks list, exportable as GPX, comparable against a future recording. If you'd loaded the elevation profile, the saved track carries the dense sampled points; if not, just the stops you tapped (with elevation to fill in later if you want).

---

## 1.32.4 — Apr 27, 2026 — Crop dialog fix for Arabic

- **Crop track dialog now works in Arabic.** Previously, opening a track's crop dialog in Arabic showed no visible track until you dragged the sliders inward. Fixed: the chart's coordinate frame and slider drag handlers now stay consistent regardless of locale.

---

## 1.32.3 — Apr 27, 2026 — One-tap elevation for waypoints

- **Fetch elevation from terrain.** When you're editing a waypoint, the Elev (m) field now has a small download icon on the right. Tap it and the app fills in the elevation from a worldwide terrain model (about 30 m accuracy) using the latitude / longitude you've typed. Useful when you're typing a waypoint by hand, or after dragging one to a new spot. The icon is greyed out until you have valid coordinates entered; it shows a brief spinner while fetching, and a quick "Couldn't fetch elevation" message if you're offline. Whatever you'd already typed in the field is replaced — you explicitly asked for it.

---

## 1.32.2 — Apr 26, 2026 — Weather on by default + full translations + Maps back-button

- **Weather is now on out of the box.** The forecast chip and "Weather here" line on waypoints are visible without having to flip a setting first. You can still turn weather off under **Settings → Weather** if you'd prefer no network calls — existing installs keep whatever you already had.
- **Full translations for the weather feature.** All weather text — the chip, the sheet (current panel, 24-hour strip, humidity / pressure trends, 7-day strip, sunset / UV / pressure / dewpoint labels), the Settings rows, and the User Guide chapter title — is now translated into German, French, Spanish, Polish and Arabic. Weather condition labels ("Light rain", "Thunderstorm + hail", "Partly cloudy", …) follow the standard meteorological vocabulary in each language.
- **Maps menu: back button now collapses an open card before leaving.** When **Download new map area** or **Saved offline maps** was expanded, pressing back used to skip the Maps menu entirely and dump you back on the map. Now back closes the open card first; one more press takes you to the map. This matches how the back button already worked elsewhere (Settings sub-screens, multi-select on the tracks / waypoints list).

---

## 1.32.1 — Apr 25, 2026 — Weather: small fixes

- **Correct sun / moon icons through midnight.** The 24-hour weather strip used to show moon glyphs against the next day's afternoon hours (11:00, 14:00, 17:00) when you opened the sheet late at night. Each hour now picks its own day's sunrise / sunset, so daytime hours always show the sun-side icons.
- **Waypoint forecast actually uses the waypoint's elevation.** When a peak waypoint sat at virtually the same coordinate as your current GPS reading, the cached current-location forecast was sometimes returned for the waypoint instead of a fresh elevation-aware fetch. On a 1480 m summit that meant the forecast was running ~9 °C too warm. The cache now keys on elevation as well as coordinates, so the waypoint's stored height is always honoured.

---

## 1.32.0 — Apr 25, 2026 — Weather: per-point polish, no map overlays

After 1.31.0 went out, the gridded weather overlays didn't pass the eye test on hiking-zoom maps — they read as blocky colour squares with no real terrain alignment, and the bottom row of controls (overlay slider + chip + speed / elevation / distance bar) ate too much screen. This release strips the map back and doubles down on the per-point sheet, which is where the useful detail lives.

- **Map overlays removed.** No more precipitation radar or cloud-cover overlays on the basemap, no time slider. The **Settings → Weather** screen shrinks to a single master toggle.
- **Richer per-point sheet.** The weather sheet (tap the chip or a waypoint's "Weather here" line) now shows: hero current panel with weather emoji, temperature, "feels like", wind / humidity / dewpoint / pressure / UV / sunset; a 24-hour strip with hour-by-hour weather icons + temperature; a humidity trend (light blue) and a pressure trend (green); and a 7-day strip with high / low + icon. Designed to fit on one screen on a typical phone.
- **Per-waypoint elevation is sent to the forecast.** Waypoints with a stored elevation field now feed it to the forecast model, so summit forecasts use the real summit height instead of the model's coarse averaged elevation. Same for the chip's current-location forecast — it uses your GPS altitude.
- **Chip aligns with waypoint card.** The stats-bar chip text now matches what you see when you tap a waypoint: emoji + temp + wind. A thin separator was added between the chip and the speed/elevation/distance row so they read as one panel.

---

## 1.31.0 — Apr 25, 2026 — Weather

ApexGPS now shows hiking-grade weather information from free public APIs, fully opt-in.

- **Forecast chip in the stats bar.** Once you turn weather on in **Settings → Weather**, a small chip above the speed/elevation/distance bar shows current conditions for your GPS location: temperature, wind, humidity. The chip updates every 15 minutes when online and tells you when the data is stale or you've gone offline (greys out and adds a clock).
- **Tap-to-expand sheet.** Tap the chip (or the new "Weather here" line on a waypoint panel) for the full breakdown — current readings, the next 24 hours as a temperature line + precipitation bars chart, and a 7-day strip with high/low temps and weather icons.
- **Manual refresh.** A ↻ button in the sheet header forces a fresh fetch when you've reconnected after a flight-mode patch.
- **Animated map overlays.** A new **Overlays** section in the Maps hub adds two independent toggles: precipitation radar (animated colour-coded rain, past 2 hours plus a 30-minute nowcast) and cloud satellite (infrared cloud-tops, geostationary). These don't send your location anywhere — they're pure tile fetches, independent of the weather chip.
- **Privacy first.** The whole feature defaults off. Forecasts come from Open-Meteo and radar from RainViewer; both are free public APIs that don't require an account or an API key. Your location is only sent when you explicitly enable the chip.

Read the full chapter under **Settings → User Guide → Weather**.

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
