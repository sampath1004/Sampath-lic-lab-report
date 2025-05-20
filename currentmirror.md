# Linear integrated circuits

# Experiment 4: Design and analysis of current mirror circuit
## Introduction :
A current mirror circuit is an essential analog building block used to replicate and regulate current in integrated circuits. It ensures that the output current closely matches the reference current, regardless of load variations. Commonly implemented using MOSFETs or BJTs, current mirrors are widely used in biasing, active loads, and current amplification in analog and mixed-signal circuits. The project aims to develop efficient mirror circuits, simulate their performance, and analyze the results in terms of gain, accuracy, and power consumption.

Here is a circuit of basic current mirror:

![image](https://github.com/user-attachments/assets/9739506d-8687-4e65-886a-e1cb70acde4f)

## Design question

Part A

i) design for gain>-10 V/V. Vdd = 1.8V, P <= 1mW

Design for the current mirror ratio 1:1 and 1:2 

ii) Analyze the circuit current mirror

iii) Case 1: Lmin = 180nm              W/L = x
             L = 500nm
             L = 1um

iv) Transient and AC analysis

max output swing,
Bandwidth

## Working principle

1. Reference Current Generation – A diode-connected MOSFET (M1) is used to establish a stable reference current (IREF).

2. Voltage Mirroring – The gate-source voltage (VGS) of M1 is applied to the second MOSFET (M2).

3. Current Replication – Since both MOSFETs have the same VGS and are identical, M2 mirrors IREF to its drain.

4. Saturation Operation – M2 operates in saturation region, ensuring a nearly constant output current.

5. Accuracy Factors – Mismatch, channel-length modulation, and temperature variations can affect precision.

6. Improved Performance – Cascode current mirrors enhance output resistance, reducing variations in VDS.

7. Applications – Used in biasing, amplifiers, and analog signal processing circuits.

#### Design steps:
Step: Power Budget & Total Current

Given: 𝑃_total<1𝑚𝑊, 𝑉𝐷𝐷=1.8𝑉

wkt, I_Total = P/ VDD =1mW/1.8v =0.55556mA

Since: 𝐼_total= 𝐼_ref+𝐼_x

therefore, I_ref =I_x = I_total/2 = 0.2778mA

## Procedure:
For LTspice simulation, TSMC018 library file was included which is crucial for acccurate MOSFET simulation in TSMC 0.18um( 180nm)CMOS technology. Stored this library file in the LTspice folder or the same directory as our simulation file. Carried out DC, AC and Transcient analysis of the differential amplifier circuit.


## L = 180nm

First we are gonna set the width value of the mos for 180nm length.

By using the spice directive option we found out the value of the width for the calculated current. i.e 6.6643357u

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20095536.png)

We took the current value 277.51uA very close to the calculated value.

## DC analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052612.png)

For better understanding 

Here one thing to notice is that the gm is changing for M3. Here are the reasons;
1. M1 and M2 are PMOS (cmosp), while M3 is NMOS (cmosn).

2. NMOS and PMOS have different mobility (μ) and threshold voltages, which directly affect gm.

3. Electron mobility (μₙ) for NMOS is higher than hole mobility (μₚ) in PMOS.

 Transconductance Depends on Overdrive Voltage:
 
So, despite same current, if Vov is lower, gm will be lower.

For M1, Vov ≈ 0.41 V, gm ≈ 1.02 mS

For M3, Vov ≈ 0.26 V, gm ≈ 0.73 mS 

## Transient Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20051425.png)

calculated Gain = -13.3V/V

Calculated Gain in db = 22.47

## AC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20051526.png)

Calculated Gain in db = 22.47

simulation Gain in db = 26.30

-3db = 23.30

Bandwidth = 1.823 GHz

## For L = 500nm

## DC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052252.png)

## Transient Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052355.png)

Calculated gain = -15.268 V/V

## AC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052427.png)

Gain in db = 34.5

-3db Gain = 31.5

Bandwidth = 166.998 MHz

We can notice the increase in the gain when we increase the length to 500nm. This is due to the decrease in the channel length modulation effect. As lambda decreases the impedence increases. 

## For L = 1um

Setting the Width value(W)

W = 27.902773u

## DC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052612.png)

## Transient Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052633.png)

Gain = 15.854 V/V

## AC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20052738.png)

Gain in db = 37.02

-3db Gain = 34.02

Bandwidth = 67.98 MHz

Comparison Table

## 📊 Gain and Bandwidth Comparison for Different Channel Lengths (L)

