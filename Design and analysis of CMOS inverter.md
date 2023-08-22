Design and analysis of CMOS inverter

This project has been created using gpdk 90nm library given with Cadence virtuoso. I have done the transient and DC analysis of the inverter and have calculated various parameters like noise margin, power consumption and propagation delay. I have also performed the Layout vs Schematic of the design and shown the results in the pictures that follow :

![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.001.png)Noise margin

The above figure shows two graphs, the upper graph is the transfer characteristics and the lower graph is the derivative of the above graph with respect to input. In order to calculate the noise margin we need four parameters : 

- **VOH** - Maximum output voltage when it is logic *'1'*.
- **VOL** - Minimum output voltage when it is logic *'0'*.
- **VIH** - Maximum input voltage that can be interpreted as logic *'0'*.
- **VIL** - Minimum input voltage that can be interpreted as logic *'1'*.

The above parameters are shown in the graph. Note that VIL and VOL are calculated by identifying the points where the slope of the transfer characteristic is -1. 

Thus,

**NML (Noise Margin for Low)** = VIL – VOL =

**NMH (Noise Margin for HIGH)** = VOH – VIH = 

Power consumption

![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.002.png)Power consumption consists of static, dynamic and leakage power consumption. In order to calculate the total power consumption I have found the average value of the multiplication of the graphs of Vout and drain current. 















From the graph we can see the average power consumption is 431.9 Nw. Now let us see the effect W/L ratio & Vdd on power consumption.





![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.003.png)![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.004.png)

Propagation Delay

- upon increasing W/L ratio, propagation delay decreases (values calculated for Tr = 10ps)

w/l = 120/100; Tpd = 4.6223ps

w/l = 240/100; Tpd = 3.7765ps

- upon reducing rise & fall time, propagation delay decreases

Tr = 50ps : Tpd = 6.65ps

Tr = 10ps : Tpd = 4.6223ps

Rise time

![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.005.png)![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.006.png)Rise time is the measure of the speed of the circuit. If rise time is low then the circuit is considered to be fast. Below are some graphs showing the effect of Load capacitance, power supply & w/l ratio on rise time. 

![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.007.png)

Layout Vs Schematic

![](Aspose.Words.e03009f2-fc7e-4195-aedb-da8bbe913288.008.png)As we can see from the above graph the response for layout circuit is slower that the schematic. This is prominently because of:

- Parasitic capacitances and resistances from the metal wires and diffusion regions are not shown in the schematic but will be present in the physical layout. These can impact performance but do not change the logical function.
- The layout includes all the non-idealities that come from fabricating the circuit physically, such as uneven diffusion widths, contacts misalignments, wire rounding, etc. The schematic is an idealized representation.
- In the layout, the components are drawn to scale in their physical proportions and locations. The schematic is not constrained by physical dimensions.

