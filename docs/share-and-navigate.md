# Share your location, tracks & waypoints — and navigate to a target

## Sharing your current location

### The quick version

1. Make sure GPS is on (crosshair button → blue triangle appears).
2. Tap the **blue triangle** on the map.
3. A panel slides up with your info. Tap **Share**.
4. Pick WhatsApp, SMS, email, whatever. Send.

### What the panel shows

```
Elevation 145 m · ±5 m · 19:42
Battery 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717
Google Maps: https://maps.google.com/?q=25.165183,55.409717
```

- **Elevation** — metres above sea level from the GPS (drops if the phone couldn't determine it).
- **±accuracy** — how confident the GPS is about your position, in metres. Trees, buildings, deep canyons increase this.
- **Time** — when this fix was taken.
- **Battery** — so the recipient knows whether you're running out.
- Two **URLs** — the first opens in ApexGPS (if the recipient has it installed), the second opens in any maps app.

### What the recipient sees

The outgoing message adds a greeting before the details:

```
Hello, this is my current location.

Elevation 145 m · ±5 m · 19:42
Battery 87%
ApexGPS: https://apexgps.duttra.de/loc?lat=...
Google Maps: https://maps.google.com/?q=...
```

On WhatsApp and similar apps, both URLs become tappable links. On SMS they're still copyable text.

### If there's no GPS fix yet

The panel opens but shows "Acquiring GPS…" and the Share button is disabled. As soon as the first fix lands, the panel updates and Share enables — you don't need to close and re-open.

## Sharing tracks & waypoints

ApexGPS lets you send your tracks and waypoints to anyone as standard `.gpx` files — open them in GaiaGPS, Strava, Garmin BaseCamp, wikiloc, or another copy of ApexGPS. Three paths into it:

### Single track or single waypoint

- **Track** — tap a track on the map → **Share** button on the overlay. Or open the track detail screen (Tracks → tap a row) → top-bar **share icon**.
- **Waypoint** — tap a waypoint on the map → **Share** button on the overlay. The recipient sees a text message with the name, coords, elevation, and two links (ApexGPS App Link + Google Maps).

### Bulk share from the list screens

Open **menu → Tracks** (or **Waypoints**), long-press a row to enter selection mode, tick the ones you want, then tap the **share icon** in the top bar:

- Tracks → bundles every selected track into a single `.gpx` file.
- Waypoints → bundles every selected waypoint into a single `.gpx`.

A share dialog opens — pick WhatsApp, Drive, Gmail, whatever. The filename includes the date.

### Share everything visible right now ("Share visible")

The fastest path when you want to hand someone "the whole area I'm looking at." Three entry points, all funnel into the same sheet:

- **Map screen → share icon** in the top bar (left of the ☰ menu). Uses your live map viewport.
- **menu → Maps → Share visible tracks & waypoints** (third card on the Maps hub, below Download / Saved offline maps). Uses the viewport you had open just before entering the hub — so you can scroll up, find the area, then jump in.
- **Map's ⋮ overflow menu → Share visible tracks & waypoints**.

A sheet slides up listing every visible track (lines that intersect the viewport AND are toggled visible) and every visible waypoint (inside the viewport bounds). Each row has a checkbox — **untick anything you don't want to send**. The default filename is geocoded from the viewport centre ("ApexGPS-Wadi-Bani-Khalid-2026-05-14.gpx" if the geocoder resolves; "ApexGPS-2026-05-14.gpx" if you're offline or it returns nothing).

Tap **Share** → a single `.gpx` file is built containing all the selected tracks + waypoints + a small metadata header, then the system share dialog opens.

#### Size limits

A "Share visible" bundle is held in memory while it's being built, so very large selections can fail with a clear toast:

| Limit | Cap |
|---|---|
| Tracks per bundle | 100 |
| Waypoints per bundle | 1,000 |
| Total track points (across all selected tracks) | 100,000 |

