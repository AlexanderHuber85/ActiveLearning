What is Phase and why do we care?
#################################

Objective
_________

The objective of this lab activity is to understand what is meant by the phase relationship between signals and to see how well theory agrees with practice. A secondary outcome will be a preliminary understanding of the Red Pitaya STEMlab hardware and software - test & measurements applications.

Notes
_____
	
.. _hardware: http://redpitaya.readthedocs.io/en/latest/doc/developerGuide/125-10/top.html

In this tutorials we use the terminology taken from the user manual when referring to the connections to the Red Pitaya STEMlab board hardware_.

Background
__________

We will investigate the concept of phase by looking at sine waves and passive components that will allow us to observe phase shift with real signals. First we will look at a sin wave and the phase term in the argument. You should be familiar with the equation:

.. math::
	
	f(t)= sin(ωt + θ)

ω sets the frequency of the sin wave as t progresses and θ defines an offset in time which defines a phase shift in the function.

The sin function results in a value from 1 to -1. First set t equal to a constant, say, 1. The argument, ωt, is now no longer a function of time. With ω in radians, the sin of π/4 is approximately 0.7071. 2π radians equals 360° so π/4 radians corresponds to 45°. In degrees the sin of 45° is also 0.7071.

Now let t vary with time like it normally does. When the value of the ωt changes linearly with time it yields a sin wave function as shown in figure 1. As ωt goes from 0 to 2π the sin wave goes from 0 up to 1 down to -1 and back to 0. This is one cycle or one period, T, of the sine wave. The x axis is the time varying argument/angle, ωt, which varies from 0 to 2π.

The value of θ is 0 in the function plotted in figure1. Since the sin(0) = 0 the plot starts at 0. This is a simple sine wave with no offset in time which means no phase offset. Note that if we are using degrees ωt, goes from 0 to 2π or 0 to 360° to yield the sine wave shown in figure 1.

.. figure:: img/Activity_1_Figure_1.png
	:align: center
	
	figure 1: 2 cycles of SIN(t)

As a side note, what happens when ωt is greater than 2π? Enter 2.5π in a calculator and see. As you should know the sine function repeats every 2π radians or 360°. It is similar to subtracting 2π(I) radians from the argument where I is the largest integer that yields a nonnegative result.

What happens when we plot a second sine wave function in figure 1 with ω the same value and θ is also 0? We have another sine wave which lands on top of the first sine wave. Since θ is 0 there is no phase difference between the sine waves and they look the same in time.

Now change θ to π/2 radians or 90° for the second waveform. We see the original sine wave and a sine wave shifted to the left in time. Figure 2 shows the original sin wave (green) and the second sin (orange) with an offset in time. Since the offset is a constant we see the original sin wave shifted in time by the value θ which in this example is 1/4 of the wave period.

.. figure:: img/Activity_1_Figure_2.png
	:align: center

	figure 2: green - SIN(t)  orange - SIN(t+ π/4)

Theta (**θ**) is the time offset or phase portion of equation 1. The phase angle defines the offset in time and vice versa. Equation 2 shows the relationship. We happened to choose a particularly common offset of 90°. The phase offset between a sine and cosine wave is 90°. The offset angle is almost always not 90. As a matter of fact is often a function of frequency.

When there are 2 sine waves for example displayed on a scope the phase angle can be calculated by measuring the time between the 2 waveforms (negative to positive zero crossings, or “rising edges”, can be used as time measurement reference points in the waveform). One full period of the sine wave in time is the same as 360°. Taking the ratio of the time between the 2 waveforms, ∆t, and the time in one period of a full sine wave, T, you can determine the angle between them. Equation 2 shows the exact relationship.

Phase
_____

.. math::

	θ=∆t/T 360° = ∆t/T 2π(rads) = ∆tf2π(rads)

Where T is the period of the sinusoid.

**Naturally occurring time offsets in sine waves.**

Some passive components yield a time offset between the voltage across them and the current through them. In class we showed that the voltage across and the current through a resistor was a simple time independent relationship. V/I=R. where R is real and in ohms. So the voltage across and current through a resistor are always in phase.

For capacitors and inductors the equation relating V to I is similar. V/I=Z, where Z is an impedance with real and imaginary components. We are only going to look at capacitors in this lab.

Generally, capacitors are made of two conductive plates separated by a dielectric material. When a potential difference is applied across the plates, an electric field is created between the plates. Capacitor dielectrics can be made of many materials, including thin insulating films and ceramic. A capacitor's distinguishing characteristic is its capacitance (C), measured in Farads (F), which measures the ratio between voltage and charge buildup.

