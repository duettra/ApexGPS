---
title: Share & navigate — ApexGPS
permalink: /docs/share-and-navigate/
---

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

## Panic button (optional)

**What it is:** a red ⚠ chip at the top-left of the map, mirroring the compass at the top-right. One tap → opens the Share location panel instantly.

**Enable it:** Settings → Appearance → Panic button → toggle **On**. Hidden by default because most users don't need it.

**What it does when pressed:**

- Opens the same Share location panel as tapping the blue triangle.
- **Auto-starts GPS** if it's not already running, so you don't hit "Acquiring GPS…" deadlock in an actual emergency.
- Does not directly share — you still have to tap **Share** on the panel. This is deliberate: a pocket-press shouldn't send your location to anyone without a confirmation.

It's a **shortcut**, not a different feature. Think of it as "skip finding the triangle, just get me to the share sheet."

---

**Related:** [The map screen →](map.md) · [Settings →](settings.md) · [FAQ →](faq.md)
