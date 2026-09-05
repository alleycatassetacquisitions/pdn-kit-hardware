# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

## **Table 15. IAlrtTh (B4h) Format (continued)** 

IMAX IMIN 

**IMAX:** Maximum current reading. An alert is generated if the current register reading exceeds this value. 

**IMIN:** Maximum current reading. An alert is generated if the current register reading falls below this value. 

### **Serial Number Feature** 

Each IC provides a unique serial number ID. To read this serial number, clear the AtRateEn and the DPEn bit in the Config2 register. The 128-bit serial information overwrites the Dynamic Power and AtRate output registers. To continue Dynamic Power and AtRate operations after reading the serial number, the host should set Config2.AtRateEn and Config2.DPEn to 1. 

**Table 16. Serial Number Format** 


### **ModelGauge m5 Memory Space** 

Registers that relate to functionality of the ModelGauge m5 fuel gauge are located on pages 0h-4h and are continued on pages Bh and Dh. See the _<u>ModelGauge m5 EZ Algorithm</u>_ section for details of specific register operation. Register locations marked reserved should not be written to. 

**Table 17. ModelGauge m5 Register Memory Map**

## Structured tables

- [Config2.DPEn to 1. Table 16. Serial Number Format](../tables/page-25-config2-dpen-to-1-table-16-serial-number-format.yaml)
- [locations marked reserved should not be written to. Table 17. ModelGauge m5 Register Memory Map](../tables/page-25-locations-marked-reserved-should-not-be-written-to-table-17-modelgauge-m5-regist.yaml)