The basic rule for capacitors is that the voltage across the capacitor will not change unless there is a current flowing into the capacitor. The rate of change of the voltage (dv/dt) depends on the magnitude of the current. For an ideal capacitor the current i(t) is related to the voltage by the following formula:

.. math::

	i(t) = C \frac{dv}{dt}

Right now, the full implications of this is beyond the scope of this lab. You will observe this behavior in later labs. The impedance of a capacitor is a function of frequency. The impedance goes down with frequency conversely the lower the frequency the higher the impedance.

.. math::

	Z_c = \frac{1}{j ω C}

Where ω is defined as the angular velocity:

.. math::
	
	ω=2πf

One subtle thing about equation 4 is the imaginary operator j. When we looked at a resistor for example there was no imaginary operator in the equation for the impedance. The sinusoidal current through a resistor and the voltage across a resistor have no time offset between them because the relationship is completely real. The only difference is the amplitude. The voltage is sinusoidal and is in phase with the current sinusoid. This is not the case with a capacitor. When we look at the waveform of a sinusoidal voltage across a capacitor it will be time shifted compared to the current through the capacitor. The imaginary operator, j, is responsible for this. Looking at figure 3 we can see that the current waveform is at a peak ( maximum ) when the slope of the voltage waveform ( time rate of change dv/dt ) is its highest.

The time difference can be expressed as a phase angle between the two waveforms as defined in Equation 2.

.. figure:: img/Activity_1_Figure_3.png
	:align: center
	
	figure 3: Phase Angle Determination between Voltage and Current.

You probably have seen circuits made entirely from resistors. These circuits have only real impedance, which means that voltages throughout the circuit will all be in phase (i.e. θ = 0 degrees) as it is the complex impedance that shifts the current in time with respect to the voltage.  Note that the impedance of a capacitor is wholly imaginary. Resistors have real impedances, so circuits that contain both resistors and capacitors will have complex impedances.

To calculate the theoretical phase angle between voltage and current in an RC circuit:

.. math::

	i(t) = \frac{v(t)}{Zc}

Where Zc is the total circuit impedance = I

Rearrange the equation until it looks like I=A+jB

Where A and B are real numbers.

The phase relationship of the current relative to the voltage is then:

.. math::

	θ = tan^{-1}(\frac{B}{A})

Materials
_________

Red Pitaya STEMlab 125-14 or STEMlab 125-10 

2 – 470 Ω resistors

1 – 1 uF capacitor 


Oscilloscope & Signal Generator
_______________________________

.. _quickstart: http://redpitaya.readthedocs.io/en/latest/doc/quickStart/first.html
.. _here: http://redpitaya.readthedocs.io/en/latest/doc/appsFeatures/apps-featured/oscSigGen/osc.html

You are going to use the Red Pitays STEMlab board and the Oscilloscope & Signal generator application. User guide for starting the Red Pitaya STEMlab board can be found at quickstart_. Oscilloscope & Signal generator application is explained here_.



Instructional Objectives
________________________

1. Explore the phase relationship of voltages a resistive circuit.
2. Explore the phase relationship of voltages in a capacitive, resistive (RC) circuit.


Procedure
_________


• Be sure the STEMlab is plugged into a local network and start up the web interface using web browser.
• Start the Oscilloscope & Signal generator application. The Main screen should look like a scope display with adjustable range, position and measurement parameters.
• On the left bottom of the screen be sure that OUT1 V/div and OUT2 V/div are both set to 200 mV/div (You can set V/div by selecting the desired channel and using vertical +/- controls)

• In the OUT1 controls menu, set the frequency of OUT1 to 1000 Hz with 0° Phase and 0.9 V  amplitude. Select SINE waveform shape and enable output.
• In the OUT2 controls menu, set the frequency of OUT2 to 1000 Hz and 0.9 V amplitude. Select SINE waveform shape and enable output.
• Set t/div to 200us/div (using horizontal +/- controls) 

.. figure:: img/Activity_1_Figure_4.png
   :scale: 50 %
   
   figure 4:  Sine signal generated with Oscilloscope and Signal generator applications. Marked with green - main setting and controls.  


Measure the phase angle between two generated waveforms: 

From the previous settings you should  see what looks like 1 sine wave. There are two just one is on top of the other - zero phase angle!

• In the OUT1 control menu, change the phase  to 90°.
• In the OUT2 control menu, change the phase  to 135°.
• Which Channel looks like the sine is occurring before the other? _______________ 

