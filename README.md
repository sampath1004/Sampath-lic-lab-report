# Experiment-1
## Aim:
Analysing  DC analysis,Transient analysis and AC analysis of a CS amplifier circuit for various parameters  using LT Spice having Specifications: 180 nm, tsmc, VDD = 1.8 V, Power budget = 50 uW


## Components required: 
Mosfet(nmos4 ,pmos4 ), Resistor(), voltage supply(1.8V,0.9V) and connecting wires.
## Theory:
An (NMOSFET) N-Channel Metal-Oxide-Semiconductor Field-Effect Transistor is a voltage-controlled device where current flows from drain to source when a positive voltage is applied to the gate. It operates in three regions—cutoff, triode, and saturation—making it essential for switching and amplification applications.
A Common Source (CS) Amplifier is a fundamental MOSFET-based amplifier that provides voltage gain with moderate input and output impedance. It operates by amplifying the input signal applied at the gate, causing an amplified and inverted output at the drain. The gain is determined by the transconductance of the MOSFET and the load resistance. It is widely used in analog circuits due to its high gain and good frequency response.
The drain current

**I<sub>d</sub> = 1/2 k<sub>n</sub> V<sub>ov</sub><sup>2</sup>** ; **V<sub>ov</sub>=V<sub>gs</sub>-V<sub>th</sub>** and **k<sub>n</sub>=u<sub>n</sub> C<sub>ox</sub> W/L**
### DC Analysis:
**DC analysis** determines the steady-state operating point of a circuit by calculating node voltages and branch currents with all capacitors treated as open circuits and inductors as short circuits. It helps in finding the biasing conditions of transistors and other active components. This analysis is crucial for ensuring proper circuit operation before performing AC or transient analysis.
### Transient Analysis:
This to done to analyse the response of the circuit to time varying signals.Transient Analysis:Examines a circuit’s time-domain response by analyzing voltage and current variations over time when subjected to a changing input, useful for studying switching behavior and signal propagation.  
### AC Analysis:
Evaluates a circuit’s frequency response by determining gain and phase shift across different frequencies, essential for amplifier and filter design.
## Procedure:
1.Create a new folder and name it as project file.Save the LT spice file in this folder.

2.Name the mosfet as CMOSN and the length as 180nm and width as 4um initially.

3.For the pmos name it as CMOSP and set the length as 180nm and width as 4um respectively

4.**DC Analysis:** Set up the circuit as per the circuit diagram with proper connections ensuring valid circuit for further analysis.
Apply the DC voltage of Vdd=1.8V and Vgs = 0.9 V . Go to simulate option in the tab and edit simulation command, click on DC analysis and press ok.(.op)
Click on Run in the tab menu to get the DC operating point ,Vout and Id.

5.**Transient Analysis:** Apply a sine wave input of Vgs=0.9V with an amplitude of 50mV and frequency of 1kHz by going to advanced menu in the voltage setting option.go to simulate option in tab ,edit simulation command 
, click on transient analysis and give the stop time as 3m and click ok.(.tran 3m) Now Run to visualise the response of the circuit to a time varying signal.

6.**AC Analysis:** Go to spice directive and give the library file path for the simulator to access the data through the path . Go to simulate option in the tab , edit simulation command , click on AC analysis 
and mention the time of sweep as decade , no of points as 20 and frequency as .1Hz to 1THzand click on ok.Now Run to analyze the gain and frequency response of the circuit.(.ac dec 20 .1 1T)
# Circuit 1:
![Image](https://github.com/user-attachments/assets/91f5eeff-ac7d-46ad-a605-490589fa519b)
# Calculation :

