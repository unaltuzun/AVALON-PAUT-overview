# AVALON-PAUT Architecture

24-layer rigid-flex mainboard, four functional zones, three flex bridges, folding handheld geometry.

## Zones

**Z1 — Optical & UI**
- 1MP global-shutter CMOS sensor (MIPI CSI-2)
- 365 nm UV LED illumination
- 5" 800×480 IPS LCD + cap multi-touch (MIPI DSI)

**Z2 — Control / DSP / FPGA**
- Dual-MCU: WiFi/BLE app MCU + Cortex-M7 DSP
- Low-LUT FPGA beamformer + LVDS deserializer
- 9-DOF IMU, cap-touch, 24-bit ADC (FSR couplant pressure), NFC
- USB-C, microSD UHS-I

**Z3 — Power**
- 3S LiPo + BMS gas gauge
- USB-C PD 100 W sink
- Multi-rail PMIC: 5 / 3.3 / 1.8 / 1.2 / 1.0 V
- Buck-boost ±100 V pulser supply

**Z4 — PAUT Front-End**
- 32-ch three-level bipolar pulser (±100 V, 1.2 A peak, integrated T/R)
- 32-ch low-noise AFE (LNA + TGC + 12-bit ADC + LVDS, 4 nV/√Hz)
- LVDS clock buffer + 32-element transducer ZIF
- Per-channel HV decoupling + ESD

## Flex bridges

| Bridge | Layers | Signals |
|---|---|---|
| Flex A · Z1↔Z2 | 6 | MIPI CSI 2-pair, MIPI DSI 5-pair, I2C touch, UV PWM, control |
| Flex B · Z2↔Z3 | 8 | 12 / 5 / 3.3 / 1.8 / 1.0 V power, USB D±, BMS telemetry |
| Flex C · Z3↔Z4 | 10 | ±100 V pulser, 8 LVDS RX pairs + clock, TX trigger, SPI |

Flex copper 0.5 oz · hatched GND pour · no vias in flex · polyimide coverlay both sides · FR4 stiffeners at transitions.

## Net classes

| Class | Track / Gap | Notes |
|---|---|---|
| LVDS_100Ω | 89 / 130 µm | length-matched ±0.1 mm |
| MIPI_90Ω | 89 / 100 µm | controlled impedance |
| USB_90Ω | 127 / 130 µm | differential |
| ANALOG_QUIET | 150 µm / 200 µm clr | dedicated GND ref |
| POWER_2OZ_HV | 400 µm / 500 µm clr | IEC 60664 creepage |
| POWER_1OZ | 300 µm | rail distribution |
| Default | 150 / 150 µm | digital |

## Signal integrity

Full LVDS isolation between TX HV switching and RX analog via dedicated GND shielding planes (L14 / L16 / L18). HV routing on 2 oz copper (L13 +V, L15 −V). LVDS RX banks on L17 / L19 bracketed by GND shields.

## Compliance roadmap

IEC 61010-1 / 61010-2-030 · EN 12668-1/2/3 · IEC 61000-4 / -6 · FCC Part 15 Subpart C · RED 2014/53/EU · MIL-STD-810H / 461G (v2).
