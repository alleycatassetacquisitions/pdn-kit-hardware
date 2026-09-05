
![](../images/ssd1315.pdf-0026-02.png)

<Power down Sequence> 

![](../images/ssd1315.pdf-0026-04.png)

<!-- Start of picture text -->
Power Stabilized<br>Normal Operation VDD/VBAT off State<br>(100ms Delay Recommended)<br>Set Display Off Power down VBBAT<br>0xAE (50ms Delay Recommended)<br>Set Charge Pump<br>0x8D, 0x10 Power down VDD<br><!-- End of picture text -->

#### <Entering Sleep Mode> 

![](../images/ssd1315.pdf-0026-06.png)

<!-- Start of picture text -->
Set Charge Pump<br>Normal Operation Sleep Mode<br>0x8D, 0x10<br>Set Display Off<br>0xAE Power down VBAT<br><Exiting Sleep Mode><br>Set Charge Pump Power Stabilized<br>Sleep Mode 0x8D, 0x14 (100ms Delay Recommended)<br>Power up VBAT Set Display On<br>(100ms Delay Recommended) 0xAF Normal Operation<br><!-- End of picture text -->

<Exiting Sleep Mode> 

### Internal  setting （ Charge pump ） 

{ 

RES=1; delay(1000); RES=0; delay(1000); RES=1; delay(1000); write_i(0xAE);    /*display off*/ write_i(0x00);    /*set lower column address*/ write_i(0x10);    /*set higher column address*/ 

![](../images/ssd1315.pdf-0026-11.png)

