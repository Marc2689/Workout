# IronLog — free Hevy-style workout tracker

Offline, no account, no ads, no subscription. All data stays on your device.

## Features
- Live workout logging: sets, reps, weight, previous-session hints (tap to copy), rest timer with vibrate/beep, screen stays awake
- Bodyweight and timed exercises, plus 100+ built-in exercises and your own custom ones
- Routines: build once, start in one tap; save any workout as a routine
- History with repeat / delete, personal-record detection on finish
- Stats: workouts per week, estimated 1RM progress charts, PR list
- kg / lb toggle, JSON backup + restore, CSV export

## Fastest way: install it as an app (2 minutes, no APK needed)
1. Upload this folder to any free static host (GitHub Pages, Netlify Drop, Cloudflare Pages). It must be served over HTTPS.
2. Open the URL in Chrome on your Android phone → menu (⋮) → **Install app** / **Add to Home screen**.
3. It now launches full-screen like a native app and works offline.

## Turn it into a real APK
**Option A – PWABuilder (easiest, no coding)**
1. Host the folder as above.
2. Go to pwabuilder.com, paste your URL, choose **Package for stores → Android**.
3. Download the package; it contains a signed `.apk` you can sideload (and an `.aab` for Play Store).

**Option B – Bubblewrap CLI**
```
npm i -g @bubblewrap/cli
bubblewrap init --manifest https://YOUR-URL/manifest.webmanifest
bubblewrap build
```
Produces `app-release-signed.apk`.

**Option C – Capacitor (bundles the files inside the APK, no hosting)**
```
npm init -y && npm i @capacitor/core @capacitor/cli @capacitor/android
npx cap init IronLog com.example.ironlog --web-dir www
mkdir www && cp index.html manifest.webmanifest sw.js icon-*.png www/
npx cap add android && npx cap sync
npx cap open android   # Build > Build APK(s) in Android Studio
```

## Back up your data
Data is stored in the app's local storage. Clearing app/browser data or uninstalling erases it, so use **Stats → Export backup** now and then.
