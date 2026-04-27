# Waypoints

A **waypoint** is a named point on the map — a trailhead, a summit, a good photo spot, a cabin, the place the car is parked. Each one has a name, a colour, and one of 32 symbols.

## Adding a waypoint

### At a specific place (long-press the map)

Long-press on the map where you want the waypoint. A sheet slides up with:

- **Name** — optional. Defaults to "Waypoint" if you leave it blank.
- **Notes** — optional description.
- **Latitude / Longitude** — auto-filled from the tapped point; **editable** if you want to tweak them.
- **Elevation (m)** — optional. Leave blank if unknown; fill in when you want the waypoint to carry a specific altitude (e.g. a summit height you looked up). Tap the small **download icon** on the right side of the field to fetch elevation from a worldwide terrain model (~30 m accuracy) using the typed Lat/Lon — handy when you're typing coordinates by hand. Greyed out until both Lat and Lon parse to valid numbers; brief spinner while fetching; a "Couldn't fetch elevation" toast if you're offline.
- **Symbol** — pick from 32 icons.
- **Colour** — 16-colour palette.
- **Save** / **Cancel**.

### By typing coordinates

Open **menu → Waypoints** → tap the blue **+** FAB at the bottom-right. Same sheet as above, but the Lat / Lon fields start empty. Type coordinates (or paste a `lat, lon` string into the Latitude field — the app auto-splits into both fields).

### By importing a GPX file

Open **menu → Waypoints** → tap the blue **folder icon** FAB at the bottom-right. Pick one or more `.gpx` files. Any waypoints inside the files are imported. Duplicates (same name, within ~11 m) are skipped automatically.

### At your current location

Turn on GPS (tap the crosshair button if the triangle isn't showing), long-press on the triangle itself (or anywhere very close to it), and the dialog opens pre-positioned at your fix.

### From an imported GPX (via share / open-with)

GPX files opened from another app (WhatsApp attachment, Gmail, file manager) also import their waypoints automatically. If the GPX has no name for a waypoint (some exporters drop the coords into the name field), ApexGPS detects that and shows "Waypoint" instead.

## Viewing a waypoint

Tap any waypoint on the map. A panel slides up from the bottom with:

- Icon + name.
- Coordinates (lat/lon to 6 decimals).
- Elevation (if set).
- Distance from your current GPS position (blue — live).
- Description (if you entered one).
- **Navigate** button (walking person, blue) — starts straight-line navigation to this waypoint. See below.
- **Share** button — sends the waypoint via WhatsApp / SMS / email. The recipient gets a text with the name, coords, elevation, and two links (ApexGPS App Link + Google Maps). If they also have ApexGPS installed, tapping the link opens the app directly with a red bullseye marker at the spot — they can Save it as their own waypoint.
- **Edit** button.

Dismiss by swiping down.

## Navigate to a waypoint

Tap the **Navigate** icon (walking person, primary-tinted) in the waypoint overlay. The overlay closes and:

- A **light-blue dotted line** draws from your live GPS position to the waypoint.
- The bottom bar becomes: *"Navigating · 0.42 km · 045° NE · [Stop]"* — distance updates live (blue when auto-updating), bearing is in degrees + a cardinal direction (N, NE, E, SE, S, SW, W, NW).
- The **DIST** field in the bottom stats row also shows this live distance in blue.
- Auto-stops when you're within **20 metres** of the waypoint ("Arrived" toast).
- Tap **Stop** to end navigation manually at any time. The waypoint is still there — tap it to reopen the overlay.

This is the same go-to mode that shared locations use. Straight-line bearing, not turn-by-turn — for hiking off-trail it's usually what you want.

Tap the waypoint again anytime during navigation to reopen the overlay (navigation continues in the background).

## Editing a waypoint

Tap the waypoint → **Edit** in the overlay, or open **menu → Waypoints** and tap a row.

Same sheet as when adding. Name, Notes, **Latitude**, **Longitude**, **Elevation**, Symbol, Colour are all editable. On Save, the app validates the coordinates (lat ∈ [−90, 90], lon ∈ [−180, 180], both must be numbers) and shows an inline red error if they're out of range. The download icon inside the Elev field re-fetches elevation from the terrain model — useful after dragging a waypoint to a new spot or after correcting Lat/Lon.

## Moving a waypoint

**Long-press-and-drag** the waypoint on the map. Drag it to the new position. When you let go, a bar appears at the bottom:

- **Move** — commits the new position.
- **Cancel** — snaps it back to where it was.

Nothing is saved until you press Move. Useful if the drag was an accident.

## The 32 symbols

Grouped by purpose so you can browse them in the picker:

| Group | Symbols |
|---|---|
| **Navigation / generic** | Flag · Place · Star · Favorite |
| **Outdoor / hiking** | Summit · Saddle · Viewpoint · Photo · Forest · Spring · Waterfall · Drinking water · Camp · Shelter · Picnic · Guidepost · Ruins |
| **Informational** | Info · Warning |
| **Services** | Parking · Fuel · Restaurant · Hotel · Hospital · Toilets |
| **Transport** | Car · Bike · Walk · Train · Boat · Plane · Gas |

All 32 are selectable when adding or editing. The symbol is stored with the waypoint and survives export → re-import.

## The Waypoints list (menu → Waypoints)

Every waypoint, with count in the title.

### Filter

**Filter icon** → two sections:

- **Colour** — tap a chip to show only that colour. Tap **Any** to clear.
- **Symbol** — scrollable list of all 32 symbols with their icons. Tap one to filter to only waypoints using that symbol.

Active filters turn the icon blue.

### Sort

**Sort icon**:

- **Newest first** — by import / creation date (default).
- **By name** — alphabetical.
- **Nearest first** — closest to your current GPS location. Shows "(no GPS)" if the phone has no cached fix.

### Search

Type into the search box to filter to waypoints whose name OR description contains your text.

### Select multiple

Long-press a waypoint in the list → selection mode. Tick more, then bulk delete. There's no bulk colour/symbol change for waypoints (yet) — use Edit per waypoint for that.

### Remove duplicates

If you've re-imported the same GPX multiple times with earlier app versions, you may have stacked duplicates (same name at the same coords). Tap the **⋮** overflow → **Remove duplicates**. It keeps the oldest copy of each and deletes the rest; shows how many were removed.

## Deleting

Single: swipe / tap the trash icon on a row, or use the Delete button in the edit dialog.

Multiple: selection mode + bulk delete.

No undo. Keep a [backup](backup.md) if you're nervous.

## Showing a waypoint on the map

From the list screen, tap a waypoint → the app navigates back to the map and pans to that waypoint. Follow-me is paused so the pan isn't immediately overridden by the next GPS fix.

---

**Related:** [Tracks →](tracks.md) · [Backup & restore →](backup.md) · [The map screen →](map.md)
