- QOD pin is unused and left floating. Using this method, there is no quick output discharge functionality, and the output remains floating after the switch is disabled. 

The fall times of the device depend on many factors including the total discharge resistance (RDIS) and the output capacitance (CL). To calculate the approximate fall time of VOUT use Equation 4. 

tFALL = 2.2 × (RDIS || RL) × CL 

(4) 

Where: 

- tFALL = output fall time from 90% to 10% (μs) 

- RDIS = total QOD + RQOD resistance (Ω) 

- RL = output load resistance (Ω) 

- CL = output load capacitance (μF) 

###### **_9.3.3.1 QOD When System Power is Removed_** 

The adjustable QOD can be used to control the power down sequencing of a system even when the system power supply is removed. When the power is removed, the input capacitor discharges at VIN. Past a certain VIN level, the strength of the RPD is reduced. If there is still remaining charge on the output capacitor, this results in longer fall times. For further information regarding this condition, see the _Setting Fall Time for Shutdown Power Sequencing_ section. 

##### **9.4 Full-Time Reverse Current Blocking** 

In a scenario where the device is enabled and VOUT is greater than VIN there is potential for reverse current to flow through the pass FET or the body diode. When the reverse current threshold (IRCB) is exceeded, the switch is disabled within tRCB. The Switch remains off and block reverse current as long as the reverse voltage condition exists. After VOUT has dropped below the VRCB release threshold the device turns back on with slew rate control. 

##### **9.5 Device Functional Modes** 

Table 9-2 describes the connection of the VOUT pin depending on the state of the ON pin as well as the various QOD pin configurations. 

**Table 9-2. VOUT Connection**

## Structured tables

- [QOD pin configurations. Table 9-2. VOUT Connection](../tables/page-16-qod-pin-configurations-table-9-2-vout-connection.yaml)
