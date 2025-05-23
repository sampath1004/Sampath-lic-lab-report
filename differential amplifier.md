# Experiment-3 
## Differential Amplifier:
A Differential amplifier is an electronic circuit that amplifies the voltage difference between two input signals while rejecting any common-mode signals. It is a 
 fundamental component in analog electronics, often used in operational amplifiers and signal processing.Differential amplifiers are widely used in 
 instrumentation, audio processing, and sensor interfacing, where precise and stable signal amplification is required.
It consist of two transistors M1 and M2, whose sources are joined together.If two transistor are connected to the different voltage input then there current 
 across M1 and M2 are different due to gate voltage.If in case the voltage supply at gate terminal is same then the current through the M1 and M2 are same 
 (Im1=Im2).This configuration is called Common Mode input voltage differential Amplifier.Whatever may be the load resistor, the MOSFET M1 and M2 should not go 
 to the Triode region. It should be verified that MOSFET should be in Saturation Region.
 This Expereiment is Based on Common Mode Input voltage Differential Amplifier.


For all this circuit we need find out the DC Analysis , Transient analysis and AC analysis 
#### To find the all the values of resistor and source resistor. we need solve the given queston specification.

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/6bc432b3d43f8f9b080229caa4b3e99a1dae3512/design.jpg)

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

## 1.Circuit 1 :

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/182eb699ddb2574914772d537b9c875194a696ae/circuit_1.png)
  
   In this circuit we have two MOSFET connected to same voltage input forming differential pair. Load Resistor is coonected to  Drain terminal of MOSFET.
   Source terminal is connected resistor and another terminal is connected to ground this is called source degenration resistor.

### Components Required

DC voltage supply, AC voltage supply, N-channel MOSFETs, resistors

Parameters of MOSFET: L=180nm
                      W=7.7um

### Procedure:

1.Open the LTspice software, merge the library file for getting accurate values of NMOS.

2.Select the components which are needed to us like for circuit 1 we need two 1.83k resistor and one 0.41666k resistor,2 CMOSN, voltage sources(2.5,1.3),ground 
 from the components list.

3.Place them all components in necessory way which is helpfull, connect all the components as in given circuit .

4.Link the specification of list of properties of mosfet like threshold voltage, temperature etc.

5.Lets do the DC Analysis first by opting a simulation, we get .op so after placing it we will get the values of it, thet will displayed.

6.After that lets take Transient analysis of 5m cycle so in input and output waveforms in 5 complete cycle, so here we get and seperate and combined waveforms of 
 input and output.

7.For AC analysis, we should do some changes like converting DC SOURCE to sinosoidal waveform (1.3,50m,1T),after that select the AC simulation from the given 
 options of simulation after giving values of (Decade,20,01,1T). So we will get a output after placing node to output waveform .


To do circit analysis first we need to check that the Both the  MOSFET should be in the  Saturation Region which should satisfy this;

 VDS > VGS - Vth

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/5fe98385152151eda2c01d43d34b01c018215a03/Screenshot%202025-03-06%20013716.png)
 
### DC Analysis
![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/afa78f3516a045c22305dce501e3049c2ba240ba/dc_1.png)
### Transient Analysis:
The transient analysis explain the  circuit response at a particular instant of  time when a time-varying signal is applied at the inputs.In this experiment we 
 can see a complete phase shift of 180 degree output to the input signal.As with respect to context of voltage gain, as the volatge gain is more leads to the 
 smaller the bandwidth size.At the particular time output wave changes with respect input in the amplitude.

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/afa78f3516a045c22305dce501e3049c2ba240ba/tran_1.png)

Voltage Gain of this circuit is given by= Vout-Vin

Av=(1.4718-1.3287/1.3481-1.2504)V/V
=1.4646V/V

Therefore Higher the Higher resistor value reduces gain but increases bandwidth and more the  transient response.

## AC Analysis:

Frequency response is determining quantity of bandwidth and stability of a MOSFET. This is divide into three regions;

1.Low frequency

2.Mid-band Frequency

3.High Frequency

In this experiment we can observe that there is no low frequency region because of there is no bypass or coupling capacitor in the circuit.We can observe that mid 
 band region upper value is nearear to the 3dB value which can used as parameter to check bandwidth of amplifier to maintain its gain.

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/afa78f3516a045c22305dce501e3049c2ba240ba/ac_1.png)

Gain =20*log(Av)
      =20*log(1.4646)
      =3.314dB

By calculating from graph we can say Therotical nad experiment value of mid band frequency is approximatly equal.

### 2.Circuit 2 :

![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/182eb699ddb2574914772d537b9c875194a696ae/circuit_2.png)
Same  as the ciruit in the resistor circuit we need to replace resistor by current source . We have two MOSFET connected to same voltage input forming 
 differential pair.And current source is connected to the Drain terminal of MOSFET.

Source terminal is connected to the current source and another terminal is connected to ground.

## Modification
- Replace the resistor **Rss** with a **current source (1mA)** to improve stability.

  
### Procedure:

1.Open the LTspice software, merge the library file for getting accurate values of NMOS.

2.Select the components which are needed to us like for circuit 2 we need two 1.83k resistor and one 0.41666k resistor,2 CMOSN, voltage sources(2.5,1.3),ground 
 from the components list.

3.Place them all components in necessory way which is helpfull, connect all the components as in given circuit .

4.Link the specification of list of properties of mosfet like threshold voltage, temperature etc.

5.Lets do the DC Analysis first by opting a simulation, we get .op so after placing it we will get the values of it, thet will displayed.

6.After that lets take Transient analysis of 5m cycle so in input and output waveforms in 5 complete cycle, so here we get and seperate and combined waveforms of 
 input and output.

