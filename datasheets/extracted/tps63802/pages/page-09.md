### **9 Detailed Description** 

#### **9.1 Overview** 

The TPS63802 buck-boost converter uses four internal switches to maintain synchronous power conversion at all possible operating conditions. This enables the device to keep high efficiency over a wide input voltage and output load range. To regulate the output voltage at all possible input voltage conditions, the device automatically transitions between buck, buck-boost, and boost operation as required by the operating conditions. Therefore, it operates as a buck converter when the input voltage is higher than the output voltage, and as a boost converter when the input voltage is lower than the output voltage. When the input voltage is close to the output voltage, it operates in a 3-cycle buck-boost operation. In this mode, all four switches are active (see _Section 9.4.1.3_ ). The RMS current through the switches and the inductor is kept at a minimum to minimize switching and conduction losses. Controlling the switches this way allows the converter to always keep high efficiency over the complete input voltage range. The device provides a seamless transition between all modes. 

#### **9.2 Functional Block Diagram** 

![](../images/tps63802.pdf-0009-06.png)

<!-- Start of picture text -->
L<br>L1 L2<br>VIN VOUT<br>CIN COUT<br>Current Gate Gate<br>Sensor Driver Driver<br>Device Device<br>Control Control<br>PG<br>VIN VOUT Device<br>VMAX Switch Control<br>EN + Device Control<br>1.1 VRef ± VIN Power Safe ModeCurrent LimitProtection +± ±+ Ref FB<br>Buck/Boost Control 500 mV<br>Off-time calculation Gate<br>Soft-Start Driver<br>MODE<br>Power<br>VOUT Good<br>GND AGND<br>L1, L2<br><!-- End of picture text -->

