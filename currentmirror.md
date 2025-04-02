# Linear integrated circuits

# Experiment 4: Design and analysis of current mirror circuit
## Introduction :
A current mirror circuit is an essential analog building block used to replicate and regulate current in integrated circuits. It ensures that the output current closely matches the reference current, regardless of load variations. Commonly implemented using MOSFETs or BJTs, current mirrors are widely used in biasing, active loads, and current amplification in analog and mixed-signal circuits. The project aims to develop efficient mirror circuits, simulate their performance, and analyze the results in terms of gain, accuracy, and power consumption.

Here is a circuit of basic current mirror:

![)
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

![SettheWvaluefor180nm_current mirror]()

We took the current value 277.51uA very close to the calculated value.

## DC analysis

![DCanalysiscurrentmirror180nm]()

For better understanding 

![BetterDCanalysis180nm]()

Here one thing to notice is that the gm is changing for M3. Here are the reasons;
1. M1 and M2 are PMOS (cmosp), while M3 is NMOS (cmosn).

2. NMOS and PMOS have different mobility (μ) and threshold voltages, which directly affect gm.

3. Electron mobility (μₙ) for NMOS is higher than hole mobility (μₚ) in PMOS.

 Transconductance Depends on Overdrive Voltage:
 
So, despite same current, if Vov is lower, gm will be lower.

For M1, Vov ≈ 0.41 V, gm ≈ 1.02 mS

For M3, Vov ≈ 0.26 V, gm ≈ 0.73 mS 

## Transient Analysis

![Transientanalysis_180nm]()

calculated Gain = -13.3V/V

Calculated Gain in db = 22.47

## AC Analysis

![AC analysis180nm]()

Calculated Gain in db = 22.47

simulation Gain in db = 26.30

-3db = 23.30

Bandwidth = 1.823 GHz

## For L = 500nm

Before getting to the analysis part we shall calculate the width by using the same method as the previous one.

![Wfor500nm]()

## DC Analysis

![DCfor500nm]()

For better understanding

![BetterDCfor500nm]()

## Transient Analysis

![Transientanalysis500nm]()

Calculated gain = -15.268 V/V

## AC Analysis

![ACfor500nm]()

Gain in db = 34.5

-3db Gain = 31.5

Bandwidth = 166.998 MHz

We can notice the increase in the gain when we increase the length to 500nm. This is due to the decrease in the channel length modulation effect. As lambda decreases the impedence increases. 

## For L = 1um

Setting the Width value(W)

![Wfor1u]()

W = 27.902773u

## DC Analysis

![DCfor1u]()

For better understanding

![BetterDCanalysis1u]()

## Transient Analysis

![Transientanalysis1u]()

Gain = 15.854 V/V

## AC Analysis

![ACfor1u]()

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

> **Observation:** As the channel length (L) increases:
> - The **gain improves** significantly due to higher output resistance.
> - The **bandwidth reduces**, indicating a trade-off between gain and speed.

## For 1:2 

We are gonna find the Iref and Ix.
By calculation we got 185uA and 370uA respectively.
So Itotal = 555uA.

I am checking for L = 500nm.

First setting the Width for M1 for 185uA. 

![Wfor1isto2]()

Then mutiplying the W value manually we got 22.150 um. For this value we got the value of current to be 369.39uA. So by incrementing the width value by 0.04 um we got the following results.

## DC Analysis

![DCfor1isto2]()

For better understanding.

![BetterDCfor1isto2]()

## Transient Analysis

![TransientAnalysisfor1isto2]()

Gain = -15.002 V/V

## AC Analysis

![ACfor1isto2]()

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
