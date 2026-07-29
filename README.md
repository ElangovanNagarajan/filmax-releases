# 70mm Filmax — releases

Public download location for the 70mm Filmax Android app.

`latest.json` is what the app's **Settings → Update** button reads. It points at
the newest APK in this repo's Releases.

This repo is public on purpose, and it is safe to be: the APK contains **no
credentials**. The gist write-token and Telegram details live in the phone's
own secure keystore (`expo-secure-store`), pasted once under
**Settings → Connection**. Anyone downloading this build gets an app that can
read the public watch list and nothing more.

## Publishing a new version

1. Bump `version` and `android.versionCode` in the app's `app.json`.
2. Build: `npx expo export --platform android` then
   `cd android && ./gradlew assembleRelease -PreactNativeArchitectures=arm64-v8a`
3. Create a GitHub Release tagged `v<version>` and attach the APK as
   `70mm-Filmax-arm64.apk`.
4. Update `latest.json` here to match. The app compares `versionCode` against
   its own, so it must increase every release.
