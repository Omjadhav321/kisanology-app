# Kisanology App - Build Instructions

## Prerequisites

1. **Android Studio** (recommended) - Download from https://developer.android.com/studio
2. **Java JDK 17** - Included with Android Studio

## Quick Build (Android Studio)

1. Open **Android Studio**
2. Click **File > Open** and select the project folder
3. Wait for Gradle sync to complete (this will download dependencies automatically)
4. Click **Build > Build Bundle(s) / APK(s) > Build APK(s)**
5. Find the APK at: `app/build/outputs/apk/debug/app-debug.apk`

## Quick Build (Command Line - Windows)

```powershell
# Set Android SDK path (adjust if your SDK is elsewhere)
setx ANDROID_HOME "%LOCALAPPDATA%\Android\Sdk"

# Build debug APK
gradlew assembleDebug

# APK will be at: app\build\outputs\apk\debug\app-debug.apk
```

## Install on Device

1. **Enable Developer Options** on your Android phone:
   - Go to **Settings > About Phone > Tap "Build Number"** 7 times
   - Go back to **Settings > Developer Options > Enable USB Debugging**

2. **Connect phone via USB** and approve the debugging prompt

3. **In Android Studio**: Click the green **Run** button (▶) with your device selected

4. **Or via command line** (once SDK tools are installed):
   ```powershell
   adb install app\build\outputs\apk\debug\app-debug.apk
   ```

## Testing Notes

- The app loads **https://kisanology.gt.tc/** inside a WebView
- Pull-to-refresh and pinch-to-zoom are enabled
- Drawer navigation: Home, Home (secondary), About, Help
- If the website is offline, a custom offline page will be shown
- Debug mode is OFF for production testing

## Troubleshooting

| Issue | Solution |
|-------|----------|
| Gradle sync fails | Ensure Android SDK 36 is installed via SDK Manager |
| App crashes on launch | Check logcat in Android Studio for error details |
| Website doesn't load | Verify kisanology.gt.tc is accessible on the device |
| "No connected devices" | Install a USB driver for your phone or use an emulator |
