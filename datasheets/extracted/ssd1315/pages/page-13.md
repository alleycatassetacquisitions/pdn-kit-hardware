
![](../images/ssd1315.pdf-0013-02.png)

#### 3.3.2.2 **80XX-Series MPU Parallel Interface with Internal Charge Pump** 

特别提醒 **(Special Tips):** 主板设计务必加电子开关 , 否则 , 可能引起漏电流现象 

(When design main board, Please add Electronic Switch circuit, otherwise, will be caused leak current) 

80xx parallel interface 

|C1<br>C2<br>1<br>2<br>3<br>4<br>5<br>6<br>7<br>8<br>9<br>10<br><br>VDD<br>C5<br>Vin<br>GPIO<br>Q1<br>D<br>G<br>S<br>Q2<br>S<br>G<br>D<br>R2<br>R3<br>C6|C2P<br>C2N<br>VSS<br>BS0<br>N.C. (GND)<br>VBAT<br>C1P<br>C1N<br>N.C.<br>VDD|
|---|---|
|11<br>12<br>13<br>14<br>15<br>16<br>17<br>RD#<br>WR#<br>D/C#<br>RES#<br>CS#|BS1<br>BS2<br>D/C#<br>R/W#<br>E/RD#<br>CS#<br>RES#|
|18<br>19<br>20<br>21<br>22<br>23<br>24<br>25<br>26<br>27<br>28<br>29<br>30<br>D[7:0]<br>GND<br>C4<br>R1<br>C3|VCOMH<br>D0<br>D6<br>IREF<br>VLSS<br>D2<br>VCC<br>D7<br>D1<br>D3<br>D5<br>D4<br>N.C. (GND)|

#### **Recommended Components:** 

C1, C2: 1μF / 16V, X5R C3: 2.2μF C4: 4.7μF / 16V, X7R C5, C6: 1μF R1: 910kΩ, R1 = (Voltage at IREF - VSS) / IREF R2, R3: 47kΩ Q1: FDN338P Q2: FDN335N **Notes:** VDD: 1.65~3.3V, it should be equal to MPU I/O voltage. Vin: 3.5~4.2V 

* VBAT will be connected to VDD when VCC be connected to external source (12V), R1 should be replaced as 

#### **910 kΩ** . 

![](../images/ssd1315.pdf-0013-12.png)

