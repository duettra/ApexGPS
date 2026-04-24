# Share your location & navigate to a target

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

Top data row: **Distance** (blue) · **ETA** · **Speed** · **Elevation**.

Central analog-style dial:
- Outer ring with tick marks every 15° (major ticks every 30°).
- **N / E / S / W** labels on the card.
- A small **red triangle** marks true north on the card.
- A **blue needle** (triangle) points at the target in real-world direction.
- **Centre badge** shows the phone's current heading (`245°`), or the letter **S** with a *"Simulated Heading"* caption when the phone's compass sensor is unreliable (near metal, strong magnets, or needing a figure-8 calibration waggle).

Bottom data row: **Lat · Lon · Bearing° + cardinal · ±Accuracy**.

At the bottom: **Stop navigation** (full-width, ends nav entirely).

### Using it

The compass dial **rotates with your phone's orientation** so the red triangle always points to real-world north regardless of how you're holding the phone. Point the top of the phone at the blue needle's direction to face the target.

When the sensor is fully reliable the centre badge shows the heading in degrees; otherwise it falls back to a stylised "S" and labels itself *Simulated Heading* — a reminder that the direction might drift.

### What happens to the bottom stats bar

While the compass is open, the usual SPEED / ELEV / DIST stats bar at the bottom of the map is **hidden** — the compass's own top panel already shows those numbers in larger type, so duplicating them below would be noisy. The stats bar re-appears the moment you drag the compass down.

### What the nav strip shows when the compass is closed

When the compass is minimised, the navigation strip at the bottom reads:

> *Navigating · **045° NE** · ETA 12 min · 🧭 · Stop*

The bearing and cardinal are in **blue** because they update with every GPS fix. ETA is an estimate based on your current walking / moving speed — shows `--` when you're stationary. Distance isn't shown on the strip any more; it's in the bottom stats bar's **DIST** field (also blue while navigating).

---

**Related:** [The map screen →](map.md) · [Settings →](settings.md) · [FAQ →](faq.md)
