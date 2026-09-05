# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

**Table 9. Current Measurement Range and Resolution vs. Sense Resistor Value (continued)** 


#### **AvgCurrent Register (0Bh)** 

#### Register Type: Current 

The AvgCurrent register reports an average of Current register readings. 

#### **MaxMinCurr Register (1Ch)** 

Register Type: Special 

#### Initial Value: 0x807F 

The MaxMinCurr register maintains the maximum and minimum Current register values since the last IC reset or until cleared by host software. At power-up, the maximum current value is set to 80h (most negative) and the minimum current value is set to 7Fh (most positive). Therefore, both values are changed to the Current register reading after the first update. Host software can reset this register by writing it to its power-up value of 0x807F. The maximum and minimum currents are each stored as two’s complement 8-bit values with (0.4mV) / Rsense resolution. <u>Table 10</u> shows the register format. 

## **Table 10. MaxMinCurr (1Ch) Format** 


**MaxCurrent:** Maximum Current register reading 

**MinCurrent:** Minimum Current register reading 

#### **Temperature Measurement** 

The IC can be configured to measure its own internal die temperature or an external NTC thermistor. 

Set Config.TSEL = 0 (default) to enable die temperature measurement. Set Config.TSEL = 1 to enable thermistor measurement. 

Thermistor conversions are initiated by periodically connecting the TH and BATT pins internally. Measurement results of TH pin are compared to the voltage of the BATT pin and converted to a ratiometric value from 0% to 100%. The active pullup is disabled when temperature measurements are complete. This reduces the current consumption. 

The ratiometric results are converted to temperature using the temperature gain (TGain), temperature offset (TOff), and temperature curve (Curve) register values. Internal die temperature measurements are factory calibrated and are not affected by TGain, TOff, and Curve register settings. Refer to the _<u>User Guide 6597: MAX1726x ModelGauge m5 EZ User Guide</u>_ for more details. Additionally, the IC maintains a record of the minimum and maximum temperature measured and an average temperature. 

#### **Temp Register (08h)** 

Register Type: Temperature 

The Temp register provides the temperature measured by the thermistor or die temperature based on the Config register setting.

## Structured tables

- [Table 9. Current Measurement Range and Resolution vs. Sense Resistor Value (continued)](../tables/page-22-table-9-current-measurement-range-and-resolution-vs-sense-resistor-value-continu.yaml)
- [format. Table 10. MaxMinCurr (1Ch) Format](../tables/page-22-format-table-10-maxmincurr-1ch-format.yaml)
