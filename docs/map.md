# The map screen

Everything revolves around this view. Here's what each control does.

## Gestures

| Gesture | Effect |
|---|---|
| One-finger drag | Pan the map. |
| Pinch | Zoom in / out. |
| Two-finger twist | Rotate the map. |
| Single tap on a track | Open the track overlay (elevation profile, scrubber). |
| Single tap on a waypoint | Open the waypoint overlay (name, description, edit button). |
| Single tap on the blue triangle (your position) | Open the **Share location** panel. |
| Long-press on empty map | Add a waypoint at that point. |

## Top-right: the compass

A round chip with a red needle. Always visible. The needle always points to true north regardless of how the map is rotated, so it also works as a permanent north indicator.

- **Tap** — smoothly rotates the map back to north-up.
- **Long-press** — toggles rotation lock. When the chip is **blue**, two-finger rotation gestures are ignored; the map stays at its current orientation. Long-press again to unlock.

A lock-at-launch option lives in **Settings → Appearance → Start with rotation locked** for users who never want to rotate the map.

## Right-side column: the action buttons

From top to bottom:

### Measure distance
The **ruler icon**. Tap to enter measure mode; tap on the map to drop pins; a line connects them and the bottom stats bar shows the total distance. Drag pin A onto your GPS position to measure "from me." Tap the icon again to exit.

### Map layers
The **layers icon**. Six styles to pick from: OpenTopoMap (default, hiking focus), OSM Standard (clean general-purpose), ESRI Topo, ESRI Shaded Relief, Satellite, Outdoors (Thunderforest — requires a free API key from Settings → API Keys).

The chosen style is remembered across app restarts.

### Follow-me (crosshair)
Three states — the button colour tells you which:

| State | Colour | Behaviour |
|---|---|---|
| **Off** | Grey | GPS off, no blue triangle on the map. |
| **On, locked** | Blue (filled) | GPS on, triangle visible, map re-centres on you every few seconds. |
| **On, unlocked** | Faded blue | GPS on, triangle still updating, but the map stays where you panned. |

- Tap from **Off** → turns GPS on + locks the camera to you.
- Tap from **Locked** → turns GPS off.
- **Drag the map** while locked → auto-switches to unlocked. Triangle keeps updating; map holds its position.
- Tap from **Unlocked** → re-centres + re-locks.
- **Long-press** on any on-state → turns GPS off instantly (skips the re-centre animation).

### Where did the Import (+) button go?

As of **v1.25.2** the map no longer has a dedicated import FAB — importing GPX now lives in the Tracks and Waypoints list screens. See [Tracks](tracks.md#importing) or [Waypoints](waypoints.md#adding-a-waypoint).

## Top-left

- **☰ menu** — nav drawer (Tracks, Waypoints, Maps, Settings).
- **Panic button** — a red ⚠ chip, only if you've enabled it in **Settings → Appearance → Panic button**. Tap opens the Share location panel (starts GPS automatically if it wasn't already on).

## Bottom stats bar

Three numbers:

- **SPEED** — current km/h from GPS.
- **ELEV** — current elevation in metres.
- **DIST** — context-dependent:
  - In **measure mode**: total length of the measure line.
  - During **navigation to a shared location**: live distance to the target (shown in blue when it's auto-updating).
  - Otherwise: blank.

## Offline indicator

If your device has no network, a small red **"Offline"** chip appears in the top bar. Cached tiles still display; tiles you haven't seen before won't load until you're back online. See [Offline maps](offline-maps.md) to pre-download regions.

---

**Related:** [Tracks →](tracks.md) · [Waypoints →](waypoints.md) · [Share your location →](share-and-navigate.md)
