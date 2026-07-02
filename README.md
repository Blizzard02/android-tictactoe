# Tic Tac Toe (Android)

A simple 2-player Tic Tac Toe game built for Android.

![screenshot placeholder](https://placehold.co/900x500?text=Screenshots+coming+soon)

## Features
- Local 2-player gameplay on a single device
- Win detection across rows, columns, and diagonals
- Running score tracker for both players, with a "who's winning" indicator
- Reset button to start a new round without losing the score

## Tech stack
- Java, Android SDK (minSdk 24, target/compile SDK 33)
- ConstraintLayout for the UI
- Gradle build (wrapper included — open in Android Studio or run `./gradlew assembleDebug`)

## Setup

```bash
git clone https://github.com/Blizzard02/android-tictactoe.git
cd android-tictactoe
./gradlew assembleDebug   # or open the folder directly in Android Studio and Run
```

No API keys or extra configuration needed — it builds and runs as-is.

## Architectural decisions

- **Single Activity, no fragments.** The whole game is one screen with fixed state
  (a 3x3 board), so splitting it into fragments or introducing a navigation graph
  would add structure without adding value.
- **Board state as a flat `int[9]` array** (`gameState`) rather than a 2D grid —
  simpler to index by button ID (`btn_0`…`btn_8`) and to check the 8 fixed winning
  lines against.
- **View lookup by generated ID name** (`getIdentifier("btn_" + i, ...)`) instead of
  9 separate `findViewById` calls — keeps the button-wiring loop short and lets the
  board size change without touching this code.

## Folder structure

```
app/src/main/java/com/example/tictactoe/
  MainActivity.java        # game state, win checking, scoring, reset
app/src/main/res/
  layout/activity_main.xml # the 3x3 board + score UI
  values/                  # strings, colors, theme
build.gradle, settings.gradle, gradlew   # standard Gradle wrapper project
```

## Future improvements

- Single-player mode with a simple AI opponent
- Win-line highlight animation
- Persist score across app restarts
