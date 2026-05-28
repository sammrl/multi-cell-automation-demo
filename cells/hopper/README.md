# Cell: Rotary Hopper


---

## Overview

The rotary hopper sorts parts into the system deterministically. It acts as the input stage for the conveyor loop. 

**Hardware:** [TBD — CAD custom designed hopper]  
**Actuator:** NEMA 17 stepper via stepper driver  
**Control:** Micro850 PLC

---

## MQTT Interface

TBD

---

## Files

```
hopper/
├── README.md
├── plc/               # Ladder / motion logic
├── mechanical/        # CAD, assembly notes
├── wiring/            # Wiring diagram, I/O list
└── notes.md
```

---

## Status

- [ ] Mechanical assembly complete
- [ ] Stepper motion tuned
- [ ] PLC I/O mapped
- [ ] MQTT subscribe/publish working
- [ ] Integrated into dispatch loop