The OUT2 signal should look like it is leading (happening before) the OUT1 signal. The OUT2 signal crosses the 0 V axis from below to above before the OUT1 signal. It turns out a positive θ is called a phase lead. The low to high crossing time reference point is arbitrary. The high to low crossing could also be used. 


.. figure:: img/Activity_1_Figure_5.png
   :scale: 50 %
   
   figure 5: Oscilloscope application showing two sine signal with phase difference. 

• Change the phase of OUT2 to 45°.

Now it looks like the CHB signal lags the CHA signal.

• Press the red STOP button to pause the Oscilloscope acquisition. 
• Select “CURSOR” menu and enable X1 and X2 cursors  
• Using horizontal +/- controls set Time to 100us/div.
• Using mouse and left press+hold on the cursor marker(white arrow on the end of the cursor line) set one cursor position so that cursor line going through point where OUT1 is crossing 0V line. Repeat the step for the second cursor and OUT2 signal.
• Readout the time difference between cursors 
       
  What is the ∆t? ________________
       
• Use the measured ∆t and equation 2 to calculate the phase offset. θ ________°
Note you cannot measure the frequency of a signal that does not have at least one full period displayed on the screen. Usually you need more than 2 cycles to get consistent results. You are generating the frequency so you already know what it is. You don't need to measure it in this part of the lab.

3. Measuring Magnitude using a real circuit. 



.. figure:: img/Activity_1_Figure_6.png
   :scale: 50 %
   
   figure 6: R-R circuit.

• Build the circuit shown in Figure 5 on your solderless breadboard using two 470 Ω, Oscilloscope probes and Red Pitaya STEMlab board.
NOTICE: For ground pin use probes ground leads (crocodile connectors)


.. figure:: img/Activity_1_Figure_7.png
   :scale: 50 %
   
   figure 7: R-R circuit on the breadboard 




We have connected OUT1 directly to IN1 so we can observe a real voltage signal across resistors R\ :sub:`1`\ and R\ :sub:`2`\.    

• In the OUT1 controls menu, set the Frequency  to 200 Hz with 0° Phase and 0.9 V amplitude. Deselect  “Show” button, select SINE waveform shape and select “ON” button.
• Set the horizontal time scale to 1.0 mS/Div to display two cycles of the waveform.
• Click on the scope Start button if it is not already running.
• Using vertical +/- controls set  200 mV/div for IN1 and IN2
The voltage waveform displayed in IN1(yellow) is the voltage across both resistors (V\ :sub:`R1`\+V\ :sub:`R2`\). The voltage waveform displayed in IN2 is the voltage across just R\ :sub:`2`\ (V\ :sub:`R2`\). To display the voltage across R\ :sub:`1`\ we use the Math waveform display options. Under the Math menu for Signal1 select IN1, select operator “-”, for Signal2 select IN2 then select enable. You should now see a third waveform for the voltage across R\ :sub:`1`\ (V\ :sub:`R1`\). 
• Using vertical +/- controls set  200 mV/div (0.2 V/div) for MATH trace.

With this settings you are observing:
IN1- Input excitation signal
IN2- Voltage drop signal across R\ :sub:`2`\
MATH - Voltage drop signal across R\ :sub:`1`\

• Record V\ :sub:`R1`\ and V\ :sub:`R2`\.

V\ :sub:`R1`\_______V\ :sub:`pp`\.

V\ :sub:`R2`\_______V\ :sub:`pp`\.

V\ :sub:`R1`\+V\ :sub:`R2`\_______V\ :sub:`pp`\.

• Can you see any difference between the zero crossings of V\ :sub:`R1`\ and V\ :sub:`R2`\? _________
• Can you even see two distinct sine waves? ________
Probably not. There should be no observable time offset and thus no phase shift.

You can see that MATH (purple) and IN2 (green) trace are overlapping. To see both traces you can adjust the vertical position of a channel to separate them. 
This can be done by selecting trace marker(on the left side of the grid) using mouse left button and moving trace up-down. Make sure to set the vertical position back to 0 to realign the signals.
Here we don’t have phase shift and value of R\ :sub:`1`\ = R\ :sub:`2`\ so the signal amplitudes for V\ :sub:`R1`\ and V\ :sub:`R2`\ will be the same. The result is that we have two identical signals (IN2=V\ :sub:`R2`\ , MATH=V\ :sub:`R1`\) on the Oscilloscope. 
What happens if you use 220 Ohm value for R\ :sub:`2`\? 

4. Measuring RC circuit
• Replace R\ :sub:`2`\ with a 1 uF capacitor C\ :sub:`1`\.


