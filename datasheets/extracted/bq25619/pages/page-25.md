During faults of BAT_FAULT, NTC_FAULT that lead to charging suspend, the safety timer is suspended as well. Once the fault goes away, the timer resumes. If the user stops the current charging cycle, and starts it again, the timer gets reset (toggle of CE pin or CHG_CONFIG bit). 

###### **_7.3.7 Ship Mode and QON Pin_** 

###### **7.3.7.1 BATFET Disable (Enter Ship Mode)** 

To extend battery life and minimize power when the system is powered off during system idle, shipping, or storage, the device turns off BATFET so that the system voltage is floating to minimize the battery leakage current. When the host sets the BATFET_DIS bit, the charger can turn off the BATFET immediately or delay by tBATFET_DLY as configured by the BATFET_DLY bit. To set the device into ship mode with the adapter present, the host has to first set BATFET_RST_VBUS to 1 and then BATFET_DIS to 1. The charger will turn off the BATFET (no charging, no supplement) while the adapter is still attached. When the adapter is removed, the charger will enter ship mode. 

###### **7.3.7.2 BATFET Enable (Exit Ship Mode)** 

When the BATFET is disabled (in ship mode) as indicated by setting BATFET_DIS, one of the following events can enable the BATFET to restore system power: 

1. Plug in adapter 

2. Clear BATFET_DIS bit 

3. Set REG_RST bit to reset all registers including BATFET_DIS bit to default (0) 

4. A logic high to low transition on QON pin with tSHIPMODE deglitch time to enable BATFET to exit ship mode. EN_HIZ bit is set to 1 (regardless of adapter present or not). Host has to set EN_HIZ bit to 0 before boost mode enable. Once adapter plugs in, EN_HIZ will be cleared. 

###### **7.3.7.3 BATFET Full System Reset** 

The BATFET functions as a load switch between the battery and system when an input source is not plugged in. When BATFET_RST_EN = 1 and BATFET_DIS = 0, the BATFET full system reset function is enabled. By changing the state of BATFET from on to off, systems connected to SYS can be effectively forced to have a power-on-reset. After the reset is complete, the device is in the POR state, and all registers are in POR default settings. The QON pin supports a push-button interface to reset system power without the host by changing the state of BATFET. Internally, it is pulled up to the VQON voltage through a 200-kΩ resistor. 

When the QON pin is driven to logic low for tQON_RST, the BATFET reset process starts. The BATFET is turned off for tBATFET_RST and then it is re-enabled to reset system power. This function can be disabled by setting the BATFET_RST_EN bit to 0. 

The BATFET full system reset functions either with or without an adapter present. If BATFET_RST_WVBUS = 1, the system reset function starts after tQON_RST when the QON pin is pushed to LOW. Once the reset process starts, the device first goes into HIZ mode to turn off the converter, and then power cycles BATFET. If BATFET_RST_WVBUS = 0, the system reset function does not start until tQON_RST after the QON pin is pushed to LOW and the adapter is removed. 

After the BATFET full system reset is complete, the device powers up again if EN_HIZ is not set to 1 before the system reset. 

