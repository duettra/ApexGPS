# Backup & restore

ApexGPS stores everything **locally on your phone**. There's no cloud sync. If you factory-reset, switch phones, or uninstall the app, **your tracks, waypoints, and downloaded offline regions are gone** unless you've made a backup.

Backup is manual but easy. Do it periodically if you have data you'd miss.

## What's in a backup

- **All tracks** (the GPX data, name, colour, visibility, activity tag).
- **All waypoints** (name, description, coords, elevation, colour, symbol).
- **All saved offline map regions** — see [Recipe vs full tiles](#recipe-vs-full-tiles) below for two ways to back these up.
- **All settings** (theme, default tile source, track width, waypoint size, rotation lock, battery saver, etc.).

What **isn't** in a backup:

- The **browse tile cache** (auto-cached tiles from general use). Not backed up because it's easily regenerable and potentially huge.
- **Thunderforest API key** is backed up with settings, so you won't have to re-enter it.

## Creating a backup

1. **menu → Settings → Data → Backup**.
2. Pick what to include — there are checkboxes for tracks / waypoints / settings, plus a **three-way picker for offline map regions** (see below).
3. Tap **Create backup**.
4. The ZIP file is saved to the app's private storage. A share dialog opens — pick where to put it:
   - **Google Drive / Dropbox / OneDrive** — cloud safekeeping.
   - **Send to yourself** via email / chat.
   - **Save to Downloads** via a file manager.

The ZIP is named like `apexgps-backup-2026-05-14.zip`. Filename includes the date.

### Recipe vs full tiles

For saved offline map regions, you pick **one of three modes**:

| Mode | Size | Behaviour | Cross-platform? |
|---|---|---|---|
| **None** | smallest | Region rows aren't backed up at all. | n/a |
| **Recipe** | ~80 KB total | Each region is backed up as a short "instructions card" — name, bounding box, zoom range, tile source. On restore the regions appear in **Maps → Saved offline maps** marked *"Not downloaded yet · X tiles"*, with a **Download** button to fetch the actual tiles from the tile server. | **Yes** — works between Android and iOS. |
| **Full tiles** | 50–500 MB | Each region's actual MBTiles bundle is embedded in the ZIP. On restore the regions are immediately usable offline; no re-download needed. | **Android-only.** iOS can't read the embedded bundles (yet). |

**Pick Recipe** for cross-device moves (phone replacement, sharing a backup with a friend on iOS, or a "just in case" backup you'll keep on Drive forever). The re-download is fast over Wi-Fi and uses your most current tiles.

**Pick Full tiles** if you specifically want a one-step offline-restorable backup on Android only — useful before a trip where you might wipe your phone and not have Wi-Fi at the destination.

**Creating a Full tiles backup can take a minute or two** and produces a large ZIP. The UI shows progress.

## Restoring a backup

### The easy way

Tap an `apexgps-backup-*.zip` file in any file manager / Google Drive / Gmail attachment. Android offers apps that can open it; pick ApexGPS. The app opens directly to Settings → Data with a restore dialog.

### Via Settings

1. **menu → Settings → Data → Restore**.
2. Pick the ZIP from the file picker.
3. Choose a mode (see below).
4. Confirm.

### Merge vs Replace

Both modes work through the ZIP one category at a time.

| Mode | What happens |
|---|---|
| **Merge** | New items from the backup are ADDED to what's already in your app. Tracks with the same name aren't collapsed — you may end up with duplicates; use **Settings → Data → Optimize all** or the per-track delete to clean up. |
| **Replace** | Every category in the backup REPLACES what you currently have. If the backup includes tracks, all your existing tracks are deleted first. Unchecked categories during backup creation are NOT touched during restore. |

**Rule of thumb:**

- Moving to a new phone → **Replace** (you want the exact state from the old phone).
- Pulling a waypoint set from a friend's backup → **Merge** (keep your own data, add theirs).

Restore runs as a streaming read — it should be fast even for a multi-hundred-MB ZIP. While it runs, a progress bar + "Restoring track N of M…" / "Restoring waypoint N of M…" caption appears under the Restore button so you can see how far it has to go. If it fails mid-way, partial categories may have been applied; re-run to be safe.

### Recipe-mode restore — downloading the regions back

If the backup used **Recipe** mode for offline maps, restore is instant but you'll see the regions in **Maps → Saved offline maps** marked *"Not downloaded yet · X tiles"* with a **Download** button. Tap it to re-fetch the tiles from the tile server. If the region uses Thunderforest tiles and you haven't pasted your API key yet, the app shows a one-time toast telling you to add it first under **Settings → API Keys**; once the key is there, tap Download again.

### Restoring across app versions

A v2 backup (created on this version or newer) refuses to open on older app versions and shows *"Backup format v2 is newer than this app supports. Please update ApexGPS."* — update first, then restore. Older v1 backups still restore on the current app with no extra step.

## Moving to a new phone

1. **On the old phone:** Create a backup including everything (all categories ticked). Send to yourself via email / save to Drive.
2. **On the new phone:** Install ApexGPS, open it, grant permissions, sign into your email / Drive.
3. **Download the ZIP** to the new phone, tap it → restore with **Replace**.

Done. Your tracks, waypoints, saved maps, and settings are all there.

## Factory-reset / uninstall protection

Android's Auto-Backup restores a *slice* of your settings (theme, default tile source, API key, track width, waypoint size, rotation lock) from Google Drive when you reinstall. That does NOT include tracks, waypoints, or offline regions — only lightweight preferences.

**The only reliable way to preserve your hiking data across a reinstall is a ZIP backup.** Make one before any phone change or major OS update.

---

**Related:** [Settings →](settings.md) · [Tracks →](tracks.md) · [Waypoints →](waypoints.md)
