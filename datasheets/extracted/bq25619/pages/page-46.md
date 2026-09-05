##### **8 Application and Implementation** 

###### **Note** 

Information in the following applications sections is not part of the TI component specification, and TI does not warrant its accuracy or completeness. TI’s customers are responsible for determining suitability of components for their purposes, as well as validating and testing their design implementation to confirm system functionality. 

###### **8.1 Application Information** 

A typical application consists of the device configured as an I<sup>2</sup> C controlled power path management device and a single cell battery charger for Li-ion and Li-polymer batteries used in a wide range of smart phones and other portable devices. It integrates an input reverse-block FET (RBFET, Q1), high-side switching FET (HSFET, Q2), low-side switching FET (LSFET, Q3), and battery FET (BATFET Q4) between the system and battery. The device also integrates a bootstrap diode for the high-side gate drive. 

###### **8.2 Typical Application** 

![](../images/bq25619.pdf-0046-08.png)

<!-- Start of picture text -->
INPUT<br>4 V ± 13.5 V Optional VAC 1 µH 3.5V-4.52VSYSTEM<br>Max 22V<br>VBUS SW<br>10kŸ<br>1 µF Q1 Q2 BTST 10 µF<br>47 nF<br>Optional Q3<br>VPB REGN<br>Ear Phone<br>PMID<br>15kŸ 10 µF 4. 7 µF<br>20kŸ<br>PGND<br>SYS<br>SYS<br>REGN<br>Q4<br>VREF STAT<br>PMID_GOOD BAT 10 µF<br>BATSNS<br>SDA<br>REGN<br>SCL<br>Host<br>/INT TS<br>Optional if  +<br>/CE TS_IGNORE=1<br>/QON<br>USB<br>PSEL<br>PHY<br>BQ25618 Optional<br>BQ25619<br><!-- End of picture text -->

**Figure 8-1. BQ25619 Application Diagram with Optional PMOS** 

