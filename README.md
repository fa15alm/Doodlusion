# Canvas & Clues

A browser-based, real-time multiplayer drawing and guessing game, developed for the COMP390 Honours Year Project at the University of Liverpool.

Players join private rooms, take turns drawing secret words, and compete to guess correctly before the timer runs out.

> Work in progress. The features below describe the planned scope and may change during development.

## How It Works

1. A host creates a room and shares its room code.
2. Players join using the code and a nickname.
3. The host configures the game and starts the session.
4. Each turn, one player becomes the artist and selects a secret word.
5. The artist draws while the other players submit guesses through live chat.
6. Correct guesses earn points based on the time remaining.
7. Players take turns drawing, with a final leaderboard shown at the end.

## Planned Features

### Core Gameplay

- Private rooms with shareable join codes.
- Nickname-based joining without requiring an account.
- Configurable rounds, drawing time, and word categories.
- Real-time shared drawing canvas with colours and drawing tools.
- Live chat with automatic correct-guess detection.
- Time-based scoring and live scoreboards.
- Server-controlled turns, timers, and round progression.
- Player disconnect handling.
- End-of-game leaderboard.

### Potential Extensions

These features will be considered once the core game is complete:

- Reconnection with canvas and game-state recovery.
- Drawing replays.
- Custom word packs.
- Host moderation controls and chat filtering.
- Chat rate limiting.
- Mobile-friendly drawing and layouts.
- Optional accounts, lifetime statistics, and global leaderboards.
- Public rooms.

## Technology

| Component | Planned Technology |
|-----------|--------------------|
| Frontend | HTML, CSS, JavaScript |
| Drawing | HTML Canvas API |
| Backend | Node.js and Express |
| Real-time communication | Socket.IO |
| Persistent storage | SQLite |
| Live room state | Redis, if required |
| Deployment | Linux VPS with PM2 |

## Technical Approach

### Server-Authoritative Game State

The server will manage room membership, artist selection, secret words, timers, scoring, and round progression. Clients will submit actions for validation rather than determine their own scores or game state.

### Drawing Synchronisation

Drawing will be transmitted as stroke events containing coordinates and drawing settings, rather than repeatedly sending full canvas images. Stroke batching will be investigated as a way to balance responsiveness and bandwidth usage.

### Room-Based Communication

Gameplay events will be routed to the appropriate room. Secret words will only be sent to the artist during their turn.

## Testing and Evaluation

Planned testing includes:

- Unit tests for scoring, guess validation, and game-state transitions.
- Integration tests for room creation, joining, and round progression.
- End-to-end tests across multiple browser sessions.
- Disconnect and reconnection testing.
- Load testing with simulated players and rooms.
- Measurement of drawing latency, bandwidth, and server resource usage.
- Voluntary usability testing and anonymised feedback.

## Development Status

The project is in development. Installation instructions and configuration details will be added once the initial playable version is available.

## Academic Context

- **Module:** COMP390 — Honours Year Project
- **Institution:** University of Liverpool
- **Author:** Faisal Mughal
