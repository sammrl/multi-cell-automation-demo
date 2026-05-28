# Cell: Conveyor

---

## Overview

The conveyor itransports objects between cells and acts as the primary mechanism for the sorting loop.

**Hardware:** HG37 brushed DC motor, relay switching, flyback diode protection  
**Control:** Micro850 PLC (ladder logic) via relay output  
**Feedback:** [TBD — end-stop sensors, encoder, or timed run]

---

## MQTT Interface
TBD

---

## PLC Logic

- Ladder logic located in: `plc/conveyor_ctrl.ccw` *(or FTWB project)*
- Interlocks: TBD

---

## Files

```
conveyor/
├── README.md
├── plc/               # Ladder logic exports
├── wiring/            # Wiring diagram, I/O list
└── notes.md           # Build notes, tuning, lessons learned
```

---

## Status

- [ ] Motor wired and tested standalone
- [ ] PLC I/O mapped
- [ ] MQTT subscribe/publish working
- [ ] Integrated into dispatch loop
