# Settings

**menu → Settings** is organised into five sub-screens: Appearance, Storage, Data, API Keys, Advanced. Each has an ⓘ info button next to group headers explaining what the feature does.

## Appearance

### Theme
- **System** (default) — follows your phone's dark/light setting.
- **Light** — always light.
- **Dark** — always dark.

### Default map
The tile style used when the app launches. Six options; see [The map screen → Map layers](map.md) for details on each. You can still switch styles mid-session via the layers button on the map. Fresh installs default to **ESRI Topo** (clean labels at hiking zooms); existing installs keep whatever you'd previously selected.

### Text size
Slider, 50 %–150 % in 10 % steps. Scales **all in-app text** — menus, lists, the stats bar, dialogs. It applies *on top of* your phone's system font-size setting rather than replacing it, so it never overrides an accessibility choice you've made system-wide; it just nudges ApexGPS up or down from there. Default is 100 %. Use it if a large system font overflows the menus, or if you want bigger text in ApexGPS specifically.

### Map controls size
Slider, 50 %–150 % (same steps as Text size). Resizes the on-map buttons (the main buttons, compass, and recording pill). Shrink it to reclaim screen space on a small phone where the controls feel like they crowd the map; grow it for easier tapping with gloves. Buttons never shrink below a comfortable tap target. Default is 100 %.

### Waypoint size
Slider, 50 %–200 %. A multiplier on top of the automatic zoom-adaptive size — markers already shrink at low zoom and grow at high zoom so they stay readable; this setting nudges the whole range up or down. Default is 100 %. (Before 1.38.0 this was a Small/Normal/Large/XL picker; it's now a slider for finer control.)

### Waypoint clustering
Stepped slider — **Off · Low · Medium · Default**. When you zoom out, nearby waypoints collapse into a single numbered badge so a busy map stays readable; tap a badge to zoom in toward that group. This setting controls how eagerly that grouping happens:

- **Off** — never group; every waypoint always shows as its own pin.
- **Low / Medium / Default** — group progressively more. Lower settings show individual pins sooner as you zoom in and group more loosely; **Default** keeps groups longest.

Default is **Medium**, which keeps crowded maps tidy while still showing individual pins at hiking zoom levels.

### Track line width
Slider from thin to thick. Heavier lines are easier to see when many tracks overlap; thinner lines look cleaner at high zoom. Default is a medium width.

### Start with rotation locked
- **Off** (default) — two-finger rotation gestures work from the moment the app opens.
- **On** — rotation is locked at launch; you need to long-press the compass to unlock. Useful if you often accidentally rotate the map and hate the extra step to un-rotate.

## Storage

### Cache usage
Total size of the browse tile cache + per-tile-source breakdown.

### Map tile cache size
Pick how much disk to allow for auto-cached map tiles: **250 MB**, **500 MB** (default), **1 GB**, **2 GB**. The new cap takes effect immediately on the next tile fetch — no app restart needed. Saved offline regions live separately and are not counted against this limit, so changing the cache size never deletes a region you explicitly downloaded.

### Clear cache
- **Clear all** — removes browse-cached tiles across every style. Does NOT delete your saved offline regions.
- **Clear [specific source]** — per-style clear. Useful if one style is taking a lot of space (e.g., satellite imagery is heavier than contour maps).

Browse tile cache rebuilds as you look at areas with signal. Clearing doesn't hurt data you've explicitly saved via the Maps hub download feature.

## Data

### Backup
Create a ZIP containing tracks, waypoints, saved offline regions, and settings. Toggles let you exclude categories. Saved offline regions have a **three-way mode**: **None** (skip them) / **Recipe** (small — just the instructions to re-download each region, works cross-platform between Android and iOS) / **Full tiles** (the old behaviour — embeds the raw tile bundles, large but offline-restorable, Android-only). See [Backup & restore](backup.md).

### Restore
Open an existing `apexgps-backup-*.zip` file. Choose **Merge** (add to existing) or **Replace** (overwrite existing). See [Backup & restore → Merge vs Replace](backup.md#merge-vs-replace).

### Optimize all tracks
Runs Douglas-Peucker simplification across every imported track. Reduces point counts without visibly changing the track shape. Useful if you've imported lots of heavily-detailed GPX files and the map feels sluggish on an older phone. Shows the total count that'll be touched.

Individual tracks can also be optimized one-at-a-time from the track detail screen.

### Load sample data
A real recording of the **Watzmann Traverse** (Berchtesgaden, Germany): Wimbachbrücke → Watzmannhaus → Hocheck → Mittelspitze → Südspitze → Wimbachgrieshütte → Wimbachbrücke, ~22.6 km loop / +2250 m / about 10–12 h on the move. Three landmark waypoints at canonical real-world coordinates: Wimbachbrücke trailhead (628 m), DAV Watzmannhaus (1930 m), Watzmann-Mittelspitze (the *Hauptgipfel* at 2713 m). Auto-imported on the first launch of a fresh install; this button re-imports it on demand if you've deleted it and want it back. The samples are just normal tracks/waypoints after import — delete them any time.

## API Keys

### Thunderforest
Required to use the **Outdoors (Thunderforest)** tile style. Free "Hobby" plan: 150,000 tile requests per month, no credit card. Sign up at [thunderforest.com](https://www.thunderforest.com/), copy your API key, paste it here → **Save**.

**Without a key, the Outdoors style is hidden** from the map-style picker (and from the Download Offline Region picker) so you don't accidentally pick it and see OpenTopoMap fallback tiles. Paste a key → the entry reappears in both menus. The other five styles work without any key.

## Advanced

### Battery saver at high speed
When you're moving faster than **36 km/h** (≈22 mph) — driving, on a train, on a fast e-bike — the app drops its GPS sampling cadence to one fix every **10 seconds** instead of one per second. Road-shaped tracks still record cleanly; lane-level accuracy is reduced during driving. Cuts roughly half of GPS power draw on the highway leg of a road trip with no visible loss of route geometry. Toggle off if you need full sampling at speed (e.g., rally telemetry).

## About

**Settings → About** shows the app version, attributions, and contact email — plus the **User Guide**: tappable entries for every chapter of this documentation, bundled with the app so the full guide works offline. Tap a chapter → a reader opens and renders the chapter in-app. Cross-chapter links inside each page are honoured; back arrow returns to the chapter list. A **"View online"** link at the bottom opens the same docs at [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) in your browser. For help, contact [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

Below User Guide, a **Privacy policy** row opens the same in-app reader on the privacy chapter — no internet needed to read what data the app collects (none beyond what's on your phone) and how it's used. The same content is mirrored at [apexgps.duttra.de/privacy.html](https://apexgps.duttra.de/privacy.html) for anyone who wants to read it before installing.

---

**Related:** [FAQ →](faq.md) · [Backup & restore →](backup.md)
