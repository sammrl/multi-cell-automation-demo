# Cell: Wheel

---

## Overview

The physical spinning wheel is the selector for the entire system. A spin produces a result that the dispatcher uses to route a job to the appropriate cell sequence.
**Hardware:** [Wheel mechanism — Gameboard wheel of fortune wheel driven by pulley + NEMA 17 stepper motor]
**Detection:** [TBD]  
**Control:** Micro850 

---


## MQTT Interface

TBD

---

## Files

```
wheel/
├── README.md
├── firmware/          # ESP32 or Pi code for detection
├── mechanical/        # CAD, assembly notes
├── wiring/            # Wiring diagram
└── notes.md
```

---

## Status

- [ ] Wheel mechanism built
- [ ] Sector detection working
- [ ] MQTT Structure established
- [ ] Dispatcher consuming result
