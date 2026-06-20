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
| 🔊 Text-to-Speech | Start reading from any paragraph; auto-scroll toggle; paragraph skip with view scroll |
| 📱 Floating Controls | Floating overlay with paragraph text, stop badge, pinch-to-resize; snap to edge |
| ✏️ Text Replacement | Replace words before TTS playback, supports 5,000+ entries |
| 👁️ Visual Replacement | Display replaced text directly in the reader |
| 🎯 Select & Translate | Tap any word → context menu: Copy / Translate / Start TTS / Add Replacement |
| 🌐 TTS Language | Select **multiple** TTS languages simultaneously — Thai, English, Chinese; auto-detects script per segment |
| 🎨 Themes | Light / Dark / Sepia |
| ⚙️ Settings | Customize fonts, line spacing, TTS speed, and language |

---

## 📲 Installation

### Install from APK

1. Download the latest APK from the [releases/](releases/) folder — e.g. [`shiori-release-1.6.0.apk`](releases/1.6.0/shiori-release-1.6.0.apk).
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
| ‹ › buttons | Previous / next chapter (or previous / next paragraph when TTS is active) |

### Infinite Scroll

- Scrolling to the end of a chapter automatically loads the next chapter.
- Scrolling to the top automatically loads the previous chapter.
- Works even for very short chapters that fit entirely within the viewport.

### Chapter Navigation

- Current chapter title is displayed in the top bar.
- Use **‹** and **›** buttons to move between chapters.

### Reader Toolbar

| Icon | Function |
|--------|--------|
| ← | Return to Library |
| Aa | Reader appearance settings |
| 🔊 | Open TTS panel |

---

## 🔊 Feature 3 — Text-to-Speech (TTS)

### Start Reading Aloud

1. **Tap** any paragraph in the book — a context menu will appear.
2. Tap **▶ Start TTS from here** to begin reading from that paragraph.

### TTS Control Bar

| Button | Function |
|----------|--------|
| ⏮ | Previous paragraph (also scrolls reader to that paragraph) |
| ⏸ / ▶ | Pause / Resume |
| ⏭ | Next paragraph (also scrolls reader to that paragraph) |
| ⏹ | Stop TTS |
| 📍 | Scroll to the currently reading paragraph |
| ⇅ | Auto-scroll toggle — when enabled, the reader automatically scrolls to each paragraph as TTS advances |

### Reading Highlight

- The currently spoken paragraph is automatically highlighted.
- Tap **📍** to jump to the current paragraph on demand.
- Enable the **⇅ Auto-scroll toggle** in the bottom toolbar to follow the paragraph automatically as TTS reads.

### Paragraph Navigation While TTS is Active

When TTS is playing or paused, the **‹** and **›** buttons in the bottom toolbar switch from chapter navigation to paragraph navigation:

- **‹** skips to the **previous paragraph** and scrolls the reader to it.
- **›** skips to the **next paragraph** and scrolls the reader to it.

### TTS Voice Settings

Navigate to **Settings → Text-to-Speech**:

- **Pitch (Tone):** 0.5× – 2.0×
- **Speed:** 0.5× – 3.0×

### TTS Language

Navigate to **Settings → TTS Language** and check one or more languages:

| Language | Script detection range |
|----------|----------------------|
| **Thai** (ภาษาไทย) — enabled by default | U+0E00 – U+0E7F |
| **English** | Latin A–Z / a–z |
| **Chinese (Simplified)** (中文 简体) | U+4E00 – U+9FFF, U+3400 – U+4DBF |

When multiple languages are enabled, each paragraph is split into segments by script. Each segment is spoken with the matching language voice automatically — no manual switching required.

> At least one language must remain enabled.

---

## 📱 Floating TTS Controls

When TTS is playing and you switch to another app (or turn off the screen), Shiori starts a foreground service to keep reading and shows a floating overlay with playback controls.

### Current Paragraph Text

- The top section of the overlay displays the text of the paragraph currently being read.
- **Pinch anywhere on the overlay** to expand or shrink the text area — shows more or fewer lines without changing the font size.

### Buttons

