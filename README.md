# NothingLost privacy policy

Public privacy policy for the NothingLost Android app (`com.nothinglost.app`), served by GitHub Pages:
**https://ahaariyan.github.io/NothingLostPrivacyPolicy/**

That URL goes in Play Console (App content → Privacy policy). Google checks it against the app's
permissions and the Data safety answers, so this page is kept accurate to the code, not to intentions.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole policy. No build step, no framework. |
| `favicon-32.png`, `apple-touch-icon.png` | From the app icon, so this repo stands alone. |
| `.nojekyll` | Serve the files as they are. |

## When to update it

Anything that changes **what leaves a user's device, where it goes, or how long it is kept** needs
this page updated in the same change: a new analytics event field, a new SDK, a new permission, a
retention change. Update the effective date when you do, and the Play Data safety form to match.

## Claims in here that the code has to keep true

Verified against the app source on 25 September 2026:

- notification and message content, sender names, search terms and app package names are never put in
  an analytics event or crash log (`core/analytics/Events.kt` is the full list of what is sent);
- saved notifications are excluded from backup (`allowBackup="false"`);
- the advertising ID and ad-services permissions are removed from the manifest;
- Settings → "Share anonymous usage stats" stops Analytics and Crashlytics and resets the app-instance ID;
- notifications older than one year are deleted automatically;
- the share button sends only a Play Store link; the survey is opened in the browser by the user's tap;
- Firebase Analytics data retention is set to 14 months in the Firebase console.

## Preview locally

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```
