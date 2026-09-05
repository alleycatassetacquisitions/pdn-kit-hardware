   - VVBUS above VPOORSRC (typical 3.8 V) when IBADSRC (typical 30 mA) current is applied (not a poor source) 

- Input adapter removed 

- USB/adapter source identified during Section 7.3.3.3. 

- Charge complete 

- Any FAULT event in REG09 

- VINDPM / IINDPM event detected (REG0A[1:0], maskable) 

- Top-off timer starts and expires 

REG09[7:0] and REG0A[6:4] report charger operation faults and status change to the host. When a fault/status change occurs, the charger sends out an INT pulse and keeps the state in REG09[7:0]/REG0A[6:4] until the host reads the registers. Before the host reads REG09[7:0]/REG0A[6:4] and all the ones are cleared, the charger does not send any INT upon new fault/status change. To read the current status, the host has to read REG09/ REG0A two times consecutively. The first read reports the pre-existing register status and the second read reports the current register status. 

###### **7.3.8.4 PMID Voltage Indicator (PMID_GOOD)** 

In the BQ25619/618, the accessory devices can be connected to the charger PMID pin to get power either from the adapter through the Q1 direct path or from battery Boost mode. An optional external PMOS FET can be placed between the charger PMID pin and accessory input to disconnect the power path during overcurrent and overvoltage conditions. PMID_GOOD is used to drive an external PMOS FET through an inverter. PMID_GOOD HIGH turns on an inverter to pull the PMOS FET gate low to turn on the PMOS FET, and PMID_GOOD LOW turns off the PMOS FET. 

Upon adapter plug-in, PMID_GOOD goes from LOW to HIGH when VBUS rises above the battery but below VACOV, and passes poor source detection. During the operation, PMID_GOOD goes from HIGH to LOW if Q1 current exceeds 115% of the IINDPM threshold, (IBLK_OCP), or adapter voltage rises above 5.8 V (VBST_OVP). 

The high-voltage adapter over VBST_OVP keeps charging the battery if all conditions are valid. The external PMOS FET stays off to protect the accessory from an overvoltage fault. 

When the adapter is removed, PMID_GOOD goes LOW before battery Boost mode starts. 

In battery Boost mode, the device regulates PMID voltage between 4.6 V to 5.15 V as a stable power supply to the accessory devices. PMID_GOOD goes from LOW to HIGH when PMID voltage rises above 3.8 V (VPOORSRC). Similar to the adapter present scenario, the PMID valid voltage range is between VPOORSRC and VBST_OVP. Once PMID voltage is out of this range, PMID_GOOD goes LOW to disconnect the accessory device from PMID. During Boost mode, all of the conditions to exit Boost mode will drive PMID_GOOD from HIGH to LOW, including Boost mode disable in register, ACOV, TS fault, battery depleted (VBAT_DPL), BATFET overcurrent, (ISYS_OCP_Q4), etc. 

###### **_7.3.9 Protections_** 

###### **7.3.9.1 Voltage and Current Monitoring in Buck Mode** 

###### **_7.3.9.1.1 Input Overvoltage Protection (ACOV)_** 

The input voltage is sensed via the VAC pin . The default OVP threshold is 14.2 V, and can be programmed at 5.7 V/6.4 V/11 V/14.2 V via OVP[1:0] register bits. ACOV event immediately stops converter switching whether in buck or Boost mode. The device automatically resumes normal operation once the input voltage drops back below the OVP threshold. During ACOV, REGN LDO is on, and the device does not enter HIZ mode. 

During ACOV, the fault register CHRG_FAULT bits are set to 01. An INT pulse is asserted to the host. 

###### **_7.3.9.1.2 System Overvoltage Protection (SYSOVP)_** 

The charger device clamps the system voltage during a load transient so that the components connected to the system are not damaged due to high voltage. The VSYS_OVP threshold is about 300 mV above battery regulation voltage when battery charging is terminated. Upon SYSOVP, the converter stops switching immediately to clamp the overshoot. The charger pulls 30-mA ISYS_LOAD discharge current to bring down the system voltage. 

