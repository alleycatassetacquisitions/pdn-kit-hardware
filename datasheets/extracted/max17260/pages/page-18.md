# MAX17260 

# 5.1μA 1-Cell Fuel Gauge with ModelGauge m5 EZ and Optional High-Side Current Sensing 

MaxPeakPower/SusPeakPower/MPPCurrent/SPPCurrent can be used as general purpose memory. 

**POWR:** Sets the time constant for the AvgPower register. The default POR value of 0100b gives a time constant of 11.25s. The equation setting the period is: 

AvgPower time constant = 45s x 2<sup>(POWR-6)</sup> 

**dSOCen:** SOC Change Alert Enable. Set this bit to 1 to enable alert output with the Status.dSOCi bit function. Write this bit to 0 to disable alert output with the Status. dSOCi bit. This bit is set to 0 at power-up. 

**TAlrten:** Temperature Alert Enable. Set this bit to 1 to enable temperature based alerts. Write this bit to 0 to disable temperature alerts. This bit is set to 1 at power-up. 

**LDMdl:** Host sets this bit to 1 in order to initiate firmware to finish processing a newly loaded model. Firmware clears this bit to zero to indicate that model loading is finished. 

**DRCfg:** Deep relax time configuration. 00 for 0.8 to 1.6 hours, 01 for 1.6 to 3.2 hours, 10 for 3.2 to 6.4 hours and 11 for 6.4 to 12.8 hours. 

**CPMode:** Constant-power mode. Set to 1 to enable constant-power mode. If it is set to 0, AtRate/AvgCurrent is used for <u>AvgVCell</u> (At)TTE/(At)QResidual/(At)AvSOC/(At)AvCap. If it is set to 1, AtRate/AvgCurrent x<sup>is used for those</sup> (AvgVCell + VEmpty) / 2 calculations 

### **ModelGauge m5 Algorithm** 

Classical coulomb-counter-based fuel gauges have excellent linearity and short-term performance. However, they suffer from drift due to the accumulation of the offset error in the current-sense measurement. Although the offset error is often very small, it cannot be eliminated. It causes the reported capacity error to increase over time and requires periodic corrections. Corrections are traditionally performed at full or empty. Some other systems also use the relaxed battery voltage to perform corrections. These systems determine the true state-of-charge (SOC) based on the battery voltage after a long time of no current flow. Both have the same limitation: if the correction condition is not observed over time in the actual application, the error in the system is boundless. The performance of classic coulomb counters is dominated by the accuracy of such corrections. Voltage measurement based SOC estimation has accuracy limitations due to imperfect cell modeling, but does not accumulate offset error over time. 

The IC includes an advanced voltage fuel gauge (VFG) that estimates open-circuit voltage (OCV), even during current flow, and simulates the nonlinear internal dynamics of a Li+ battery to determine the SOC with improved accuracy. The model considers the time effects of a battery caused by the chemical reactions and impedance in the battery to determine SOC. This SOC estimation does not accumulate offset error over time. The IC performs a smart empty compensation algorithm that automatically compensates for the effect of temperature condition and load condition to provide accurate state-of-charge information. The converge-to-empty function eliminates error toward empty state. The IC learns battery capacity over time automatically to improve long-term performance. The age information of the battery is available in the output registers. 

The ModelGauge m5 algorithm combines a high-accuracy coulomb counter with a VFG. See <u>Figure 2. The</u> complementary combined result eliminates the weaknesses of both the coulomb counter and the VFG while providing the strengths of both. A mixing algorithm weighs and combines the VFG capacity with the coulomb counter and weighs each result so that both are used optimally to determine the battery state. In this way, the VFG capacity result is used to continuously make small adjustments to the battery state, cancelling the coulomb-counter drift. 

