# MiniSpotify Full-Stack Music App

MiniSpotify is a full-stack music streaming application that simulates core Spotify features.
It consists of an Android client (built with Kotlin and Jetpack Compose) and a backend service (built with Kotlin and Ktor).

---

## Overview

This project demonstrates a complete client-server architecture:

* The **Android app** provides the user interface for browsing albums, viewing playlists, and playing music
* The **backend service** provides RESTful APIs and serves static audio resources
* Communication is handled through HTTP requests

---

## Tech Stack

### Frontend (Android)

* Kotlin
* Jetpack Compose
* MVVM (ViewModel + StateFlow)
* Retrofit + OkHttp
* Room (local favorites storage)
* Hilt (dependency injection)

### Backend

* Kotlin
* Ktor (Netty server)
* kotlinx.serialization
* JSON-based data storage

---

## Project Structure

```id="root-structure"
MiniSpotify/
├── Backend/     # Ktor backend service (APIs + static audio)
├── Frontend/    # Android app (Jetpack Compose)
├── .gitignore
└── README.md
```

---

## Features

### Core Features

* Browse album feed
* View playlist details
* Play music from backend server

### Android App

* Modern UI built with Jetpack Compose
* Navigation between screens (Home / Playlist / Player / Favorites)
* Local favorites storage using Room

### Backend

* RESTful API for album and playlist data
* JSON-based data management
* Static serving of audio files

---

## System Architecture

```id="arch"
Android App (Frontend)
        |
        |  HTTP (Retrofit)
        v
Ktor Backend Server
        |
        |  JSON Files (feed / playlists)
        v
 Local Data + Static Audio Files
```

---

## How to Run

### 1. Start Backend

```id="run-backend"
cd Backend
./gradlew run
```

Backend runs at:

```id="backend-url"
http://localhost:8080
```

---

### 2. Run Android App

* Open `Frontend/` in Android Studio
* Sync Gradle
* Run on emulator or device

Important:

* Emulator base URL: `http://10.0.2.2:8080`
* Physical device: use your computer IP

---

## API Overview

| Method | Endpoint         | Description          |
| ------ | ---------------- | -------------------- |
| GET    | `/feed`          | Fetch album feed     |
| GET    | `/playlists`     | Fetch all playlists  |
| GET    | `/playlist/{id}` | Fetch playlist by ID |

---

## Key Design Decisions

* Used **Ktor** for a lightweight and simple backend
* Used **JSON instead of database** for easier setup and focus on API design
* Used **MVVM architecture** on Android for separation of concerns
* Used **Room** for local persistence (favorites)

---

## What I Learned

* Building a full-stack system with clear separation between client and server
* Designing REST APIs and integrating them with a mobile client
* Managing asynchronous data flow using coroutines and StateFlow
* Structuring a scalable Android application

---

## Future Improvements

* Add authentication and user system
* Replace JSON with a real database (MySQL / PostgreSQL)
* Deploy backend to cloud (AWS / GCP)
* Improve UI/UX and add animations

---

## Author

Yixun Li
