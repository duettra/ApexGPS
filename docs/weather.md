# Weather

ApexGPS can show current conditions, an hour-by-hour outlook, and a 7-day outlook for any point you care about.

## What you'll see

Weather is **on by default** as of 1.32.2. As soon as you have a GPS fix:

- A small chip appears above the stats bar showing the conditions at your current location.
- Tapping a waypoint shows a "Weather here" line on the waypoint panel.
- Tapping either surface opens a sheet with the full breakdown.

When weather is on, your latitude / longitude is sent to Open-Meteo (a free public weather API) for each forecast lookup. If you'd rather no network calls leave the app, open **Settings → Weather** and switch off **Show weather** — the chip and "Weather here" line disappear and ApexGPS stops contacting Open-Meteo.

## What the chip shows

The chip rotates between a few states:

| State | Looks like | Meaning |
|---|---|---|
| Fresh | `☼ 24° · 12 km/h NE` | Updated within the last 15 minutes. |
| Aging | `… · 32 min ago` | More than 15 minutes old, but still likely accurate. |
| Stale / offline | `⚠ … · 2h ago` (greyed) | More than an hour old or no connectivity. Tap the chip to refresh manually. |

The chip never disappears once weather is on — it just changes its appearance to tell you how trustworthy the data is.

## The forecast sheet

Tap the chip (or the "Weather here" line on a waypoint) to open the full sheet. Top-to-bottom it shows:

- **Now** — large weather emoji + temperature, "feels like", and a row each for wind / humidity + max precip / dewpoint + UV / pressure + sunset.
- **Next 24 hours** — eight icons every 3 hours (sun-side or moon-side depending on the local sunrise / sunset for that hour) with the hourly temperature.
- **Pressure trend** (green) — 24-hour line chart, useful for spotting an approaching front.
- **Humidity trend** (light blue) — 24-hour line chart.
- **Next 7 days** — a row of weekday icons with the day's high / low temperature.

There's a refresh button (↻) in the sheet header that bypasses the cache and fetches fresh data. If you're offline, the previous data stays on screen and the chip's stale indicator stays visible.

## Elevation-aware forecasts on peaks

If a waypoint has a stored elevation (entered manually, set from GPS, or imported from a GPX with `<ele>`), that elevation is sent to Open-Meteo so the model knows it's a summit and not a valley point at the same lat / lon. The same applies to the chip: it uses your GPS altitude. On a 1500 m peak this typically corrects the forecast temperature by ~9 °C compared to a coordinates-only lookup.

## Auto-refresh

When weather is enabled, the chip updates every 15 minutes while the app is open and online. If you're in airplane mode the chip stays put with the last known data and a "stale" indicator until you reconnect.

## Data sources

Forecasts come from **[Open-Meteo](https://open-meteo.com)**, a free public API that blends ECMWF, GFS, ICON and other top-tier global models. Free for personal use, no account, no API key.

## Limitations

- **Convective rain in arid regions** is hard to predict for any model. Expect occasional misses on flash-flood thunderstorms in places like the UAE Hajar mountains. The probability number is honest about this, but localised events can land off-grid.
- **Severe-weather alerts** are not part of this feature. ApexGPS doesn't broadcast push notifications when storms approach.
- **Route weather** isn't supported — forecasts are point lookups, not "what's the weather along this trail in 2 hours". You can tap individual waypoints along a route to spot-check.
