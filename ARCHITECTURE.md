# AVALON-PAUT Architecture

*Public capability overview. Detailed design files (schematics, layout, BOM) are private.*

64-channel handheld phased-array ultrasonic inspection platform on a 24-layer rigid-flex
mainboard — four functional zones joined by flex bridges, folding handheld geometry.

## Zones

**Z1 — Optical & UI**
- global-shutter CMOS sensor + UV illumination
- 10" sunlight-readable IPS touchscreen

**Z2 — Control / Compute / DSP**
- dual-MCU (wireless app + real-time control)
- FPGA beamformer + LVDS deserializer
- NVIDIA Jetson edge-AI compute
- 9-DOF IMU, capacitive touch, couplant-pressure sensing, NFC
- USB-C, microSD

**Z3 — Power**
- Li-ion pack + BMS
- USB-C PD 100 W
- multi-rail power management
- ±100 V high-voltage pulser supply

**Z4 — PAUT Front-End (64 ch)**
- 64-channel three-level bipolar pulser (±100 V, integrated T/R switch)
- 64-channel low-noise receive AFE (LNA + TGC + 12-bit ADC + LVDS)
- 64-element transducer interface
- per-channel HV decoupling + ESD

## Construction

24-layer rigid-flex with flex bridges between zones — no vias in flex, polyimide coverlay,
FR-4 stiffeners at transitions. Dedicated high-voltage, ground-shield and LVDS-reference
planes isolate transmit HV switching from the receive analog path. Controlled-impedance
routing for LVDS, MIPI and USB.

## Compute & DSP

Full-matrix capture (FMC) → GPU Total-Focusing-Method (TFM) / S-scan reconstruction on
NVIDIA Jetson → AI-assisted defect classification.

## Target sectors

Energy & nuclear · power turbines · aerospace & space · automotive & EV · semiconductors · heavy industry.

## Compliance roadmap

IEC 61010-1 / 61010-2-030 · EN 12668-1/2/3 · IEC 61000-4 / -6 · FCC Part 15 Subpart C · RED 2014/53/EU
