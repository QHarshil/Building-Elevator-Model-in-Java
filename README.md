# Elevator System Simulation

Multi-elevator simulation with Java Swing GUI. Models elevator scheduling, request handling, and real-time status display using MVC architecture.

## Features

- Real-time visualization of elevator position, direction, and scheduled stops
- Manual step-through mode for debugging scheduling logic
- Elevator service controls (start, stop, out-of-service)
- Configurable building parameters (floors, elevator count)

## Running

```bash
java -jar res/BuildingSystem.jar
```

Requires Java 8+.

## Usage

1. **Start** — Initialize simulation with default or custom parameters
2. **Step** — Advance simulation one tick (manual mode)
3. **Service toggle** — Put elevators in/out of service during simulation

## Architecture

```
┌─────────────┐    updates    ┌─────────────┐
│    Model    │ ───────────→  │    View     │
│  (Building, │               │  (Swing UI) │
│  Elevators) │ ←───────────  │             │
└─────────────┘   user input  └─────────────┘
       ↑                            │
       │         commands           │
       └────────────────────────────┘
                Controller
```

| Component | Responsibility |
|-----------|----------------|
| Model | Building state, elevator scheduling, request queue |
| View | Swing GUI, status display, user controls |
| Controller | Input handling, simulation tick coordination |

## Constraints

- Elevators start from ground floor
- Floor inputs must be valid integers within building range
- Movement is instantaneous per tick (no real-time delays)
- Floor/elevator count fixed at simulation start

## License

MIT
