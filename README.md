# Eye Gymnastics — Legal

Privacy Policy and Terms of Use for **Eye Gymnastics** (`com.indiehacker.eye_gymnastics`), published by Fazogirapps.

Served via GitHub Pages:

| Document | URL |
|---|---|
| Landing page | https://elyorberdiev.github.io/eyegym-legal/ |
| Privacy Policy | https://elyorberdiev.github.io/eyegym-legal/privacy.html |
| Terms of Use | https://elyorberdiev.github.io/eyegym-legal/terms.html |

These URLs are submitted to App Store Connect and the Google Play Console, and are linked from the app's Settings screen. **Do not rename these files** — changing a path breaks the links already registered with the stores.

## Updating

Edit the HTML, bump the "Last Updated" date in the file header, then commit and push. GitHub Pages redeploys automatically within a minute or two.

For material changes, also update the effective date and give users notice in-app.

## Claims that depend on the app's actual behaviour

These documents describe what the app does today. If a feature changes, the corresponding text must change too — an inaccurate privacy policy is worse than none.

| Text says | True only while |
|---|---|
| "no registration and no sign-in" | The app stays account-free. Adding Firebase Auth or any login requires rewriting §2 of the Privacy Policy. |
| "your practice data never leaves the device" | Drift/SQLite stays the only store. Adding cloud sync requires rewriting §3, §6, §8 and §10 of the Terms. |
| "Firebase Crashlytics and Analytics" | Both are actually shipped in the released build. Remove the rows if they are not. |
| Analytics event list (`exercise_started`, `exercise_completed`, `premium_purchased`, `review_requested`) | Matches `lib/core/services/analytics_service.dart`. Update §4 when events are added or renamed. |
| "does not request camera, microphone, photo library, location, or contacts" | No such permission is added to `AndroidManifest.xml` / `Info.plist`. |
| "exact alarms and start on boot" | `USE_EXACT_ALARM` and `RECEIVE_BOOT_COMPLETED` remain in the Android manifest. |
| "premium is an auto-renewing subscription" | RevenueCat entitlements stay subscription-based. A one-off purchase would change §9 of the Terms. |
| Photosensitivity warning | Keep it as long as the exercises use moving or flashing visuals — Rive animations qualify. |

## Publishing checklist

1. Push this folder to the **public** repo `eyegym-legal`. GitHub Pages needs public, or a paid plan.
2. Settings → Pages → Source: `main` branch, `/` root.
3. Wait for the first build, then open all three URLs and check them on a phone.
4. Put the URLs into:
   - the Settings screen of the app (Privacy Policy, Terms of Use)
   - App Store Connect → App Privacy → Privacy Policy URL
   - App Store Connect → App Information → EULA (or link the Terms)
   - Google Play Console → Store listing → Privacy Policy
