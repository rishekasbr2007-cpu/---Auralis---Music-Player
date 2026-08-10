# Auralis — Music Library & Audio Player

**Auralis** is a modern, zero-dependency single-page HTML5/CSS3/JavaScript web application for listening to and organizing a audio collection. It features a dark emerald visual design, dynamic vinyl rotation animations, full player bar controls, real-time search, interactive queueing, favorites management, and keyboard shortcuts.

---

## 🎵 Project Overview

- **Architecture**: Single-page application (SPA) with zero external frameworks or build steps.
- **Audio Library**: Includes **198 pre-loaded tracks** (`01.mp3` through `198.mp3`) stored in the `songs/` directory.
- **Track Diversity**: Spans multiple genres including Lofi, Instrumental, Chill, Corporate/Vlog, Acoustic Guitar, Cinematic, Indian Classical, and Devotional Mantras.

---

## ✨ Key Features

### 1. Music Navigation & Filtering
- **Library View**: Browse the entire library of 198 tracks with track numbers, procedural color artwork badges, title, and artist info.
- **Favorites View**: Quick access to bookmarked songs. Persistence is powered by browser `localStorage` (`verdant_favs`).
- **Queue View**: Manage an "Up Next" queue of custom selected songs (`verdant_queue`).
- **Recently Played**: Automatically keeps track of your 20 most recent plays (`verdant_recent`).
- **Real-Time Search**: Instant filtering by track title or artist name as you type.

### 2. Audio Playback & Visual Controls
- **Full Player Bar**: Persistent bottom bar featuring:
  - Play / Pause toggle
  - Next / Previous track controls
  - Shuffle mode toggle
  - 3-State Repeat mode (Off / Repeat All / Repeat One)
  - Audio seek bar with live time progress (`mm:ss`)
  - Volume slider and Mute toggle
  - Animated CSS equalizer bar on active playing tracks
- **Fullscreen "Now Playing" Modal**:
  - Clickable player bar opens a fullscreen modal with a spinning vinyl record animation synced to audio playback state.

### 3. Keyboard Shortcuts
- `Space`: Play / Pause toggle (when not typing in search input)
- `ArrowRight`: Skip to next track
- `ArrowLeft`: Return to previous track (or restart current track if elapsed time > 3 seconds)
- `Escape`: Close the fullscreen Now Playing modal

### 4. Responsive Design
- Built-in media queries that seamlessly adjust layout for desktop and mobile screen sizes.

---

## 🛠️ Tech Stack & Dependencies

- **Frontend Core**: HTML5, CSS3, Vanilla JavaScript (ES6+).
- **Styling**: Native CSS variables, CSS Grid, Flexbox, HSL gradient palettes, and CSS Keyframe animations.
- **Typography** (via Google Fonts):
  - **Fraunces**: Serif headings & branding wordmark
  - **Manrope**: Primary UI font
  - **JetBrains Mono**: Track numbers and time code display
- **State Persistence**: Browser `localStorage` API.

---

## 📁 Project Structure

```text
Auralis Music Player/
├── index.html        # Main application file (HTML, CSS design system, JS audio engine)
├── README.md         # Project documentation
└── songs/            # Audio storage directory
    ├── 01.mp3
    ├── 02.mp3
    ├── ...
    └── 198.mp3        # 198 MP3 audio files
```

---

## 🚀 How to Run

Because this project uses native web technologies without npm dependencies or build tools, running it is simple:

1. **Direct File Open**:
   Double-click `index.html` or drag it into any modern web browser (Google Chrome, Mozilla Firefox, Microsoft Edge, Safari).

2. **Local HTTP Server** (Optional):
   Run a local server from the project directory:
   ```bash
   npx serve .
   ```
   Or use extensions like VS Code **Live Server**.

---

## ➕ Adding New Songs

To add new tracks to the player:

1. Place your `.mp3` file inside the `songs/` folder.
2. Open `index.html` and locate the `TRACKS` array inside the `<script>` tag.
3. Add a new object to the array following this format:
   ```javascript
   {
     "id": 199,
     "title": "Your Song Title",
     "artist": "Artist Name",
     "src": "songs/199.mp3",
     "color": "linear-gradient(135deg, #0F9D68, #C9A227)"
   }
   ```