| Button | Function |
|--------|----------|
| ✕ | Stop TTS — small red badge in the top-right corner of the overlay |
| 🧭 Navigate | Open Shiori and scroll to the paragraph currently being read |
| ✏️ Add Replacement | Open the **Add Text Replacement** popup without leaving the current app |
| ⏮ | Previous paragraph |
| ⏸ / ▶ | Pause / Resume |
| ⏭ | Next paragraph |

### Dragging & Snapping

- **Drag** the control panel anywhere on screen — it can be moved partially off-screen.
- **Snap to edge**: If you drag it more than 50% off the edge, it snaps to 15% visible so it stays accessible without covering content.
- **Double-tap** anywhere on the controls to animate it back to the center of the screen.

### Enable / Resize

Go to **Settings → Text-to-Speech**:

| Setting | Description |
|---------|-------------|
| **Floating Controls** | Toggle the overlay on or off |
| **Float Controls Size** | Scale the controls from ×0.5 to ×2.0 |

> On first use, Android will ask for **Display over other apps** permission — tap **Allow** to enable the overlay.

---

## ✏️ Feature 4 — Text Replacement

Text Replacement modifies words or phrases before TTS playback and can also affect visual rendering.

### Access

**Settings → Text Replacement → Visual Replacement**

### Add a New Rule

1. Tap **+**
2. Enter the text to find in **Find (from)**.
3. Enter the replacement text in **Replace with (to)**.
   - Leading and trailing spaces are preserved — useful for adding spacing around words.
   - If edge spaces are present, a `·` indicator appears below the field to make them visible.
4. Tap **Save**.

### Example

| Find | Replace With | Result |
|--------|--------|--------|
| AI | A.I. | Better pronunciation |
| Dr. | Doctor | Expands abbreviations |
| Mr. | Mister | More natural speech |

### Edit or Delete Rules

- Tap ✏️ to edit.
- Tap 🗑️ to delete (confirmation required).

### Enable / Disable Rules

- Use the toggle switch beside each entry.
- Temporarily disable rules without deleting them.

### Search Rules

