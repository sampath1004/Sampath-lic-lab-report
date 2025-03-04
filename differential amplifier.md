# Experiment-3 
## Differential Amplifier:
A Differential amplifier is an electronic circuit that amplifies the voltage difference between two input signals while rejecting any common-mode signals. It is a fundamental component in analog electronics, often used in operational amplifiers and signal processing.Differential amplifiers are widely used in instrumentation, audio processing, and sensor interfacing, where precise and stable signal amplification is required.
It consist of two transistors M1 and M2, whose sources are joined together.If two transistor are connected to the different voltage input then there current across M1 and M2 are different due to gate voltage.If in case the voltage supply at gate terminal is same then the current through the M1 and M2 are same (Im1=Im2).This configuration is called "Common Mode input voltage differential Amplifier".Whatever may be the load resistor, the MOSFET M1 and M2 should not go to the Triode region. It should be verified that MOSFET should be in Saturation Region.
This Expereiment is Based on Common Mode Input voltage Differential Amplifier..Where common source terminal is connected with

1.Resistor 

2.Source resister

3.MOSFET 

For all this circuit we need find out the Transient analysis , AC analysis And Frequency Response.
#### To find the all the values of resistor and source resistor. we need solve the given queston specification.

P=3mW

Iss=P/VDD=3*10^(-3)/2.5=1.2mA

Is1=Is2=Iss/2=0.6mA

RD=VDD-Vocm/Is1=2.5-1.4/0.6*10^(-3)=1.83kΩ

Rss=Vp/Iss=0.5/1.2*10^(-3)=416.66Ω


 Finially by solving we get

Iss=1.2mA

I1=I2=0.6mA

RD=1.83kΩ

Rss=416.66Ω

By this values we are going continue our experiment for getting graphical representation.

## 1.Circuit 1 (Common Source terminal is connected to resistor):
  
   In this circuit we have two MOSFET connected to same voltage input forming differential pair. Load Resistor is coonected to  Drain terminal of MOSFET.
   Source terminal is connected resistor and another terminal is connected to ground this is called source degenration resistor.
   
