# ApexGPS — Public Web Repo Contents

This folder is the source for the public GitHub Pages site that serves:

- `apexgps.duttra.de/.well-known/assetlinks.json` — Android App Links verification
- `apexgps.duttra.de/loc?lat=…&lon=…` — shared-location landing page (deep-links into ApexGPS, falls back to a web map preview)
- `apexgps.duttra.de/privacy.md` — copy of the privacy policy (rendered by GitHub Pages Jekyll front-matter)

The original `duettra/apexgps-privacy` repo is **kept as-is** so the existing Play Store privacy URL stays valid until you choose to switch it.

---

## One-time setup

### 1. Rename the private repo on GitHub
GitHub repo names are unique per account, and we want the new public repo to claim the clean name `ApexGPS`. So first rename the existing private one:

- GitHub UI: **Your repositories → ApexGPS → Settings → General → Repository name** → change to `ApexGPS-private` → **Rename**.
- GitHub auto-creates a permanent redirect from the old name to the new one, so any old `git remote` URLs keep working for ~1 month. Local clones aren't broken — but you should still update your remote so future pushes go straight to the new URL:

```bash
cd "C:\Users\rdu\dev\ApexGPS"
git remote set-url origin git@github.com:duettra/ApexGPS-private.git
git remote -v   # verify it now points to ApexGPS-private
```

### 2. Create the new public repo on GitHub
- GitHub UI: **+ → New repository** → owner `duettra`, name `ApexGPS`, visibility **Public**, do NOT initialize with README/license/.gitignore (we're going to push our own initial commit).

### 3. Push these files to the new public repo

From the project root:
```bash
cd "C:\Users\rdu\dev\ApexGPS\tools\web-share"
git init
git add .
git commit -m "Initial public site: assetlinks + /loc landing + privacy copy"
git branch -M main
git remote add origin git@github.com:duettra/ApexGPS.git
git push -u origin main
```

### 4. Enable GitHub Pages
- **Settings → Pages → Source**: branch `main`, folder `/ (root)`.
- **Custom domain**: `apexgps.duttra.de` (the `CNAME` file in this folder pre-fills it).
- Tick **Enforce HTTPS** once Pages reports the cert is provisioned (~10 min).

### 5. Add the DNS record at your duttra.de registrar
Add a single **CNAME** record:

| Name | Type | Value | TTL |
|---|---|---|---|
| `apexgps` | CNAME | `duettra.github.io.` | default (300–3600) |

(Note: the trailing `.` on `duettra.github.io.` matters in some control panels — use it if your DNS UI shows other records with trailing dots; otherwise drop it.)

Wait 5–15 min for propagation. Verify with: `dig apexgps.duttra.de` (should show `duettra.github.io` in the answer).

### 6. Verify the App Links setup
Once DNS is live and Pages reports HTTPS-ready:

```
https://apexgps.duttra.de/.well-known/assetlinks.json
```
…must return the JSON file from this folder. Check with `curl`:
```bash
curl https://apexgps.duttra.de/.well-known/assetlinks.json
```

Then on your phone, **uninstall and reinstall ApexGPS** (or update via `adb install -r`) — Android verifies App Links on install/update by fetching that file. Verify the result:
```bash
adb shell pm get-app-links com.apexgps.app
```
The output should show `apexgps.duttra.de: verified`.

### 7. Test the deep link
On your phone (with ApexGPS installed and verified):
```bash
adb shell am start -W -a android.intent.action.VIEW \
  -d "https://apexgps.duttra.de/loc?lat=25.165183&lon=55.409717" \
  com.apexgps.app
```
ApexGPS should open and pan the map to that location.

In WhatsApp: paste a URL like `https://apexgps.duttra.de/loc?lat=25.16&lon=55.40` and tap it — it should open ApexGPS directly (no chooser prompt).

---

## Updating the share text in the app

Once verification is confirmed (step 5 returns `verified`), the app's share text can be flipped from the Google Maps URL to the new ApexGPS URL. Tell Claude to do the flip.

---

## (Optional) Move the privacy URL on Play Store

The privacy policy is now also at `https://apexgps.duttra.de/privacy.html` (Pages renders the `privacy.md` markdown automatically when `permalink: /privacy.html` is in the front-matter — already set up in your `privacy.md` copy).

To switch the Play Store privacy URL:
1. Visit the link in a browser to confirm it renders.
2. Play Console → ApexGPS → **Policy → App content → Privacy Policy** → paste the new URL → Save.
3. The change is live immediately for the Play listing.

The old `duettra/apexgps-privacy` repo can then either be archived or kept as a backup.

---

## Updating signing fingerprints later

`assetlinks.json` currently lists only your local release-keystore SHA-256:
```
86:12:2A:F5:B8:4E:A9:C0:33:77:55:64:F3:A0:A4:B1:83:26:55:A2:88:2B:D5:97:29:C1:9B:CA:7C:BA:82:00
```

If you opt into **Play App Signing** for production releases, Google re-signs the AAB with their own cert — App Links would fail to verify on Play-installed builds until you also add **that** fingerprint here. Find it under **Play Console → Setup → App Integrity → App signing key certificate → SHA-256 fingerprint**, then add it as a second entry in the `sha256_cert_fingerprints` array. Push the change; reinstall to re-verify.
