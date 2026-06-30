# Inkwell — App Website

Public landing page for **Inkwell**, a local comic and book reader for Android.

Hosted at → **[solutionbyhour.github.io/inkwell-web](https://solutionbyhour.github.io/inkwell-web/)**

---

## What's in this repo

| File / Folder | Purpose |
|---|---|
| `index.html` | Landing page — hero, screenshot carousel, feature grid, download CTA |
| `privacy-policy.html` | Privacy policy (linked from Play Store and in-app Settings) |
| `screenshots/` | PNG screenshots shown in the carousel |
| `inkwell-*.apk` | Sideloadable release APK for direct download |

The app source code lives in a separate private repo (`inkwell-android`). This repo is public so GitHub Pages can serve it for free.

---

## Updating for a new release

**1. Build the release APK** (in the `inkwell-android` repo):
```bash
gradle assembleRelease
```

**2. Copy the new APK here:**
```bash
cp app/build/outputs/apk/release/app-release.apk ../inkwell-app/inkwell-<version>.apk
```

**3. Update `index.html`** — change the two `href="inkwell-*.apk"` download links to the new filename, and bump the version string in the `apk-meta` line.

**4. Add new screenshots** if needed — drop PNGs into `screenshots/` and update the `<img>` tags in the carousel section of `index.html`.

**5. Commit and push:**
```bash
git add .
git commit -m "Release vX.Y"
git push
```

GitHub Pages rebuilds automatically — live in ~60 seconds.

---

## Privacy policy updates

Edit `privacy-policy.html` directly and update the `Last updated` date at the top. The canonical URL is:

```
https://solutionbyhour.github.io/inkwell-web/privacy-policy.html
```

This URL is hardcoded in:
- Play Console → App content → Privacy policy
- In-app Settings → About → Privacy Policy (link opens browser)

---

## Local preview

```bash
python3 -m http.server 8080
# open http://localhost:8080
```

---

## Links

- **App website:** https://solutionbyhour.github.io/inkwell-web/
- **Play Store:** *(coming soon)*
- **Contact:** shubhamkokul@gmail.com
