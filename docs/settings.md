# Settings

**menu → Settings** is organised into four sub-screens: Appearance, Storage, Data, API Keys. Each has an ⓘ info button next to group headers explaining what the feature does.

## Appearance

### Theme
- **System** (default) — follows your phone's dark/light setting.
- **Light** — always light.
- **Dark** — always dark.

### Default map
The tile style used when the app launches. Six options; see [The map screen → Map layers](map.md) for details on each. You can still switch styles mid-session via the layers button on the map. Fresh installs default to **ESRI Topo** (clean labels at hiking zooms); existing installs keep whatever you'd previously selected.

### Track line width
Slider, 4–24 dp. Heavier lines are easier to see when many tracks overlap; thinner lines look cleaner at high zoom. Default is around 6 dp.

### Waypoint size
Small / Normal / Large / XL. This is a multiplier on top of the automatic zoom-adaptive size — markers already shrink at low zoom and grow at high zoom so they stay readable; this setting nudges the whole range up or down. Default is Normal (1.0×).

### Start with rotation locked
- **Off** (default) — two-finger rotation gestures work from the moment the app opens.
- **On** — rotation is locked at launch; you need to long-press the compass to unlock. Useful if you often accidentally rotate the map and hate the extra step to un-rotate.

## Storage

### Cache usage
Total size of the browse tile cache + per-tile-source breakdown.

### Clear cache
- **Clear all** — removes browse-cached tiles across every style. Does NOT delete your saved offline regions.
- **Clear [specific source]** — per-style clear. Useful if one style is taking a lot of space (e.g., satellite imagery is heavier than contour maps).

Browse tile cache rebuilds as you look at areas with signal. Clearing doesn't hurt data you've explicitly saved via the Maps hub download feature.

## Data

### Backup
Create a ZIP containing tracks, waypoints, saved offline regions, and settings. Optional toggles let you exclude categories (saved maps are the biggest — often left out for quick "just my tracks" backups). See [Backup & restore](backup.md).

### Restore
Open an existing `apexgps-backup-*.zip` file. Choose **Merge** (add to existing) or **Replace** (overwrite existing). See [Backup & restore → Merge vs Replace](backup.md#merge-vs-replace).

### Optimize all tracks
Runs Douglas-Peucker simplification across every imported track. Reduces point counts without visibly changing the track shape. Useful if you've imported lots of heavily-detailed GPX files and the map feels sluggish on an older phone. Shows the total count that'll be touched.

Individual tracks can also be optimized one-at-a-time from the track detail screen.

### Load sample data
Imports 3 example waypoints (Summit / Viewpoint / Trailhead) and 3 tracks of different lengths and elevation profiles (5 km / 12 km / 25 km, with realistic +260 m to +3030 m elevation gain). Useful for exploring what the app can do without needing your own GPX files yet. The samples are just normal tracks/waypoints after import — delete them any time.

## API Keys

### Thunderforest
Required to use the **Outdoors (Thunderforest)** tile style. Free "Hobby" plan: 150,000 tile requests per month, no credit card. Sign up at [thunderforest.com](https://www.thunderforest.com/), copy your API key, paste it here → **Save**.

Without a key, the Outdoors style shows a placeholder; the other five styles work without any key.

## About

**Settings → About** shows the app version, attributions, and contact email — plus the **User Guide**: tappable entries for every chapter of this documentation, bundled with the app so the full guide works offline. Tap a chapter → a reader opens and renders the chapter in-app. Cross-chapter links inside each page are honoured; back arrow returns to the chapter list. A **"View online"** link at the bottom opens the same docs at [apexgps.duttra.de/docs](https://apexgps.duttra.de/docs/) in your browser. For help, contact [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me).

---

**Related:** [FAQ →](faq.md) · [Backup & restore →](backup.md)
