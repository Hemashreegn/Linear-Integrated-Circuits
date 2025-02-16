# A Linear-Integrated-Circuits

 ## Aim
 Analysis of a CS Amplifier using LT Spice. 
 
 Specifications: 180nm, tsmc, Vdd=1.8V, Vg=0.9V, Power=100uW.

 Analysis: DC analysis, Transient analysis, AC analysis. 

 ## 

 ### Question 1
 ### Analysis of CS Amplifier with Resistive load circuit. 

 #### Components Required 

**• NMOS Transistor** : **M1**(nmos4) 
**• Resistor** : **R**(1k ohm) 
**• Power supply** : **V2**(Vdd = 1.8V) 
**• Input signal source** : **V1**(Vg = 0.9V) 

 #### Circuit Diagram 

 #### 1.Transistor setup 
  • Select nmos4 transistor from the library and place it i.e., **M1**
  • Connect source of **M1** to ground. 
  • Connect drain of **M1** to one terminal of resistor. 

 #### 2.Resistor 
   Select 1k ohm resistor and place it, conect drain terminal of **M1** to one terminal of resistor and other terminal to **V2**(power supply). 

 #### 3.Biasing 
   Input signal source of 0.9V, **V1** to gate of **M1**. 

  
 
 