| Channel Length (L) | Gain (dB) | -3 dB Gain (dB) | Bandwidth |
|--------------------|-----------|------------------|-----------|
| 180 nm             | 26.30     | 23.30            | 1.823 GHz |
| 500 nm             | 34.50     | 31.50            | 166.998 MHz |
| 1 µm               | 37.02     | 34.02            | 67.98 MHz |


## For 1:2 


By calculation we got 185uA and 370uA respectively.
So Itotal = 555uA.

I am checking for L = 500nm.

First setting the Width for M1 for 185uA. 


Then mutiplying the W value manually we got 22.150 um. For this value we got the value of current to be 369.39uA. So by incrementing the width value by 0.04 um we got the following results.

## DC Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20061351.png)

## Transient Analysis

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20065349.png)

Gain = -15.002 V/V

## AC Analysis
![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20065414.png)


Gain in db = 34.53
-3db gain = 31.53
Bandwidth = 126.95 MHz

Conclusion:

1:1 Current Mirror

Effect of W/L Ratio: Increasing the W/L ratio improves current matching accuracy and reduces output resistance variations, enhancing performance.
Power Efficiency: The circuit operates efficiently within a 1.8V supply, making it suitable for low-power analog applications.

1:2 Current Mirror

Current Scaling: The output current is ideally twice the reference current, as designed for a 1:2 current mirror ratio.
Deviation from Ideal Ratio: Minor mismatches are observed due to process variations, threshold voltage differences, and channel-length modulation.
Higher Power Dissipation: Since the output current is doubled, power consumption is higher compared to a 1:1 current mirror.

## Current Mirror Comparison: 1:1 vs. 1:2

| Parameter                   | 1:1 Current Mirror       | 1:2 Current Mirror       |
|----------------------------|--------------------------|--------------------------|
| Input to Output Current Ratio | 1:1                      | 1:2                      |
| Transistor Width Ratio     | M1 = M2                  | M2 = 2 × M1              |
| Gain (Approximate, in dB)  | Lower                    | Higher                   |
| Output Resistance          | Moderate                 | Slightly Lower           |
| Accuracy                   | Higher (if matched well) | Can suffer mismatch      |
| Power Consumption          | Lower                    | Higher (due to doubled output current) |


# PART-B
## Aim
Design the differential amplifier using the same design specification as Experiment-3.
Perform DC analysis,trasient and AC analysis.

### DC Analysis:

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20063359.png)


## **DC Analysis of the Given Circuit**

### **1. Overview of the Circuit**
The circuit consists of six MOSFETs (M1 to M6) with different **(W/L) ratios**, and we need to ensure that all transistors remain in the **saturation region** during the analysis. The given (W/L) ratios for each transistor are:

- **M1**: 400mm / 180nm  
- **M2**: 400mm / 180nm  
- **M3**: 600mm / 180nm  
- **M4**: 600mm / 180nm  
- **M5**: 600mm / 180nm  
- **M6**: 600mm / 180nm  

### **2. DC Analysis - Ensuring Same Current & Voltage Values**
DC analysis involves finding the **DC operating points (voltages and currents)** of each MOSFET. Based on Experiment 3, we ensure the following:

- **Current Matching:** The drain current (\( I_D \)) of matched transistors (M1, M2, M3) must be the same.
- **Voltage Consistency:** The node voltages should match experimental results.

Since **M1, M2, and M3** have the **same W/L ratio**, they will have identical drain currents, ensuring symmetry.

For **M4, M5, and M6**, their **(W/L) ratios differ**, but they must still be biased properly to maintain the same experimental **current and voltage values**.

---

### **3. Steps to Verify the DC Analysis**
1. **Compute \( V_{GS} \) for each transistor**  
   - Ensure each MOSFET is in **saturation** by checking \( V_{GS} \) and \( V_{th} \).
   
2. **Find the DC operating point (voltages and currents)**  
   - Solve Kirchhoff’s Current Law (KCL) and Kirchhoff’s Voltage Law (KVL) equations.
   
3. **Check consistency with Experiment 3 results**  
   - Verify that **simulated values** match **measured values** in the lab.


**Output:**



### Transient Analysis:

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20095415.png)

### AC Analysis:

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/f3033e0f88a369c6068e575911c527411adbc103/Screenshot%202025-04-03%20095442.png)

#### Steps to get Ac analysis Waveform:
- In simulation tab select AC Analysis.
- In the AC Analysis tab, select **Type of Sweep as Decade**.
- Enter the number of points per decade (ex:20) and the frequency range ( 0.1Hz to 1THz).





### Inference:

The higher-than-expected gain suggests the circuit might have additional gain contributions from parasitic effects or device mismatches.
The gain deviation could also be due to underestimation of drain resistance or transconductance variations.
