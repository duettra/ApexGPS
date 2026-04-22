---
title: ApexGPS Privacy Policy
permalink: /privacy.html
---

# ApexGPS Privacy Policy

_Last updated: 2026-04-22_

ApexGPS is a free Android hiking app. This policy explains what data the app reads, where it stays, and who it's shared with.

## Summary

Your location data and everything you create (tracks, waypoints, saved map regions, settings) stays on your device. Nothing is uploaded to ApexGPS servers — we don't operate any.

## What data the app reads

**Device location (precise GPS)** — optional. Read while the app is open for the position marker on the map and for the "follow me" mode. Required only if you want live GPS features; the app works without it for browsing maps and viewing imported tracks.

**GPX files you import** — read from the file you select or share in.

## Where the data goes

**Nowhere external by default.** All tracks, waypoints, saved maps and settings live in the app's local storage. You can export them as a GPX or ZIP file and share with anyone you choose; we never see it.

**On-device storage details.** Tracks and waypoints are stored in a local SQLite database on your device. That database is not encrypted — on a rooted device or if your phone is attached to a debug-enabled computer, the contents are readable. Your Thunderforest API key, if you set one, is stored in an Android Keystore-backed encrypted preferences file (AES-256-GCM). Backup ZIPs you create carry a plaintext copy of the API key so the backup is portable to a new device; keep those ZIPs private.

**Map tile requests** — when you view a map, tiles are fetched over HTTPS from one of these public providers:

- OpenStreetMap / OpenTopoMap (openstreetmap.org, opentopomap.org)
- ESRI (arcgisonline.com)
- Thunderforest (tile.thunderforest.com), only if you configure an API key

Those providers see a standard HTTP request — IP address, User-Agent — as they would for any map on any app. Nothing ApexGPS-specific is sent. Refer to each provider's own privacy policy for their handling.

## Third-party SDKs

- **Google Play Services** (`FusedLocationProviderClient`) is used to read GPS fixes efficiently. It does not collect data from this app.
- **No analytics, no crash reporting, no advertising SDKs.**

## Data retention and deletion

Everything is stored locally. To remove it:

- Per-track / per-waypoint delete inside the app
- Settings → Clear cache (removes cached map tiles only)
- Uninstall the app (removes everything)

## Children's privacy

ApexGPS is not directed at children under 13 and does not knowingly collect any data from them.

## Contact

Issues or questions: **sandwalker.one@proton.me**

## Changes to this policy

If the policy changes, the "Last updated" date above will change. Material changes will be announced in the app release notes.
