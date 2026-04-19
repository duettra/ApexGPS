---
title: Backup & restore — ApexGPS
permalink: /docs/backup/
---

# Backup & restore

ApexGPS stores everything **locally on your phone**. There's no cloud sync. If you factory-reset, switch phones, or uninstall the app, **your tracks, waypoints, and downloaded offline regions are gone** unless you've made a backup.

Backup is manual but easy. Do it periodically if you have data you'd miss.

## What's in a backup

- **All tracks** (the GPX data, name, colour, visibility).
- **All waypoints** (name, description, coords, elevation, colour, symbol).
- **All saved offline map regions** (the actual tile bundles — can be large).
- **All settings** (theme, default tile source, track width, waypoint size, rotation lock, panic-button visibility).

What **isn't** in a backup:

- The **browse tile cache** (auto-cached tiles from general use). Not backed up because it's easily regenerable and potentially huge. Saved offline regions are backed up; the browse cache is not.
- **Thunderforest API key** is backed up with settings, so you won't have to re-enter it.

## Creating a backup

1. **menu → Settings → Data → Backup**.
2. Optional: uncheck categories you don't want (saved maps are the largest — skip them if you're just backing up tracks/waypoints to save space).
3. Tap **Create backup**.
4. The ZIP file is saved to the app's private storage. A share dialog opens — pick where to put it:
   - **Google Drive / Dropbox / OneDrive** — cloud safekeeping.
   - **Send to yourself** via email / chat.
   - **Save to Downloads** via a file manager.

The ZIP is named like `apexgps-backup-2026-04-19.zip`. Filename includes the date.

**Creating a backup with saved offline regions can take a minute or two** and produces a large ZIP (50-500 MB depending on how many regions). The UI shows progress.

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

Restore runs as a streaming read — it should be fast even for a multi-hundred-MB ZIP. If it fails mid-way, partial categories may have been applied; re-run to be safe.

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
