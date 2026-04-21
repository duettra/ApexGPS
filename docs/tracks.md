---
title: Tracks — ApexGPS
permalink: /docs/tracks/
---

# Tracks

A **track** is a recorded path — a sequence of GPS points connected as a line on the map. You get tracks by importing GPX files (from GaiaGPS, Strava, Garmin Connect, wikiloc.com, or anything else that exports GPX).

**Note:** ApexGPS does not record new tracks itself in this version. Live recording is planned for a future release.

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

Tap the **filter icon**. Two options:

- **Visibility** — All / Visible only / Hidden only. Tracks you've hidden via the visibility toggle still exist in the list but don't draw on the map.
- **Color** — 16-colour palette. Tap a colour chip to see only tracks of that colour.

Active filter turns the icon blue. Tap **Any** in either section to clear.

### Sort

Tap the **sort icon**:

- **Newest first** — by import date (default).
- **By name** — alphabetical.
- **Nearest first** — closest centre-point to your current location. Uses your phone's last-known GPS fix so it works even if you haven't turned on GPS in ApexGPS this session. Shows "(no GPS)" if location permission is denied or there's no cached fix.
- **By points** — tracks with the most points first (useful for picking out heavily-detailed tracks vs simple routes).

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

- **Name** — editable.
- **Colour** — tap to open colour picker.
- **Visibility** — show / hide on the map.
- **Elevation profile** — the same chart as the map overlay, but full-size.
- **Ascent / descent** totals.
- **Point count** — how many GPS samples make up this track.
- **Show on map** — closes the detail and zooms the map to fit the track.
- **Optimize** — simplify the track by dropping redundant points. Useful for importing huge overly-detailed exports. Non-destructive; you can re-import to get the original back.
- **Share as GPX** — same as the map overlay's share button.
- **Delete** — with confirmation.

## Bulk optimize (for heavy libraries)

If you've imported many extremely dense tracks, the map can feel sluggish on older phones. **Settings → Data → Optimize all tracks** runs the same simplification across every track at once. There's a count in the Settings UI so you know how many will be touched.

## Deleting

Single: swipe / tap the trash icon on any track row, or use the Delete button on the detail screen.

Multiple: selection mode + bulk delete.

There's no undo. Keep a [backup](backup.md) if you're nervous.

---

**Related:** [Waypoints →](waypoints.md) · [The map screen →](map.md) · [Backup & restore →](backup.md)
