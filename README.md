# Raki-Chatapp

Raki-Chatapp is a native Android chat application built with Kotlin and Jetpack Compose.  
It demonstrates Firebase-based authentication and real-time messaging using a simple, maintainable architecture.

## Overview

This project was built to implement core chat functionality on Android without managing custom backend infrastructure. Firebase is used for authentication and data storage, while the Android client is structured for clarity and incremental feature growth.

Current implementation includes:

- user registration and login
- one-to-one messaging
- real-time chat updates
- profile-related user data handling
- Compose-based UI screens for authentication and chat flows

## Architecture

The app follows MVVM with a repository layer to separate UI logic, state management, and data access.

### Layers

- **UI (Jetpack Compose)**  
  Composable screens and UI state rendering.

- **ViewModel**  
  Handles screen state, business rules, and asynchronous operations.

- **Repository**  
  Encapsulates Firebase interactions and exposes clean data APIs to ViewModels.

- **Firebase**  
  Authentication and persistent chat/user data storage.

### Data flow

1. User actions are triggered from Compose screens.
2. ViewModel validates input and executes use-case logic.
3. Repository performs reads/writes against Firebase services.
4. Updated state is emitted back to the UI.

## Tech Stack

- **Language:** Kotlin
- **UI:** Jetpack Compose
- **Architecture:** MVVM + Repository pattern
- **Backend:** Firebase Authentication, Firestore/Realtime Database, Firebase Storage
- **Async:** Kotlin Coroutines and Flow
- **Build:** Gradle (Kotlin DSL)
- **Navigation:** Jetpack Navigation

## Project Structure

```text
z_RaKi/MyApplication/
├── app/
│   ├── src/main/
│   │   ├── AndroidManifest.xml
│   │   ├── java/com/example/myapplication/
│   │   │   ├── MainActivity.kt
│   │   │   └── ui/
│   │   │       ├── chat/
│   │   │       ├── login/
│   │   │       ├── personal/
│   │   │       └── signup/
│   │   └── res/
│   ├── build.gradle.kts
│   └── google-services.json
├── build.gradle.kts
└── settings.gradle.kts
```

## Setup and Run

### Prerequisites

- Android Studio (recent stable version)
- JDK 17+
- Firebase project (recommended for production/testing isolation)

### Steps

1. Clone the repository:

   ```bash
   git clone https://github.com/rahulrathnavel/Raki-Chatapp.git
   cd Raki-Chatapp
   ```

2. Open the Android project in Android Studio:

   - Open `Raki-Chatapp/z_RaKi/MyApplication`

3. Configure Firebase:

   - Create/select a Firebase project
   - Register Android app package (currently expected: `com.example.RaKi`, confirm in source)
   - Download `google-services.json`
   - Replace `app/google-services.json`

4. Build and run from Android Studio on an emulator or physical device.

## Current Status

Implemented:

- authentication (sign up / login)
- real-time chat basics
- Compose-based chat/auth screens

Planned:

- push notifications (FCM)
- media sharing
- group messaging
- dark theme improvements
- offline caching (Room)

## Contributing

Contributions are welcome.

1. Fork the repository
2. Create a feature branch
3. Commit focused changes with clear messages
4. Open a pull request with implementation details
