# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

#### **VAlrtTh Register (01h)** 

Register Type: Special 

Initial Value: 0xFF00 (Disabled) 

The VAlrtTh register shown in <u>Table 12</u> sets upper and lower limits that generate an alert if exceeded by the VCell register value. The upper 8 bits set the maximum value and the lower 8 bits set the minimum value. Interrupt threshold limits are selectable with 20mV resolution over the full operating range of the VCell register. 

## **Table 12. VAlrtTh (01h) Format** 

D15 D14 D13 D12 D11 D10 D9 D8 D7 D6 D5 D4 D3 D2 D1 D0 VMAX VMIN 

**VMAX:** Maximum voltage reading. An alert is generated if the VCell register reading exceeds this value. 

**VMIN:** Minimum voltage reading. An alert is generated if the VCell register reading falls below this value. 

#### **TAlrtTh Register (02h)** 

Register Type: Special 

Initial Value: 0x7F80 (Disabled) 

The TAlrtTh register (Table 13) sets upper and lower limits that generate an alert if exceeded by the Temp register value. The upper 8 bits set the maximum value and the lower 8 bits set the minimum value. Interrupt threshold limits are stored in two’s-complement format with 1°C resolution over the full operating range of the Temp register. 

## **Table 13. TAlrtTh (02h) Format** 

D15 D14 D13 D12 D11 D10 D9 D8 D7 D6 D5 D4 D3 D2 D1 D0 TMAX TMIN 

**TMAX:** Maximum temperature reading. An alert is generated if the Temp register reading exceeds this value. 

**TMIN:** Minimum temperature reading. An alert is generated if the Temp register reading falls below this value. 

#### **SAlrtTh Register (03h)** 

Register Type: Special 

Initial Value: 0xFF00 (Disabled) 

The SAlrtTh register shown (Table 14) sets upper and lower limits that generate an alert if exceeded by RepSOC. The upper 8 bits set the maximum value and the lower 8 bits set the minimum value. Interrupt threshold limits are configurable with 1% resolution over the full operating range of the RepSOC register. 

## **Table 14. SAlrtTh (03h) Format** 


**SMAX:** Maximum state-of-charge threshold. An alert is generated if the RepSOC register exceeds this value. **SMIN:** Minimum state-of-charge threshold. An alert is generated if the RepSOC register falls below this value. 

#### **IAlrtTh Register (B4h)** 

Register Type: Special 

Initial Value: 0x7F80 (Disabled) 

The IAlrtTh register (Table 15) sets upper and lower limits that generate an alert if exceeded by the Current register value. The upper 8 bits set the maximum value and the lower 8 bits set the minimum value. Interrupt threshold limits are selectable with 0.4mV/RSENSE resolution over the full operating range of the Current register. 

## **Table 15. IAlrtTh (B4h) Format** 

D15 D14 D13 D12 D11 D10 D9 D8 D7 D6 D5 D4 D3 D2 D1 D0

## Structured tables

- [with 1% resolution over the full operating range of the RepSOC register. Table 14. SAlrtTh (03h) Format](../tables/page-24-with-1-resolution-over-the-full-operating-range-of-the-repsoc-register-table-14.yaml)
