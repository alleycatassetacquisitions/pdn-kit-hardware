# **IS31FL3236A** 

For example: D7:D0 = 10110101, 

IOUT = IMAX (2<sup>0</sup> +2<sup>2</sup> +2<sup>4</sup> +2<sup>5</sup> +2<sup>7</sup> )/256 

The IOUT of each channel is setting by the SL bit of LED Control Register (26h~49h). Please refer to the detail information in Page 11. 

### **25h  PWM Update Register** 

The data sent to the PWM Registers and the LED Control Registers will be stored in temporary registers. A write operation of “0000 0000” value to the Update Register is required to update the registers (01h~24h, 26h~49h). 

**Table 5  26h~49h  LED Control Register** **<u>(OUT1~OUT36)</u>** 


The LED Control Registers store the on or off state of each LED and set the output current. 

- **SL Output Current Setting (IOUT)** 00 IMAX 01 IMAX/2 10 IMAX/3 11 IMAX/4 

- **OUT** LED State 0 LED off 1 LED on 

![](../images/IS31FL3236A.pdf-0008-11.png)

**Table 6  4Ah  Global Control Register** 


The Global Control Register set all channels enable. 

### **G_EN Global LED Enable** 

0 Normal operation 1 Shutdown all LEDs 

**Table 7  4Bh Output Frequency Setting Register** 


The Output Frequency Setting Register selects a fixed PWM operating frequency for all output channels. 

- **OFS Output Frequency Setting** 0 3kHz 

- 1 22kHz 

### **4Fh  Reset Register** 

Once user writes “0000 0000” data to the Reset Register, IS31FL3236A will reset all registers to default value. On initial power-up, the IS31FL3236A registers are reset to their default values for a blank display.

## Structured tables

- [Table 6 4Ah Global Control Register](../tables/page-08-table-6-4ah-global-control-register.yaml)
- [1 Shutdown all LEDs Table 7 4Bh Output Frequency Setting Register](../tables/page-08-1-shutdown-all-leds-table-7-4bh-output-frequency-setting-register.yaml)
- [Table 5 26h~49h LED Control Register (OUT1~OUT36)](../tables/page-08-table-5-26h-49h-led-control-register-out1-out36.yaml)
