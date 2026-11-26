# Axiom IDE

**Axiom IDE** is a 100% free, open-source, offline-first Android coding IDE built with Kotlin, Jetpack Compose, and Material 3. No accounts, no subscriptions, no ads, and no tracking.

## Features

### Code Editor (Acode-Inspired)
- Multi-tab editing with cached syntax highlighting across 40+ programming languages
- Slide-out **Project File Tree Drawer** inside the editor
- **Command Palette** for 1-tap access to Save, Save All, Go to Line, Format, Comment Toggle, Word Wrap, Read-Only Mode, Encoding Picker, Snippets, Diff, and Shell
- Auto-indent, auto-close brackets, unsaved-changes close guard, and Find & Replace with live match count and case-sensitivity toggle (`Aa`)
- **20-key Extra Coding Bar** pinned directly above the keyboard (`TAB`, `{`, `}`, `(`, `)`, `[`, `]`, `<`, `>`, `;`, `:`, `"`, `'`, `=`, `/`, `\`, `|`, `&`, `!`, `$`)
- Custom Room-persisted code snippets and open-tab line-by-line Diff comparison

### Projects & File Management
- 10 starter project templates (HTML/CSS/JS, React, Python, Java, Kotlin, C/C++, PHP, Node.js, Flutter, Empty)
- Full local file and folder CRUD, search, favorites, project duplication
- Zip Slip–protected **ZIP import & export**
- **Android Storage Access Framework (SAF)** folder import

### Terminal, Execution & Live Preview
- Built-in multi-session Android shell (`/system/bin/sh`) with working directory persistence, command history, output search, and 20-second execution timeout
- **Termux** detection and quick launcher for full Linux toolchains (`git`, `python`, `node`, `clang`, `openjdk`, `rust`, `go`)
- **Live Web Preview** (`WebView`) for HTML/CSS/JS projects with Mobile/Desktop viewport toggle and real JavaScript console log capture
- Optional HTTPS **Piston-compatible remote runner** with `stdin` support and explicit trust confirmation before running code

### 19 Built-In Local Developer Tools
JSON Formatter & Validator, XML Formatter, SQL Formatter, Base64 & URL Codec, Hash Generator (MD5, SHA-1, SHA-256, SHA-512), UUID Generator, Regex Tester, JWT Decoder, Markdown Previewer, Color Picker (HEX/RGB), Timestamp Converter, Cron Helper, HTTPS API Request Tester, HTTP Headers Viewer, Diff Checker, Text Compare, and Image-to-Base64 Converter.

### Optional Integrations & Customization
- **GitHub**: Connect via a Personal Access Token (encrypted in Android Keystore) to sync live repositories
- **Local Extensions**: Import permission-scoped `.json` extension manifests (untrusted `exec`/`shell` permissions blocked)
- **BYOK AI Assistant**: Optional OpenAI-compatible HTTPS provider with Keystore-encrypted API key
- **Themes**: Dark (default), Light, OLED Black, and 6 accent colors with responsive phone (`NavigationBar`) and tablet (`NavigationRail`) layouts

## Download & Install
1. Open the **Releases** section of this repository.
2. Download the latest `AxiomIDE-v*.apk` file on your Android device (Android 8.0 / API 26 or higher).
3. Tap the downloaded APK and allow installation from unknown sources if prompted.

## Tech Stack
- **Language & UI**: Kotlin 2.0, Jetpack Compose, Material 3, Navigation Compose
- **Persistence & Security**: Room Database, Jetpack DataStore, Android Keystore (`EncryptedSharedPreferences` AES-256-GCM), HTTPS-only network policy (`usesCleartextTraffic=false`)
- **Networking & Storage**: OkHttp 4, Android Storage Access Framework (`DocumentFile`), `FileProvider`

## Building from Source
### Local / Android Studio
```bash
./gradlew assembleDebug
```
The debug APK is generated at `app/build/outputs/apk/debug/`.

### Cloud Build via GitHub Actions
This repository includes `.github/workflows/build-apk.yml` using JDK 17 and Gradle 8.9. Trigger **Build & Release Axiom IDE APK** from the **Actions** tab to compile a fresh APK automatically.

## Android Sandbox Note
Axiom IDE runs Android's real `/system/bin/sh` inside the app sandbox and never simulates fake compiler or terminal output. For native Linux packages (`git`, `python`, `node`, `clang`, `rustc`, `go`), install the official F-Droid or GitHub build of Termux or configure your own HTTPS Piston execution backend.

## License
Released under the [MIT License](https://www.google.com/search?q=LICENSE).
