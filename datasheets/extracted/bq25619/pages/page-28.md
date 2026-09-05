###### **7.3.9.2 Voltage and Current Monitoring in Boost Mode** 

###### **_7.3.9.2.1 Boost Mode Overvoltage Protection_** 

When PMID voltage rises above the regulation target and exceeds VBST_OVP, the device stops switching immediately and the device exits Boost mode and PMID_GOOD is pulled low as well. The BST_CONFIG bit is set to 0. During Boost mode overvoltage, the fault register bit BOOST_FAULT is set to 1 to indicate a fault in boost operation. An INT is asserted to the host. 

###### **_7.3.9.2.2 PMID Overcurrent Protection_** 

The BQ25619/618 closely monitors the battery discharge current through BATFET (Q4) to ensure safe Boost mode operation. During an overcurrent condition when boost input current exceeds ISYS_OCP_Q4, the device latches off in 100 µs. When an overcurrent condition is detected, the fault register bit BOOST_FAULT is set high to indicate a fault in boost operation. An INT is asserted to the host. 

###### **7.3.9.3 Thermal Regulation and Thermal Shutdown** 

###### **_7.3.9.3.1 Thermal Protection in Buck Mode_** 

Besides the battery temperature monitor on the TS pin, the device monitors the internal junction temperature TJ to avoid overheating the chip and limits the IC junction temperature in buck mode. When the internal junction temperature exceeds the thermal regulation limit (110°C), the device lowers down the charge current. During thermal regulation, the actual charging current is usually below the programmed battery charging current. Therefore, termination is disabled, the safety timer runs at half the clock rate, and the status register THERM_STAT bit goes high. 

Additionally, the device has thermal shutdown to turn off the converter and the BATFET when the IC surface temperature exceeds TSHUT 150°C. The BATFET and converter are enabled to recover when IC temperature is 130°C. The fault register CHRG_FAULT is set to 10 during thermal shutdown and an INT is asserted to the host. 

###### **_7.3.9.3.2 Thermal Protection in Boost Mode_** 

Besides the battery temperature monitor on the TS pin, the device monitors the internal junction temperature to provide thermal shutdown during Boost mode. When the IC junction temperature exceeds TSHUT 150°C, Boost mode is disabled by setting the BST_CONFIG bit low. When the IC junction temperature is below 145°C, the host can re-enable Boost mode. 

###### **7.3.9.4 Battery Protection** 

###### **_7.3.9.4.1 Battery Overvoltage Protection (BATOVP)_** 

The battery overvoltage limit is clamped at 4% above battery regulation voltage. When battery overvoltage occurs, the charger device immediately stops switching. The fault register BAT_FAULT bit goes high and an INT is asserted to the host. 

###### **_7.3.9.4.2 Battery Overdischarge Protection_** 

When the battery is discharged below VBAT_DPL_FALL, the BATFET latches off to protect the battery from overdischarge. To recover from overdischarge latch-off, an input source plug-in is required at VAC/VBUS. 

###### **_7.3.9.4.3 System Overcurrent Protection_** 

ISYS_OCP_Q4 sets the battery discharge current limit. Once IBAT > ISYS_OCP_Q4 , the charger latches off Q4 and puts the device into Ship mode. All methods to exit Ship mode are valid to bring the part out of Q4 latch-off. 

###### **_7.3.10 Serial Interface_** 

The device uses an I<sup>2</sup> C compatible interface for flexible charging parameter programming and instantaneous device status reporting. I<sup>2</sup> C<sup>TM</sup> is a bi-directional 2-wire serial interface developed by Philips Semiconductor (now NXP Semiconductors). Only two bus lines are required: a serial data line (SDA) and a serial clock line (SCL). Devices can be considered as masters or slaves when performing data transfers. A master is the device which initiates a data transfer on the bus and generates the clock signals to permit that transfer. At that time, any device addressed is considered a slave. 

