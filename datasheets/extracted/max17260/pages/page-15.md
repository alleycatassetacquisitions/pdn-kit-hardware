# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

### **Application Notes** 

Refer to the following application notes for additional reference material: 

- _<u>User Guide 6597: MAX1726x ModelGauge m5 EZ User Guide</u>_ 

   - Documents full register set 

   - More details about ModelGauge m5 algorithm 

   - Discusses additional applications 

- _<u>User Guide 6595: MAX1726x Software Implementation Guide</u>_ 

   - Guidelines for software drivers including example code 

### **Standard Register Formats** 

Unless otherwise stated during a given register's description, all IC registers follow the same format depending on the type of register. See <u>Table 2</u> for the resolution and range of any register described hereafter. Note that current and capacity values are displayed as a voltage and must be divided by the sense resistor to determine Amps or Amp-hours. 

**Table 2. ModelGauge m5 Register Standard Resolutions** 


### **ModelGauge m5 EZ Configuration Registers** 

The following registers are inputs to the ModelGauge m5 algorithm and store characterization information for the application cells as well as important application specific parameters. They are described briefly here. 

Only the following information is required for configuring ModelGauge m5 EZ: 

- Label Capacity—DesignCap 

- Empty Voltage—VEmpty 

- Charge Termination Current—ICHGTerm 

Refer to the _<u>MAX1726x Software Implementation Guide</u>_ for more details on how to initialize the fuel gauge. 

#### **DesignCap Register (18h)** 

Register Type: Capacity 

Initial value: 0x0BB8 

The DesignCap register holds the nominal capacity of the cell. 

#### **VEmpty Register (3Ah)** 

Register Type: Special Initial Value: 0xA561 (3.3V/3.88V)

## Structured tables

- [capacity values are displayed as a voltage and must be divided by the sense resistor to determine Amps or Amp-hours. Table 2. ModelGauge m5 Register Standard Resolutions](../tables/page-15-capacity-values-are-displayed-as-a-voltage-and-must-be-divided-by-the-sense-resi.yaml)
