**Figure 14. T1/E1/Ethernet protection** 

![](../images/usblc6-2.pdf-0010-02.png)

<!-- Start of picture text -->
+VCC<br>Tx 100nF<br>SMP75-8<br>DATA<br>TRANSCEIVER<br>+VCC<br>Rx 100nF<br>SMP75-8<br>USBLC6-2SC6<br>USBLC6-2SC6<br><!-- End of picture text -->

## **2.6** 

## **PSpice model** 

Figure 15. PSpice model shows the PSpice model of one USBLC6-2 cell. In this model, the diodes are defined by the PSpice parameters given in Figure 16. PSpice parameters. 

**Figure 15. PSpice model** 

![](../images/usblc6-2.pdf-0010-07.png)

<!-- Start of picture text -->
LI/O RI/O RI/O LI/O<br>D+in D+out<br>MODEL = Dlow MODEL = Dhigh<br>LGND RGND RI/O LI/O<br>MODEL = Dzener<br>GND VBUS<br>MODEL = Dlow MODEL = Dhigh<br>LI/O RI/O RI/O LI/O<br>D-in D-out<br><!-- End of picture text -->

_Note:_ 

_This simulation model is available only for an ambient temperature of 27 °C._ 

