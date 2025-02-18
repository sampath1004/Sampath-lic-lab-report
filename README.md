# Experiment-1


## Aim:
Analysing  DC analysis,Transient analysis and AC analysis of a CS amplifier circuit for various parameters  using LT Spice having Specifications: 180 nm, tsmc, VDD = 1.8 V, Power budget = 50 uW


## Components required: 
Mosfet(nmos4 ,pmos4 ), Resistor(), voltage supply(1.8V,0.9V) and connecting wires.
## Theory:
An (NMOSFET) N-Channel Metal-Oxide-Semiconductor Field-Effect Transistor is a voltage-controlled device where current flows from drain to source when a positive voltage is applied to the gate. It operates in three regions cutoff, triode, and saturation making it essential for switching and amplification applications.
A Common Source (CS) Amplifier is a fundamental MOSFET-based amplifier that provides voltage gain with moderate input and output impedance. It operates by amplifying the input signal applied at the gate, causing an amplified and inverted output at the drain. The gain is determined by the transconductance of the MOSFET and the load resistance. It is widely used in analog circuits due to its high gain and good frequency response.
The drain current

![image](https://github.com/user-attachments/assets/ea869251-cb48-4a74-ba47-bb11f8534e6b)

**I<sub>d</sub> = 1/2 k<sub>n</sub> V<sub>ov</sub><sup>2</sup>** ; **V<sub>ov</sub>=V<sub>gs</sub>-V<sub>th</sub>** and **k<sub>n</sub>=u<sub>n</sub> C<sub>ox</sub> W/L**
### DC Analysis:
**DC analysis** determines the steady-state operating point of a circuit by calculating node voltages and branch currents with all capacitors treated as open circuits and inductors as short circuits. It helps in finding the biasing conditions of transistors and other active components. This analysis is crucial for ensuring proper circuit operation before performing AC or transient analysis.
The *Drain current (Id)* Can be determined:  

P = V * I

I = P / V

I = 50μW / 1.8V

I = 27.7μA

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/2a879dd09edc2668188ef5dc52abdfac2ad74c3d/dc%20analysis%20.png)
We determine the *MOSFET width (W) = 1.12um* in order to obtain the target operating conditions and good current conduction.  

### Transient Analysis:
This to done to analyse the response of the circuit to time varying signals.Transient Analysis:Examines a circuit’s time-domain response by analyzing voltage and current variations over time when subjected to a changing input, useful for studying switching behavior and signal propagation.  
*Stop Time* = 5ms.
![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/d870607d57fed6526f2a40a313b6ecc098d4e3bf/transient.png)
### AC Analysis:
Evaluates a circuit’s frequency response by determining gain and phase shift across different frequencies, essential for amplifier and filter design.
1.*Sweep Type* = Decade.  
2. *Number of Points per Decade* = 20.  
3. *Start Frequency* = 0.1 Hz.  
4. *Stop Frequency* = 1THz
![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/d870607d57fed6526f2a40a313b6ecc098d4e3bf/ac%20analysis.png)
## Procedure:
### **Steps for LTSpice Simulation**  

1.  Make a new folder named **"Project File"** and save your LTSpice circuit file inside it.  

 

2.  Build the circuit as per the given schematic, ensuring all connections are correct.  
    Apply **Vdd = 1.8V** and **Vgs = 0.6V**.  
    In LTSpice, go to **Simulate**, select the .op option, and tap OK.  
    Click **Run** to obtain the DC operating point, output voltage (Vout), and drain current (Id).  

5. Apply a **sine wave input** with **Vgs = 0.6V**, an **amplitude of 50mV**, and a **frequency of 1kHz** (set this in the **Advanced Voltage Source Settings**).Go to **Simulate** and click OK.  Click **Run** to observe the circuit’s time-domain response.  

6.  Use a **SPICE directive** to provide the library file path for accessing MOSFET model data. Go to **Simulate**, and define the frequency range from ** 1kz**.  
    Click **Run** to analyze the gain and frequency response of the circuit.
# Calculation :
The given specifications for our amplifier are:  

1.  *Channel Length (L)* = 180nm.
2.  *Supply Voltage (Vdd)* = 1.8V.
3.  *Gate Voltage (Vg)* = 0.6V.
4.  *Power Budget* = 50μW.
5.  *Drain Current (Id)* = 27.7μA. 
6.  *MOSFET Width (W)* = 1.12um.  


## INFERENCE:
Biasing is essential to keep the **MOSFET in saturation mode**, allowing it to function as an amplifier. The **DC operating point (Q-point)** determines how the amplifier behaves and must be set correctly to ensure proper signal amplification. If the biasing is incorrect, the MOSFET may enter the **cutoff or triode region**, preventing amplification. A stable Q-point helps maintain consistent performance despite variations in temperature and transistor properties.  
The **drain current (ID)** depends on the **channel width (W)** and **channel length (L)** of the MOSFET. A **larger W** increases **ID**, improving amplification. Since **L is fixed at 180nm**, adjusting **W** is the only way to achieve the desired current level. A higher **W/L ratio** enhances gain but also increases power consumption and parasitic capacitances, which can affect high-frequency performance.    
To meet the **power requirement of 50μW**, the **drain current (ID) must be 27.78μA**, as verified through LTSpice simulations. The optimal **W** value was determined through trial and error to balance power efficiency and performance. Choosing the correct **W/L ratio** ensures that the circuit meets its design goals without excessive power dissipation.  
The amplifier’s **gain (AV)** and **frequency response** depend on MOSFET parameters and external resistances. **AC analysis** in LTSpice helps determine how the gain changes across different frequencies. At high frequencies, **parasitic capacitances** may reduce gain and introduce phase shifts, affecting circuit stability. Proper circuit design ensures a wider bandwidth and consistent performance across the desired frequency range.  
The **transient analysis** evaluates how the amplifier responds to a **time-varying signal**. A **sine wave input** (50mV, 1kHz) is applied, and the output should be an amplified version of the input. Any distortions may indicate **incorrect biasing, non-linearity, or excessive loading effects**. Observing the transient response helps in refining the design to achieve smooth and accurate signal amplification.  



