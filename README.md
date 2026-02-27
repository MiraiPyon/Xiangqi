# Xiangqi (Chinese Chess)

A Xiangqi game built with Python, featuring both **Human vs Human** and **Human vs AI** (powered by [Pikafish](https://github.com/official-pikafish/Pikafish)) modes.

## Screenshots

> Coming soon

## Features

- Human vs Human mode
- Human vs AI mode with 4 difficulty levels (Medium / Hard / Very Hard / Impossible)
- Undo move (`Ctrl+Z`)
- Surrender (`Ctrl+R` / `Ctrl+B` in Human mode, `Ctrl+S` in AI mode)
- Sound effects (move, capture, start, end)

## Prerequisites

- **Python 3.10+**
- **Tkinter** (usually bundled with Python, except on some Linux distros)
- **Pikafish engine** (for AI mode)

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/MiraiPyon/Xiangqi.git
cd Xiangqi
```

### 2. Create and activate virtual environment

**Linux / macOS:**
```bash
python3 -m venv .venv
source .venv/bin/activate
```

**Windows:**
```bash
python -m venv .venv
.venv\Scripts\activate
```

### 3. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 4. Install system dependencies

#### Linux

**Arch Linux:**
```bash
sudo pacman -S tk sdl2_mixer
```

**Ubuntu / Debian:**
```bash
sudo apt install python3-tk libsdl2-mixer-2.0-0
```

**Fedora:**
```bash
sudo dnf install python3-tkinter SDL2_mixer
```

#### Windows

Tkinter is included when installing Python (make sure to check **tcl/tk** during installation). SDL2_mixer is bundled with `pygame` on Windows.

#### macOS

```bash
brew install python-tk sdl2_mixer
```

### 5. Set up Pikafish engine (for AI mode)

#### Option A: Build from source

```bash
cd pikafish_ai/Pikafish/src
make -j$(nproc)
cd ../../..
```

> Requires `g++` (Linux/macOS) or MinGW/MSYS2 (Windows).

#### Option B: Download pre-built binary

1. Download from [Pikafish Releases](https://github.com/official-pikafish/Pikafish/releases)
2. Place the binary at `pikafish_ai/Pikafish/src/pikafish` (Linux/macOS) or `pikafish_ai/Pikafish/src/pikafish.exe` (Windows)
3. On Linux/macOS, make it executable: `chmod +x pikafish_ai/Pikafish/src/pikafish`

## Usage

```bash
python main.py
```

## Controls

| Shortcut | Action | Mode |
|----------|--------|------|
| `Ctrl+Z` | Undo last move | Both |
| `Ctrl+R` | Red surrenders | Human vs Human |
| `Ctrl+B` | Black surrenders | Human vs Human |
| `Ctrl+S` | Surrender | Human vs AI |

## Project Structure

```
Xiangqi/
├── main.py                  # Entry point
├── requirements.txt         # Python dependencies
├── assets/
│   ├── audio/               # Sound effects
│   └── pictures/            # Piece images & menu background
├── classes/
│   ├── ai.py                # Pikafish engine wrapper
│   ├── board.py             # Board state management
│   ├── game_ai.py           # Human vs AI game logic
│   ├── game_human.py        # Human vs Human game logic
│   ├── get_path.py          # Path utility
│   ├── menu.py              # Main menu UI
│   ├── piece.py             # Abstract piece class
│   └── pieces/              # Individual piece implementations
│       ├── advisor.py
│       ├── cannon.py
│       ├── chariot.py
│       ├── elephant.py
│       ├── general.py
│       ├── horse.py
│       └── soldier.py
└── pikafish_ai/
    └── Pikafish/             # Pikafish engine (submodule/source)
```

## License

This project uses the [Pikafish](https://github.com/official-pikafish/Pikafish) engine which is licensed under GPL-3.0.