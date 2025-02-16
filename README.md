 # **Linear-Integrated-Circuits**
 
 ## **Experiment - 01**

 ## Aim
  To design and analyse a Common Source Amplifier using a 180nm MOSFET and perform DC, Transient and AC analysis in LT Spice.
 
 ### Specifications
  180nm technology, tsmc, Vdd=1.8V, Vg=0.9V, Vs=0V, Power=100uW, AC amplitude=50mV.

 ### Question 1
 ### Analysis of nMOS CS Amplifier with Resistive load circuit. 

 ### Components Required 

- **NMOS Transistor** : **M1**(nmos4) 
- **Resistor** : **R**(1k ohm) 
- **Power supply** : **V2**(Vdd = 1.8V) 
- **Input signal source** : **V1**(Vg = 0.9V) 

 ### Circuit Diagram 

 #### **1.Transistor setup**
  - Select nmos4 transistor from the library and place it i.e., **M1**
  - Connect source of **M1** to ground. 
  - Connect drain of **M1** to one terminal of resistor. 

 #### **2.Resistor setup**
   Select 1k ohm resistor and place it, conect drain terminal of **M1** to one terminal of resistor and other terminal to **V2**(power supply). 

 #### **3.Biasing**
   Input signal source of 0.9V, **V1** to gate of **M1**. 
 
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
 ![IMG-20250217-WA0004.jpg](https://github.com/user-attachments/assets/057b03ac-a933-47be-96d0-f594b9e743bd)


- The obtained gain is, **Av= -34dB**.
- The 3dB frequency found was 
- The Bandwidth obtained is 

## Inference 

- The importance of MOSFET to be in saturation region to act as linear amplifier was observed.

- We can obtain the required current by altering the aspect ratio which withholds their proportionality.

- We can obtain the sinusoidal waveform with visible phase shift in the input and output.

- We can obtain the gain through the graph and tally it with the theoretical values.

 ### Question 2
 ### Analysis of nMOS CS Amplifier with Resistive load replaced by pMOS circuit.





 
 
    


  
         
      
    
   

  
 
 
