# System map (as-built)

> **Status: observation only.** This file is generated from the schematic on disk.
> It describes what is drawn, not what *should* be. See `open-questions.md` before
> treating any detail as a requirement.

- **Root schematic:** `C:\Users\Elli Furedy\projects\pdn-hardware\pdn-v2.5\PDN V2.5\PDN V2.5.kicad_sch`
- **Generated:** 2026-08-23 14:46 UTC
- **Components:** 124
- **Nets:** 162

## Hierarchy

- **brain** (`brain.kicad_sch`) — pins: BT_PRIM, BT_SEC, CE, CS, D+, D-, DC, INT, MAX_ALRT, PWR_HOLD, PWR_OFF, RESET, SCLK, SDIN, VIB_MOTOR, I2C_SDA, I2C_SCL, LED_OFF
- **power** (`power.kicad_sch`) — pins: CE, D+, D-, INT, MAX_ALRT, PWR_HOLD, PWR_OFF, I2C_SCL, I2C_SDA
- **LEDs** (`leds.kicad_sch`) — pins: I2C_SCL, I2C_SDA, LED_OFF
- **ui** (`ui.kicad_sch`) — pins: BT_PRIM, BT_SEC, CS, DC, RESET, SCLK, SDIN, VIB_MOTOR

## Major ICs

| Ref | Part | LCSC | Sheet |
|-----|------|------|-------|
| B+/-1 | GH-2AW R | C16965 | /power/ |
| MOT1 | Vibration Motor | C2759984 | /ui/ |
| TV2 | SRV05-4-P-T7 | C85364 | /brain/ |
| TV3 | SRV05-4-P-T7 | C85364 | /brain/ |
| U1 | BQ25619RTWR | C2864534 | /power/ |
| U2 | TPS22917DBVR | C2681320 | /power/ |
| U3 | TPS63802DLAR | C2845237 | /power/ |
| U4 | MAX17260SEWL | C3682467 | /power/ |
| U5 | IS31FL3236A-QFLS2-TR | C246443 | /LEDs/ |
| U6 | ESP32-S3-WROOM-1(N8R8) | C2913201 | /brain/ |
| U7 | IS31FL3236A-QFLS2-TR | C246443 | /LEDs/ |
| U9 | X096-2864KSWPG01-H30 | C18723026 | /ui/ |
| USB1 | USB-C Connector | C2982555 | /power/ |

## Cross-sheet signals

- **BT_PRIM** → brain, ui
- **BT_SEC** → brain, ui
- **CE** → brain, power
- **CS** → brain, ui
- **D+** → brain, power
- **D-** → brain, power
- **DC** → brain, ui
- **I2C_SCL** → brain, power, LEDs
- **I2C_SDA** → brain, power, LEDs
- **INT** → brain, power
- **LED_OFF** → brain, LEDs
- **MAX_ALRT** → brain, power
- **PWR_HOLD** → brain, power
- **PWR_OFF** → brain, power
- **RESET** → brain, ui
- **SCLK** → brain, ui
- **SDIN** → brain, ui
- **VIB_MOTOR** → brain, ui

## ESP32 GPIO map (from netlist)

| GPIO | Net | Pin |
|------|-----|-----|
| 3V3_2 | `+3V3` | 2 |
| EN_3 | `Net-(U6-EN)` | 3 |
| GND_1 | `GND` | 1 |
| GND_40 | `GND` | 40 |
| GND_41 | `GND` | 41 |
| IO0 | `Net-(U6-IO0)` | 27 |
| IO1 | `/LEDs/I2C_SDA` | 39 |
| IO10 | `/ui/CS` | 18 |
| IO11 | `/ui/SDIN` | 19 |
| IO12 | `/ui/SCLK` | 20 |
| IO13 | `/LEDs/LED_OFF` | 21 |
| IO14 | `/ui/RESET` | 22 |
| IO15 | `/ui/BT_PRIM` | 8 |
| IO16 | `/ui/BT_SEC` | 9 |
| IO17 | `/ui/VIB_MOTOR` | 10 |
| IO18 | `unconnected-(U6-IO18-Pad11)` | 11 |
| IO19 | `/power/D-` | 13 |
| IO2 | `/LEDs/I2C_SCL` | 38 |
| IO20 | `/power/D+` | 14 |
| IO21 | `unconnected-(U6-IO21-Pad23)` | 23 |
| IO3 | `unconnected-(U6-IO3-Pad15)` | 15 |
| IO35 | `unconnected-(U6-IO35-Pad28)` | 28 |
| IO36 | `unconnected-(U6-IO36-Pad29)` | 29 |
| IO37 | `unconnected-(U6-IO37-Pad30)` | 30 |
| IO38 | `unconnected-(U6-IO38-Pad31)` | 31 |
| IO39 | `/brain/J2T` | 32 |
| IO4 | `/power/PWR_HOLD` | 4 |
| IO40 | `/brain/J2R1` | 33 |
| IO41 | `/brain/J2R2` | 34 |
| IO42 | `/brain/J2R3` | 35 |
| IO43 | `/brain/J1T` | 37 |
| IO44 | `/brain/J1R1` | 36 |
| IO45 | `unconnected-(U6-IO45-Pad26)` | 26 |
| IO46 | `unconnected-(U6-IO46-Pad16)` | 16 |
| IO47 | `/brain/J1R2` | 24 |
| IO48 | `/brain/J1R3` | 25 |
| IO5 | `/power/PWR_OFF` | 5 |
| IO6 | `/power/CE` | 6 |
| IO7 | `/power/INT` | 7 |
| IO8 | `/power/MAX_ALRT` | 12 |
| IO9 | `/ui/DC` | 17 |

## Power rails (selected)

- **+3V3** (28 nodes) — ICs: U3.VOUT_6, U6.3V3_2, U9.VDD_9
- **+BATT** (10 nodes) — ICs: U1.BATSNS_10, U4.TH_A1, U4.CSN_A3, U4.BATT_B1
- **-BATT** (3 nodes) — ICs: —
- **/power/BATT_BQ** (5 nodes) — ICs: U1.BAT_13, U1.BAT_14, U4.CSPH_C2
- **/power/REGN** (4 nodes) — ICs: U1.REGN_22
- **GND** (105 nodes) — ICs: U1.PGND_17, U1.PGND_18, U1.PSEL_2, U1.EP_25, U2.GND_2, U3.MODE_2, U3.AGND_3, U3.GND_8, U4.GND/CSPL_C3, U5.GND_17, U5.AD_37, U5.GND_39
- **Net-(U9-VCC)** (3 nodes) — ICs: U9.VCC_28
- **VBUS** (9 nodes) — ICs: U1.VAC_1, U1.VBUS_24, USB1.VBUS_A4B9, USB1.VBUS_B4A9
- **VCC** (18 nodes) — ICs: U2.QOD_5, U2.VOUT_6, U3.EN_1, U3.VIN_10, U5.VCC_38, U7.AD_37, U7.VCC_38, U9.VBAT_6
- **VSYS** (9 nodes) — ICs: U1.SYS_15, U1.SYS_16, U2.VIN_1

## Placeholders / generics

11 components still use generic or non-LCSC symbols (connectors, switches, passives without C-numbers, etc.).

## Open questions

See `open-questions.md` (14 items, including process reminders).
