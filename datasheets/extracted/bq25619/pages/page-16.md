##### **7 Detailed Description** 

###### **7.1 Overview** 

The BQ25619/618 device is a highly integrated 1.5-A switch-mode battery charger for single cell Li-ion and Li-polymer battery. It includes an input reverse-blocking FET (RBFET, Q1), high-side switching FET (HSFET, Q2), low-side switching FET (LSFET, Q3), and battery FET (BATFET, Q4), and bootstrap diode for the high-side gate drive. 

###### **7.2 Functional Block Diagram** 

![](../images/bq25619.pdf-0016-06.png)

<!-- Start of picture text -->
VBUS PMID<br>VVBUS_UVLOZ + UVLO RBFET (Q1)<br>IIN VBAT + VVSLEEPVBUS ± Q1 Gate Control<br>+ SLEEP EN_REGN REGN<br>VAC VVBUS ± REGN<br>VVBUS EN_HIZ LDO<br>+ ACOV<br>VVAC_OV ±<br>FBO BTST<br>VVBUS<br>+ VBUS_OVP_BOOST<br>VOTG_OVP<br>±<br>IQ2<br>+ Q2_UCP_BOOST<br>VVINDPMVBUSIIN ±++ VOTG_HSZCPVOTG_BATIQ3 ±+± Q3_OCP_BOOST CONVERTERControl REGN HSFET (Q2) SW<br>IINDPM BAT<br>± + BATOVP<br>IC TJ + 104% × V BAT_REG ± LSFET (Q3) PGND<br>TREG ± + BATSNS ILSFET_UCP + UCP Q2_OCP + IQ2<br>SYS ± ± VBAT_REG IQ3 ± ± IHSFET_OCP<br>VSYSMIN + + ICHG EN_HIZ REFRESH + VBTST - VSW<br>± ICHG_REG ENEN_CHARGE_BOOST ± VBTST_REFRESH<br>SYS<br>ICHG<br>VBAT_REG<br>ICHG_REG Q4 Gate  BATFET<br>Control (Q4)<br>IBADSRC BAT<br>REF BAD_SRC +<br>DAC IDC<br>Converter  ±<br>Control State Machine TSHUT + IC TJ<br>TSHUT<br>± BATSNS<br>BATSNS<br>Input Source Detection USB BAT_GD +± VBATGD VQON<br>PSEL Adapter VREG -VRECHG<br>RECHRG +<br>BATSNS<br>± /QON<br>INT ICHG<br>TERMINATION +<br>ITERM<br>±<br>CHARGE VBATLOWV<br>STAT CONTROL BATLOWV +<br>MACHINESTATE ± BATSNS BQ25618<br>VSHORT BQ25619<br>BATSHORT +<br>PMID_GOOD InterfaceI2C SUSPEND ± BATSNS Battery<br>Sensing  TS<br>Thermistor<br>SCL SDA /CE Copyright © 2019, Texas Instruments Incorporated<br><!-- End of picture text -->

