# RIDDHI AI Android APK project

This Android app is a lightweight native WebView wrapper for your existing hosted RIDDHI AI PWA:
https://riddhi-ai-1.onrender.com

## Included
- Android launcher icon and app name.
- Full-screen web app experience.
- JavaScript + local storage enabled for the existing web app.
- HTTPS-only hosted site.
- Microphone permission bridge for web voice features.
- ESP32 and Gemini continue using your existing Render backend.
- GitHub Actions workflow to build a debug APK remotely.

## Build APK without installing Android Studio locally (GitHub Actions)
1. Upload the contents of this folder to a new GitHub repository, or add them to a separate repository. Keep `.github/workflows/build-apk.yml` in the repository.
2. Push to `main` or `master`.
3. Open the repository's **Actions** tab.
4. Select **Build Riddhi AI APK** and run it if it did not start automatically.
5. Wait for the workflow to complete successfully.
6. Open the completed workflow run, scroll to **Artifacts**, and download `Riddhi-AI-debug-APK`.
7. Extract the artifact; it contains `app-debug.apk`.
8. Transfer the APK to your Android phone, open it, and allow installation from that source when Android asks.

## Build on Windows with Android Studio
1. Install Android Studio and Android SDK Platform 35.
2. Open this folder as an existing project.
3. Let Gradle sync; Gradle 8.9 and JDK 17 are configured.
4. Select Build > Build Bundle(s) / APK(s) > Build APK(s).
5. Find the output at `app/build/outputs/apk/debug/app-debug.apk`.

## Important
- This is an Android APK wrapper for the hosted PWA, not an offline standalone Gemini model. AI chat and ESP32 need internet.
- The APK does not contain your Gemini API key. The key remains on Render.
- Debug APK is suitable for personal testing/sideloading. For Play Store release, create a signed release APK/AAB with your own signing key and Play Console setup.
- Voice input depends on Android System WebView and device speech services. The app asks for microphone permission when the website requests audio capture.
- Render free tier may sleep and need time to wake.
