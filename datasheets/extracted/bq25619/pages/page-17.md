###### **7.3 Feature Description** 

###### **_7.3.1 Power-On-Reset (POR)_** 

The device powers internal bias circuits from the higher voltage of VBUS and BAT. When VVBUS rises above VVBUS_UVLOZ or VBAT rises above VBAT_UVLOZ, the sleep comparator, battery depletion comparator, and BATFET driver are active. The I<sup>2</sup> C interface is ready for communication and all registers are reset to default values. The host can access all registers after POR. 

###### **_7.3.2 Device Power Up From Battery Without Input Source_** 

If only the battery is present and the voltage is above depletion threshold (VBAT _DPLZ), the BATFET turns on and connects the battery to the system. The REGN stays off to minimize the quiescent current. The low RDSON of BATFET and the low quiescent current on BAT minimize the conduction loss and maximize the battery run time. 

The device always monitors the discharge current through the BATFET. When the system is overloaded or shorted (IBAT > ISYS_OCP_Q4), the device turns off BATFET immediately. 

With I<sup>2</sup> C, when the BATFET turns off due to overcurrent, the device sets the BATFET_DIS bit to indicate the BATFET is disabled until the input source plugs in again or one of the methods described in Section 7.3.7.2 is applied to re-enable BATFET. 

###### **_7.3.3 Power Up From Input Source_** 

When an input source is plugged in, the device checks the input source voltage to turn on the REGN LDO and all the bias circuits. It detects and sets the input current limit before the buck converter is started. The power-up sequence from input source is as listed: 

1. Power Up REGN LDO, see Section 7.3.3.1 

2. Poor Source Qualification, see Section 7.3.3.2 

3. Input Source Type Detection is based on PSEL to set default input current limit (IINDPM threshold), see Section 7.3.3.3 

4. Input Voltage Limit Threshold Setting (VINDPM threshold), see Section 7.3.3.4 

5. Power Up Converter, see Section 7.3.3.5 

###### **7.3.3.1 Power Up REGN LDO** 

The REGN LDO supplies internal bias circuits as well as the HSFET and LSFET gate drive. It also provides the bias rail to TS external resistors. The pull-up rail of STAT can be connected to REGN as well. The REGN LDO is enabled when all the below conditions are valid: 

- VVBUS > VVBUS_UVLOZ 

- In buck mode, VVBUS > VBAT + VSLEEPZ 

- In boost mode, VVBUS < VBAT + VSLEEPZ 

- After 220-ms delay is completed 

During high impedance mode when EN_HIZ bit is 1, REGN LDO turns off. The battery powers up the system. 

###### **7.3.3.2 Poor Source Qualification** 

After the REGN LDO powers up, the device starts to check current capability of the input source. The first step is poor source detection. 

- VBUS voltage above VPOORSRC when pulling IBADSRC (typical 30 mA) 

With I<sup>2</sup> C, once the input source passes poor source detection, the status register bit VBUS_GD is set to 1 and the INT pin is pulsed to signal to the host. 

If the device fails the poor source detection, it repeats poor source qualification every 2 seconds. 