- Tap 🔍 in the top bar.
- Searches both source and replacement text in real time.

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
```

### Import Rules

1. Tap **⬇ Import**
2. Select a previously exported `.txt` file.
3. Choose **Replace all** to overwrite the current list, or **Add to list** to merge.

---

## 👁️ Feature 5 — Visual Text Replacement

Replacement rules are not limited to TTS — they also affect what is **displayed in the reader**.

- Every word matching a rule is visually replaced in the WebView.
- Updates immediately when a new rule is added.
- Applies to all `<p>`, `<h1>` – `<h6>` elements.

---

## 🎯 Feature 6 — Word Selection & Context Menu

Tap any word in the reader to get an instant context menu — no mode switching required.

### How to Use

1. **Tap** any word in the book — it will be highlighted and a context menu appears immediately.
2. Choose an action from the context menu.

### Context Menu Options

| Option | Function |
|--------|----------|
| **▶ Start TTS from here** | Begin TTS playback from the tapped paragraph |
| **📋 Copy** | Copy the selected text to clipboard |
| **🌐 Translate** | Translate the selection using Google Translate in a popup — without leaving the reader |
| **+ Add to Replacement** | Opens a popup with **Visual** and **TTS** checkboxes — add to one or both types in a single action |

### Extend the Selection

- After tapping a word, drag the **selection handles** to select multiple words.
- The context menu updates its preview text in real time.
- Scrolling dismisses the context menu but keeps the text highlighted.

---

## 🔇 Feature 7 — TTS Replacement

Replace words only when sent to the TTS engine — the reader displays the original text unchanged.

### Access

**Settings → Text Replacement → TTS Replacement**

### Comparison

| Type | Shown in Reader | Read by TTS |
|------|----------------|-------------|
| **Visual Replacement** | ✅ Replaced text | ✅ Replaced text |
| **TTS Replacement** | ❌ Original text | ✅ Replaced text |

### Example Use Cases

- A character name that TTS mispronounces — replace the pronunciation for TTS while keeping the original name visible.
- Abbreviations that you want TTS to expand into full words while the reader still shows the abbreviation.

### Add from Context Menu

Tap any word → context menu → **+ Add to Replacement** → check **TTS** (and optionally **Visual**) → tap **Save**.

---

## 🎨 Feature 8 — Reader Themes & Display Settings

### Change Theme

Go to **Settings → Theme**:

| Theme | Appearance | Best For |
|-------|--------|------------|
| **Light** | White background, dark text | Daytime reading |
| **Dark** | Dark background, light text | Night / battery saving |
| **Sepia** | Warm cream background | Extended reading sessions |

### Display Settings

**Settings → Reading:**

| Option | Range | Notes |
|---------|-----|---------|
| **Font Size** | 12–28sp | Adjusts text size |
| **Line Height** | 1.0×–2.5× | Adjusts line spacing |

### Advanced Options

| Option | Effect |
|---------|-----|
| **Force System Font** | Overrides EPUB fonts with system Thai font (Noto Thai) |
| **Disable EPUB CSS** | Removes all EPUB stylesheets and uses the app's own styling |
| **Remove Font Color** | Strips color declarations from EPUB styles |

---

## ⚙️ Feature 9 — Settings

Accessible via the **⚙️** icon in the Library top bar.

### Reading
- **Font Size**: 12–28sp (slider)
- **Line Height**: 1.0×–2.5× (slider)

### Theme
- Light / Dark / Sepia

### Text-to-Speech
- **Pitch (Tone)**: ×0.5–×2.0
- **Speed**: ×0.5–×3.0
- **Floating Controls**: Toggle the floating overlay on/off
- **Float Controls Size**: Scale ×0.5–×2.0

### TTS Language
Select one or more languages (checkboxes):
- **Thai** (ภาษาไทย) — enabled by default
- **English**
- **Chinese (Simplified)** (中文 简体)

When multiple languages are checked, Shiori automatically detects the script of each text segment and reads it with the appropriate voice.

### Text Replacement
- **Visual Replacement** → Replaces words in both the reader view and before TTS playback
- **TTS Replacement** → Replaces words only when sent to TTS — the reader displays the original text unchanged

### About
- App version information
- Support & Donate links

---

## 🗂️ Project Structure

```
app/src/main/java/com/shiori/epubreader/
├── data/
│   ├── AppDatabase.kt
│   ├── Book.kt
│   ├── BookDao.kt
│   ├── BookRepository.kt
│   ├── TextReplacement.kt
│   ├── TextReplacementDao.kt
│   ├── TextReplacementRepository.kt
│   └── UserPreferencesRepository.kt
├── epub/
│   ├── EpubParser.kt
│   ├── EpubBook.kt
│   └── HtmlTextExtractor.kt
├── tts/
│   └── TtsManager.kt
├── ui/
│   ├── library/
│   ├── reader/
│   ├── replacements/
│   ├── settings/
│   └── navigation/
└── ShioriApplication.kt
```

---

## 🛠️ Tech Stack

| Technology | Usage |
|-----------|-------|
| **Kotlin** | Primary language |
| **Jetpack Compose** | UI framework |
| **Room** | Local database (books, replacements) |
| **Hilt** | Dependency injection |
| **DataStore** | User preferences |
| **WebView + JS** | EPUB rendering |
| **Android TTS** | Text-to-Speech engine |
| **Coil** | Cover image loading |
| **Google AdMob** | Banner advertising |

---

## 🔨 Build from Source

### Prerequisites
- Android Studio Hedgehog (2023.1.1) or newer
- JDK 17
- Android SDK API 35

### Steps
```bash
git clone https://github.com/YOUR_USERNAME/shiori-epub-reader.git
cd shiori-epub-reader
./gradlew assembleDebug
```

APK output: `app/build/outputs/apk/debug/app-debug.apk`

### Release Build
```bash
./gradlew assembleRelease
```

> Requires `shiori-release.jks` keystore and signing config in `app/build.gradle.kts`

---

## 📋 Permissions

| Permission | Required for |
|-----------|-------------|
| `READ_EXTERNAL_STORAGE` | Open EPUB files (Android 12 and below) |
| `INTERNET` | Load AdMob advertisements |
| `SYSTEM_ALERT_WINDOW` | Show floating TTS controls over other apps |
| `FOREGROUND_SERVICE` | Keep TTS playback alive in the background |
| `POST_NOTIFICATIONS` | Show TTS playback notification |

---

## 🗺️ Roadmap

- [ ] Bookmarks and highlights
- [ ] In-book text search
- [ ] Reading statistics
- [ ] Custom fonts (import TTF)
- [ ] Night mode auto-schedule
- [ ] Cloud backup via Google Drive

---

## 🐛 Known Issues

- EPUB files with DRM (Digital Rights Management) cannot be opened.
- EPUBs with very large embedded images may load slowly.

---

## 📄 License

```
MIT License

