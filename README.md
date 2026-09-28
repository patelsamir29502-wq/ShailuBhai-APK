# Shailu Bhai Daily Collection — GitHub APK Builder

This project wraps the supplied HTML app in Capacitor and builds an Android APK with GitHub Actions.

## Included app functionality

The supplied HTML is kept as the app UI/business logic. It includes the existing customer/loan ledger, partial and advance payments, late-payment/penalty handling, WhatsApp messages/reminders, expense diary, reports, recovery/trash, JSON backup/restore, Excel import/export, settings, search/navigation and IndexedDB persistence.

The Excel browser library is bundled locally during the GitHub build instead of relying on the CDN at runtime.

## Build APK on GitHub

1. Create a new GitHub repository.
2. Upload all files/folders from this project.
3. Open **Actions**.
4. Select **Build Android APK**.
5. Click **Run workflow**.
6. Wait for the workflow to finish.
7. Open the completed workflow run and download the **shailu-bhai-debug-apk** artifact.
8. Extract the artifact and install `app-debug.apk` on Android.

## Local build

Requirements: Node.js 22+, Java 21, Android SDK/Android Studio.

```bash
npm install
npm run build
npx cap add android
npx cap sync android
cd android
./gradlew assembleDebug
```

APK:
`android/app/build/outputs/apk/debug/app-debug.apk`

## Important

This is a debug APK. For Play Store distribution, create a release signing key and a release GitHub Actions workflow.

The original HTML source was preserved rather than rewritten into a different framework, so the existing business rules remain in place.
