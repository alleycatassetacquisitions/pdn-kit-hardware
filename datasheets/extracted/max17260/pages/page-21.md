# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

### **Analog Measurements** 

The IC monitors voltage, current, and temperature. This information is provided to the fuel-gauge algorithm to predict cell capacity and also made available to the user. 

#### **Voltage Measurement** 

#### **VCell Register (09h)** 

Register Type: Voltage 

VCell reports the voltage measured between BATT and GND. 

#### **AvgVCell Register (19h)** 

Register Type: Voltage 

The AvgVCell register reports an average of the VCell register readings. 

#### **MaxMinVolt Register (1Bh)** 

Register Type: Special 

Initial Value: 0x00FF 

The MaxMinVolt register maintains the maximum and minimum of VCell register values since device reset. At power-up, the maximum voltage value is set to 00h (the minimum) and the minimum voltage value is set to FFh (the maximum). Therefore, both values are changed to the voltage register reading after the first update. Host software can reset this register by writing it to its power-up value of 0x00FF. The maximum and minimum voltages are each stored as 8-bit values with a 20mV resolution. Table 8 shows the register format. 

## **Table 8. MaxMinVolt (1Bh) Format** 

D15 D14 D13 D12 D11 D10 D9 D8 D7 D6 D5 D4 D3 D2 D1 D0 MaxVCELL MinVCELL 

**MaxVCELL:** Maximum VCell register reading 

**MinVCELL:** Minimum VCell register reading 

#### **Current Measurement** 

The IC monitors the current flow through the battery by measuring the voltage across the current-sensing element over a ±51.2mV range. The IC is precalibrated for current-measurement accuracy in Maxim's factory. 

Additionally, the IC maintains a record of the minimum and maximum current measured by the IC and an average current. 

See the _<u>Layout Guidelines</u>_ section for the recommended board layout to minimize current-sense error. 

#### **Current Register (0Ah)** 

Register Type: Current 

The IC measures the voltage across the sense resistor, and the result is stored as a two’s complement value in the Current register. Voltages outside the minimum and maximum register values are reported as the minimum or maximum value. The register value should be divided by the sense resistance to convert to amperes. The value of the sense resistor determines the resolution and the full-scale range of the current readings. Table 9 shows range and resolution values for typical sense resistances. This is for rechargeable applications. Non-rechargeable applications with long run-times should generally use higher sense resistor value. 

**Table 9. Current Measurement Range and Resolution vs. Sense Resistor Value**

## Structured tables

- [should generally use higher sense resistor value. Table 9. Current Measurement Range and Resolution vs. Sense Resistor Value](../tables/page-21-should-generally-use-higher-sense-resistor-value-table-9-current-measurement-ran.yaml)
