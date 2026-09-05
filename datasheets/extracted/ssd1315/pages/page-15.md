
![](../images/ssd1315.pdf-0015-02.png)

#### 3.3.1.2 **4-wire Serial Interface with Internal Charge Pump** 

#### 特别提醒 **(Special Tips):** 主板设计务必加电子开关 , 否则 , 可能引起漏电流现象 

(When design main board, Please add Electronic Switch circuit, otherwise, will be caused leak current) 

4-w ire serial interface 

![](../images/ssd1315.pdf-0015-07.png)

<!-- Start of picture text -->
V in 1<br>N .C . (G N D )<br>R 2 2<br>S C 2P<br>C 2 3<br>D C 2N<br>G Q 1 4<br>C 1P<br>G Q 2 D C 1 5 C 1N<br>G PIO S 6 V D D B<br>R 3 7<br>N .C .<br>8<br>V S S<br>V D D<br>9<br>V D D<br>1 0<br>B S0<br>1 1<br>B S1<br>12<br>B S2<br>13<br>C S# C S#<br>1 4<br>R ES# R E S#<br>15<br>D /C # D /C #<br>R 4 1 6<br>R /W #<br>R 5 17<br>E /R D #<br>18<br>S C L K D 0<br>19<br>S D IN D 1<br>2 0<br>D 2<br>2 1<br>D 3<br>22<br>D 4<br>23<br>D 5<br>2 4<br>D 6<br>25<br>D 7<br>R 1 2 6<br>IR E F<br>C 4 27<br>V C O M H<br>C 3 28<br>V C C<br>29<br>V L S S<br>3 0<br>N .C . (G N D )<br>G N D<br>C6 C5<br>UT-0206-P05<br><!-- End of picture text -->

**Recommended Components:** C1, C2: 1μF / 16V, X5R C3: 2.2μF / 16V, X7R C4: 4.7μF / 16V, X7R C5, C6: 1μF / 6.3V, X5R R1: 620kΩ, R1 = (Voltage at IREF - VSS) / IREF R2, R3: 47kΩ R 4 , R 5 : 4.7 kΩ Q1: FDN338P Q2: FDN335N **Notes:** VDD: 1.65~3.3V, it should be equal to MPU I/O voltage. Vin: 3.5~4.2V 

* VBAT will be connected to VDD when VCC be connected to external source (9V), R1 should be 

replaced as 62 **0 kΩ** . 

![](../images/ssd1315.pdf-0015-11.png)

