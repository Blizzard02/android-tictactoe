# Tic Tac Toe (Android)

A simple 2-player Tic Tac Toe game built for Android.

## Features
- Local 2-player gameplay on a single device
- Win detection across rows, columns, and diagonals
- Running score tracker for both players, with a "who's winning" indicator
- Reset button to start a new round without losing the score

## Tech stack
- Java, Android SDK (minSdk 24, target/compile SDK 33)
- ConstraintLayout for the UI
- Gradle build (wrapper included — open in Android Studio or run `./gradlew assembleDebug`)

## Project structure
- `app/src/main/java/com/example/tictactoe/MainActivity.java` — game logic (board state, win checking, scoring)
- `app/src/main/res/layout/activity_main.xml` — the 3x3 board UI
