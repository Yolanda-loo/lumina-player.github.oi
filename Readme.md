# 🎬 Lumina Player

**Lumina Player** is a high-performance, custom HTML5 video player built entirely with **Vanilla JavaScript**. It features a modern, responsive UI, persistent playback state (LocalStorage), Picture-in-Picture support, and a playlist system—all without external dependencies or heavy frameworks.

## ✨ Key Features

* **Zero Dependencies:** Pure Vanilla JS (ES6+), HTML5, and CSS3.
* **Persistent State:** Uses `LocalStorage` to remember the last played video, exact timestamp, and volume preferences even after the browser is closed.
* **Playlist System:** Responsive sidebar playlist with auto-advance functionality.
* **Advanced Controls:**
* Picture-in-Picture (PiP) mode.
* Playback speed controls (0.5x - 2x).
* WebVTT Caption/Subtitle support with custom styling.
* Keyboard shortcuts (`K`/Space to play, `F` for fullscreen, `M` to mute).


* **Responsive Design:** CSS Grid layout that adapts gracefully from desktop to mobile.
* **Accessibility:** ARIA labels and keyboard navigation support.

## 🛠️ Tech Stack

* **Core:** HTML5 Video API
* **Styling:** CSS3 (Flexbox, Grid, CSS Variables)
* **Logic:** Vanilla JavaScript (Event-driven architecture)
* **Icons:** Inline SVG (No font libraries required)

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Yolanda-loo/lumina-player.git
cd lumina-player

```

### 2. Run Locally

Due to browser security policies regarding CORS (specifically for loading WebVTT subtitles), you must run this project on a local server rather than opening the HTML file directly.

**Using VS Code:**

1. Install the "Live Server" extension.
2. Right-click `index.html` and select **"Open with Live Server"**.

**Using Python:**

```bash
# If you have Python 3 installed
python -m http.server 8000

```

Then open `http://localhost:8000` in your browser.

## 📂 Project Structure

```text
lumina-player/
│
├── index.html          # Main application structure (CSS/JS embedded for portability)
├── subtitles-en.vtt    # Sample WebVTT caption file
└── README.md           # Documentation

```

## 🧠 Architecture Highlights

### Event-Driven UI

The player relies on native media events (`timeupdate`, `loadedmetadata`, `waiting`, `ended`) to drive the UI. This ensures the visual state (progress bar, time display) never desyncs from the actual video state.

### Persistence Logic

To create a "Netflix-like" resume experience, the app utilizes `LocalStorage`:

* **Volume/Index:** Saved instantly on change.
* **Time:** Saved on `pause`, `beforeunload`, and periodically every 5 seconds (to handle crashes).
* **Restoration:** On boot, the app checks for stored keys and restores the user's specific context.

### Custom CSS Styling

The UI uses CSS Variables (`--primary-color`, `--bg-color`) for easy theming. The caption text is styled using the `::cue` pseudo-element to match the application's aesthetic.

## 🎮 Keyboard Shortcuts

| Key | Action |
| --- | --- |
| **Space** / **K** | Play / Pause |
| **F** | Toggle Fullscreen |
| **M** | Mute / Unmute |
| **Arrow Right** | Forward 5 seconds |
| **Arrow Left** | Rewind 5 seconds |
| **P** | Toggle Picture-in-Picture |
| **C** | Toggle Captions |

## 🔮 Future Improvements

* [ ] Add thumbnail previews on hover over the progress bar.
* [ ] Support for HLS (.m3u8) streaming.
* [ ] "Skip Intro" button logic.

## 📄 License

This project is open source and available under the [MIT License](https://www.google.com/search?q=LICENSE).