Copyright (c) 2026 Shiori EPUB Reader

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software.
```

## 📋 Release Notes

---

### v1.0.0 — Initial Release
- Library: Add/remove books, 3 view modes, reading progress tracking.
- EPUB Reader: Infinite scroll between chapters, resume from last position.
- Text-to-Speech: Start from any paragraph, highlight active paragraph during playback.
- Text Replacement: Add/edit/delete rules, export/import TSV, search.
- Visual Replacement: Replacement rules reflected in the reader view.
- Selection Mode: Tap words in the book to create replacement rules directly.
- Themes: Light / Dark / Sepia.
- AdMob banner.

---

### v1.0.1
- **TTS**: Removed auto-scroll when changing paragraphs — the screen no longer jumps while listening.
- **TTS**: Added 📍 "Navigate to current paragraph" button — tap to jump to the active paragraph on demand.
- **Text Replacement**: "Replace with" field now preserves leading and trailing spaces (no longer trimmed).
- **Text Replacement**: Added `·` visual indicator for edge spaces in both the dialog hint and the list.
- **Settings**: Added "❤️ Support the Project" section on the About page.
- **Bug fix**: Infinite scroll now works correctly for short chapters whose content fits entirely within the viewport.

---

### v1.1.0
- **Selection Mode**: Replaced the single-action popup with a full context menu — Copy / Translate / Start TTS from here / Add to TTS Replacement / Add to Replacement.
- **Translate**: Translations now open in a Google Translate bottom sheet popup inside the app — no browser required.
- **TTS-Only Replacements**: New replacement type that only affects TTS playback — the reader displays the original text unchanged.
- **Start TTS from here**: Moved into the Selection Mode context menu (previously required a separate long-press gesture).
- **Context menu design**: Redesigned with a dark card style that is readable across all themes.
- **Bug fix**: White flash when opening an EPUB file — background color is now applied before content loads.
- **Bug fix**: White screen after navigating Settings → back — fixed AdBanner lifecycle handling in Compose navigation.
- **App transitions**: Changed to instant switching — eliminates white flash between all screens.

---

### v1.1.1
- **TTS Language**: Added language selector in Settings — choose Thai, English, or Chinese (Simplified) for TTS playback.
- **Renamed screens**: Text Replacement screens renamed for clarity — "Visual + TTS Replacements" → "Visual Replacement", "TTS-Only Replacements" → "TTS Replacement".
- **Export filenames**: Visual Replacement exports default to `shiori_visual.txt`; TTS Replacement exports default to `shiori_tts.txt`.
- **Settings**: "TTS Tools" section renamed to "Text Replacement"; app version now displays correctly.
- **Word selection**: Context menu is now always active — no mode toggle required.
- **Bug fix**: Black screen when tapping back button multiple times rapidly in Settings or Text Replacement screens.

---

### v1.2.0
- **Floating TTS Controls**: A floating overlay (prev / pause / next) now appears when TTS is playing and the app goes to the background. TTS continues reading via a foreground service — no more stopping when switching apps or turning off the screen.
  - 🧭 Navigate button: tap to return to Shiori and scroll to the paragraph currently being read.
  - ✏️ Add Replacement button: opens the **Add Text Replacement** popup directly — no need to go back into the app.
  - Drag anywhere on screen; snap to 15% visible when dragged >50% off the edge.
  - Double-tap controls to animate back to screen center.
  - Enable / disable and resize in **Settings → Text-to-Speech → Floating Controls**.
- **Add Text Replacement popup**: The ✏️ button in Floating Controls and the **+ Add to Replacement** context menu item now open a unified popup with **Visual** and **TTS** checkboxes — add to one or both replacement lists in a single step.
- **Context menu**: Merged the two separate "Add to TTS Replacement" and "Add to Replacement" items into one **+ Add to Replacement** entry that opens the unified popup.
- **Permissions**: Added `SYSTEM_ALERT_WINDOW` (floating overlay), `FOREGROUND_SERVICE`, `POST_NOTIFICATIONS` (playback notification).

---

### v1.2.1
- **Bug fix**: Floating controls overlay now automatically hides when returning to the Reader screen — previously the overlay remained visible after tapping the 🧭 Navigate button or opening a book from the Library while TTS was playing.

---

### v1.2.2
- **Bug fix**: Floating controls Navigate (🧭) button now scrolls to the current TTS paragraph every time — previously it only worked on the first tap; after scrolling on the reading page it would stop working.
- **Bug fix**: Floating controls overlay now hides instantly when the Navigate button is tapped — previously a race condition could leave the overlay visible on top of the Reader screen.
- **Bug fix**: Floating controls overlay now hides correctly when returning to the Reader from the Library while TTS is playing.

---

### v1.3.0
- **Feature**: Replacement list now shows the order number for each entry.
- **Feature**: Order number is editable in the Add/Edit dialog — type any number to set exact position.
- **Feature**: Regex support — check "Use Regex" in the Add/Edit dialog to use standard regex patterns as the find rule (e.g. find `(ด){3,}` → replace `ดด`). Regex entries are marked with **Rx** in the list. Works for both TTS and visual (on-screen) replacements.

---

### v1.4.0

**Floating TTS Controls — Paragraph Text Display**
- The floating overlay now shows the text of the paragraph currently being read at the top of the panel.
- Pinch anywhere on the overlay to expand or shrink the text display area — more lines visible on pinch-out, fewer on pinch-in (font size unchanged).

**Floating TTS Controls — Stop Button**
- Added a small ✕ red badge button at the top-right corner of the overlay to stop TTS immediately.

**Reader Toolbar — Paragraph Skip with Auto-scroll**
- When TTS is active, the **‹** and **›** buttons now skip to the previous / next paragraph **and** automatically scroll the reader to show the highlighted paragraph.

**Reader Toolbar — Auto-scroll Toggle**
- New **⇅** toggle button in the bottom toolbar. When on, the reader follows the TTS paragraph automatically as playback advances — no need to tap 📍 each time.

**Reader Toolbar — Stop TTS Button**
- Added a dedicated **⏹ Stop** button directly in the bottom toolbar (next to play/pause) for quick access without opening the TTS panel.

**Duplicate EPUB Detection**
- Opening an EPUB file with the same filename and file size as an existing book now opens the existing book instead of creating a duplicate entry in the library.

**Bug fixes**
- Fixed: TTS controls disappearing after skip → stop → navigate back → play sequence.
- Fixed: Book being added to library repeatedly when pressing back from an externally opened EPUB.
- Fixed: Floating TTS overlay appearing after pressing back even though TTS had already bee n stopped.
- Fixed: Could not open a duplicate EPUB from the system file manager while reading a different book.

---

### v1.4.1

**Floating TTS Controls — Compact Layout**
- Merged the two button rows into a single row: **Navigate → Add Replacement → ⏮ → ⏸/▶ → ⏭**.

**Floating TTS Controls — Stop Button Redesign**
- The ✕ stop button is now a small plain text character, transparent background, positioned flush to the top-right corner of the overlay with no padding or margin.

---

### v1.4.2

**Library — Search / Filter**
- Added a **Search** text field in the bookshelf toolbar, immediately after the "Shiori" title.
- Type any text to instantly filter the book list by title or filename (case-insensitive).
- A small **✕** clear button appears inline when there is text to erase.
- Applies to all three view modes: Thumbnail, List, and Detail.

---

### v1.4.3

**Multi-language TTS**
- TTS language selection now uses **checkboxes** instead of radio buttons — enable Thai, English, and/or Chinese (Simplified) simultaneously.
- When multiple languages are enabled, each paragraph is automatically split into segments by Unicode script range and spoken with the appropriate language voice:
  - Thai characters (U+0E00 – U+0E7F) → Thai TTS engine
  - Latin characters (A–Z / a–z) → English TTS engine
  - CJK characters (U+4E00 – U+9FFF, U+3400 – U+4DBF) → Chinese TTS engine
  - Neutral characters (spaces, digits, punctuation) inherit the current segment's language — no choppy micro-pauses.
- A book with mixed Thai–English content (e.g. Thai prose with English proper nouns) will now pronounce each part correctly without any manual setup.
- At least one language must remain checked.

**Bug fix — chapter pre-buffering after paragraph skip**
- Pressing **‹** or **›** while TTS was playing could corrupt the previous/next chapter pre-buffer.
- Root cause: Android TTS fires an `onDone` callback even for utterances cancelled by `tts.stop()`. The stale callback was advancing the chapter counter or firing `onAllParagraphsDone` prematurely, which cleared the chapter buffer at the wrong time.
- Fixed by embedding a **speaker sequence number** in every utterance ID. `onDone` and `onError` now discard any callback whose embedded sequence number does not match the current value — stale callbacks from skipped utterances are silently ignored.

---

### v1.4.4

**TTS Preview buttons in replacement dialogs**
- Added a **▶ Play** button to the right of the **Find (from)** field and the **Replace with (to)** field in all three replacement dialogs:
  - **Edit Replacement** — the Add/Edit dialog in the Text Replacement screen.
  - **Add Replacement from reader** — the popup that opens when you tap **+ Add to Replacement** from the word-selection context menu.
  - **Add Replacement from floating overlay** — the **✏️ Add Replacement** popup opened from the floating TTS controls.
- Tapping **▶** reads the current field text aloud using TTS. Script is auto-detected per the same rules as main TTS (Thai / Chinese / Latin).
- While the field is being read, the button changes to a **■ Stop** icon so you can see which field is playing.
- Tapping **■** while playing stops playback immediately and reverts to **▶**.
- When TTS finishes reading, the button reverts to **▶** automatically.
- Each dialog creates its own lightweight TTS instance that is independent of the main book TTS — preview does not interrupt or affect book playback state.

### v1.5.0

**Per-language TTS Settings — Pitch, Speed, and Voice**

- **Per-language Pitch (Tone)** — Each enabled TTS language (Thai / English / Chinese) now has its own **Pitch** slider (×0.5 – ×2.0), placed above the Speed slider in Settings → TTS Language. Pitch is applied per-segment when switching between languages mid-paragraph.
- **Per-language Speed** — Each language has its own **Speed** slider (×0.5 – ×3.0), replacing the previous single global Speed slider. On first upgrade, existing users keep their saved speed as the default for all languages.
- **Per-language Voice selection** — A **Voice** dropdown appears under each language's sliders, showing all voices available from the TTS engine for that language, sorted by quality. Select "Default" to use the engine's automatic choice.
- **TTS Voice Preview** — A **▶ Play** button sits beside a sample sentence below each language's sliders. Tap it to hear the currently selected pitch, speed, and voice. The button becomes **■** while playing and reverts to **▶** when done or tapped again.
  - Thai: "สวัสดีครับ นี่คือตัวอย่างเสียงภาษาไทย"
  - English: "Hello, this is a sample of English speech."
  - Chinese: "你好，这是中文语音示例。"
- **TTS Engine selector** — If the device has more than one TTS engine installed (e.g., old and new Google TTS), a **TTS Engine** dropdown appears in the Text-to-Speech settings section. Switching engines reloads the voice lists for all languages and uses that engine for both preview and book playback.

---

### v1.6.0

**Reader TTS Panel — Per-language Controls & Improved Layout**

- **Per-language controls in Reader** — The TTS panel in the reader view now shows individual **Pitch** and **Speed** sliders for every enabled language (Thai / English / Chinese), matching the per-language settings in the Settings screen.
- **Per-language on/off toggle** — A **checkbox** beside each language name lets you enable or disable that language directly from the reader TTS panel without going to Settings.
- **Playback controls moved to bottom** — The control row (⏮ / ▶ / ⏸ / ⏭ / ⏹ / ⊙) is now anchored at the **bottom** of the TTS panel, keeping language sliders at the top.
- **Tap outside to close panel** — Tapping anywhere on the book content while the **TTS panel** or **Font Settings panel** is open now dismisses the panel immediately.

---

## ❤️ Support & Donate

If this app has improved your reading experience, saved you time, or you just want to support its continued development, please consider donating!

Your support is incredibly appreciated, helps fix bugs, and keeps this project alive and growing. 🙏

https://buymeacoffee.com/endofday

<a href="https://www.buymeacoffee.com/endofday" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>

---
**Built with ❤️ for readers everywhere**
