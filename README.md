# Tank Game

A lightweight 2-player tank game built with Python and Pygame, featuring local and LAN multiplayer via UDP multicast.

## Table of Contents

- [Tank Game](#tank-game)
  - [Table of Contents](#table-of-contents)
  - [Features](#features)
  - [Installation](#installation)
    - [Prerequisites](#prerequisites)
    - [Using uv](#using-uv)
  - [Usage](#usage)
    - [Running the Game](#running-the-game)
    - [Game Setup](#game-setup)
  - [Controls](#controls)
  - [Project Structure](#project-structure)
  - [Networking](#networking)
  - [Troubleshooting](#troubleshooting)
  - [Contributing](#contributing)
  - [License](#license)
  - [Credits](#credits)

## Features

- Local and LAN multiplayer support
- Simple, readable codebase ideal for learning game development concepts like game loops, input handling, and basic networking
- Minimal external dependencies (only Pygame)
- Real-time tank battles with physics-based projectiles
- Cross-platform compatibility (Windows, macOS, Linux)

## Installation

### Prerequisites

- Python 3.13 or newer
- uv package manager (recommended for dependency management)

### Using uv

1. Clone or download the repository.
2. Navigate to the project directory.
3. Install dependencies:

```bash
uv sync
```

## Usage

### Running the Game

Using uv:

```bash
uv run main.py
```

### Game Setup

- Enter your player name.
- Choose game mode: `0` for local (single machine), `1` for LAN (multiplayer over network).

For LAN games, run the command on two machines connected to the same local network.

## Controls

- **Player 1**: Q (aim left), W (power up), E (aim right), A (move left), S (power down), D (move right)
- **Player 2**: U (aim left), I (power up), O (aim right), J (move left), K (power down), L (move right)
- **SPACE**: Shoot
- **R**: Restart (when game over)
- **ESC**: Quit

## Project Structure

- `main.py`: Application entry point, menu, and main game loop
- `tank.py`: Tank logic and controls
- `input_handler.py`: Input mapping abstraction
- `sprites.py`, `bullet.py`, `terrain.py`, `colors.py`: Game objects and rendering
- `multicast_transceiver.py`: UDP multicast for LAN play
- `fsm.py`: Finite state machine for game states
- `images/`: Image assets used by the game

## Networking

LAN play uses UDP multicast for player discovery and lightweight state synchronization. Both players must be on the same LAN, and the network must allow UDP multicast traffic.

If players cannot discover each other:

- Check local firewall settings
- Ensure both machines are on the same subnet
- Try temporarily disabling firewalls to isolate the issue

## Troubleshooting

- **Game fails to start**: Ensure Python 3.13+ is used and Pygame is installed for the active Python interpreter.
- **LAN discovery fails**: Refer to the [Networking](#networking) section.
- **Performance issues**: The game is lightweight; check system resources if experiencing slowdowns.

## Contributing

Contributions, issues, and PRs are welcome. Good first changes include:

- Improving art or adding sound effects in `images/`
- Adding unit tests for non-graphical logic
- Implementing new game modes or features
- Enhancing networking robustness

## License

This project is licensed under the MIT License. See LICENSE file for details.

## Credits

Created as a small demo project by Carlos Valente to explore Pygame and simple LAN multiplayer.
