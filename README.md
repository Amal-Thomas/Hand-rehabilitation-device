# Hand Rehabilitation Device

## Overview

A portable, battery-powered mechanical hand rehabilitation device designed to aid recovery from hand injuries and stroke-related mobility impairment. The device sits on the dorsal (back) side of the hand like a glove and uses a servo-motor-driven linkage system to guide all five fingers through therapeutic flexion/extension cycles, mimicking natural hand movements such as gripping a bottle or lifting light objects.

This project was developed as part of **ME423** at IIT Bombay.

---

## Key Features

- **5 independent degrees of freedom** — one servo motor per finger
- **Portable** — powered by 9V batteries, no mains electricity required
- **Lightweight** — PLA (3D-printed sleeves) and 2mm acrylic (laser-cut linkages)
- **Customisable** — linkage dimensions can be adjusted for individual hand sizes
- **Low cost** — total prototype cost of ~₹5,966, significantly cheaper than commercial alternatives

---

## Mechanical Design

### Degrees of Freedom
A healthy human hand has 25 degrees of freedom, but for rehabilitation purposes this device simplifies each finger to **1 DOF** (flexion/extension only), covering the **DIP, PIP, and MCP** joints simultaneously. The wrist and CMC joints are excluded.

### Linkage Mechanism
A combination of revolute joints and sliding mechanisms (slider-crank) was designed and simulated in *Linkage Mechanism Designer and Simulator* to achieve coordinated, simultaneous joint movement with a single actuator per finger.

### Range of Motion

| Joint | Angle |
|-------|-------|
| MCP   | 50°   |
| PIP   | 32°   |
| DIP   | 19°   |

These values correspond to the motion of squeezing a hand therapy ball, a standard rehabilitation exercise.

---

## Components & Materials

| Component | Material / Spec | Manufacturing Method |
|---|---|---|
| Finger sleeves | PLA | FDM 3D printing |
| Linkages | 2mm Acrylic sheet | Laser cutting |
| Back plate | PLA | FDM 3D printing |
| Actuators | SG90 Servo motors (1 kgF·cm) × 5 | — |
| Microcontroller | Arduino Uno × 5 | — |
| Power supply | 9V batteries | — |

**Why PLA?** Good balance of rigidity and strength, low warping, biodegradable, and easy to print at low temperatures.

**Why Acrylic?** Lightweight, chemically resistant, easy to machine, and laser-cuttable to high precision — critical for the small hole tolerances required in the linkages.

---

## Structural Analysis

CAD models were analysed in **ANSYS 2023 R2** using both static structural and transient (rigid dynamics) analyses. Results for deformation and equivalent (von Mises) stress were within acceptable limits under normal operating loads.

---

## Electrical System

Each finger is driven by one **SG90 servo motor** controlled by an **Arduino Uno**. The motors follow a sinusoidal motion profile for smooth, uniform crank traversal. Each motor is powered by a 9V battery to keep the device self-contained and portable.

---

## Bill of Materials

| Component | Qty | Cost (₹) |
|---|---|---|
| Servo Motors (SG90, 1 kgF·cm) | 5 | 825 |
| Arduino Uno | 5 | 1345 |
| PLA filament (1 kg) | 1 | 1416 |
| 3D printing cost | — | 1800 |
| Laser cutting cost | — | 400 |
| Pins and wires | 1 box | 180 |
| **Total** | | **₹5,966** |

---

## Manufacturing Process

### Linkages
The team iterated through three approaches before arriving at laser-cut acrylic:
1. **Steel machining** — abandoned due to inability to drill 1mm holes via EDM
2. **ABS 3D printing** — abandoned due to undesirable flexibility and imprecise small holes
3. **Laser-cut 2mm acrylic** ✅ — chosen for its precision, rigidity, and ease of assembly

### Sleeves
- **3D printing (PLA)** used for the final sleeve geometry due to design complexity
- **Laser cutting** used for rapid prototyping of 2D cross-sections to verify fit before committing to 3D printing

---

## Repository Contents

```
└── ME423.pdf    # Full project report including design, analysis, and results
```

---

## References

1. Kabir R et al. "Hand Rehabilitation Devices: A Comprehensive Systematic Review." *Micromachines* (2022). https://doi.org/10.3390/mi13071033
2. Xiaopeng Yang et al. "Development and Evaluation of a 25-Degree of Freedom Hand Kinematic Model." (2008).
