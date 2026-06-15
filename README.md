# 📖 Shiori — EPUB Reader for Android

<p align="center">
  <strong>Shiori (栞)</strong> — means <em>bookmark</em> in Japanese.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Android%208.0%2B-green?logo=android" />
  <img src="https://img.shields.io/badge/Language-Kotlin-purple?logo=kotlin" />
  <img src="https://img.shields.io/badge/UI-Jetpack%20Compose-blue?logo=jetpackcompose" />
  <img src="https://img.shields.io/badge/License-MIT-lightgrey" />
</p>

---

An EPUB reader for Android designed with Thai readers in mind.

Features built-in Text-to-Speech with customizable text replacement before speech synthesis. No account required. No cloud dependency.

---

## ✨ Features Overview

| Feature | Description |
|----------|-------------|
| 📚 Library | Manage books in 3 different views with reading progress tracking |
| 📖 EPUB Reader | Smooth reading experience with infinite chapter scrolling |
| 🔊 Text-to-Speech | Start reading from any paragraph with a long press |
| ✏️ Text Replacement | Replace words before TTS playback, supports 5,000+ entries |
| 👁️ Visual Replacement | Display replaced text directly in the reader |
| 🎯 Select Mode | Tap words in a book to instantly create replacement rules |
| 🎨 Themes | Light / Dark / Sepia |
| ⚙️ Settings | Customize fonts, line spacing, and TTS speed |

---
## App Snapshot 
[Reading View](https://github.com/usero2/android-Shiori-EPUB-Reader-public/blob/main/images/Screenshot_20260615_194213_com_shiori_epubreader_MainActivity.jpg)

[Reading View TTS](https://github.com/usero2/android-Shiori-EPUB-Reader-public/blob/main/images/Screenshot_20260615_194226_com_shiori_epubreader_MainActivity.jpg)

[Reading View Font config](https://github.com/usero2/android-Shiori-EPUB-Reader-public/blob/main/images/Screenshot_20260615_194234_com_shiori_epubreader_MainActivity.jpg)

## 📲 Installation

### Install from APK

1. Download `shiori-release.apk` from the Releases page.
2. Enable **Settings → Security → Install unknown apps** for your browser or file manager.
3. Open the APK and tap **Install**.

### Requirements

- Android 8.0 (API 26) or higher
- Internet connection not required (except for AdMob advertisements)

---

## 📚 Feature 1 — Library

The Library screen displays all books stored in your collection.

### Adding Books

1. Tap the **+** (FAB) button in the bottom-right corner.
2. Select an `.epub` file using the Android file picker.
3. The book will automatically appear in the library with its cover, title, and author information.

> You can also open an EPUB directly from your file manager and choose **Shiori** as the default app.

### Library Views

Tap the **Grid** icon in the top bar to switch between:

| View | Description |
|--------|--------|
| **Thumbnail** | Large cover grid |
| **List** | Compact list with cover and progress bar |
| **Detail** | Extended information including chapter progress and date added |

### Reading Progress

- Displays reading progress in every view.
- Automatically updates as you continue reading.

### Removing Books

- Long-press a book and confirm deletion.

---

## 📖 Feature 2 — EPUB Reader

### Opening a Book

- Tap a book in the library.
- Shiori automatically resumes from your last reading position.

### Reader Controls

| Gesture | Action |
|----------|--------|
| Tap screen | Show / hide control bars |
| Swipe up/down | Scroll content |
| ‹ › buttons | Previous / next chapter |

### Infinite Scroll

- Scrolling to the end of a chapter automatically loads the next chapter.
- Scrolling to the top automatically loads the previous chapter.

### Chapter Navigation

- Current chapter title is displayed in the top bar.
- Use **‹** and **›** buttons to move between chapters.

### Reader Toolbar

| Icon | Function |
|--------|--------|
| ← | Return to Library |
| Aa | Reader appearance settings |
| ☀️ / 🌙 | Quick theme switch |
| ✋ | Toggle Selection Mode |
| ⚙️ | Open Settings |

---

## 🔊 Feature 3 — Text-to-Speech (TTS)

### Start Reading Aloud

1. Long-press any paragraph.
2. Select **▶ Start TTS from here**.
3. Reading begins from the selected paragraph.

### TTS Control Bar

| Button | Function |
|----------|--------|
| ⏮ | Previous paragraph |
| ⏸ / ▶ | Pause / Resume |
| ⏹ | Stop TTS |
| ⏭ | Next paragraph |

### Reading Highlight

- The currently spoken paragraph is automatically highlighted.
- The reader scrolls automatically as playback progresses.

### TTS Voice Settings

Navigate to **Settings → Text-to-Speech**:

- **Pitch (Tone):** 0.5× – 2.0×
- **Speed:** 0.5× – 3.0×

---

## ✏️ Feature 4 — Text Replacement

Text Replacement modifies words or phrases before TTS playback and can also affect visual rendering.

### Access

**Settings → TTS Tools → Text Replacements**

### Add a New Rule

1. Tap **+**
2. Enter the text to find.
3. Enter the replacement text.
4. Tap **Save**.

### Example

| Find | Replace With | Result |
|--------|--------|--------|
| AI | A.I. | Better pronunciation |
| Dr. | Doctor | Expands abbreviations |
| Mr. | Mister | More natural speech |

### Edit or Delete Rules

- Tap ✏️ to edit.
- Tap 🗑️ to delete.

### Enable / Disable Rules

- Use the toggle switch beside each entry.
- Temporarily disable rules without deleting them.

### Search Rules

- Tap 🔍 in the top bar.
- Search both source and replacement text in real time.

### Export Rules

1. Tap **⬆ Export**
2. Choose a save location.
3. A TSV-formatted `.txt` file is created.

Example:

```txt
# Shiori TTS Replacements
# Format: from<TAB>to
AI	A.I.
Dr.	Doctor
Mr.	Mister
