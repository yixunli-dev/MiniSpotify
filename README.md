# Spotify Full-Stack Music App

A full-stack music streaming application with a separated backend and frontend architecture.
This project simulates a simplified Spotify-like experience, including browsing albums, managing playlists, and playing music.

---

## Tech Stack

### Frontend

* React
* Ant Design
* Axios

### Backend

* Kotlin
* Ktor (REST API)
* JSON-based data storage

### Others

* RESTful API design
* Client-server architecture
* Git & GitHub

---

## Project Structure

```
Spotify/
├── Backend/     # Kotlin + Ktor backend service
├── Frontend/    # React frontend application
├── .gitignore
└── README.md
```

---

## Features

* Browse music albums and playlists
* Play songs with custom audio player
* View playlist details
* REST API integration between frontend and backend
* Clean UI with responsive layout

---

## How to Run

### 1. Clone the repository

```
git clone https://github.com/yixunli-dev/MiniSpotify.git
cd MiniSpotify
```

---

### 2. Run Backend

```
cd Backend
./gradlew run
```

Backend will start on:

```
http://localhost:8080
```

---

### 3. Run Frontend

```
cd Frontend
npm install
npm start
```

Frontend will start on:

```
http://localhost:3000
```

---

## API Overview

| Method | Endpoint         | Description          |
| ------ | ---------------- | -------------------- |
| GET    | `/feed`          | Get album feed       |
| GET    | `/playlist/{id}` | Get playlist details |

---

## What I Learned

* Designing a full-stack application with clear separation of concerns
* Building RESTful APIs using Kotlin and Ktor
* Connecting frontend and backend via HTTP requests
* Managing project structure for scalability

---

## Author

**Yixun Li**

---

## Notes

This project is for learning and demonstration purposes.
It showcases full-stack development skills and system design thinking.