.. figure:: img/Activity_1_Figure_8.png
   :scale: 50 %
   
   figure 8: RC circuit on

NOTICE: For 1uF capacitor you will be probably using an electrolytic capacitor.
This capacitors are polarity sensitive i.e  on the positive capacitor pin the voltage should never go negative and on negative pin (GND) voltage should never go positive. 
   
From previous example (RR circuit ) and Oscilloscope & Signal generator settings we are generating sine wave which is going from -0.9V to 0.9V and causing a wrong polarization of capacitor(it can damage a capacitor) we need to adjust our output signal so we generate a sine signal which is always positive (sine signal with an offset).

• In the OUT1 settings menu set Amplitude and Offset values  to 0.45 V
  (Now we are generating sine signal which is oscillating around 0.45 V of DC offset value i.e sine signal is going  from 0 to 0.9V )

Because there is no DC current through the capacitor we are not interested in this DC value. In order to re-center our signals on the grid we need to shift signals in vertical direction using negative offset values.

• In the IN1 and IN2 settings menu set the value of Vertical Offset to -450mV 
• For the stable acquisition set the trigger level in TRIGGER menu to 0.45V



.. figure:: img/Activity_1_Figure_9.png
   :scale: 50 %
   
   figure 9: Oscilloscope signals with the RC circuit


• Measure IN1, IN2  and Math P2P (peak to peak) value.
What signal is the Math waveform? _________________

• Record V\ :sub:`R1`\, V\ :sub:`C1`\ and V\ :sub:`R1`\+V\ :sub:`C1`\.

V\ :sub:`R1`\____________V\ :sub:`PP`\.

V\ :sub:`C1`\_______________V\ :sub:`PP`\.

V\ :sub:`R1`\+V\ :sub:`C1`\____________V\ :sub:`PP`\.

Now something to do with phase. Hopefully you see a few sine waves with time offsets or phase differences displayed on the grid. Let's measure the time offsets and calculate the phase differences.
5. Measure the time difference between V\ :sub:`R1`\ and V\ :sub:`C1`\. and calculate the phase offsets.
Use equation 2 and the measured ∆t to calculate the phase angle θ.

The CURSORS are useful for determining ∆t. Here's how.
• Display at least 2 cycles of the sine waves.
• Set the horizontal time/div  to  500us/div. 
Note the Delta  cursor display keeps track of the sign of the difference.
You can use the measurement display to get frequency. Since you set the frequency of the source you don't really need to depend on the measurement window for this value.
Assume ∆t is 0 if you really can't see any difference with 1 or 2 cycles of the sine wave on the screen.
• Put a first cursor at the neg. to pos. zero crossing location for the IN1 ( V\ :sub:`R1`\ + V\ :sub:`C1`\) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the Math ( V\ :sub:`R1`\ ) signal. Record the time difference and calculate the phase angle. Note ∆t maybe a negative number. Does this mean the phase angle leads or lags?

∆t _________, θ_________

• Put a first cursor at the neg. to pos. zero crossing location for the IN1 ( V\ :sub:`R1`\ + V\ :sub:`C1`\) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the IN2 ( V\ :sub:`C1`\ ) signal. Record the time difference and calculate the phase angle.

∆t _________, θ_________

• Put a first cursor at the neg. to pos. zero crossing location for the Math ( V\ :sub:`R1`\ ) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the IN2 ( V\ :sub:`C1`\ ) signal. Record the time difference and calculate the phase angle.

∆t _________, θ_________


6. Measure the time difference and calculate the phase θ offset at a different frequency.
• Set OUT1 frequency to 1000 Hz and the time / div to 200us/div.
• Put a first cursor at the neg. to pos. zero crossing location for the IN1 ( V\ :sub:`R1`\ + V\ :sub:`C1`\) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the Math ( V\ :sub:`R1`\ ) signal. Record the time difference and calculate the phase angle. Note ∆t maybe a negative number. Does this mean the phase angle leads or lags?

∆t _________, θ_________

• Put a first cursor at the neg. to pos. zero crossing location for the IN1 ( V\ :sub:`R1`\ + V\ :sub:`C1`\) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the IN2 ( V\ :sub:`C1`\ ) signal. Record the time difference and calculate the phase angle.

∆t _________, θ_________

• Put a first cursor at the neg. to pos. zero crossing location for the Math ( V\ :sub:`R1`\ ) signal. Put a second cursor at the nearest neg. to pos. zero crossing location for the IN2 ( V\ :sub:`C1`\ ) signal. Record the time difference and calculate the phase angle.

∆t _________, θ_________

