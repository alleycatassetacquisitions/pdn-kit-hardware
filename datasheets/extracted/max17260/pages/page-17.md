# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

## **Table 5. Config (1Dh) Format** 

|D15|D14|D13|D12|<br>D11|D10|D9|D8<br>D7|D6|D5|<br>D4||D3|D2|D1|D0|
|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|---|
|TSel|SS|TS|VS|IS|THSH|<br>Ten|Tex<br>SHDN<br>CO|MMSH|0|ETH|RM|FTHRM|Aen|Bei|Ber|
|**Tabl**|**e 6. C**|**onfig**|**2 (**|**BBh)**|**Form**|**at**||||||||||
|D15|D14|D1|3|D12|D11|D10|D9<br>D8<br>D7|D6||D5|D4|D3<br>D2||D1|D0|
|0|0|AtRat|eEn|DPEn||POW|R<br>dSOCen|TAlrtEn||LDMdl|1|DRCfg|CP|Mode|0|

**0:** Bit must be written 0. Do not write 1. 

#### **1:** Bit must be written 1. Do not write 0. 

**TSEL:** Temperature sensor select. Set to 0 to use internal die temperature. Set to 1 to use temperature information from thermistor. ETHRM bit must be set to 1 when TSel is 1. 

**SS:** SOC ALRT Sticky. When SS = 1, SOC alerts can only be cleared through software. When SS = 0, SOC alerts are cleared automatically when the threshold is no longer exceeded. 

**TS:** Temperature ALRT Sticky. When TS = 1, temperature alerts can only be cleared through software. When TS = 0, temperature alerts are cleared automatically when the threshold is no longer exceeded. 

**VS:** Voltage ALRT Sticky. When VS = 1, voltage alerts can only be cleared through software. When VS = 0, voltage alerts are cleared automatically when the threshold is no longer exceeded. 

**IS:** Current ALRT Sticky. When IS = 1, current alerts can only be cleared through software. When IS = 0, current alerts are cleared automatically when the threshold is no longer exceeded. 

**THSH:** TH Pin Shutdown. Set to 1 to enable device shutdown when the IC is mounted host-side and the battery is removed. The IC enters shutdown if the TH pin remains high (VTH > VBATT - VDET) for longer than the timeout of the ShdnTimer register. This also configures the device to wake up when TH is pulled low with a thermistor on-cell insertion. Note that if COMMSH and AINSH are both set to 0, the device wakes up on any edge of SDA. 

**Ten:** Enable Temperature Channel. Set to 1 and set ETHRM or FTHRM to 1 to enable temperature measurement. 

**Tex:** Temperature External. When set to 1, the fuel gauge requires external temperature measurements to be written from the host. When set to 0, the ICs own measurements are used instead. 

**SHDN:** Shutdown. Write this bit to logic 1 to force a shutdown of the device after timeout of the ShdnTimer register (default 45s delay). SHDN is reset to 0 at power-up and upon exiting shutdown mode. In order to command shutdown within 45 seconds, first write HibCFG = 0x0000 to enter active mode. 

**COMMSH:** Communication Shutdown. Set to logic 1 to force the device to enter shutdown mode if both SDA and SCL are held low for more than timeout of the ShdnTimer register. This also configures the device to wake up on a rising edge of any communication. Note that if COMMSH and THSH are both set to 0, the device wakes up on any edge of SDA. Refer to the _<u>User Guide 6597: MAX1726x ModelGauge m5 EZ User Guide</u>_ for details. 

**ETHRM:** Enable Thermistor. Set to logic 1 to enable the TH pin measurement. 

**FTHRM:** Force Thermistor Bias Switch. This allows the host to control the bias of the thermistor switch or enable fast detection of battery removal. Set FTHRM = 1 to always enable the thermistor bias switch. With a standard 10kΩ thermistor, this adds an additional ~200μA to the current drain of the circuit. 

**Aen:** Enable alert on fuel-gauge outputs. When Aen = 1, any violation of the alert threshold register values by temperature, voltage, current, or SOC triggers an alert. This bit affects the ALRT pin operation only. The Smx, Smn, Tmx, Tmn, Vmx, Vmn, Imx, and Imn bits of the Status register (000h) are not disabled. 

**Bei:** Enable alert on battery insertion when the IC is mounted host-side. When Bei = 1, a battery-insertion condition, as detected by the TH pin voltage, triggers an alert. 

**Ber:** Enable alert on battery removal when the IC is mounted host-side. When Ber = 1, a battery-removal condition, as detected by the TH pin voltage, triggers an alert. 

**AtRateEn:** AtRate enable. When this bit is set to 0, AtRate calculations are disabled and registers AtQResidual/AtTTE/ AtAvSOC/AtAvCap can be used as general purpose memory. 

**DPEn:** Dynamic power enable. When this bit is set to 0, Dynamic Power calculations are disabled and registers 

