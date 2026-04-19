---
title: Waypoints — ApexGPS
permalink: /docs/waypoints/
---

# Waypoints

A **waypoint** is a named point on the map — a trailhead, a summit, a good photo spot, a cabin, the place the car is parked. Each one has a name, a colour, and one of 32 symbols.

## Adding a waypoint

### At a specific place

Long-press on the map where you want the waypoint. A dialog opens:

- **Name** — optional. Defaults to "Waypoint" if you leave it blank.
- **Description** — optional notes.
- **Symbol** — pick from 32 icons (see list below).
- **Colour** — 16-colour palette.
- **Elevation** — auto-filled from the GPS if available; editable.
- **Save** / **Cancel**.

### At your current location

Turn on GPS (tap the crosshair button if the triangle isn't showing), long-press on the triangle itself (or anywhere very close to it), and the dialog opens pre-positioned at your fix.

### From an imported GPX

GPX files often contain waypoints alongside tracks. They're imported automatically when you open the GPX. If the GPX has no name for a waypoint (some exporters drop the coords into the name field), ApexGPS detects that and shows "Waypoint" instead.

## Viewing a waypoint

Tap any waypoint on the map. A panel slides up from the bottom with:

- Icon + name.
- Coordinates (lat/lon to 6 decimals).
- Elevation (if set).
- Distance from your current GPS position (blue — live).
- Description (if you entered one).
- **Edit** button.

Dismiss by swiping down.

## Editing a waypoint

Tap the waypoint → **Edit** in the overlay, or open **menu → Waypoints** and tap a row.

The same dialog as when adding — change any field, Save.

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
