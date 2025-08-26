# Respawn Timer — Introduction & Features

### Introduction

**Respawn Timer** is a **game-agnostic** Discord bot designed to track **boss respawns and time-based events** (e.g., world spawns, raids, dungeon resets, vendor rotations) across various games. It provides a **live-updating dashboard** with per-row countdowns, refreshed every second, and supports interactive elements like dropdowns and modals. Users can manage timers via slash commands—**`/addrespawn`**, **`/updatetime`**, **`/removerespawn`**—with flexible duration inputs like `2h`, `15m`, or `45s`. Bulk management is enabled through a `respawn.json` file.

---

## Feature Details

### Overview
- **Channel-specific boss table with independent timers**  
  Displays a table of bosses in in your chosen channel, with each row tracking its own countdown. Timers are isolated to the channel, ensuring no cross-channel interference.

- **Action dropdown per boss**  
  Each boss row includes a dropdown menu with:
  - `Reset`: Marks the boss as defeated, resetting or clearing its timer.
  - `Update Time`: Opens a modal for precise timer adjustments.

- **Interactive edit modal**  
  The `Update Time` option launches a modal for entering exact durations, supporting formats like `2h`, `15m`, `45s`, or `HH:MM:SS`.

- **Live dashboard updates**  
  The dashboard auto-refreshes every second, ensuring accurate countdowns without user intervention.

- **Bulk boss management via `respawn.json`**  
  Allows importing or syncing a list of bosses for quick setup across channels or servers.

---

### Slash Commands

| Command | Usage | Example | Notes |
|---------|-------|---------|-------|
| **`/addrespawn`** | `/addrespawn [bossname] [duration]` | `/addrespawn "Dragon King" 2h` | Adds a boss and starts its timer. Supports durations like `2h`, `15m`, `45s`, or `HH:MM:SS`. |
| **`/updatetime`** | `/updatetime [bossname] [duration]` | `/updatetime "Dragon King" 15m` | Updates an existing boss’s timer. Use the `Edit Time` modal for precise control. |
| **`/removerespawn`** | `/removerespawn` | `/removerespawn` | Opens a dropdown to select and remove a boss (and its timer) from the current channel. |

---

### Time Input Formats
Supported duration formats:
- **Unit shorthand**: `2h`, `30m`, `45s`
- **Mixed units**: `1h30m` (parser-dependent)

> **Tip**: Use `2h`, `15m`, or `HH:MM:SS` for consistent parsing.

---

### `respawn.json` Example
Use this file to seed or manage bosses in bulk. Ensure unique names per channel.

```json
{
  "bosses": [
    { "name": "Clamchowder Goon", "respawn": 28800 },
    { "name": "Suzera's Toenail", "respawn": 46800 },
    { "name": "Dumb Captain", "respawn": 54000 },
    { "name": "Admirable Moron ", "respawn": 75600 },
    { "name": "Harmless Retard", "respawn": 82800 }
  ]
}


