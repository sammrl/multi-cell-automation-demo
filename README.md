# An Industry 4.0 Multi-Cell Automation Demo 

## Overview

A modular, multi-cell automation demo built around a physical spinning wheel that determines the next sequence of events. The wheel dispatches jobs across independent automation cells.

Built on a double Micro850 PLC + double Raspberry Pi 5 architecture, orchestrated via MQTT/EthernetIP.

---

## System Architecture

```
[ Physical Wheel ]
       |
       v
[ MQTT Broker (Mosquitto) ]
       |
  _____|_____
 |     |     |
 v     v     v
[Cell] [Cell] [Cell] ...
```

- **PLC (Micro850 @ 192.168.8.50)** — deterministic, safety-critical control
- **Raspberry Pi 5 (@ 192.168.8.60)** — non-deterministic decisions, vision, AI, orchestration
- **MQTT** — orchestration backbone; all cells subscribe/publish to a shared broker
- **Node-RED** — dashboard, flow logic, HMI
- **OT LAN** — air-gapped network via GL.iNet Opal router

See [`docs/architecture.md`](docs/architecture.md) for the full system design.

---

## MVP Cells

| Cell | Description | Status |
|------|-------------|--------|
| [`cells/conveyor/`](cells/conveyor/) | Belt conveyor  |  In Progress |
| [`cells/wheel/`](cells/wheel/) | Physical spinning wheel   |  In Progress |
| [`cells/hopper/`](cells/hopper/) | Rotary hopper — part/material dispenser |  In Progress |

> MVP target: all three cells communicating over MQTT with a working dispatch loop.
> Tag: `v0.1-mvp`

---

## Planned Expansion Cells

TBD

---

## Repo Structure

```
multi-cell-automation-demo/
├── cells/              # One subdirectory per automation cell
├── orchestration/      # MQTT broker config, Node-RED flows, dispatcher
├── hardware/           # MC-01 panel, BOM, network config
├── shared/             # Reusable PLC blocks, MQTT schemas, utilities
└── docs/               # Architecture, narrative, presentation notes
```

---

## Contributors

Sam and Obed

---

## License

MIT
