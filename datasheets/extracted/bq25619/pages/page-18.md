###### **7.3.3.3 Input Source Type Detection (IINDPM Threshold)** 

After poor source detection, the device runs input source detection through the PSEL pin. The PSEL pin sets input current limit 0.5 A (HIGH) or 2.4 A (LOW). After input source type detection is completed, the PMID_GOOD pin is asserted to HIGH and the PG_STAT bit goes to 1. 

With I<sup>2</sup> C, after input source type detection is completed, an INT pulse is asserted to the host. In addition, the following register bits are updated: 

1. Input Current Limit (IINDPM) register is updated from detection result 

2. VBUS_STAT bit is updated to indicate USB or other input source 

3. PG_STAT bit is updated to indicate good adapter plugs in 

The host can overwrite the IINDPM register to change the input current limit if needed. 

###### **_7.3.3.3.1 PSEL Pins Sets Input Current Limit_** 

The device with the PSEL pin directly takes the USB PHY device output to decide whether the input is a USB host or charging port. When the device operates in host-control mode, the host needs the INDET_EN bit set to 1 to update the IINDPM register. When the device is in default mode, the PSEL value updates IINDPM in real time. 

**Table 7-1. Input Current Limit Setting from PSEL** 


###### **7.3.3.4 Input Voltage Limit Threshold Setting (VINDPM Threshold)** 

The device has two modes to set the VINDPM threshold. 

- Fixed VINDPM threshold. VINDPM is in default set at 4.5 V (programmable from 3.9 V to 5.4 V) . 

- VINDPM threshold tracks the battery voltage to optimize the converter headroom between input and output. When it is enabled in REG07[1:0], the actual input voltage limit is the higher of the VINDPM setting in register and VBAT + offset voltage in VINDPM_BAT_TRACK[1:0] . 

###### **7.3.3.5 Power Up Converter in Buck Mode** 

After the input current limit is set, the converter is enabled and the HSFET and LSFET start switching. The system voltage is powered from the converter instead of the battery. If battery charging is disabled, the BATFET turns off. Otherwise, the BATFET stays on to charge the battery. 

The device provides soft start when the system rail is ramping up. When the system rail is below VBAT_SHORT, the input current is limited to the lower of 200 mA or IINDPM register setting. The system load should be appropriately planned not to exceed the 200-mA IINDPM limit. After the system rises above VBAT_SHORTZ, the device input current limit is the value set by the IINDPM register. 

As a battery charger, the device deploys a highly efficient 1.5-MHz step-down switching regulator. The fixed frequency oscillator keeps tight control of the switching frequency under all conditions of input voltage, battery voltage, charge current, and temperature simplifying output filter design. 

The converter supports PFM operation by default for fast transient response during system voltage regulation and better light load efficiency. The PFM_DIS bit disables PFM operation if system voltage is not in regulation. 

###### **7.3.3.6 HIZ Mode with Adapter Present** 

By setting the EN_HIZ bit to 1 with adapter, the device enters a high impedance state (HIZ). In HIZ mode, the system is powered from the battery even with good adapter present. The device is in the low input quiescent current state with Q1 RBFET, REGN LDO, and the bias circuits off.

## Structured tables

- [to update the IINDPM register. When the device is in default mode, the PSEL value updates IINDPM in real time. Table 7-1. Input Current Limit Setting from PSEL](../tables/page-18-to-update-the-iindpm-register-when-the-device-is-in-default-mode-the-psel-value.yaml)
