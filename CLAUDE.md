# CLAUDE.md — LG Remote

Android app by Bensal that wraps an HTML/JS LG TV remote control in a WebView. Also works as a PWA. Controls an LG TV over WiFi using the LG webOS control protocol. Public repo. Write docs and changelog for users, not about development history.

## Repo layout

```
/
├── android/               ← Android project (WebView wrapper)
│   ├── app/src/main/      ← MainActivity loads the remote UI
│   └── app/build.gradle   ← version + dependencies
├── index.html             ← the remote control UI
├── sw.js                  ← service worker (PWA offline support)
├── manifest.json          ← PWA manifest
├── icon.svg               ← app icon
├── .github/workflows/     ← CI build
├── CHANGELOG.md, LICENSE
└── README.md
```

## Build and release

- The Android APK is built by GitHub Actions.
- Signing: secrets `KEYSTORE_BASE64` (base64 of the keystore) and `KEYSTORE_PASSWORD`. **Never create or replace the signing key**: updates would no longer install over the existing app.
- **On every user-visible change bump `versionCode` and `versionName`** in `android/app/build.gradle` and add an entry at the top of `CHANGELOG.md`.
- Current version: 1.0, package `com.bensalk.lgremote`.
- Commit identity: `343577983+Bensalk@users.noreply.github.com`. Never a personal email.
- `main` is protected (no force push, no deletion). Private vulnerability reporting is on.

## App facts

- Package: `com.bensalk.lgremote`, minSdk 21, targetSdk 34
- Current version: 1.0 (versionCode 1)
- The Android app is a thin WebView wrapper. The main logic lives in `index.html`.
- Also usable as a PWA in a mobile browser.

## Working style

- Bensal installs the APK from the GitHub Release on his phone.
- Suggest changes and wait for his approval before implementing.
- Keep explanations short and non-technical.
- Start every reply with a `Model:` line (Sonnet for routine/support, Opus for hard coding or design decisions) and a one-line reason; Bensal can't judge difficulty himself.
