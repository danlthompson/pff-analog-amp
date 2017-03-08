# pff-analog-amp
Analog amplifier for PFF application

Design considerations:

- Resistor choices were made with ideal conditions in mind

- Op-amp choice: I placed an LM741 in my schematic because it was one I was able to find in the default KiCad library, however it wouldn't work well for this application as it is unable to get close to the voltage rails. No real-life op-amp would be able to acheive 0-5 V output on a supply of +5 V and ground, but a carefully selected chip like the TLV2771 would be able to come close. 

- Variable gain: By default, the gain of the amplifier would be 2.5 (2 V in, 5 V out), and since that reaches the maximum possible output voltage, I designed with the idea that 2.5 would be the maximum gain. This occurs when RV1 is set to its maximum value of 15K, which can be lowered to lower the gain (to a minumum of 1 at 0K, the gain can be found by V_OUT/V_IN = 1 + RV1/R1).

- Low-pass filter with variable cutoff frequency: The problem doesn't specify what frequencies are needed to be filtered, so I chose values of 100K (potentiometer) and 1000pF for my filter, which allows a very wide range of cutoff frequencies (from 1591 Hz, to up to the 100 MHz range). This filter should be better tailored if the specific requirements are known.

- BOM: I'm not familiar with KiCad's BOM tools so I created a BOM by hand, it is included as a .CSV


Thank you for your consideration!

Dan
