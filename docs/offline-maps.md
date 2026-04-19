---
title: Offline maps — ApexGPS
permalink: /docs/offline-maps/
---

# Offline maps

ApexGPS works without signal if the map tiles for the area are already on your phone. Two ways that happens: automatic caching, and manual pre-downloading.

## Automatic caching

Anywhere you've looked at while you had signal is saved to your phone's tile cache. Re-visit the same area offline → tiles load instantly from cache.

Cache is **per tile-source** — OpenTopoMap and Satellite are separate stores. Looking at an area in OpenTopoMap doesn't help if you switch to Satellite offline.

Cache size shows in **Settings → Storage** with a per-source breakdown.

## Manual pre-download (recommended for trips)

Before heading somewhere without signal, download the region deliberately:

### Pick the area

1. Pan/zoom the map so the area you care about fills the screen.
2. **menu → Maps** → tap **Download new area**.
3. A small preview map shows the current area. Move it around to refine if needed.

### Set the zoom range

A **slider** defines the zoom levels you want cached. Higher zoom = more detail but exponentially more tiles.

- For a **weekend hike**: 10-16 is usually plenty.
- For a **major expedition** / week-long trip: 10-17 or 10-18 if you want maximum detail.
- Zoom 19+ is rarely worth it for outdoors — a lot of tiles, little extra info.

The UI shows the estimated **tile count** and **MB size** as you move the slider. Match against your free storage.

### Download

Tap **Download**. A foreground notification appears; you can leave the app, lock the phone, whatever — the download continues. Progress updates live in the notification and on the Maps hub screen.

To cancel mid-download: go to the Maps hub → the download card has a **Cancel** button. (Pressing the back arrow does NOT cancel — that's intentional so you can browse tracks while tiles download.)

### Current tile source only

The download uses whichever tile source is active when you start it. To cache a different style, switch tile sources first (layers FAB on map screen), then initiate.

## Saved regions (menu → Maps → Saved offline maps)

Every completed download shows here. Tap a region to open its detail screen:

- **Name** — editable. Default is based on the country/region geocoded from the bounding box.
- **Tile source**, **zoom range**, **tile count**, **size on disk**.
- **Show on map** — closes the detail and zooms to the region's bounding box.
- **Delete** — frees the storage. With confirmation.

Deleting a saved region removes its tile bundle but does NOT affect the general tile cache. The area may still be cached from prior browsing.

## Cache management (menu → Settings → Storage)

- **Total cache size** across all tile sources.
- **Per-source breakdown** — how many MB each style occupies.
- **Clear all cache** — nukes browse-cached tiles for every source. Does NOT delete your saved regions (they're separate files).
- **Clear [specific source]** — only that style's browse cache.

Saved offline regions are managed separately on the Maps hub, not here.

## What uses network on the trail

Even with everything cached, a few things may still try to reach the internet:

- **Switching tile styles** if you haven't cached the new style for that area — tiles will be blank.
- **Thunderforest (Outdoors)** tiles are fetched with your API key over HTTPS.
- Nothing else. Tracks, waypoints, and navigation are fully local.

If your phone has no signal, the **Offline** badge appears in the top bar. This is the device-level signal, not an app-level choice.

## Tips

- **Always pre-download before a trip.** Don't rely on auto-cache — it only covers what you've actually looked at.
- **Two map styles** can be helpful: OpenTopoMap for contours + paths, Satellite for visual reality. Download both for critical areas.
- **Higher zoom = more storage, diminishing returns.** Past zoom 17 the extra detail rarely helps route-finding; it's mostly building shapes and street labels.
- **Check free space before big downloads.** A large region at zoom 18 can easily top 500 MB.

---

**Related:** [The map screen →](map.md) · [Settings →](settings.md) · [Backup & restore →](backup.md)
