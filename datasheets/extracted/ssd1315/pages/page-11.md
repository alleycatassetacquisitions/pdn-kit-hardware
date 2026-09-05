
![](../images/ssd1315.pdf-0011-02.png)

#### 3.3.1.2 **68XX-Series MPU Parallel Interface with Internal Charge Pump** 

特别提醒 **(Special Tips):** 主板设计务必加电子开关 , 否则 , 可能引起漏电流现象 

(When design main board, Please add Electronic Switch circuit, otherwise, will be caused leak current) 

![](../images/ssd1315.pdf-0011-06.png)

<!-- Start of picture text -->
68xx parallel interface<br>Vin 1<br>N.C. (GND)<br>R2 2<br>S C2P<br>C2 3<br>D C2N<br>G Q1 4<br>C1P<br>G Q2 D C1 5 C1N<br>GPIO S 6 VBAT<br>R3 C6 7<br>N.C.<br>8<br>VSS<br>VDD<br>9<br>VDD<br>C5 10<br>BS0<br>11<br>BS1<br>12<br>BS2<br>13<br>CS# CS#<br>14<br>RES# RES#<br>15<br>D/C# D/C#<br>16<br>R/W# R/W#<br>17<br>E E/RD#<br>18<br>D[7:0] D0<br>19<br>D1<br>20<br>D2<br>21<br>D3<br>22<br>D4<br>23<br>D5<br>24<br>D6<br>25<br>D7<br>R1 26<br>IREF<br>C4 27<br>VCOMH<br>C3 28<br>VCC<br>29<br>VLSS<br>30<br>N.C. (GND)<br>GND<br>UT-0206-P05<br><!-- End of picture text -->

#### **Recommended Components:** 

C1, C2: 1μF / 16V, X5R C3: 2.2μF C4: 4.7μF / 16V, X7R C5, C6: 1μF R1: 910kΩ, R1 = (Voltage at IREF - VSS) / IREF R2, R3: 47kΩ Q1: FDN338P Q2: FDN335N **Notes:** 

VDD: 1.65~3.3V, it should be equal to MPU I/O voltage. Vin: 3.5~4.2V 

* VBAT will be connected to VDD when VCC be connected to external source (12V), R1 should be 

replaced as **910 kΩ** . 

![](../images/ssd1315.pdf-0011-12.png)

