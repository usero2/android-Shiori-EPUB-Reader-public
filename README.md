# Shiori EPUB Reader — v1.5.0

## Download

**[shiori-release-1.5.0.apk](shiori-release-1.5.0.apk)** (≈ 3.7 MB)

## Installation

1. Download the APK file above.
2. Enable **Settings → Security → Install unknown apps** for your browser or file manager.
3. Open the APK and tap **Install**.

Requires Android 8.0 (API 26) or higher.

---

## What's New in v1.5.0

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

[Full README and source](../../README.md)
