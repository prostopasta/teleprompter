# 📹 Browser Teleprompter & Video Pitch Recorder

[![Live Demo](https://img.shields.io/badge/Live%20Demo-GitHub%20Pages-00d2aa?style=for-the-badge&logo=github)](https://prostopasta.github.io/teleprompter/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/Dependencies-0%20(Vanilla%20JS)-blue?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![Privacy First](https://img.shields.io/badge/Privacy-100%25%20Client--Side-success?style=for-the-badge)](https://developer.mozilla.org/en-US/docs/Web/API/MediaStream_Recording_API)

A lightweight, zero-dependency, privacy-first in-browser teleprompter and video recorder. Built specifically for recording job pitches, presentations, async video intros, demos, and speeches with flawless eye contact and zero stress.

**🚀 [Launch Live Web App](https://prostopasta.github.io/teleprompter/)**

---

## ✨ Why This Project?

Most online teleprompters and recording tools suffer from one or more drawbacks:
- 🚫 **Paywalls & Subscriptions** for basic video recording.
- 🚫 **Watermarked exports** or resolution limits.
- 🚫 **Privacy risks** — uploading your camera feed and voice to third-party cloud servers.
- 🚫 **Clunky interfaces** that make you look away from the camera lens.

This application is **100% free, open-source, and runs entirely inside your browser**. **Zero bytes of video or audio ever leave your computer.**

---

## 🎯 Key Features

- 👁️ **Eye-Line Contact Guide:** A dedicated guideline positioned right at the top 25% of your screen directly beneath the webcam lens, keeping your gaze natural and focused on your audience.
- 🪞 **Ghost Camera Mirror & Draggable PiP:** Displays your live webcam feed behind the scrolling prompter text or in a draggable PiP box, allowing you to monitor your posture, lighting, and framing in real time.
- 📹 **Integrated HD Video Recording:** Records crisp 1080p video directly from your webcam with support for both universal **MP4 (H.264/AAC)** and high-quality **WebM (VP9/VP8/Opus)**.
- 🎙️ **Microphone Audio Level (VU) Meter:** Real-time Web Audio API frequency analysis visualizer ensures your microphone is live and balanced before you start speaking.
- ⏱️ **3-2-1 Action Countdown:** Smooth 3-second animated countdown overlay gives you time to smile, center yourself, and breathe before recording and scrolling begins.
- 💾 **Instant Auto-Save & Take Review Player:** When you finish or hit <kbd>Esc</kbd> / <kbd>S</kbd>, the video take is automatically downloaded directly to your local `Downloads` folder, and an instant preview player opens with take duration, file size, and retake controls.
- ⚙️ **Fully Customizable Prompter:**
  - **Scroll Speed:** Precision adjustment from `0.5x` to `8.0x`.
  - **Font Sizing:** Adjustable from `20px` to `72px`.
  - **Column Width:** Adaptable from `250px` to `1000px` (optimizing for 2–4 words per line for minimal horizontal eye movement).
  - **Paragraph Gap:** Adjust spacing between thoughts from `0.00em` to `2.00em`.
- ⌨️ **Comprehensive Keyboard Shortcuts:** Control playback, speed, font, and review with simple single-key shortcuts.
- 📄 **Markdown & Text File Support:** Load any `.md` or `.txt` speech script from disk via the "📂 Open .md File" picker, or place a `script.md` file next to `index.html` for instant auto-loading. Headings, bold text, italics, and bullet lists are automatically formatted.
- 💾 **Automatic Local Persistence:** Custom text edits and prompter preferences are automatically saved in browser `localStorage`.
- 🔌 **100% Offline & Zero Dependencies:** Pure HTML5, CSS3, and Vanilla JavaScript in a single lightweight file. No `npm`, no bundlers, no external CDNs.

---

## ⌨️ Keyboard Shortcuts Reference

| Key | Action |
|---|---|
| <kbd>Space</kbd> | **Play / Pause** scroll and recording |
| <kbd>Esc</kbd> or <kbd>S</kbd> | **Stop & Preview Take** (Auto-saves video & opens review player) |
| <kbd>R</kbd> | **Reset** prompter to top & reset timer |
| <kbd>↑</kbd> / <kbd>↓</kbd> | **Speed Up / Slow Down** scrolling speed |
| <kbd>[</kbd> / <kbd>]</kbd> | **Decrease / Increase** font size |
| <kbd>F</kbd> | **Toggle Fullscreen** mode |

---

## 🔒 Privacy & How It Works (Zero Cloud Storage Needed)

### Does it require a backend or cloud storage?
**No.** All video encoding and downloading happens **100% client-side** directly inside the browser using modern Web APIs:

```
[Webcam & Mic]
      ↓ (WebRTC getUserMedia)
[MediaStream Track] ──> [Web Audio API Analyser (VU Meter)]
      ↓
[MediaRecorder API (Client-Side Encoding)]
      ↓
[In-Memory Binary Blob (Local RAM)]
      ↓ (URL.createObjectURL)
[Native Browser File Download to your Machine]
```

- **Video Processing:** Frames from `navigator.mediaDevices.getUserMedia` are passed into the browser's native `MediaRecorder` API.
- **File Creation:** When you stop recording, binary chunks are assembled into a local `Blob`.
- **Instant Save:** A local `blob:` URL triggers a native browser download (`<a download>`). No network traffic is generated.
- **Zero Telemetry / Zero Tracking:** No analytics, cookies, or external trackers.

---

## 🚀 Quick Start

### 1. Online (GitHub Pages)
Visit **[https://prostopasta.github.io/teleprompter/](https://prostopasta.github.io/teleprompter/)** in any modern web browser (Chrome, Brave, Edge, Firefox, Safari).

### 2. Run Locally / Completely Offline
You can run this project locally without any web server or internet connection:

```bash
# Clone the repository
git clone https://github.com/prostopasta/teleprompter.git

# Open index.html in your browser
xdg-open teleprompter/index.html   # Linux
open teleprompter/index.html       # macOS
start teleprompter/index.html      # Windows
```

Or run a local static server:
```bash
cd teleprompter
python3 -m http.server 8080
# Open http://localhost:8080 in your browser
```

---

## 🛠️ Browser Compatibility

| Browser | Camera Preview | Audio Meter | MP4 Recording | WebM Recording |
|---|:---:|:---:|:---:|:---:|
| **Google Chrome / Chromium** | ✅ | ✅ | ✅ | ✅ |
| **Brave** | ✅ | ✅ | ✅ | ✅ |
| **Microsoft Edge** | ✅ | ✅ | ✅ | ✅ |
| **Mozilla Firefox** | ✅ | ✅ | ⚠️ *(OS dependent)* | ✅ |
| **Apple Safari** | ✅ | ✅ | ✅ | ⚠️ *(VP8/VP9 optional)* |

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

Developed with ❤️ by **[Pavel Statsenko](https://github.com/prostopasta)**.
