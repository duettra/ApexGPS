# FAQ & troubleshooting

## "My blue triangle isn't showing"

Three possible reasons:

1. **GPS isn't on.** Tap the crosshair button in the right-side column. Goes from grey → blue. See [The map screen → Follow-me](map.md#follow-me-crosshair).
2. **Location permission isn't granted.** Go to your phone's Settings → Apps → ApexGPS → Permissions → Location → **Allow only while using the app**, **Precise** location. Then re-open ApexGPS.
3. **No GPS fix yet.** Indoors, near tall buildings, or in a deep canyon, first acquisition can take 30 seconds or more. Step outside if possible.

## "The map keeps dragging back to me every few seconds"

That's the locked follow-me state. Drag the map once — the crosshair button turns a lighter blue and the map will now stay wherever you pan it. The triangle still updates; only the camera stops chasing. To re-centre: tap the crosshair button.

See [The map screen → Follow-me](map.md#follow-me-crosshair).

## "How do I turn off GPS entirely?"

**Long-press** the crosshair button. GPS stops, triangle disappears, battery saved.

Tap-to-toggle from the locked state also turns it off, but a long-press skips the re-centre animation — useful when you've panned away and don't want the map jumping back before turning off.

## "Someone sent me a location link — how do I view it?"

If the link is like `https://apexgps.duttra.de/loc?lat=...&lon=...`, tap it directly from your message. With ApexGPS installed, it opens in-app with a red bullseye marker. Without ApexGPS, it opens a web page with a map preview + a link to install.

Other types of map links (Google Maps URLs, etc.) open in whatever maps app you prefer — they don't tie into ApexGPS.

See [Share → Receiving a shared location](share-and-navigate.md#receiving-a-shared-location).

## "Can I record a new track while hiking?"

Not in this version. Live track recording (your path as you walk) is planned for a future release. Right now tracks come from importing GPX files (yours from another app, or someone else's).

## "How much storage does the app use?"

The app itself is small (~10 MB). Storage grows based on:

- **Browse tile cache** — tiles from the areas you've looked at. See **Settings → Storage** for size.
- **Saved offline regions** — tiles you've explicitly pre-downloaded via Maps hub. These can be large (50-500 MB per region depending on zoom levels).
- **Tracks + waypoints** — tiny, usually <1 MB even with hundreds of items.

Clear browse cache via Settings → Storage → Clear. Delete saved regions via Maps hub → tap a region → Delete.

## "The map is slow when I zoom in / pan"

A few things to try:

1. **Too many tracks loaded.** Go to Tracks list → filter by visibility → hide the ones you're not using today. Or bulk-delete old imports.
2. **Heavily-detailed tracks.** Use **Settings → Data → Optimize all tracks** to simplify — point counts drop ~90% without visible change.
3. **Low zoom with many waypoints.** Waypoints cluster automatically at low zoom (single dot with a count) — tap a cluster to zoom into it. If your phone is still struggling, the cluster threshold in code is fixed; consider hiding tracks instead.
4. **Old phone.** ApexGPS targets modern Android. If yours is pre-2020, some performance issues are unavoidable with 500+ tracks on screen.

## "I can't see the new version in the Play Store"

You're a closed-testing tester and just got notified there's an update. If it's not appearing:

1. Play Store → profile icon (top right) → **Manage apps & device** → **Updates available** → refresh. If ApexGPS appears, tap **Update**.
2. Still nothing? Open the tester invite link again (the one you first used to join the test). Then force-stop Play Store, re-open, search ApexGPS.
3. Still nothing? **Settings → Apps → Google Play Store → Storage → Clear cache**. Re-open Play Store, search again.
4. Google's CDN rollout takes 2-24 hours after "auto-published." If you just heard about the update, wait a few hours.

## "Can I use ApexGPS without giving it location permission?"

Mostly yes. You can import GPX files, view tracks, plan routes, measure distances, manage waypoints, and pre-download map regions — all without location. What you lose:

- Live position triangle.
- Follow-me / nearest-first sorts.
- The Share location feature (no location to share).
- Navigation-to-target (no "you" to draw a line from).

## "Does the app send my location anywhere?"

No. ApexGPS makes no network requests with your location. The only outbound network activity is fetching map tiles, which is indistinguishable from browsing a map — map servers see an IP + the tile coordinates, nothing about you. See the [privacy policy](/privacy.html).

Sharing via the Share button is entirely user-initiated — you choose the app (WhatsApp, etc.) and recipient.

## "My friend's Android phone opens the shared link in a browser, not in ApexGPS"

The link deep-links into ApexGPS only on devices where the Google-issued App Links verification has completed. Fresh installs sometimes need a first launch of the app before verification kicks in. Have your friend:

1. Open ApexGPS once, grant location permission, close it.
2. Re-tap your shared link.

Now it should open in the app directly. If it still opens in a browser, Android may be offering a chooser — they can pick "Always open in ApexGPS" from the chooser dialog.

## "Can I restore an ApexGPS backup on iPhone?"

No. ApexGPS is Android-only. The backup format is specific to the app.

## "Where is my data stored physically?"

On your phone, in ApexGPS's private app storage (`/data/data/com.apexgps.app/` on rooted access — otherwise not directly reachable). Tracks + waypoints live in a SQLite database; settings in a preferences file; tiles as image files on disk.

Nothing is uploaded anywhere. To back up, use [Backup & restore](backup.md).

---

**Still stuck?** [sandwalker.one@proton.me](mailto:sandwalker.one@proton.me) — bug reports welcome.