If you hit a cap, the toast tells you which one — reduce your selection in the sheet (untick a few large tracks), or use **Settings → Data → Backup** for very large exports (that path streams the ZIP and isn't bounded by these limits).

## Receiving a shared location

Someone sends you an `apexgps.duttra.de/loc?...` link.

### If you have ApexGPS installed

Tap the link → **ApexGPS opens directly**, the map pans to their spot, and a red bullseye marker appears there. A bar slides up at the bottom with three buttons:

- **Navigate** — start go-to mode (see below).
- **Save** — add this spot as a waypoint (you pick the name, colour, symbol).
- **Dismiss** — clear the marker, do nothing.

### If you don't have ApexGPS

Tap the link → opens a simple web page with a map preview of the location plus:

- **Open in ApexGPS** button (Android only; prompts to install if you don't have it).
- **Open in Google Maps** button.

## Navigate to a shared location

After tapping a shared link, tap **Navigate** on the bottom bar:

- A **light-blue dotted line** draws from your live position to the target.
- The bar changes to: *"Navigating · 0.42 km · 045° NE · [Stop]"*.
  - Distance updates on every GPS fix, shown in **blue** to indicate it's auto-updating.
  - **Bearing** is in degrees + one of eight cardinal directions (N, NE, E, SE, S, SW, W, NW) — walk in that direction.
  - The same distance also appears in the **DIST** field of the bottom stats bar, in blue, while navigation is active.
- When you get within **20 metres** of the target, navigation auto-stops with an "Arrived" message.
- **Stop** ends navigation manually at any time. The bullseye marker stays; you can **Navigate** again or **Save** it as a waypoint.

This is straight-line bearing — not turn-by-turn. For hiking off-trail it's usually what you want; in a city, prefer opening the Google Maps link for street routing.

### Also works for your own waypoints

The same go-to mode also starts from any waypoint on the map. Tap a waypoint → the **Navigate** icon (walking person) in its overlay → the waypoint overlay closes and the navigation strip takes over. Covered in detail in [Waypoints → Navigate to a waypoint](waypoints.md#navigate-to-a-waypoint).

## The navigation compass (full-screen)

While navigating to a target, a small **compass icon** 🧭 appears on the navigation strip, left of Stop. Tap it to open a full-screen compass view. Drag the sheet down to minimise back to the strip.

### Layout

Top data row: **Distance** (blue) · **ETA** · **Speed** · **Elevation**. The **ETA turns green** while you're actually closing in on the target, and turns **red and reads "away"** when you're heading away from it (or straight sideways) — so a shrinking time never fools you into thinking you're making progress when you aren't.

Central analog-style dial:
- Outer ring with tick marks every 15° (major ticks every 30°).
- **N / E / S / W** labels on the card.
- A small **red triangle** marks true north on the card.
- A **blue needle** (triangle) points at the target in real-world direction.
- **Centre badge** shows the phone's current heading (`245°`), or the letter **S** with a *"Compass uncalibrated — wave your phone in a figure-8"* caption when the phone's compass sensor is unreliable (near metal, strong magnets, or simply needing calibration).

Bottom data row: **Lat · Lon · Bearing° + cardinal · ±Accuracy**.

At the bottom: **Stop navigation** (full-width, ends nav entirely).

### Using it

The compass dial **rotates with your phone's orientation** so the red triangle always points to real-world north regardless of how you're holding the phone. Point the top of the phone at the blue needle's direction to face the target. The dial now glides smoothly as you turn, and points to **true** north (not magnetic).

**While moving fast (driving, above ~10 km/h)** the dial follows your **direction of travel** from GPS instead of the phone's compass — in a car the magnetic compass is thrown off by the metal body and the mount, and a propped-up phone isn't pointing where the car is going, so GPS travel direction is the trustworthy heading. On foot / standing still it uses the phone's compass as before.

When the compass sensor is unreliable the centre badge falls back to a stylised "S" and prompts you to **calibrate: wave the phone in a figure-8**. You can do this **anytime — even while navigating** (it's a built-in Android gesture, nothing to press); within a second or two the badge returns to a live degree reading. Do it **clear of metal and electronics** (a laptop, the car, a metal desk) for a good result — calibration fixes the phone's own bias, not the room's. This is also why the compass is an outdoor tool: indoors, building steel and a weak GPS fix make both the heading and the target direction unreliable, calibrated or not.

### What happens to the bottom stats bar

While the compass is open, the usual SPEED / ELEV / DIST stats bar at the bottom of the map is **hidden** — the compass's own top panel already shows those numbers in larger type, so duplicating them below would be noisy. The stats bar re-appears the moment you drag the compass down.

### What the nav strip shows when the compass is closed

When the compass is minimised, the navigation strip at the bottom reads:

> *Navigating · **045° NE** · ETA 12 min · 🧭 · Stop*

The bearing and cardinal are in **blue** because they update with every GPS fix. ETA is an estimate based on your current walking / moving speed — shows `--` when you're stationary, and reads **"away"** when you're actually heading away from the target. Distance isn't shown on the strip any more; it's in the bottom stats bar's **DIST** field (also blue while navigating).

---

**Related:** [The map screen →](map.md) · [Settings →](settings.md) · [FAQ →](faq.md)
