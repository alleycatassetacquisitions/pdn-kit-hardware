# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

The TTF register holds the estimated time to full for the application under present conditions. The TTF value is determined by learning the constant current and constant voltage portions of the charge cycle based on experience of prior charge cycles. Time-to-full is then estimated by comparing the present charge current to the charge termination current. Operation of the TTF register assumes all charge profiles are consistent in the application. The TTF register is only valid when the current register is positive. 

#### **Cycles Register (17h)** 

#### Register Type: Special 

The Cycles register maintains a total count of the number of charge/discharge cycles of the cell. The result is stored as a fraction of a full cycle. For example, a full charge/discharge cycle results in the Cycles register incrementing by 100%. The Cycles register accumulates fractional or whole cycles. For example, if a battery is cycled 10% x 10 times, then it is equivalent to 100% of one cycle. The Cycles register has a full range of 0 to 655.35 cycles with a 1% LSb. 

#### **Status Register (00h)** 

Register Type: Special 

Initial Value: 0x8082 

The Status register maintains all flags related to alert thresholds and battery insertion or removal. <u>Table 7</u> shows the Status register format. 

## **Table 7. Status (00h) Format** 


**POR (Power-On Reset):** This bit is set to 1 when the device detects that a software or hardware POR event has occurred. This bit must be cleared by system software to detect the next POR event. POR is set to 1 at power-up. 

**Imn and Imx (Minimum/Maximum Current-Alert Threshold Exceeded):** These bits are set to 1 whenever a Current register reading is below (Imn) or above (Imx) the IAlrtTh thresholds. These bits may or may not need to be cleared by system software to detect the next event. See Config.IS bit description. Imn and Imx are cleared to 0 at power-up. 

**Vmn and Vmx (Minimum/Maximum Voltage-Alert Threshold Exceeded):** These bits are set to 1 whenever a VCell register reading is below (Vmn) or above (Vmx) the VAlrtTh thresholds. These bits may or may not need to be cleared by system software to detect the next event. See Config.VS bit description. Vmn and Vmx are cleared to 0 at power-up. 

**Tmn and Tmx (Minimum/Maximum Temperature-Alert Threshold Exceeded):** These bits are set to 1 whenever a Temperature register reading is below (Tmn) or above (Tmx) the TAlrtTh thresholds. These bits may or may not need to be cleared by system software to detect the next event. See Config.TS bit description. Tmn and Tmx are cleared to 0 at power-up. 

**Smn and Smx (Minimum/Maximum SOC-Alert Threshold Exceeded):** These bits are set to 1 whenever SOC is below (Smn) or above (Smx) the SAlrtTh thresholds. These bits may or may not need to be cleared by system software to detect the next event. See Config.SS description. Smn and Smx are cleared to 0 at power-up. 

**Bst (Battery Status):** Useful when the IC is used in a host-side application. This bit is set to 0 when a battery is present in the system, and set to 1 when the battery is absent. Bst is set to 0 at power-up. 

**dSOCi (State-of-Charge 1% Change Alert):** This is set to 1 whenever the RepSOC register crosses an integer percentage boundary such as 50.0%, 51.0%, etc. Must be cleared by host software. dSOCi is set to 1 at power-up. 

**Bi (Battery Insertion):** Useful when the IC is used in a host-side application. This bit is set to 1 when the device detects that a battery has been inserted into the system by monitoring the TH pin. This bit must be cleared by system software to detect the next insertion event. Bi is set to 0 at power-up. 

**Br (Battery Removal):** Useful when the IC is used in a host-side application. This bit is set to 1 when the system detects that a battery has been removed from the system. This bit must be cleared by system software to detect the next removal event. Br is set to 1 at power-up. 

**X (Don’t Care):** This bit is undefined and can be logic 0 or 1.

## Structured tables

- [Status register format. Table 7. Status (00h) Format](../tables/page-20-status-register-format-table-7-status-00h-format.yaml)
