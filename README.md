# BeatUp Engine 🎵

**BeatUp Engine** is a high-performance, lightweight 2D rhythm game engine and chart editor written in modern C++. It acts as a spiritual successor and standalone simulator for classic 6-key + spacebar arcade rhythm games. 

With zero input lag, perfect frame timings, and a fully featured modern UI, it offers both players and chart mappers the ultimate rhythm experience.

### Main Menu
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/MainMenu.png?raw=true)

## Chart Editor
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/BuEditor.png?raw=true)

## Patcher
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/BuPatcher.png?raw=true)

## ✨ Features

- **Modern C++ Architecture:** Fully rewritten to eliminate the input-lag and micro-stuttering found in older VB6 or C# rhythm game clients.
- **Beat-Based Hit Windows:** Judgment accuracy (Perfect, Great, Cool) is calculated mathematically in *Beats*, not milliseconds. This means higher BPM songs are authentically harder to perfect!
- **Built-in Chart Editor:** Create, modify, and test your own `.slk` and `.ssc` charts seamlessly. Features auto-play, variable playback speed, snap settings, and a metronome.
- **BeatUp Patcher:** A dedicated Song Select menu that instantly decrypts and loads custom `.bue` (charts) and `.san` (audio) files directly into RAM. Features background audio preloading for zero-latency previews.
- **Hardware Fullscreen:** Press `F` anytime to toggle flawless borderless hardware scaling (Pillarboxing) while keeping the original 4:3 arcade aspect ratio intact.
- **Integrity Checker & Update System:** Checks the repository for newer releases and verifies the integrity of your game assets every time you boot up the game.

## 🎮 Controls

### In-Game
- **Numpad 9, 6, 3:** Right lane arrows
- **Numpad 7, 4, 1:** Left lane arrows
- **Spacebar:** Middle receptor (Space / SLINE)
- **ESC:** Hold for 3 seconds to abort a song.
- **F:** Toggle Fullscreen

### Patcher (Song Select)
- **Up / Down Arrows:** Navigate songs (triggers instant audio preview)
- **Enter / Double Click:** Start Song
- **ESC:** Return to main menu

## 📁 Folder Structure

To run the game, ensure your directory looks like this:
```text
BeatUpEngine.exe
├── assets/
│   ├── arrows/
│   ├── backgrounds/
│   ├── bars/
│   ├── combo/
│   ├── font/
│   ├── game/
│   ├── sounds/
│   └── space/
└── patcher/
    ├── music/            (Encrypted .san audio files)
    └── script/
        ├── master.bue    (Encrypted song index)
        └── charts/       (Encrypted .bue chart files)
