**Table 7-2. Charging Parameter Default Settings** 

**<u>(continued)</u>** 


A new charge cycle starts when the following conditions are valid: 

- Converter starts 

- Battery charging is enabled (CHG_CONFIG bit = 1 and ICHG register is not 0 mA and CE is low) 

- No thermistor fault on TS. (TS pin can be ignored by setting TS_IGNORE bit to 1) 

- No safety timer fault 

- BATFET is not forced to turn off (BATFET_DIS bit = 0) 

The device automatically terminates the charging cycle when the charging current is below the termination threshold, the battery voltage is above the recharge threshold, and the device is not in DPM mode or thermal regulation. When a fully charged battery is discharged below recharge threshold (selectable through VRECHG bit), the device automatically starts a new charging cycle. After the charge is done, a toggle of the CE pin or CHG_CONFIG bit initiates a new charging cycle. Adapter removal and replug will also restart a charging cycle. 

The STAT output indicates charging status: charging (LOW), charging complete or charge disable (HIGH), or charging fault (blinking). The status register (CHRG_STAT) indicates the different charging phases: 00-charging disable, 01-precharge, 10-fast charge (CC) and constant voltage (CV), 11-charging done. Once a charging cycle is completed, an INT pulse is asserted to notify the host. 

###### **7.3.6.2 Battery Charging Profile** 

The device charges the battery in five phases: battery short, preconditioning, constant current, constant voltage, and top-off trickle charging (optional). At the beginning of a charging cycle, the device checks the battery voltage and regulates current and voltage accordingly. 

Resistance between charger output and battery cell terminal such as board routing, connector, MOSFETs, and sense resistor can force the charging process to move from constant current to constant voltage too early and increase charge time. To speed up the charging cycle, the device provides the BATSNS pin to extend the constant current charge time to deliver maximum power to battery. The BATSNS pin is connected directly to the battery cell terminal to remotely sense battery cell voltage. BATSNS is by default enabled and can be disabled through the BATSNS_DIS bit. If BATSNS is connected to GND or left floating, the charger regulates the BAT pin instead. 

**Table 7-3. Charging Current Setting**

## Structured tables

- [Table 7-2. Charging Parameter Default Settings (continued)](../tables/page-21-table-7-2-charging-parameter-default-settings-continued.yaml)
- [instead. Table 7-3. Charging Current Setting](../tables/page-21-instead-table-7-3-charging-current-setting.yaml)
