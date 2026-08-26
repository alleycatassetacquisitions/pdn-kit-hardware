# Open questions

> Generated from the as-built dump. Each item is a *candidate* review task.
> Resolve against datasheets, ERC, and system intent before closing.

## Bom

- [ ] **passive-bom-incomplete** — 71 resistors/capacitors have no LCSC part (brain.kicad_sch: 8, leds.kicad_sch: 7, power.kicad_sch: 40, ui.kicad_sch: 16). Fill BOM before PCB.
  - Source: `netlist`

## Connectivity

- [ ] **explicit-nc-pins** — 29 pins are explicitly marked unconnected — verify these are intentional NC, not missing wiring.
  - Source: `netlist`

## Net Naming

- [ ] **auto-net-names** — 96 nets still use KiCad auto-names (Net-(C7-Pad1), Net-(D2-A), Net-(D2-K), Net-(D4-A), Net-(D5-A), Net-(D6-K), Net-(D7-K), Net-(LED1-BK) (+88 more)). Review before treating netlist as documentation.
  - Source: `netlist`

## Part Selection

- [ ] **placeholder-D2** — D2 (Schottky) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:D2`
- [ ] **placeholder-D6** — D6 (LED) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:D6`
- [ ] **placeholder-D7** — D7 (LED) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:D7`
- [ ] **placeholder-SW2** — SW2 (SW_Push_Dual) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:SW2`
- [ ] **placeholder-J1** — J1 (AudioJack5) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:J1`
- [ ] **placeholder-J2** — J2 (AudioJack5) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:J2`
- [ ] **placeholder-SW4** — SW4 (BOOT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:SW4`
- [ ] **placeholder-SW1** — SW1 (Primary Button) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:SW1`
- [ ] **placeholder-SW3** — SW3 (Secondary Button) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:SW3`

## System Integration

- [ ] **cross-sheet-interfaces** — 18 signals cross hierarchical sheets (BT_PRIM, BT_SEC, CE, CS, D+, D-, …) — verify pull-ups, levels, and firmware pin map.
  - Source: `hierarchy`

## Process

- [ ] Re-run ERC and resolve errors/warnings
- [ ] Cross-check IC passives against datasheet typical application circuits
- [ ] Promote validated items from `design-rules-draft.yaml` to Konnect only after explicit review
