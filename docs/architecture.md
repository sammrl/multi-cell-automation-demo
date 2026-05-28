# System Architecture

## Overview

A multi-cell automation demo with a centralized orchestration layer. The design separates deterministic (PLC) from non-deterministic decision-making (Raspberry Pi).

---

## Network

TBD

---

## Control Layer Separation

| Layer | Platform | Responsibilities |
|-------|----------|-----------------|
| Deterministic | Micro850 PLC | Motor control, I/O, interlocks, E-stop, safety-critical sequencing |
| Non-deterministic | Raspberry Pi 5 | Recipe dispatch, vision inspection, AI decisions, HMI, MQTT broker |

---

## Power Architecture (MCC-01 Panel)

| Bus | Supply | Purpose |
|-----|--------|---------|
| Control | HDR-100-24 | Micro850, I/O, logic |
| Load | AB 1606-XLP | Motors, solenoids, actuators |

WAGO 857 relay opens load rail circuit - PSU 24V+ rail on E-stop while the Micro850 stays powered.

---

## Software Stack

| Tool | Purpose |
|------|---------|
| Connected Components Workbench (CCW) and FactoryTalk Workbench (FTWB) | Micro850 PLC programming |
| Node-RED | HMI dashboard, flow logic |
| Mosquitto | MQTT broker |
| Python (pylogix / pycomm3) | Pi ↔ PLC communication |
| PlatformIO | ESP32 firmware (AGVs, wheel detection) |

---

## MVP Scope

- Physical wheel → MQTT result → dispatcher → conveyor + hopper sequence
- Basic Node-RED dashboard showing system state and active wave
- PLC controlling conveyor motor and hopper stepper
- Release tag: `v0.1-mvp`
