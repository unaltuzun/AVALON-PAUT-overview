# AVALON-PAUT

Handheld **64-channel phased-array ultrasonic inspection platform**.

Built by **GODBRAIN** — sovereign wave-physics + edge-AI hardware for safety-critical
industries: **energy & nuclear · power turbines · aerospace & space · automotive & EV
· semiconductors · heavy industry.**

## Status

June 2026 · Phase 0 control board fabricated; 64-channel front-end (Phase 1b) in design.
Solo-founder execution · tier-1 supply chain (TI, Würth Elektronik, NVIDIA).

## Architecture

Four functional zones on a 24-layer rigid-flex mainboard, bridged by flex regions:

| Zone | Function |
|---|---|
| Z1 | Optical & UI — camera, UV illumination, 10" sunlight-readable touchscreen |
| Z2 | Control / Compute — dual-MCU + FPGA beamformer + NVIDIA Jetson edge-AI + sensors |
| Z3 | Power — Li-ion + BMS + USB-C PD + multi-rail PMIC + ±100 V pulser supply |
| Z4 | PAUT Front-End — 64-ch ±100 V three-level pulser + 64-ch receive AFE + transducer interface |

Swappable phased-array probes (linear / matrix), application-dependent.

Detail in [ARCHITECTURE.md](ARCHITECTURE.md).

## Roadmap

| Phase | Form factor | Target |
|---|---|---|
| Phase 0 — control dev board | 4-layer | Fabricated (Jun 2026) |
| Phase 1a — Z1+Z2+Z3 integration | multilayer | Q3 2026 |
| Phase 1b — Z4 64-ch front-end | multilayer + PCBA | Q4 2026 |
| Phase 2 — full 24-layer integration | 24-layer rigid-flex | Q1 2027 |
| Ruggedized / extended-environment variant | 24-layer rigid-flex | 2028+ |
| Aerospace / high-reliability variant | rad-tolerant | 2029+ |

## Principles

**De-risk before commit** — intermediate boards validate integration and BGA process before production rigid-flex.

**Capability first** — engineering rigor and a real supplier ecosystem are the primary deliverables.

**Sovereign hardware** — indigenously designed and built; one wave-physics + edge-AI stack across all target sectors.

## Contact

`ceo@godbrain.org` · <https://godbrain.org>
