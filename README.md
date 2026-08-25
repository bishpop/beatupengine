# 🎮 BeatUp Engine

**BeatUp Engine** is a high-performance, lightweight 2D rhythm game engine and chart editor written in modern C++. It acts as a spiritual successor and standalone simulator for classic 6-key + spacebar arcade rhythm games. 

Featuring low latency, precise frame timings, and a fully featured user interface, it provides both players and chart mappers with a robust rhythm gaming experience.

## ⭐ Main Menu
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/MainMenu.png?raw=true)

## ⭐ Chart Editor
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/BuEditor.png?raw=true)

## ⭐ Patcher
![BeatUp Engine UI Main Menu](https://github.com/bishpop/beatupengine/blob/main/BuPatcher.png?raw=true)

---

## 🖥️ System Requirements

### Operating System
* **Windows 10 / 11** (64-bit recommended)

### Build Dependencies (For Developers)
* **CMake** (Version 3.15 or higher)
* **Visual Studio** with C++ desktop development workload (MSVC)
* **SDL2** and **SDL2_image** development libraries
* **miniaudio** (integrated for audio playback)
* **Dear ImGui** (integrated for graphical user interface rendering)

---

## ⌨️ Hotkeys

### Global Hotkeys
* **Esc**: Back / Menu / Exit (In-game: Hold for 3 seconds to abort)
* **Ctrl + S**: Open Sound Settings

### Menu & Patcher (Song Select)
* **Up Arrow / Down Arrow**: Navigate through the song list
* **Enter / Numpad Enter**: Start the selected song

### Editor & Playback
* **F1**: Game Mode (Full screen gameplay)
* **F2**: Editor Mode (Chart timeline view)
* **F3**: Split View (Gameplay + Editor side-by-side)
* **F4**: Toggle Metronome
* **F5 / Spacebar**: Audio Play / Pause
* **F6**: Toggle Auto-Play
* **F7**: Stop playback and completely reset
* **Ctrl + Left Arrow**: Decrease playback speed (-5%)
* **Ctrl + Right Arrow**: Increase playback speed (+5%)
* **Ctrl + 0**: Reset playback speed to 100%

### Chart Editing
* **Left Click**: Place / Remove note
* **Right Click**: Open Context Menu (Auto-place, snap settings, etc.)
* **Ctrl + Click & Drag**: Draw a selection box to select multiple notes
* **Ctrl + A**: Select all notes
* **Ctrl + C**: Copy selection
* **Ctrl + V**: Paste selection
* **Ctrl + Z**: Undo action
* **Ctrl + Y**: Redo action
* **Ctrl + W**: Mirror selection horizontally
* **Ctrl + E**: Mirror selection vertically
* **Delete (Del)**: Delete selected notes
* **Tab**: Toggle tab selection

---

## 🙎🏼‍♂️ Author

(C) Sanya. All rights reserved.
