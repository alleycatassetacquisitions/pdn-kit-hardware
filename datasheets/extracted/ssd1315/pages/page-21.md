
![](../images/ssd1315.pdf-0021-02.png)

#### **4.4 Actual Application Example** 

Command usage and explanation of an actual example 

#### 4.4.1 VCC Supplied Externally 

<Power up Sequence> 

![](../images/ssd1315.pdf-0021-07.png)

<!-- Start of picture text -->
Set Display Offset Set Entire Display On/Off<br>VDD/VCC off State<br>0xD3, 0x00 0xA4<br>Power up VDD Set Display Start Line Set Normal/Inverse Display<br>(RES# as Low State)  0x40 0xA6<br>Power Stabilized Set Charge Pump<br>Clear Screen<br>(Delay Recommended)  0x8D, 0x10<br>Set RES# as High Set Segment Re-Map Power up VCC & Stabilized<br>(3μs Delay Minimum)  0xA1 (Delay Recommended)<br>Initialized State Set COM Output Scan Direction Set Display On<br>(Parameters as Default)  0xC8 0xAF<br>Set Display Off Set COM Pins Hardware Configuration<br>(100ms Delay Recommended)<br>0xAE  0xDA, 0x12<br>Initial Settings  Set Contrast Control<br>Display Data Sent<br>Configuration  0x81, 0xb0<br>Set Display Clock Divide Ratio/Oscillator Frequency Set Pre-Charge Period<br>0xD5, 0x90  0xD9, 0X22<br>Set Multiplex Ratio Set VCOMH Deselect Level<br>0xA8, 0x3F  0xDB, 0x30<br><!-- End of picture text -->

If the noise is accidentally occurred at the displaying window during the operation, please reset the display in order to recover the display function. 

![](../images/ssd1315.pdf-0021-09.png)

