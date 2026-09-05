# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

The VEmpty register sets thresholds related to empty detection during operation. Table 3 shows the register format. 

## **Table 3. VEmpty (3Ah) Format** 

D15 D14 D13 D12 D11 D10 D9 D8 D7 D6 D5 D4 D3 D2 D1 D0 VE VR 

**VE:** Empty voltage target, during load. The fuel gauge provides capacity and percentage relative to the empty voltage target, eventually declaring 0% at VE. A 10mV resolution gives a 0V to 5.11V range. This value defaults to 3.3V after reset. 

**VR:** Recovery voltage. Sets the voltage level for clearing empty detection. Once the cell voltage rises above this point, empty voltage detection is reenabled. A 40mV resolution gives a 0V to 5.08V range. This value defaults to 3.88V, which is recommended for most applications. 

#### **ModelCfg Register (DBh)** 

Register Type: Special 

The ModelCFG register controls basic options of the EZ algorithm. Table 4 shows the register format. 

## **Table 4. ModelCFG (DBh) Format** 


**Refresh:** Set Refresh to 1 to command the model reload. After completion the MAX17260 clears Refresh to 0. 

**R100:** if using 100kΩ NTC, set R100 = 1; if using 10kΩ NTC, set R100 = 0. 

**0:** Bit must be written 0. Do not write 1. 

**ModelID:** Choose from one of the following Lithium models. For the majority of batteries, use ModelID = 0. 

ModelID = 0: Use for most lithium cobalt-oxide variants (a large majority of lithium in the market-place). Supported by EZ without characterization. 

ModelID = 2: Use for lithium NCR or NCA cells such as Panasonic. Custom characterization is recommended in this case. 

ModelID = 6: Use for lithium iron-phosphate (LiFePO4). Custom characterization is recommended in this case. 

**VChg:** Set VChg to 1 for charge voltage higher than 4.25V (4.3V–4.4V). Set VChg to 0 for 4.2V charge voltage. 

**CSEL:** Hi-side / lo-side current sense selection. The current-sense schematic is automatically determined at bootup, and CSEL is initialized to the appropriate setting. Applications should generally not change CSEL to preserve the autodetected setting. 

#### **IChgTerm Register (1Eh)** 

Register Type: Current 

Initial Value: 0x0640 (250mA on 10mΩ) 

The IChgTerm register allows the device to detect when charge termination has occurred. Program IChgTerm to the exact charge termination current used in the application. 

Refer to the _End-of-Charge Detection_ section of the _<u>User Guide 6597: MAX1726x ModelGauge m5 EZ User Guide</u>_ for more details. 

#### **Config Register (1Dh) and Config2 Register (BBh)** 

Register Type: Special 

Initial Value: 0x2210 for Config, 0x3658 for Config2 

The Config registers hold all shutdown enable, alert enable, and temperature enable control bits. Writing a bit location enables the corresponding function within one task period. Table 5 and Table 6 show the register formats.

## Structured tables

- [The ModelCFG register controls basic options of the EZ algorithm. Table 4 shows the register format. Table 4. ModelCFG (DBh) Format](../tables/page-16-the-modelcfg-register-controls-basic-options-of-the-ez-algorithm-table-4-shows-t.yaml)
