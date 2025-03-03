# **Linear Integrated Circuits**

## **Experiment - 03** {Analysis of MOS Differential Amplifier}

### **Aim**
  Perform  DC, Transient and AC analysis of differential amplifier with the following specifications using LT Spice      

- **Vdd** = 2V 
- **Vin** = 1V 
- **Power budget** = 1mW 
- **Vo,cm** = 1.1V 
- **Vp** = 0.4V 

Also extract the following parameters:
- DC operating point
- Input and output maximum swing
- Gain 

### Differential Amplifier with a Resistive Load
  ![IMG_20250303_074814.jpg](https://github.com/user-attachments/assets/cfc32586-fcce-4aa7-b1e8-74ae135d6dd4)

Above circuit depecits the two common source amplifier having same Vdd connected to a single resistor Rss(Ron3) this constitutes differential amplifier with resistive load. 

#### Calculations

- Both the transistor are nMOS transistors with 180nm technology. 

- P = 1mW and Vdd = 2V\
  W.K.T  P=V×I\
         1×10^-3 = 2 × I\
         I = (1×10^-3)/2\
         'Iss = 0.5mA'
        
- Id1=Id2=Id\
  Id=Iss/2\
  Id=0.25mA

- Iss=0.5mA and Vp=0.4V\
  Rss=Vp/Iss\
  Rss=0.4/0.5m\
  Rss=800 ohm

#### Procedure

  - Perform DC analysis to obtain operating point(.op) by adjusting width and length of both MOSFETS. 
  - 

### **Differential Amplifier with a current source {tail current}** 
  ![IMG_20250303_074851.jpg](https://github.com/user-attachments/assets/751870f1-ecc0-43e5-91e5-b385ad413211)


  The above figure shows the basic MOS differential-pair configuration. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a constant-currentsource I.  

- Differential amplifiers apply gain not to one input signal but to the difference between two input signals. This means that a differential amplifier naturally eliminates noise or interference that is present in both input signals.
- It also suppresses common-mode signals—in other words, a DC offset that is present in both input signals will be removed, and the gain will be applied only to the signal of interest (assuming, of course, that the signal of interest is not present in both inputs). 
- This is particularly advantageous in the context of IC design because it eliminates the need for bulky DC-blocking capacitors.The subtraction that occurs in a differential pair makes it easy to incorporate the circuit into a negative-feedback amplifier.

The differential pair is all about balance. Thus, for optimal performance the resistors and MOSFETs must be matched. This means that the channel dimensions of both FETs must be the same and that R1 must equal R2. The resistance value chosen for the two resistors will be referred to as RD (for drain resistance).
  

