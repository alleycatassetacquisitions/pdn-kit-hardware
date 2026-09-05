# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

### **Layout Guidelines** 

Proper circuit layouts for low-side current measurement as shown in <u>Figure 3</u> or high-side current measurement as shown in Figure 4 is essential for voltage, temperature, and current-measurement accuracy. The recommended layout guidelines are as follows: 

- CSN and GND traces should make Kelvin connections to the sense resistor. Current is measured differentially through the CSN and GND pins. Any shared high current paths on these traces affect current measurement accuracy. 

- For TDFN package designs, connect EP directly to the GND pin. 

- REG capacitor trace loop area should be minimized. REG should be connected to the GND pin as close as possible to the IC. Run only a single GND trace to the sense resistor. This helps filter any noise from the internal regulated supply. 

- All other ground connections should be kept separate from the current sensing traces. 

   - The Kelvin lines should not be shared with other circuits. 

   - Vias on the Kelvin traces are not recommended. 

- There are no limitations on any other IC connection. Other IC pins, as well as any external components mounted to these pins, have no special layout requirements. 

![](../images/max17260.pdf-0026-11.png)

<!-- Start of picture text -->
SYSPWR Pack +<br>Pack + SYSPWR<br>TH 1 14 SCL<br>SDA BATT TH NC 2 13 SDA<br>CBATT<br>CSPH ALRT SCL NC 3 12 ALRT<br>GND REG CSN NC 4 MAX17260 11 REG<br>MAX17260 CBATT<br>NC 5 10 CSPH<br>CREG<br>BATT 6 9 CSPL<br>CREG<br>EP<br>CSN 7 8 GND<br>Pack - Rsense SYSGND<br>SYSGND Rsense Pack -<br><!-- End of picture text -->

_Figure 3. MAX17260 Low-Side Current Measurement Layout Guide_ 