7.For AC analysis, we should do some changes like converting DC SOURCE to sinosoidal waveform (1.3,50m,1T),after that select the AC simulation from the given 
 options of simulation after giving values of (Decade,20,01,1T). So we will get a output after placing node to output waveform .



### DC Analysis:

 We need set voltage of Vicm to maintain the desired value of the current and voltage at source point.As a result opertaing point will be given as;

 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/182eb699ddb2574914772d537b9c875194a696ae/dc_2.png)
 
 In the operating values we got the current flowing through the common source terminal is exactly what we had derived in intial stage of the experiment.

 ## Transient Analysis:

 The volatge gain of the ciruits inceases because of the current source drop across it is less compared to the Rs resistor drop. So the Voltage gain of circuit is 
 more compared to the circuit 1.
 - Apply a **180-degree phase shift** to one MOSFET while keeping the other at **0 degrees**.
- Assign an **AC amplitude of 1** to one input and **0 to the other** (even -1).
- Run the simulation and analyze the improved transient response.

 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/182eb699ddb2574914772d537b9c875194a696ae/tran_2.png)

 Voltage gain= vout/vin
              =(1.6287-1.1744)/(1.3982-1.2503)
              =4.533V/V

## AC Analysis:

 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/182eb699ddb2574914772d537b9c875194a696ae/ac_2.png)

  Gain =20*log(Av)
      =20*log(4.533)
      =13.12dB


### 3. Circuit 3 ;

  ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/0d0d1e554556b02bcfc6c4fceb4b5722d759ab7a/circuit_3.png)

Now we are replacing the current source to the mosfet(M3) where we need to keep current Id3 as our desired value And to keep the mosfet(M1,M2,M3) in saturation 
 region so that voltage gain will be maintained.In this ciruit MMOsfet is connected to drain of it to source terminal and to other ground.
 

 ## Modification
- Replace the current source with a **MOSFET acting as an active current source**.
- Given parameters: **Vp = 0.5V, Vt = 0.36V**, leading to a **gate voltage of 0.86V**.
- Adjust **W/L ratio** of the new MOSFET to optimize performance.

  
### Procedure:

1.Open the LTspice software, merge the library file for getting accurate values of NMOS.

2.Select the components which are needed to us like for circuit 3 we need two 1.83k resistor and one 0.41666k resistor,2 CMOSN, voltage sources(2.5,1.3),ground 
 from the components list.

3.Place them all components in necessory way which is helpfull, connect all the components as in given circuit .

4.Link the specification of list of properties of mosfet like threshold voltage, temperature etc.

5.Lets do the DC Analysis first by opting a simulation, we get .op so after placing it we will get the values of it, thet will displayed.

6.After that lets take Transient analysis of 5m cycle so in input and output waveforms in 5 complete cycle, so here we get and seperate and combined waveforms of 
 input and output.

7.For AC analysis, we should do some changes like converting DC SOURCE to sinosoidal waveform (1.3,50m,1T),after that select the AC simulation from the given 
 options of simulation after giving values of (Decade,20,01,1T). So we will get a output after placing node to output waveform .   
  
 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/0d0d1e554556b02bcfc6c4fceb4b5722d759ab7a/mos.png) 
  

### DC Analysis:
![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/0d0d1e554556b02bcfc6c4fceb4b5722d759ab7a/dc_3.png)

By identifying the value of VB of MOSFET M3 we need check the current flow through the MOSFET and It should be in saturation region.

VB value (Gate terminal of MOSFET M3)=0.86v


### Transient Anlysis:

 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/0d0d1e554556b02bcfc6c4fceb4b5722d759ab7a/tran_3.png)


- Apply an **AC amplitude of 1** to one MOSFET and **0 to the other**.
- Run the simulation to observe improved transient response.

  
Voltage gain(Av) = vout/vin
            =(1.628-1.1751)/(1.350-1.249)
            =4.53V/V
 Voltage gain of MOSFET is 4.53V/V


### AC Analysis:

 ![image](https://github.com/sampath1004/Sampath-lic-lab-report/blob/0d0d1e554556b02bcfc6c4fceb4b5722d759ab7a/ac_3.png)

Gain(dB)=20*log(Av)
        =20*log(4.53)
        =13.12dB

  Gain of MOSFET is 13.12dB which same that of waveform obtained.

  # Results

## Circuit-1 
- DC analysis confirms **MOSFET operation in saturation** with equal drain currents for identical inputs.  
- Transient response demonstrates **proper differential operation**.  
- AC analysis reveals **moderate gain and limited common-mode rejection**.  

## Circuit-2 
- Replacing the resistor with a **current source** improves **bias stability**.  
- The transient response is **more stable and symmetrical**.  
- AC analysis shows **higher gain and increased bandwidth** compared to Circuit-1.  

## Circuit-3 
- DC analysis validates that the **MOSFET-based current source effectively regulates tail current**.  
- Transient response is **more accurate and stable**.  
- AC analysis demonstrates **higher gain and improved frequency response**.  
 

## Inference
  From this experiment, we can infer that the differential amplifier plays a crucial role in amplifying the difference between two signals while rejecting common-
 mode noise, making it an essential building block in operational amplifiers. The choice of configuration significantly impacts the circuit’s performance in terms 
 of gain.It also introduces negative feedback, which enhances stability but is sensitive to temperature variations in resistance values.On the other hand, the 
 current source-based configuration offers higher gain and better Common Mode Rejection Ratio, making it more precise and stable compared to the resistor-based 
 design.The results showed that the current source design closely matched the calculated values.Overall, the differential amplifier is a very useful configuration, since it measures the difference between the two drain voltages, thereby preventing the effects of any noise.
