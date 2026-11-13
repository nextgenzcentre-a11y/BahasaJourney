# BahasaJourney

A mobile-first Bahasa Melayu learning app for Malaysian Malay, with Arabic (الفصحى) and English meanings, a 1,000-entry vocabulary curriculum, exercises and real interactive games.

## Website

The web app is the root `index.html` and is deployed on Vercel. All learning progress is stored locally in the device/browser.

## Android app

The Capacitor source lives in `mobile/`. Requirements: Node.js 22+, Java 21, Android SDK.

```bash
cd mobile
npm install
npm run sync:web
npx cap add android
npx cap sync android
npx cap open android
```

Build a debug APK in Android Studio or with `cd android && ./gradlew assembleDebug`. The GitHub Actions workflow also builds a debug APK on pushes and manual runs; download it from the workflow's **Artifacts** section after the run completes.

## Important

- The debug APK is for personal testing; Play Store publishing needs a release build and signing.
- Photographs and synthesized speech may require internet access.
- Native scheduled device notifications are not yet implemented. ChatGPT reminders are independent.
- Words with multiple possible translations require contextual review; the entire translation dataset has not been fully audited.
- This repository contains no backend or account sync; the app saves progress locally.

## Verify Android phone notifications

1. Install the newest **BahasaJourney-debug-apk** from GitHub Actions on an Android phone.
2. Open **Reminders → Test phone notifications**.
3. Tap **Send test now** and grant Android notification permission. Check your notification shade.
4. Tap **Test in 10 seconds**, lock the screen, and wait for the test alert. Android may delay timed notifications when alarms or battery activity are restricted.
5. Tap **Check status** to inspect Android notification permission, whether notifications are enabled, pending delayed test and exact alarm status.
6. Tap **Enable phone reminders** to schedule the morning lesson (08:30 by default) and evening review (18:45).

The browser cannot run these tests; they require the Android APK. Test notifications are not evidence that recurring reminders will always arrive exactly on time—Android may throttle alarms or restrict background work.
