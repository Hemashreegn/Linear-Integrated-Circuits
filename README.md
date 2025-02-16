 # Linear-Integrated-Circuits
 
 ## Experiment - 01

 ## Aim
    To design and analyse a Common Source Amplifier using a 180nm MOSFET and perform DC, Transient and AC analysis in LT Spice.
 
 ### Specifications
     180nm technology, tsmc, Vdd=1.8V, Vg=0.9V, Vs=0V, Power=100uW, AC amplitude=50mV.

 ### Question 1
 ### Analysis of CS Amplifier with Resistive load circuit. 

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

 #### **2.Resistor**
   Select 1k ohm resistor and place it, conect drain terminal of **M1** to one terminal of resistor and other terminal to **V2**(power supply). 

 #### **3.Biasing**
   Input signal source of 0.9V, **V1** to gate of **M1**. 
 
 #### **4.Calculations**
     **Drain current(Id)** = 5.55 × 10^-5 A (calculated using P = V×I)

     **Resistor** = 2.764k ohms (calculated using Vout=Vdd -(Id×Rd))

## DC Analysis 

   #### Objective 
           To determine the operating point of the MOSFET.

   #### Procedure
           
           1. Set up the circuit in the Spice.
           2. Attach the tsmc018.lib library file to the 180nm MOSFET.
           3. Perform a DC operating point(DC op pnt) analysis.
           4. Find expected Vout(Output voltage) and Id(drain current) by changing the aspect ratio.

   #### Observations
           
           The expected operating point (5.55×10^-5A , 1.64V) was obtained at the length=180nm and width=0.209um. 

## Transient Analysis 

   #### Objective 
           To analyse the output waveforms to an input signal and 

   #### Procedure 
      
           1. Apply a sinusoidal input signal of 50mV at 1kHz.
           2. Perform a Transient Analysis in LT Spice.
           3. 
         
      
    
   

  
 
 
