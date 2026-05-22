# AVALON-PAUT

Handheld 32-channel phased-array ultrasonic inspection instrument.

Built by **GODBRAIN Co.** — civilian industrial NDT v1, evolving to MIL-STD-810 v2 (2028) and space-tolerant v3 (2029-2030).

## Status

May 2026 · Phase 0 dev board in fabrication. 30+ commits in 22 days from concept to first fab order. Solo-founder execution.

## Architecture

Four functional zones on a 24-layer rigid-flex mainboard, bridged by three flex regions:

| Zone | Function |
|---|---|
| Z1 | Optical & UI — camera, UV illumination, 5" IPS + touch |
| Z2 | Control / DSP / FPGA — dual-MCU + FPGA beamformer + IMU + NFC + microSD |
| Z3 | Power — 3S LiPo + BMS + USB-C PD + multi-rail PMIC + ±100V pulser supply |
| Z4 | PAUT Front-End — 32-ch ±100V pulser + 32-ch AFE + LVDS + transducer ZIF |

Transducer: 32-element 5 MHz phased-array linear probe.

Detail in [ARCHITECTURE.md](ARCHITECTURE.md).

## Roadmap

| Phase | Form factor | Target |
|---|---|---|
| Phase 0 — control dev board | 4L FR-4 | May 2026 (in fab) |
| Phase 1a — Z1+Z2+Z3 integrated | 8-12L FR-4 | Q3 2026 |
| Phase 1b — Z4 standalone | 8L FR-4 + PCBA | Q4 2026 |
| Phase 2 — full 24L integration | 24L rigid-flex | Q1 2027 |
| v2 — MIL-STD-810 / 461 | 24L rigid-flex | 2028 |
| v3 — space-tolerant | 24L rigid-flex + rad-tolerant Si | 2029-2030 |

## Principles

**De-risk before commit** — Phase 1.5 split validates integration + BGA process on intermediate boards before production rigid-flex.

**Capability first** — engineering rigor and supplier ecosystem are the primary deliverables; commercial revenue is downstream.

**Dual-use sovereignty** — civilian NDT and defense infrastructure inspection share the same silicon stack. Indigenously built, ITAR-free, Wassenaar Cat 6.

## Contact

`ceo@godbrain.org` · <https://godbrain.org>
