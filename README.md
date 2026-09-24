# 🎮 BeatUp Engine

**BeatUp Engine** is a lightweight 2D rhythm game engine and chart editor written in modern C++. It is designed as a standalone simulator and development environment for classic **6-key + Spacebar rhythm gameplay**, with additional support for **Finish Move** charts, chart editing, patch management and customizable themes.

The project focuses on responsive input, consistent timing, low-overhead rendering and a workflow that combines **playing, testing and chart creation** in one application.

> **Current release:** `v0.6.1`
>
> See the complete release history on [GitHub Releases](https://github.com/bishpop/beatupengine/releases).

## Screenshots

### Main Menu
![BeatUp Engine Main Menu](https://github.com/bishpop/beatupengine/blob/main/MainMenu.png?raw=true)

### Chart Editor
![BeatUp Engine Chart Editor](https://github.com/bishpop/beatupengine/blob/main/BuEditor.png?raw=true)

### Patcher
![BeatUp Engine Patcher](https://github.com/bishpop/beatupengine/blob/main/BuPatcher.png?raw=true)

---

## Features

### Gameplay

- 6-key rhythm gameplay with **Spacebar** support.
- **Finish Move** support.
- Precise note timing and synchronized visual/hit timing.
- Configurable timing offset with a default of `0.7`.
- Adjustable **Perfect** timing window, with `0.18` used as the default Perfect window introduced in v0.4.
- Animated arrows and receptor effects.
- MP/RP receptor beams and hit effects.
- Auto-Play mode for testing charts.
- Metronome support.
- Playback speed control.
- **Challenger Mode** for stricter performance-based runs.
- Multiple Patcher Chance modes for alternate gameplay patterns.

### Chart Editor

The integrated editor is built for creating, testing and refining charts without switching applications.

- Vertical and horizontal chart layouts.
- Resizable **Split View** for gameplay + editor at the same time.
- In-game-style **Receptor Bar** matching the gameplay hit position.
- Optional classic position line instead of the Receptor Bar.
- Waveform visualization behind the chart.
- Arrow Vortex-style waveform core/inner-line visualization.
- Minimap with song-position marker.
- Colored snap grid.
- Beat and MADI navigation.
- Rectangle selection using **Ctrl + Left Mouse Button**.
- Edge scrolling while selecting.
- Copy/paste with destination replacement for true 1:1 section editing.
- Undo/redo history with action feedback.
- Live duplicate-note detection.
- Direct HEX color customization.
- Persistent editor, audio and visualization settings.
- Save and restore editor playback position through `.bu` projects.
- Direct chart import/export for supported formats.
- Integration with **Silencer** for timing and audio preparation.

### Patcher

The Patcher manages additional game content and helps keep an installation synchronized with the required files.

- Patch downloading and installation workflow.
- Required-file validation.
- Detection of missing music, charts and scripts.
- `master.bue` based patch validation.
- Automatic recovery guidance for incomplete installations.
- GitHub release/update checking.
- Song and level information in the Patcher interface.
- Patcher-specific Chance modes.
- Per-song timing offsets used by the Patcher.
- **Download New Patches** workflow.
- **Hard Restart** support via `Ctrl + Shift + R`.

### Themes & UI

- Built-in and user-created themes.
- Theme Editor with live preview.
- Base color controls for background, surface, accent, text, muted text and borders.
- Additional customization for waveform, minimap and Receptor Bar elements.
- Persistent themes through `theme.ini`.
- Custom main menu background support via `menu_background.png`.
- Categorized Options for graphics, gameplay, editor and Patcher settings.
- First-launch onboarding with configurable Charter Name.
- Charter Name attribution for `.slk` exports.
- Animated menu and interface elements.

---

## Patcher Chance Modes

BeatUp Engine includes several optional Chance modes for Patcher gameplay. They can be selected independently from the normal chart data.

| Chance | Description |
| --- | --- |
| **Default** | Standard Patcher behavior. |
| **Rapid** | Arrows move at 2× speed and return to normal near the end of the approach. |
| **Vanishing** | Arrows smoothly fade in and out during their approach. |
| **Wave** | Arrows use a subtle wave motion. |
| **Inverted** | Lane/input mapping is inverted, for example `1↔9` and `2↔8`. |
| **Speed Up** | Arrow movement continuously accelerates during the approach. |
| **Halfway** | Arrows are only displayed from the halfway point of their approach. |

### Challenger Mode

**Challenger Mode** is a separate Patcher gameplay modifier designed for stricter chart runs.

A Challenger attempt is evaluated after at least **200 notes**. The run fails when either:

- the Perfect ratio falls below **80%**, or
- **Cool + Bad + Miss** exceeds **15%** of the notes played so far.

Failed attempts display **YOU FAILED** with an **F** rank and are marked as Challenger attempts.

---

## Chart Editor Workflow

### Editor Columns

The editor uses the BeatUp-style column order:

```text
7  4  1  9  6  3  SP  F
```

The first six columns represent the directional arrows, followed by **Space** and **Finish Move**.

### Receptor Bar

Since `v0.6.1`, the Chart Editor can display an in-game-style receptor bar at the chart hit position. The editor receptor bar uses the same gameplay receptor assets and is available in both vertical and horizontal layouts.

You can switch between:

- **Receptor Bar**
- **Classic Position Line**

The Receptor Bar also has dedicated theme controls for its band, icon tint and edge colors.

### Split View

Split View allows the gameplay field and chart timeline to be displayed together. The center divider can be dragged to resize both sides, and double-clicking the divider restores a 50/50 layout.

### Selection & Editing

The editor supports:

- Single-note placement/removal.
- Rectangle selection.
- Multi-note copy/paste.
- Mirroring.
- Delete operations.
- Undo/redo.
- Beat/MADI navigation.
- Automatic edge scrolling while selecting.
- Duplicate-note warnings for invalid repeated inputs on the same beat.

Pasting a copied section **replaces the notes in the destination region**, allowing chart sections to be copied and overwritten 1:1.

---

## Supported Files & Formats

| File | Purpose |
| --- | --- |
| `.bu` | Full BeatUp Engine editor/project/session format. Stores chart-related project state including playback position. |
| `.slk` | Chart export format. Export attribution can include the configured Charter Name. |
| `.ssc` | Chart export format with BPM and music filename information. |
| `config.ini` | Persistent application, editor, audio and gameplay settings. |
| `theme.ini` | Saved user themes and visual customization. |
| `menu_background.png` | Optional custom main menu background. |
| `patcher/` | Patcher content expected alongside the BeatUp Engine executable. |

---

## Controls

### Global

| Key | Action |
| --- | --- |
| `Esc` | Back / menu / exit. In-game, hold for 3 seconds to abort. |
| `Ctrl + S` | Open Sound Settings. |
| `Ctrl + Shift + R` | Hard Restart. |
| `F11` | Toggle borderless fullscreen. |

### Menu & Patcher

| Key | Action |
| --- | --- |
| `↑ / ↓` | Navigate through the song list. |
| `Enter / Numpad Enter` | Start the selected song. |

### Editor & Playback

| Key | Action |
| --- | --- |
| `F1` | Game Mode. |
| `F2` | Editor-only / chart view. |
| `F3` | Split View. |
| `F4` | Toggle metronome. |
| `F5 / Spacebar` | Play / pause audio. |
| `F6` | Toggle Auto-Play. |
| `F7` | Stop playback and reset. |
| `Ctrl + Left Arrow` | Decrease playback speed by 5%. |
| `Ctrl + Right Arrow` | Increase playback speed by 5%. |
| `Ctrl + 0` | Reset playback speed to 100%. |
| `↑ / ↓` | Move by one beat in the editor. |
| `Shift + ↑ / ↓` | Move by one MADI in the editor. |

### Chart Editing

| Key / Input | Action |
| --- | --- |
| `Left Click` | Place / remove a note. |
| `Right Click` | Open the editor context menu. |
| `Ctrl + Left Click + Drag` | Rectangle-select multiple notes. |
| `Ctrl + A` | Select all notes. |
| `Ctrl + C` | Copy selection. |
| `Ctrl + V` | Paste selection. |
| `Ctrl + Z` | Undo. |
| `Ctrl + Y` | Redo. |
| `Ctrl + W` | Mirror selection horizontally. |
| `Ctrl + E` | Mirror selection vertically. |
| `Delete` | Delete selected notes. |
| `Tab` | Toggle tab selection. |
| `S` | Space action. |
| `F` | Finish Move action. |

### Project & Import/Export

| Key | Action |
| --- | --- |
| `Ctrl + Shift + S` | Save `.bu` project. |
| `Ctrl + Shift + E` | Direct `.slk` export. |
| `Ctrl + Shift + V` | Direct `.ssc` export. |
| `Ctrl + Alt + A` | Import audio. |
| `Ctrl + Alt + E` | Import `.slk`. |
| `Ctrl + Alt + V` | Import `.ssc`. |
| `Ctrl + Alt + B` | Open `.bu` project. |

---

## Installation

### Using a Release Build

1. Download the latest release from the [GitHub Releases](https://github.com/bishpop/beatupengine/releases) page.
2. Extract the release to a directory of your choice.
3. Keep the `assets/` folder beside the BeatUp Engine executable.
4. Keep the `patcher/` folder beside the executable when using Patcher content.
5. Keep existing `config.ini`, `theme.ini` and project files when upgrading.
6. Start BeatUp Engine.

BeatUp Engine can also associate `.bu` project files with the application on Windows. Opening a `.bu` file restores the project, chart and saved playback position.

### Updating

For updates, replace the application executable while keeping your existing project and configuration files. Patch updates are handled through the Patcher's patch-management workflow.

The application can also check the GitHub Releases page for newer versions and present an in-app update notice.

---

## Building From Source

### Requirements

#### Operating System

- **Windows 10 / 11** (64-bit recommended)

#### Build Tools

- **CMake** 3.15 or newer
- **Visual Studio** with the C++ Desktop Development workload / MSVC
- **SDL2**
- **SDL2_image**
- **Dear ImGui**
- **miniaudio**

### Build

From the repository root:

```bash
cmake -S . -B build
cmake --build build --config Release
```

The resulting binaries are generated by the selected CMake generator. For Visual Studio/MSBuild configurations, use the `Release` configuration as shown above.

---

## Release History

| Version | Date | Main Changes |
| --- | --- | --- |
| **v0.6.1** | 2026-09-24 | Chart Editor Receptor Bar, Receptor Bar theming, per-song Patcher timing offsets. |
| **v0.6** | 2026-09-21 | Main UI redesign, onboarding, categorized Options, Theme Editor, Split View improvements, editor navigation, playback UI and judgment fixes. |
| **v0.5.1** | 2026-09-18 | Onboarding, menu/Patcher redesign, Perfect positioning fixes, judgment-window refinement and additional animations. |
| **v0.5** | 2026-09-17 | Challenger Mode, 2K/4K support, DPI-aware scaling, save confirmations and automatic `.bu` file association. |
| **v0.4** | 2026-09-13 | BeatUp timing rewrite, animated arrows, `.bu` project workflow, colored snap grid and expanded import/export tools. |
| **v0.3** | 2026-09-10 | Patch management, required-file validation, missing-content detection and improved Patcher recovery. |
| **v0.2.2** | 2026-09-07 | Horizontal editor canvas, waveform, selection, copy/paste replacement, undo/redo, minimap and HEX colors. |
| **v0.2.1** | 2026-09-06 | Patch Manager, GitHub update checker, patch validation and RAM-based music previews. |
| **v0.2** | 2026-09-05 | Patcher Chance system, duplicate-note detection, About window, Silencer integration and release checking. |
| **v0.1.2** | 2026-09-04 | Initial stable separation of Editor/Patcher, screen-size selection and configuration support. |

For the detailed changes of every version, see the [complete release history](https://github.com/bishpop/beatupengine/releases).

---

## Development Timeline

BeatUp Engine has evolved through several major development phases:

1. **Foundation (`v0.1.2`)** — Editor/Patcher separation, resolution support and configuration.
2. **Patcher & Chart Validation (`v0.2–v0.3`)** — Chance modes, duplicate detection, patch management and missing-file recovery.
3. **Editor Expansion (`v0.2.2`)** — Horizontal editing, waveform visualization, selection, copy/paste, undo/redo and HEX customization.
4. **Core Timing & Project System (`v0.4`)** — Unified timing, animated arrows, `.bu` projects and expanded import/export.
5. **Competitive & Display Features (`v0.5`)** — Challenger Mode, high-resolution support, DPI handling and save protection.
6. **UI & Editor Redesign (`v0.5.1–v0.6`)** — Onboarding, redesigned menus, Theme Editor, categorized Options and improved Split View.
7. **Editor/Game Parity (`v0.6.1`)** — Receptor Bar support in the editor and per-song Patcher timing.

---

## Project Goals

BeatUp Engine is built around a few core goals:

- **Responsive gameplay** — input should feel immediate and consistent.
- **Accurate timing** — visual positions and hit detection should use the same timing model.
- **Mapper-friendly editing** — chart creation should be fast, visual and reversible.
- **Practical tooling** — playing, testing, editing and patch management should work together.
- **Customizable presentation** — users can adapt the interface and editor to their workflow.
- **Portable project data** — charts and editor state should be easy to save, move and reopen.

---

## Author

**Sanya**

---

## Links

- [GitHub Repository](https://github.com/bishpop/beatupengine)
- [GitHub Releases](https://github.com/bishpop/beatupengine/releases)
