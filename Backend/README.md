# Spotify Backend Service

This is the backend service for the Spotify Full-Stack Music App.
It provides RESTful APIs for fetching album data and playlist details, and serves static audio resources for music playback.

---

## Overview

The backend is built using Kotlin and Ktor, following a lightweight service-oriented architecture.
It handles client requests from the frontend and returns structured JSON data.

---

## Tech Stack

* Kotlin
* Ktor (HTTP server framework)
* Gradle (build tool)
* JSON (data storage)

---

## Project Structure

```id="qk4b8g"
Backend/
├── src/main/kotlin/com/laioffer/
│   └── Application.kt        # Entry point of the server
├── src/main/resources/
│   ├── feed.json             # Album feed data
│   ├── playlists.json        # Playlist data
│   └── static/songs/         # Audio files
├── build.gradle.kts
└── settings.gradle.kts
```

---

## Features

* Provide album feed data via REST API
* Provide playlist details based on album ID
* Serve static audio files for streaming
* Lightweight backend with no external database dependency

---

## API Endpoints

| Method | Endpoint         | Description                   |
| ------ | ---------------- | ----------------------------- |
| GET    | `/feed`          | Retrieve album feed           |
| GET    | `/playlist/{id}` | Retrieve playlist by album ID |

---

## How to Run

### 1. Navigate to Backend directory

```id="z6ycb2"
cd Backend
```

### 2. Start the server

```id="xk8p3s"
./gradlew run
```

### 3. Server will run at

```id="6p2r8n"
http://localhost:8080
```

---

## Example Requests

```id="f8h2lm"
GET http://localhost:8080/feed
```

```id="4t9w1k"
GET http://localhost:8080/playlist/1
```

---

## Design Notes

* The backend uses JSON files instead of a database to simplify development and focus on API design.
* Static resources (audio files) are served directly by the server.
* The architecture separates data handling and API routing for clarity and maintainability.

---

## Future Improvements

* Add database support (e.g., MySQL or PostgreSQL)
* Implement user authentication and authorization
* Support dynamic playlist creation and persistence
* Add caching for improved performance

---

## Author

Yixun Li
