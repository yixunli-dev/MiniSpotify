# MiniSpotify Backend Service

This is the backend service for the MiniSpotify project.
It is built using Kotlin and Ktor, and provides RESTful APIs along with static audio resources for the Android client.

---

## Overview

The backend is a lightweight HTTP server built with Ktor.
It serves album and playlist data from local JSON files and provides endpoints for the frontend (Android app) to fetch and play music.

---

## Tech Stack

* Kotlin
* Ktor (Netty server)
* kotlinx.serialization (JSON parsing)
* Gradle

---

## Project Structure

```
Backend/
├── src/main/kotlin/com/laioffer/
│   └── Application.kt        # Server entry point & routing
├── src/main/resources/
│   ├── feed.json             # Album feed data
│   ├── playlists.json        # Playlist data
│   └── static/songs/         # Audio files (served as static resources)
├── build.gradle.kts
└── settings.gradle.kts
```

---

## Features

* Provide album feed data
* Provide playlist data and filtering by ID
* Serve static audio files for playback
* Simple and lightweight backend without database dependency

---

## API Endpoints

| Method | Endpoint         | Description                            |
| ------ | ---------------- | -------------------------------------- |
| GET    | `/`              | Health check (Hello World)             |
| GET    | `/feed`          | Retrieve album feed (from `feed.json`) |
| GET    | `/playlists`     | Retrieve all playlists                 |
| GET    | `/playlist/{id}` | Retrieve a specific playlist by ID     |

---

## Static Resources

Audio files are served via:

```
http://localhost:8080/songs/{filename}
```

Example:

```
http://localhost:8080/songs/solo.mp3
```

---

## How It Works

* Data is stored in JSON files (`feed.json`, `playlists.json`)
* Ktor reads and returns JSON responses
* Playlist endpoint parses JSON into Kotlin objects using `kotlinx.serialization`
* Static files are served using Ktor’s `static` routing

---

## How to Run

### 1. Navigate to Backend directory

```
cd Backend
```

### 2. Start the server

```
./gradlew run
```

### 3. Server will run at

```
http://localhost:8080
```

---

## Example Requests

```
GET http://localhost:8080/feed
```

```
GET http://localhost:8080/playlist/1
```

---

## Notes

* No database is used; all data is stored in local JSON files
* Static audio files are bundled inside the project
* Designed for simplicity and learning purposes

---

## Future Improvements

* Replace JSON files with a real database (e.g., MySQL)
* Add user authentication and authorization
* Support creating and modifying playlists
* Improve error handling and validation

---

## Author

Yixun Li