# Experiment-2

## Inverted CS Amplifier Analysis
![Screenshot 2025-02-18 160849](https://github.com/user-attachments/assets/a1d68fa8-1b9f-4e32-aebf-48e3b6139e2a)

### AIM

The objective of this report is to evaluate the inverting behavior of a CS amplifier when it operates on both DC and AC sources. 

### THEORY
The **inverted common-source (CS) amplifier** is a variation of the standard CS amplifier where the output is taken from the **source terminal** instead of the drain. This configuration introduces **negative feedback**, which reduces the gain but improves stability and linearity. Unlike the regular CS amplifier, the inverted version does **not provide phase inversion** between input and output. The voltage gain is always **less than unity**, making it function similarly to a **source follower** with high input impedance and low output impedance. This makes it ideal for **impedance matching** rather than voltage amplification. Due to the presence of the source resistor, the circuit achieves better **thermal stability** and **frequency response**. Overall, the inverted CS amplifier is useful when buffering signals or driving low-impedance loads.

### **Procedure for Inverted Common-Source (CS) Amplifier**  

1. **Select the MOSFET** – Choose an **N-channel MOSFET** with suitable **\( g_m \)** for the desired gain.  

2. **Circuit Components**  
   - **Gate Resistor (\( R_G \))** – Stabilizes bias.  
   - **Source Resistor (\( R_S \))** – Controls gain and adds negative feedback.  
   - **Drain Resistor (\( R_D \))** – Biasing component.  
   - **Coupling Capacitors (\( C_{in}, C_{out} \))** – Block DC, pass AC signals.  
   - **Bypass Capacitor (\( C_S \)) (optional)** – Affects gain and frequency response.  

3. **Biasing the MOSFET**  
   - Use a **voltage divider** or **self-biasing** with \( R_S \).  
   

4. **Determine the Gain**  

   - Gain is always **< 1** (acts as a buffer).  

5. **Impedance Considerations**  
   - **High input impedance** (good for signal sources).  
   - **Low output impedance** (good for driving loads).  

6. **Test the Circuit**  
   - Apply an **AC input signal** and observe the output.  
   - Measure **gain, phase shift, and impedance**.  
   - Adjust \( R_S \) and biasing resistors for optimal performance.

### DC Analysis:
**DC analysis** determines the steady-state operating point of a circuit by calculating node voltages and branch currents with all capacitors treated as open circuits and inductors as short circuits. It helps in finding the biasing conditions of transistors and other active components. This analysis is crucial for ensuring proper circuit operation before performing AC or transient analysis.
**Supply Voltage (VDD)**: 1.8V  
**Gate Voltage (VG)**: 0.9V  
**Power Budget (P)**: 50μW  

P = VDD * ID

ID = P/VDD

ID = 50μW / 1.8V

ID = 27.7μA
![Screenshot 2025-02-18 153133](https://github.com/user-attachments/assets/e48bcb6b-a554-431f-93ff-36957c54b7b6)


### Transient Analysis:
This to done to analyse the response of the circuit to time varying signals.Transient Analysis:Examines a circuit’s time-domain response by analyzing voltage and current variations over time when subjected to a changing input, useful for studying switching behavior and signal propagation.
Stop Time: 5m (5 milliseconds)

The transient analysis provides information about the amplifier's time-domain behavior, such as distortion, settling time, and waveform reproduction.

![WhatsApp Image 2025-02-18 at 16 17 01_6c628c90](https://github.com/user-attachments/assets/a21376b3-a265-46ea-98d3-424c6767b45e)


### AC Analysis:
Evaluates a circuit’s frequency response by determining gain and phase shift across different frequencies, essential for amplifier and filter design.
 DC Offset: 0.9V  
  Amplitude: 50mV  
  Frequency: 1kHz
![WhatsApp Image 2025-02-18 at 16 15 02_026ef94b](https://github.com/user-attachments/assets/2262f0d7-45fa-40b7-b23c-637a0ad3d00b)


### Gain :
![WhatsApp Image 2025-02-18 at 16 15 02_641f0dc3](https://github.com/user-attachments/assets/37af0274-6941-4ca9-8dfe-479f7d3bb9fb)



## **Inference**
An inverted common-source (CS) amplifier is a variation of the standard CS configuration where the output is taken from the source terminal instead of the drain. This alters the circuit’s behavior significantly. The **voltage gain is **less than unity (\(|A_v| < 1\)), making it similar to a  source follower (common-drain amplifier). This means it does not provide significant voltage amplification but instead serves as a buffer with high input impedance and low **output impedance**, making it useful for impedance matching. Unlike a standard CS amplifier, this configuration does **not invert the phase** of the input signal. Due to the presence of the source resistor, **negative feedback** is introduced, improving the circuit’s **stability** and **linearity**. Additionally, the inverted CS amplifier offers **better high-frequency response**, making it suitable for high-speed applications. Although it does not amplify voltage significantly, it can provide **current gain**, which can be useful for driving low-impedance loads efficiently.



  


