# NovApp

NovApp is an Android application. This repository contains the project and GitHub Actions workflow to build the debug APK.

## Build (local)

To build the debug APK locally:

1. Ensure the Gradle wrapper is executable: `chmod +x ./gradlew`
2. Run:

   ./gradlew assembleDebug

The debug APK will be produced at: `app/build/outputs/apk/debug/app-debug.apk`

## CI

A GitHub Actions workflow is included at `.github/workflows/android.yml` that runs on push and will build the debug APK and upload it as an artifact named `app-debug`.

## Notes

- If you want automated signed release builds, I can add signing steps but you must add repository secrets (ANDROID_KEYSTORE, ANDROID_KEYSTORE_PASSWORD, ANDROID_KEY_ALIAS, ANDROID_KEY_PASSWORD).
- Make sure the repository contains an Android Gradle project with an `app/` module and the Gradle wrapper (`gradlew`).