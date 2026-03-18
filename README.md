# Chronicles of CodeCraft — APK Cloud Build Guide

This project is a ready-to-build Android app that wraps the
Chronicles of CodeCraft coding education game in a native WebView.

---

## How to build your APK (free, no Android Studio needed)

### Step 1 — Create a GitHub account
Go to https://github.com and sign up for free if you don't have one.

### Step 2 — Create a new repository
1. Click the green "New" button on your GitHub dashboard
2. Name it: `chronicles-of-codecraft`
3. Set it to Public (free accounts need this for Actions)
4. Click "Create repository"

### Step 3 — Upload this project
Option A — GitHub web UI (easiest):
1. Open your new repository
2. Click "Add file" → "Upload files"
3. Drag and drop ALL the files and folders from this zip
4. Make sure the folder structure is preserved:
   - .github/workflows/build-apk.yml
   - android-project/  (entire folder)
5. Click "Commit changes"

Option B — Git command line:
  git init
  git add .
  git commit -m "Initial commit"
  git remote add origin https://github.com/YOUR_USERNAME/chronicles-of-codecraft.git
  git push -u origin main

### Step 4 — Watch the build run
1. Go to your repository on GitHub
2. Click the "Actions" tab at the top
3. You'll see "Build Chronicles of CodeCraft APK" running
4. Click on it to watch the live progress (takes ~3-5 minutes)

### Step 5 — Download your APK
1. Once the build shows a green checkmark, click on the run
2. Scroll to the bottom of the page to find "Artifacts"
3. Click "chronicles-of-codecraft-debug" to download your APK zip
4. Unzip it — you'll find app-debug.apk inside

### Step 6 — Install on your Android device
1. Transfer app-debug.apk to your Android phone
   (via USB, email, Google Drive, etc.)
2. On your phone: Settings → Security → Enable "Unknown sources"
   (or "Install unknown apps" on Android 8+)
3. Open the APK file and tap Install
4. Launch "Chronicles of CodeCraft" from your home screen!

---

## Project structure

  chronicles-of-codecraft/
  ├── .github/
  │   └── workflows/
  │       └── build-apk.yml          ← GitHub Actions build script
  └── android-project/
      ├── build.gradle               ← Root Gradle config
      ├── settings.gradle
      ├── gradle.properties
      ├── gradle/wrapper/
      │   └── gradle-wrapper.properties
      └── app/
          ├── build.gradle           ← App Gradle config
          ├── proguard-rules.pro
          └── src/main/
              ├── AndroidManifest.xml
              ├── assets/public/
              │   └── index.html     ← THE GAME (all in one file)
              ├── java/com/codecraft/chronicles/
              │   └── MainActivity.java
              └── res/
                  ├── layout/activity_main.xml
                  └── values/strings.xml

---

## Notes

- The debug APK is fully functional for personal use and testing
- To publish on Google Play, you'd need to sign a release APK
  (ask Claude for signing instructions when you're ready)
- The game works fully offline — no internet required after install
- Supports Android 5.0 (API 21) and above

---

Built with: Native Android WebView + HTML/CSS/JavaScript
No frameworks, no dependencies, no tracking.

