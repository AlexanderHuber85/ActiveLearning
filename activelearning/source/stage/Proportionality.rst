Proportionality and Superposition
#################################

Objective
_________

The objective of this Lab activity is to verify the proportionality and superposition theorems.

Notes
_____

As in all the ALM labs we use the following terminology when referring to the connections to the M1000 connector and configuring the hardware. The green shaded rectangles indicate connections to the M1000 analog I/O connector. The analog I/O channel pins are referred to as CA and CB. When configured to force voltage / measure current -V is added as in CA-V or when configured to force current  / measure voltage -I is added as in CA-I. When a channel is configured in the high impedance mode to only measure voltage -H is added as CA-H.

Scope traces are similarly referred to by channel and voltage / current. Such as CA-V , CB-V for the voltage waveforms and CA-I , CB-I for the current waveforms.

Background
__________

In this activity proportionality and superposition theorems are examined by applying them to the circuits shown in the following figures. 

1. The Proportionality Theorem states that the response of a circuit is proportional to the source acting on the circuit. This is also known as Linearity. The proportionality constant A relates the input voltage to the output voltage as:
 
<m>V_out = A * V_in</m> (1)

The proportionality constant A is sometimes referred to as the gain of a circuit. 
For the circuit of figure 1, the source voltage is V<sub>in</sub>. The response V<sub>out</sub> is across the 4.7 KΩ. resistor. The most important result of linearity is superposition.

.. image:: alm-cir-lab3-fig1.png 

<WRAP centeralign>Figure 1</WRAP>

2. The Superposition Theorem states that the response of a linear circuit with multiple independent sources, such as in figure 2,  can be obtained by adding the individual responses caused by the individual sources acting alone.
 
For an independent source acting alone, all other independent voltage sources in the circuit are replaced by short circuits and all other independent current sources are replaced by open circuits, as in figure 3.

.. image:: alm-cir-lab3-fig2.png  

<WRAP centeralign>Figure 2. Circuit with two voltage sources</WRAP>

.. image:: alm-cir-lab3-fig3.png 

<WRAP centeralign>Figure 3. Circuit for response of just one source</WRAP>

Materials
_________

RedPitaya
Various Resistors (1 KΩ, 2.2 KΩ, 4.7 KΩ) 

Procedure
_________

1. Verify the proportionality theorem:\\ 
a) Construct the circuit of figure 1. Using the multimeter, accurately measure V<sub>out</sub> for the three input voltages using fixed power supply voltages as shown in the table below. You should measure and record the actual fixed power supply voltages as well.

^V<sub>in</sub>(volts)^V<sub>out</sub> (volts) ^A (no units) ^
|2.5V|  |  |
|3.3V|  |  |
|5.0V|  |  |

Table 1 

b) Calculate the value of A in each case using equation 1.
 
c) Plot a graph with Vin on x-axis and Vout on y-axis. 

2. Verifying the Superposition theorem:\\
a) Construct the circuit of figure 2. Measure and record the voltage across the 4.7 KΩ. resistor.

b) Construct the circuit of figure 3. Measure and record the voltage across the 4.7 KΩ. resistor.

c) Calculate the total response "Vout" for circuit of figure 2 by adding the responses from steps 1a and 2b. Compare your calculated result to what you measured in step 2a. Explain any differences.

Questions
_________

1. Is the graph obtained a straight line? Compute the slope of the graph at any point and compare it to the value of K obtained from the measurements. Explain any differences. 

2. For each of the three circuits you built for the superposition experiment, how well did the calculated and measured outputs compare? Explain any differences. 
