# MiniSpotify Android Client (Frontend)

This is the Android client (frontend) for the MiniSpotify project.
It provides the UI for browsing the music feed, viewing playlists, and playing songs by communicating with the backend service.

---

## Overview

The client is built with Kotlin and Jetpack Compose.
It follows a layered architecture with MVVM, and uses Retrofit for API communication.
Favorites are stored locally using Room.

---

## Tech Stack

* Kotlin
* Android Jetpack Compose
* MVVM (ViewModel + StateFlow)
* Retrofit + OkHttp (REST API)
* Room (local favorites)
* Hilt (dependency injection)
* Navigation Component (Safe Args)

---

## Project Structure

```id="front-structure"
Frontend/
├── app/
│   ├── src/main/java/com/laioffer/spotify/
│   │   ├── ui/                 # Compose screens (Home/Favorite/Playlist/Player)
│   │   ├── repository/         # Data repositories
│   │   ├── network/            # Retrofit API + network module
│   │   ├── database/           # Room database/dao/module
│   │   └── datamodel/          # Data models (Album/Playlist/etc.)
│   ├── src/main/res/           # Resources
│   └── build.gradle            # Android module config
└── build.gradle                # Project config
```

---

## Features

* Browse album feed from backend
* View playlist details for a selected album
* Play audio with an in-app player UI
* Add/remove favorite albums (stored locally via Room)
* Clean navigation flow between screens

---

## Configuration

The app expects the backend service to be running locally.
If your emulator/device cannot access `localhost`, use `10.0.2.2` for Android Emulator.

Common base URLs:

* Android Emulator: `http://10.0.2.2:8080`
* Physical device (same Wi-Fi): `http://<your-computer-ip>:8080`

Update the base URL in the network layer (Retrofit configuration) if needed.

---

## How to Run

1. Open `Frontend/` in Android Studio (or open the root project and select the Android module).
2. Sync Gradle.
3. Start the backend service (see `Backend/README.md`).
4. Run the app on an emulator or device.

---

## API Endpoints Used

| Method | Endpoint         | Description            |
| ------ | ---------------- | ---------------------- |
| GET    | `/feed`          | Fetch album feed       |
| GET    | `/playlist/{id}` | Fetch playlist details |

---

## Notes

* Favorites are stored locally using Room (no backend persistence for favorites).
* If you see network errors on emulator, confirm the base URL uses `10.0.2.2` instead of `localhost`.

---

## Author

Yixun Li
