# Open questions

> Generated from the as-built dump. Each item is a *candidate* review task.
> Resolve against datasheets, ERC, and system intent before closing.

## Bom

- [ ] **missing-lcsc-MOT1** — MOT1 (Vibration Motor) has no LCSC part number in schematic fields.
  - Source: `ui.kicad_sch:MOT1`
- [ ] **passive-bom-incomplete** — 71 resistors/capacitors have no LCSC part (brain.kicad_sch: 8, leds.kicad_sch: 7, power.kicad_sch: 40, ui.kicad_sch: 16). Fill BOM before PCB.
  - Source: `netlist`

## Connectivity

- [ ] **explicit-nc-pins** — 29 pins are explicitly marked unconnected — verify these are intentional NC, not missing wiring.
  - Source: `netlist`

## Net Naming

- [ ] **auto-net-names** — 96 nets still use KiCad auto-names (Net-(C7-Pad1), Net-(D2-A), Net-(D2-K), Net-(D4-A), Net-(D5-A), Net-(D6-K), Net-(D7-K), Net-(NTC1-Pad1) (+88 more)). Review before treating netlist as documentation.
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
- [ ] **placeholder-TP1** — TP1 (TP_GND) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP1`
- [ ] **placeholder-TP2** — TP2 (TP_BATT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP2`
- [ ] **placeholder-TP3** — TP3 (TP_VCC) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP3`
- [ ] **placeholder-TP4** — TP4 (TP_3V3) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP4`
- [ ] **placeholder-TP5** — TP5 (TP_VBUS) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP5`
- [ ] **placeholder-TP6** — TP6 (TP_VSYS) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP6`
- [ ] **placeholder-TP7** — TP7 (TP_INT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP7`
- [ ] **placeholder-TP10** — TP10 (TP_HOLD) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP10`
- [ ] **placeholder-TP15** — TP15 (TP_PMID) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP15`
- [ ] **placeholder-TP17** — TP17 (TP_REGN) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP17`
- [ ] **placeholder-TP19** — TP19 (TP_TS) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP19`
- [ ] **placeholder-TP20** — TP20 (TP_BQ_BATT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP20`
- [ ] **placeholder-TP22** — TP22 (TP_STAT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP22`
- [ ] **placeholder-TP23** — TP23 (TP_PG) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP23`
- [ ] **placeholder-TP24** — TP24 (TP_ALRT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP24`
- [ ] **placeholder-TP25** — TP25 (TP_OFF) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP25`
- [ ] **placeholder-TP26** — TP26 (TP_CE) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `power.kicad_sch:TP26`
- [ ] **placeholder-J1** — J1 (AudioJack5) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:J1`
- [ ] **placeholder-J2** — J2 (AudioJack5) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:J2`
- [ ] **placeholder-SW4** — SW4 (BOOT) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:SW4`
- [ ] **placeholder-TP8** — TP8 (TP_SCL) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:TP8`
- [ ] **placeholder-TP9** — TP9 (TP_SDA) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:TP9`
- [ ] **placeholder-TP11** — TP11 (TP_EN) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:TP11`
- [ ] **placeholder-TP18** — TP18 (TP_IO0) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `brain.kicad_sch:TP18`
- [ ] **placeholder-TP21** — TP21 (TP_LED_OFF) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `leds.kicad_sch:TP21`
- [ ] **placeholder-SW1** — SW1 (Primary Button) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:SW1`
- [ ] **placeholder-SW3** — SW3 (Secondary Button) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:SW3`
- [ ] **placeholder-TP14** — TP14 (TP_CS) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:TP14`
- [ ] **placeholder-TP16** — TP16 (TP_MOTOR) uses a generic symbol — confirm LCSC part and footprint before PCB.
  - Source: `ui.kicad_sch:TP16`

## System Integration

- [ ] **cross-sheet-interfaces** — 18 signals cross hierarchical sheets (BT_PRIM, BT_SEC, CE, CS, D+, D-, …) — verify pull-ups, levels, and firmware pin map.
  - Source: `hierarchy`

## Process

- [ ] Re-run ERC and resolve errors/warnings
- [ ] Cross-check IC passives against datasheet typical application circuits
- [ ] Promote validated items from `design-rules-draft.yaml` to Konnect only after explicit review
