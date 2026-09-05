
![](../images/ssd1315.pdf-0019-02.png)

#### 3.3.5.2 **I**<sup>**2**</sup> **C Interface with Internal Charge Pump** 

特别提醒 **(Special Tips):** 主板设计务必加电子开关 , 否则 , 可能引起漏电流现象 

(When design main board, Please add Electronic Switch circuit, otherwise, will be caused leak current) 

![](../images/ssd1315.pdf-0019-06.png)

<!-- Start of picture text -->
I2 C in te r fa c e<br>V in 1<br>N .C . (G N D )<br>R 2 2<br>S C 2 P<br>C 2 3<br>D C 2 N<br>G Q 1 4<br>C 1 P<br>G Q 2 D C 1 5 C 1 N<br>G P I O S 6 V D D B<br>R 3 7<br>N .C .<br>8<br>V S S<br>V D D<br>9<br>V D D<br>1 0<br>B S 0<br>1 1<br>B S 1<br>1 2<br>B S 2<br>1 3<br>C S #<br>1 4<br>R E S # R E S #<br>1 5<br>D /C #<br>R 4 1 6<br>R /W #<br>R 5 1 7<br>E /R D #<br>1 8<br>S C L D 0<br>1 9<br>S D A D 1<br>2 0<br>D 2<br>2 1<br>D 3<br>2 2<br>D 4<br>2 3<br>D 5<br>2 4<br>D 6<br>2 5<br>D 7<br>R 1 2 6<br>IR E F<br>C 4 2 7<br>V C O M H<br>C 3 2 8<br>V C C<br>2 9<br>V L S S<br>3 0<br>N .C . (G N D )<br>G N D<br>C6 C5<br>UT-0206-P05<br><!-- End of picture text -->

**Recommended Components:** C1, C2: 1μF / 16V, X5R C3: 2.2μF / 16V, X7R C4: 4.7μF / 16V, X7R C5, C6: 1μF / 6.3V, X5R R1: 620kΩ, R1 = (Voltage at IREF - VSS) / IREF R2, R3: 47kΩ R 4 , R 5 : 4 . 7kΩ Q1: FDN338P Q2: FDN335N **Notes:** VDD: 1.65~3.3V, it should be equal to MPU I/O voltage. Vin: 3.5~4.2V 

* VBAT will be connected to VDD when VCC be connected to external source (9V), R1 should be replaced as 62 **0 kΩ** . 

![](../images/ssd1315.pdf-0019-09.png)

