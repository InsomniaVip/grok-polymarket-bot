# System Architecture

## GROK × POLYMARKET

The Bot Floor is presented as a visual orchestration model rather than a production trading stack.

```text
                         ┌─────────────────────┐
                         │   GROK COMMAND CORE │
                         │     ORCHESTRATOR    │
                         └──────────┬──────────┘
                                    │
          ┌─────────────┬───────────┼───────────┬─────────────┐
          ▼             ▼           ▼           ▼             ▼
       SCOUT          SIGNAL       ODDS        NEWS          RISK
    discovery       sentiment    probability  catalysts    exposure
          └─────────────┴───────────┬───────────┴─────────────┘
                                    ▼
                              EXEC // SIM
                                    │
                                    ▼
                              HUMAN GATE
```

### Agent roles

| Agent | Role |
|---|---|
| GROK | Coordinates the visual workflow and priorities |
| SCOUT | Discovers and ranks simulated market opportunities |
| SIGNAL | Represents sentiment and social-signal analysis |
| ODDS | Represents probability / fair-value analysis |
| NEWS | Represents catalyst and news monitoring |
| RISK | Represents exposure and risk checks |
| EXEC | Represents a staged simulated execution |

### Data flow

`SCAN → SIGNAL → ODDS → RISK → EXEC`

The browser generates changing values, chart points, events and agent motion locally. There is no external market connection in the current build.

### Design principles

- **Command-center first:** the master agent remains the visual anchor.
- **Readable motion:** movement communicates activity without becoming distracting.
- **Dense telemetry:** charts, cards, events and status indicators make the floor feel alive.
- **Simulation-safe:** market and execution states are clearly presented as simulated.
- **Self-contained:** no framework, package manager or external runtime is required.
