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
### **Steps for LTSpice Simulation**  

1.  Make a new folder named **"Project File"** and save your LTSpice circuit file inside it.  

2. Name the NMOS transistor **"CMOSN"** with a **length of 180nm** and **width of 4µm**.  

3.  Name the PMOS transistor **"CMOSP"** with a **length of 180nm** and **width of 4µm**.  

4.  Build the circuit as per the given schematic, ensuring all connections are correct.  
    Apply **Vdd = 1.8V** and **Vgs = 0.9V**.  
    In LTSpice, go to **Simulate**, select the .op option, and tap OK.  
    Click **Run** to obtain the DC operating point, output voltage (Vout), and drain current (Id).  

5. Apply a **sine wave input** with **Vgs = 0.9V**, an **amplitude of 50mV**, and a **frequency of 1kHz** (set this in the **Advanced Voltage Source Settings**).Go to **Simulate** and click OK.  Click **Run** to observe the circuit’s time-domain response.  

6.  Use a **SPICE directive** to provide the library file path for accessing MOSFET model data. Go to **Simulate**, and define the frequency range from ** 1kz**.  
    Click **Run** to analyze the gain and frequency response of the circuit.
# Circuit 1:
![Image](https://github.com/sampath1004/LIC-LAB-REPORT/blob/28e0b87a7b73a26290bd9d71876dde2395723597/WhatsApp%20Image%202025-02-16%20at%2022.15.50.jpeg)
# Calculation :

