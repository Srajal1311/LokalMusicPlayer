# Lokal Music Player 🎵

A React Native music streaming application built using the JioSaavn public API.  
The app focuses on reliable audio playback, clean architecture, and consistent state synchronization between the mini player and full player views.

This project was built as part of a technical assignment with emphasis on **architecture, state management, and playback behavior** rather than visual polish.

---

## ✨ Features

- 🔍 Search songs using the JioSaavn API
- 📃 Paginated song listing
- ▶️ Full music player with play / pause and seek support
- 🎧 Background audio playback (continues when app is minimized or screen is off)
- 📌 Persistent Mini Player synced with the Full Player
- 🔄 Global playback state shared across screens
- 💾 Local state persistence for playback-related data

---

## 🏗 Architecture Overview

The application follows a **modular and separation-of-concerns–based architecture**:

- **UI Layer**  
  Screens and components are kept presentational and consume state from centralized stores.

- **State Management**  
  Playback-related state (current track, play/pause status, progress) is centralized to ensure:

  - Perfect synchronization between Mini Player and Full Player
  - Consistent behavior across navigation changes
  - Reliable updates during background playback

- **Audio Service Layer**  
  Audio playback is handled through a dedicated service abstraction, keeping playback logic decoupled from UI components.

This structure makes the app easier to maintain, reason about, and extend.

---

## 🧠 State Management

- Global playback state is centralized to avoid duplication across screens.
- Both Mini Player and Full Player subscribe to the same source of truth.
- This ensures that:
  - Play/Pause actions remain consistent everywhere
  - Playback state survives navigation changes
  - UI always reflects the actual playback status

---

## 🔊 Background Playback

The app supports background audio playback, meaning:

- Music continues when the app is minimized
- Music continues when the screen is locked

This behavior is essential for a real-world music streaming experience and was treated as a core requirement.

---

## 📦 Tech Stack

- **React Native (Expo)**
- **TypeScript**
- **React Navigation v6**
- **State Management:** Zustand
- **Audio Playback:** Native audio player integration
- **Storage:** Local persistence for playback-related data
- **API:** JioSaavn public API  
  Base URL: `https://saavn.sumit.co`

---

## 🚀 Getting Started

### Prerequisites

- Node.js (LTS recommended)
- npm or yarn
- Android Studio / Android device (for background playback testing)
- Expo CLI

### Installation

```bash
npm install
```

Running the App
npx expo start

Note: For full background playback support, the app should be run using an Android device or emulator rather than Expo Go.
