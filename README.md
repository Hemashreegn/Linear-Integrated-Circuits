 # **Linear-Integrated-Circuits**
 
 ## **Experiment - 01**

 ## Aim
  To design and analyse a Common Source Amplifier using a 180nm MOSFET and perform DC, Transient and AC analysis in LT Spice.
 
 ### Specifications
  180nm technology, tsmc, Vdd=1.8V, Vg=0.9V, Vs=0V, Power Budget=100uW, AC amplitude=50mV.

 
 ### Question 1
 ### Analysis of nMOS CS Amplifier with Resistive load circuit. 

 ### Components Required 

- **NMOS Transistor** : **M1**(nmos4) 
- **Resistor** : **R**(1k ohm) 
- **Power supply** : **V1**(Vdd = 1.8V) 
- **Input signal source** : **V2**(Vg = 0.9V) 

 ### Circuit Diagram 
![IMG_20250217_013254.jpg](https://github.com/user-attachments/assets/3561dead-2724-4be3-87ad-47b659163859)

 #### **1.Transistor setup**
  - Select nmos4 transistor from the library and place it i.e., **M1**
  - Connect source of **M1** to ground. 
  - Connect drain of **M1** to one terminal of resistor. 

 #### **2.Resistor setup**
   Select 1k ohm resistor and place it, conect drain terminal of **M1** to one terminal of resistor and other terminal to **V1**(power supply). 

 #### **3.Biasing**
   Input signal source of 0.9V, **V2** to gate of **M1**. 
 
 #### **4.Calculations**
 - **Drain current(Id)** = 5.55 × 10^-5 A (calculated using P = V×I)
 - **Resistor** = 2.764k ohms (calculated using Vout=Vdd -(Id×Rd),later 1k ohm resistor is changed to 2.764k ohm)

## DC Analysis 

  #### Objective 
   To determine the operating point of the MOSFET.

  #### Procedure
           
   1. Set up the circuit in the Spice.
   2. Attach the tsmc018.lib library file to the 180nm MOSFET.
   3. Perform a DC operating point(DC op pnt) analysis.(.op)
   4. Find expected Vout(Output voltage) and Id(drain current) by changing the aspect ratio.

   #### Result
   ![IMG-20250217-WA0000.jpg](https://github.com/user-attachments/assets/a9f90c76-d5d6-41e0-84c6-fd06138fcf1f)   

         
   The expected operating point **(5.55×10^-5A , 1.64V)** was obtained at the **length=180nm** and **width=0.209um**. 

## Transient Analysis 

  #### Objective 
   To analyse the output waveforms to an input signal.

  #### Procedure 
      
   1. Apply a sinusoidal input signal of Vg=O.9V with an amplitude of 50mV and frequency of 1kHz.
   2. Perform a Transient Analysis by setting up stop time as 3ms, start time as 0 and run.(.tran 0 3m 0)

  #### Result
  ![IMG_20250217_012513.jpg](https://github.com/user-attachments/assets/38967def-a49d-4155-888e-eff9f4d63404)


   We can observe the **180° phase shift** between the input and output signal.

## AC Analysis 
  
 #### Objective 
  To determine voltage gain and frequency response.

 #### Procedure 

  1. Perform AC analysis with an input of 50mV AC.
  2. Set type of sweep to decade, number of points per decade to 100, Start frequency to 0.1Hz and Stop frequency to 1THz.
  3. Then run the simulation.(.ac dec 100 0.1 1T)

 #### Result 
![Image](https://github.com/user-attachments/assets/3d61aab1-2585-4766-970b-eb3432a89cbb)

- The obtained gain is, **Av= -22dB**.
- The Bandwidth will be f_H in GHz (as lower frequency cutoff(f_L) is usually very low due to coupling and bypass capacitors so, the bandwidth is equal to high frequency cutoff(f_H)).

## Inference 

- The importance of MOSFET to be in saturation region to act as linear amplifier was observed.

- We can obtain the required current by altering the aspect ratio which withholds their proportionality.

- We can obtain the sinusoidal waveform with visible phase shift in the input and output.

- We can obtain the gain through the graph and tally it with the theoretical values.

 ### Question 2
 ### Analysis of nMOS CS Amplifier with Resistive load replaced by pMOS transistor circuit.

 ### Components Required 

- **NMOS Transistor** : **M1**(nmos4) 
- **PMOS Transistor** : **M2**(pmos4) 
- **Power supply** : **V2**(Vdd = 1.8V) 
- **Input signal source** : **V1**(Vg = 0.9V) 

 ### Circuit Diagram 
![Image](https://github.com/user-attachments/assets/ac6e3a45-41db-427d-8aa3-c77534f413e1)
#### **1. NMOS setup**
  - Select nmos4 transistor from the library and place it i.e., **M1**
  - Connect source of **M1** to ground. 
  - Connect drain of **M1** to source of **M2**. 
  - Connect gate of **M1** to input signal of 0.9V.

#### **2. PMOS setup**
  - Select pmos4 transistor from the library and place it i.e., **M2**  
  - Connect drain of **M2** to supply voltage (Vdd). 
  - Connect gate of **M2** to Vb(bias voltage).

#### **3.Biasing**
  - Input signal source of 0.9V, **V2** to gate of **M1**.
  - Input signal source, **Vb** to gate of **M2**.
      - **Vb=0** as it is a common diode circuit and Vb has to be zero for the circuit to operate in saturation region.

## DC Analysis 

  #### Objective 
   To determine the operating point of the MOSFET.

  #### Procedure
           
   1. Set up the circuit in the LT Spice.
   2. Attach the tsmc018.lib library file to the 180nm MOSFET(It has data of both nMOS and pMOS transistor).
   3. Perform a DC operating point(DC op pnt) analysis.(.op)
   4. Find expected Vout(Output voltage) and Id(drain current) by changing the aspect ratio of both **M1** and **M2**.

  #### Result
  ![Image](https://github.com/user-attachments/assets/016a03c3-6afc-4a30-9c12-40a86ba97de1)

   The expected operating point **(5.55×10^-5A , 1.64V)**(same drain current for M1 and M2) was obtained at the **length=180nm** and **width=0.209um** of **M1**(nMOS) and **length=180nm** and **width=0.775um** of **M2**(pMOS). 

  ## Transient Analysis 

  #### Objective 
   To analyse the output waveforms to an input signal.

  #### Procedure 
      
   1. Apply a sinusoidal input signal of Vg=O.9V with an amplitude of 50mV and frequency of 1kHz.
   2. Perform a Transient Analysis by setting up stop time as 3ms and run.(.tran 3m )

  #### Result
  ![Image](https://github.com/user-attachments/assets/49fa334b-e124-4d2e-aa64-e96f2b5ccfd3)

  We can observe the **180° phase shift** between the input and output signal.

  ## AC Analysis 
  
 #### Objective 
  To determine voltage gain and frequency response.

 #### Procedure 

  1. Perform AC analysis with an input of 50mV AC.
  2. Set type of sweep to decade, number of points per decade to 100, Start frequency to 0.1Hz and Stop frequency to 1THz.
  3. Then run the simulation.(.ac dec 100 0.1 1T)

 #### Result 
![Image](https://github.com/user-attachments/assets/8b89d4bf-9f24-4352-a527-8179ab96115d)
- The obtained gain is, **Av= -33.5dB**.
- The Bandwidth will be f_H in GHz (as lower frequency cutoff(f_L) is usually very low due to coupling and bypass capacitors so, the bandwidth is equal to high frequency cutoff(f_H)).

 ## Inference

 - pMOS acts as a active load for this circuit instead of load resistor, so this amplifier circuit causes the inverting behaviour due to commom source transisto rbehaviour in conjunction with pMOS active load.

 - Using pMOS transistor we can observe phase inversion.

 - Operating point is obtained where Id1=Id2 with different aspect ratio of both transistors.

 - The gain increases compared to the first circuit.

  

    
  

 
 
    


  
         
      
    
   

  
 
 
