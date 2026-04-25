# Weather

ApexGPS can show current conditions, an hourly forecast, and a 7-day outlook for any point you care about, plus animated precipitation radar and cloud-satellite layers on the map. Everything is opt-in.

## Turning weather on

Open **Settings → Weather** and switch on **Show weather**. Once enabled:

- A small chip appears above the stats bar showing the conditions at your current GPS location.
- Tapping a waypoint shows a "Weather here" line on the waypoint panel.
- Tapping either surface opens a sheet with the full breakdown.

The default is **off** so the app doesn't send your location to a third-party service unless you ask. When you enable it, your latitude/longitude is sent to Open-Meteo (a free public weather API) for each forecast lookup.

## What the chip shows

The chip rotates between a few states:

| State | Looks like | Meaning |
|---|---|---|
| Fresh | `☼ 24° · 12 km/h NE · 38%` | Updated within the last 15 minutes. |
| Aging | `… · 32 min ago` | More than 15 minutes old, but still likely accurate. |
| Stale / offline | `⚠ … · 2h ago` (greyed) | More than an hour old or no connectivity. Tap the chip to refresh manually. |

The chip never disappears once weather is on — it just changes its appearance to tell you how trustworthy the data is.

## The forecast sheet

Tap the chip (or the "Weather here" line on a waypoint) to open the full sheet:

- **Now** — temperature, "feels like", wind speed/direction/gusts, humidity, cloud cover, pressure, UV index, sunset.
- **Next 24 hours** — a chart with temperature as a line and precipitation as bars.
- **Next 7 days** — a row of weekday icons with the day's high/low temperature.

There's a refresh button (↻) in the sheet header that bypasses the cache and fetches fresh data. If you're offline, the button briefly shows "No connection — showing last cached data" and the previous data stays on screen.

## Map overlays

The Maps hub (☰ → Maps) has an **Overlays** section with two independent toggles:

- **Precipitation radar** — animated rain layer in colour-coded blue → green → yellow → red, covering the past 2 hours plus a 30-minute nowcast. Coverage is global; the network of ground-stations is sparser in some regions (notably the Middle East), so radar fine detail varies.
- **Cloud satellite** — infrared cloud-top layer from geostationary weather satellites, refreshed about every 10 minutes.

Both overlays are tile-only — they don't send your location anywhere. They're independent of the master weather toggle, so you can have radar on the map without enabling per-point forecasts (or vice versa).

## Auto-refresh

When weather is enabled, the chip updates every 15 minutes while the app is open and online. The map overlays refresh in the background as new tiles become available (~every 10 minutes for radar). If you're in airplane mode the chip stays put with the last known data and a "stale" indicator until you reconnect.

## Data sources

Forecasts come from **[Open-Meteo](https://open-meteo.com)**, a free public API that blends ECMWF, GFS, ICON and other top-tier global models. Animated radar comes from **[RainViewer](https://rainviewer.com)**. Both are free for personal use and require no account or API key on your part.

## Limitations

- **Convective rain in arid regions** is hard to predict for any model. Expect occasional misses on flash-flood thunderstorms in places like the UAE Hajar mountains. The probability number is honest about this, but localised events can land off-grid.
- **Severe-weather alerts** are not part of this feature. ApexGPS doesn't broadcast push notifications when storms approach.
- **Route weather** isn't supported — forecasts are point lookups, not "what's the weather along this trail in 2 hours". You can tap individual waypoints along a route to spot-check.
