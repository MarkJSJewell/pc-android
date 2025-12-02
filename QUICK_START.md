# Quick Start Guide - Pub Crawler Android App

## Option 1: WebView Wrapper (What's Included)

The project I've created wraps your existing web app in an Android WebView. This is the **fastest approach** to get your app on Android.

### Advantages:
✅ Reuses your existing web code completely
✅ Quick to set up and deploy
✅ Updates to web app automatically update in the app
✅ Single codebase to maintain

### Current Configuration:
- Loads from: `https://markjsjewell.github.io/pub-crawler/`
- Supports geolocation
- Handles Google Maps API calls
- Full back-button navigation

## Getting Started in 5 Minutes

### Step 1: Install Android Studio
Download from: https://developer.android.com/studio

### Step 2: Open Project
1. Extract the `pub-crawler-android` folder
2. Open it in Android Studio
3. Wait for Gradle sync to complete

### Step 3: Run the App
1. Click the green play button
2. Choose an emulator or connected device
3. Your app will launch!

## Important: Update Your Web App URL

If your web app is hosted somewhere other than the default GitHub Pages URL:

1. Open: `app/src/main/java/com/pubcrawler/app/MainActivity.java`
2. Find line ~72: `webView.loadUrl("https://markjsjewell.github.io/pub-crawler/");`
3. Change to your URL: `webView.loadUrl("https://your-domain.com");`

## Google Maps API Configuration

Your Google Maps API key needs to allow Android app requests:

1. Go to Google Cloud Console: https://console.cloud.google.com/
2. Select your project
3. Go to "APIs & Services" → "Credentials"
4. Edit your Maps JavaScript API key
5. Under "Application restrictions", add:
   - **Android apps**
   - Package name: `com.pubcrawler.app`
   - SHA-1 fingerprint (get with: `keytool -list -v -keystore ~/.android/debug.keystore`)

## Next Steps

### Test on Real Device
1. Enable Developer Mode on your phone
2. Enable USB Debugging
3. Connect via USB
4. Select your device and run

### Build APK for Testing
1. Build → Build Bundle(s) / APK(s) → Build APK(s)
2. Share `app-debug.apk` with testers

### Publish to Play Store
1. Build signed release APK
2. Create Play Console account
3. Upload and publish

## Alternative: Progressive Web App (PWA)

Instead of this native wrapper, you could convert your web app to a PWA:

### Advantages:
- No app store approval needed
- Smaller "download" size
- Easier to update

### To Create PWA:
1. Add a `manifest.json` to your web app
2. Implement a service worker for offline support
3. Users install directly from browser

Would you like help setting up a PWA instead?

## Need Help?

Common issues and solutions:

**Problem**: App won't load
- Check internet connection
- Verify URL is correct
- Check Logcat for errors

**Problem**: Maps not working
- Verify API key configuration
- Check API key restrictions
- Ensure billing is enabled in Google Cloud

**Problem**: Location not working
- Grant location permissions when prompted
- Check AndroidManifest.xml has location permissions

## File Structure

```
pub-crawler-android/
├── app/
│   ├── src/main/
│   │   ├── java/com/pubcrawler/app/
│   │   │   └── MainActivity.java          # Main app logic
│   │   ├── res/
│   │   │   ├── layout/
│   │   │   │   └── activity_main.xml      # WebView layout
│   │   │   ├── values/
│   │   │   │   ├── strings.xml            # App name
│   │   │   │   ├── colors.xml
│   │   │   │   └── themes.xml
│   │   └── AndroidManifest.xml            # Permissions & config
│   └── build.gradle                       # App dependencies
├── build.gradle                           # Project config
├── settings.gradle
└── README.md                              # Full documentation
```

## Customization Checklist

- [ ] Update app name in `strings.xml`
- [ ] Update web URL in `MainActivity.java`
- [ ] Configure Google Maps API for Android
- [ ] Add custom app icon
- [ ] Test on real device
- [ ] Build signed APK
- [ ] Create Play Store listing

---

Ready to build? Open the project in Android Studio and click Run! 🚀
