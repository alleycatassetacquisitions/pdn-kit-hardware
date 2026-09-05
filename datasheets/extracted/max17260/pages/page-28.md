# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

## **Typical Application Circuits** 

<u>Figure 5</u> shows a typical operating circuit for low-side current sensing. A sense resistor is typically used. Alternatively, a PCB trace can be used for high-current or small-form-factor applications. For better measurement, place the sensing element as close as possible to the CSN and GND pins. The IC automatically compensates for the effect of environmental temperature and trace heating on trace resistance. 

<u>Figure 6</u> shows the typical application circuit for high-side current measurement. In this configuration, tie the CSN pin to the battery pack positive terminal. Connect a desired sense resistor or PCB trace across CSN and CSPH. 

![](../images/max17260.pdf-0028-05.png)

<!-- Start of picture text -->
PACK+ SYSPWR SYSPWR<br>BATT BATT<br>0.1µF REG 0.1µF REG<br>0.47µF 0.47µF<br>ALRT ALRT<br>PROTECTION  SDA PROTECTION  SDA<br>CIRCUIT SCL CIRCUIT SCL<br>THRM MAX17260 MAX17260<br>TH TH<br>CSPL(TDFN) CSPL(TDFN)<br>GND EP (TDFN) CSN GND EP (TDFN) CSN<br>10kΩ<br>NTC<br>PACK- 10mΩ RSENSE or  SYSGND 10mΩ RSENSE or  SYSGND<br>BATTERY SYSTEM 2mΩ PCB Trace CAPTIVE BATTERY SYSTEM 2mΩ PCB Trace<br><!-- End of picture text -->

_Figure 5. Low-Side Current Measurement Typical Applications Circuit_ 

![](../images/max17260.pdf-0028-07.png)

<!-- Start of picture text -->
PACK+ 10mΩ R2mΩ PCB traceSENSE or  SYSPWR 10mΩ R2mΩ PCB traceSENSE or  SYSPWR<br>CSN CSPH CSN CSPH<br>BATT BATT<br>0.1µF REG 0.1µF REG<br>0.47µF 0.47µF<br>ALRT ALRT<br>PROTECTION  SDA PROTECTION  SDA<br>CIRCUIT SCL CIRCUIT SCL<br>THRM MAX17260 MAX17260<br>TH TH<br>CSPL(TDFN) CSPL(TDFN)<br>GND EP (TDFN) GND EP (TDFN)<br>10kΩ<br>NTC<br>PACK- SYSGND SYSGND<br>BATTERY SYSTEM CAPTIVE BATTERY SYSTEM<br><!-- End of picture text -->

_Figure 6. High-Side Current Measurement Typical Applications Circuit_ 

