# Reverse Engineering and Decoding Process

## Overview
This project involves reverse engineering an APK file to rebuild and analyze its structure, extract resources, and ultimately decode the challenge presented in the game. The final objective was to successfully play the game and uncover the hidden message.

---

## Tools Used
- [Java Decompiler](http://www.javadecompilers.com/apk): To decompile the APK and obtain source files.
- **Android Studio**: To rebuild the app and debug the game.
- **Text Editor**: To clean and modify code, including removing invisible characters.

---

## Steps to Decode the APK

### 1. Decompiling the APK
I used [Java Decompiler](http://www.javadecompilers.com/apk) to decompile the APK file. This provided access to the source code and resource folders, which included the `sources` and `res` directories.

### 2. Rebuilding the Project in Android Studio
- Created a new Android Studio project.
- Imported the `.java` activity files from `\sources\com\classy\survivegame` into the new project.

### 3. Modifying the Manifest
- Updated the `AndroidManifest.xml` file to include all required activities.
- Added the necessary theme and internet permissions from the `res` folder.

### 4. Importing Layouts and Drawables
- Added activity layouts from `\resources\res\layout`.
- Imported corresponding drawable files from `\resources\res\drawable`.

### 5. Adding Themes and Colors
- Integrated `Theme.SurviveGame` from `\resources\res\values-night` and `\resources\res\values`.
- Imported relevant colors to match the original theme.

### 6. Retrieving and Cleaning the URL
- Retrieved the URL from `\resources\res\values\strings.xml`.
- Removed invisible characters from the URL to ensure it was functional.

---

## The Game
After completing the above steps, I successfully rebuilt the game. Here's how the game works:
- The game asks the player to submit their ID.
- Each character in the ID is processed using a modulo operation (`% 4`), determining the direction the player must press:
  - `0`: Left (`game_BTN_left`)
  - `1`: Right (`game_BTN_right`)
  - `2`: Up (`game_BTN_up`)
  - `3`: Down (`game_BTN_down`)

By playing the game and completing the game, I received the message: **"Survived in Pennsylvania"**.

---

## Conclusion
This project provided valuable hands-on experience with reverse engineering and working with APK files. By carefully analyzing and reconstructing the app, I was able to uncover the hidden message and understand the game mechanics.
