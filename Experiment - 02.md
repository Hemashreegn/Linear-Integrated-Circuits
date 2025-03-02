# **Linear Integrated Circuits**

## **Experiment - 03** {Analysis of MOS Differential Amplifier}

### **Aim**
  Perform  DC, Transient and AC analysis of differential amplifier with the following specifications using LT Spice      - **Vdd** = 2V 
- **Vin** = 1V 
- **Power budget** = 1mW 
- **Vo,cm** = 1.1V 
- **Vp** = 0.4V 
Also extract the following parameters:
- DC operating point
- Input and output maximum swing
- Gain 

### **Differential Amplifier** 
  ![IMG-20250302-WA0000.jpg](https://github.com/user-attachments/assets/296e3473-ed00-4e61-86e6-6d93b64bdc2e)


  The above figure shows the basic MOS differential-pair configuration. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a constant-currentsource I.  

- Differential amplifiers apply gain not to one input signal but to the difference between two input signals. This means that a differential amplifier naturally eliminates noise or interference that is present in both input signals.
- It also suppresses common-mode signals—in other words, a DC offset that is present in both input signals will be removed, and the gain will be applied only to the signal of interest (assuming, of course, that the signal of interest is not present in both inputs). 
- This is particularly advantageous in the context of IC design because it eliminates the need for bulky DC-blocking capacitors.The subtraction that occurs in a differential pair makes it easy to incorporate the circuit into a negative-feedback amplifier.

The differential pair is all about balance. Thus, for optimal performance the resistors and MOSFETs must be matched. This means that the channel dimensions of both FETs must be the same and that R1 must equal R2. The resistance value chosen for the two resistors will be referred to as RD (for drain resistance).
  

### Differential Amplifier with a Resistive Load
  
