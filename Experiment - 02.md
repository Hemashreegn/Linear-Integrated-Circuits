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
         `Iss = 0.5mA`
        
- Id1=Id2=Id\
  Id=Iss/2\
  `Id=0.25mA`

- Iss=0.5mA and Vp=0.4V\
  Rss=Vp/Iss\
  Rss=0.4/0.5m\
  `Rss=800 ohm`

#### Procedure
 
- Circuit 
 ![IMG-20250303-WA0005.jpg](https://github.com/user-attachments/assets/beac2cf1-9d3a-4c21-8823-efaa5b459583)


  - Perform DC analysis to obtain operating point(.op) by adjusting width and length of both MOSFETS and also increase Vin and observe the changes in output.\ 

  - Perform transient analysis and obtain maximum input and output swings. 

  - Perform AC analysis and obtain gain. 

#### Results

![IMG-20250303-WA0006.jpg](https://github.com/user-attachments/assets/630f615f-d7f0-4bea-b38c-20eecbfc8c61)

- Operating point (1.1V , 0.25mA) is obtained at length=180nm and width=19.3625um for both the MOSFETs. 

![IMG_20250303_135129.jpg](https://github.com/user-attachments/assets/205ec111-bf04-4652-8462-0c88cc481ee7)

- Input maximum swing can be obtain using equation\
    Vds>=Vov+x\
    Vds=Vgs-Vth+x\
    Vd-Vs=Vg-Vs-Vth+x\
    Vo-Vp=Vin-Vp-Vth+x\
    1.1-0.4=1-0.4-0.497+x\
    0.7=0.103+x\
    `x=0.497V`

    x=0.497-Vp\
    x=0.497-0.4\
    x=0.197\
    `x=197mV`

After running .op if we use shift+L we can obtain Vth (along with body effect). \
x is the amplitude to be given in transient analysis to obtain maximum input swing. 

![IMG_20250303_135446.jpg](https://github.com/user-attachments/assets/21fc1f71-9501-40a8-aee5-65db3c1da939)

- Gain obtained is 5.5dB\
  -3dB frequency is found out to be 3.958GHz


### **Differential Amplifier with a current source {tail current}** 
  ![IMG_20250303_074851.jpg](https://github.com/user-attachments/assets/751870f1-ecc0-43e5-91e5-b385ad413211)


  The above figure shows the basic MOS differential-pair configuration. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a constant-currentsource I.  

- The differential pair is all about balance. Thus, for optimal performance the resistors and MOSFETs must be matched. This means that the channel dimensions of both FETs must be the same and that R1 must equal R2. The resistance value chosen for the two resistors will be referred to as RD (for drain resistance).

#### Procedure
 
- Circuit 
 ![IMG-20250303-WA0009.jpg](https://github.com/user-attachments/assets/a8f7064f-b4d8-4fd4-b6a0-fa3e3d04d675)


  - Perform DC analysis to obtain operating point(.op) by adjusting width and length of both MOSFETS and also increase Vin and observe the changes in output.\ 

  - Perform transient analysis and obtain maximum input and output swings. 

  - Perform AC analysis and obtain gain. 

#### Results

![IMG-20250303-WA0010.jpg](https://github.com/user-attachments/assets/a59091a9-2a8a-44f0-a41f-4420cc95b04a)

- Operating point (1.1V , 0.25mA) is obtained at length=180nm and width=19.3625um for both the MOSFETs. 

![IMG_20250303_135129.jpg](https://github.com/user-attachments/assets/205ec111-bf04-4652-8462-0c88cc481ee7)

- Input maximum swing can be obtain using equation\
    Vds>=Vov+x\
    Vds=Vgs-Vth+x\
    Vd-Vs=Vg-Vs-Vth+x\
    Vo-Vp=Vin-Vp-Vth+x\
    1.1-0.4=1-0.4-0.497+x\
    0.7=0.103+x\
    `x=0.497V`

    x=0.497-Vp\
    x=0.497-0.4\
    x=0.197\
    `x=197mV`

After running .op if we use shift+L we can obtain Vth (along with body effect). \
x is the amplitude to be given in transient analysis to obtain maximum input swing. 

![IMG-20250303-WA0011.jpg](https://github.com/user-attachments/assets/f0744134-3038-488a-b585-3bfd82681b71)

- Gain obtained is 0dB(it has gradually decreased)\
  -3dB frequency is found out to be 60.189MHz

### **Differential Amplifier with a MOSFET acts as current source** 
  ![IMG_20250303_075023.jpg](https://github.com/user-attachments/assets/21cf9887-ac19-4ed6-ad8b-eb4617dbc46f)

  The above figure shows the MOS differential-pair configuration with current source replaced by MOSFET. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a 180nm technology MOSFET M3. 


#### Procedure
 
- Circuit 
 ![IMG-20250303-WA0013.jpg](https://github.com/user-attachments/assets/8d35b5d6-c210-40f5-a734-a42fe6d78e06)


  - Perform DC analysis to obtain operating point(.op) by adjusting width and length of both MOSFETS and also increase Vin and observe the changes in output.\ 

  - Perform transient analysis and obtain maximum input and output swings. 

  - Perform AC analysis and obtain gain. 

#### Results

![IMG-20250303-WA0014.jpg](https://github.com/user-attachments/assets/575f0e4d-d4d9-43cb-b86f-1c952aabc478)


- Operating point (1.1V , 0.25mA) is obtained at length=180nm and width=19.3625um for both the MOSFETs M1 and M2 and length=180nm , width=4.69009um for MOSFET M3. 
- Vb is calculated using the condition Vgd<=Vth\
       Vgd<=Vth\
       Vb-Vp=Vth\
       Vb=Vth+Vp\
       Vb=0.497+0.4\
       `^Vb=0897V`
   
![IMG-20250303-WA0015.jpg](https://github.com/user-attachments/assets/49aeb12b-46c8-4b31-b765-deded5d45014)

- Input maximum swing can be obtain using equation\
    Vds>=Vov+x\
    Vds=Vgs-Vth+x\
    Vd-Vs=Vg-Vs-Vth+x\
    Vo-Vp=Vin-Vp-Vth+x\
    1.1-0.4=1-0.4-0.497+x\
    0.7=0.103+x\
    `x=0.497V`

    x=0.497-Vp\
    x=0.497-0.4\
    x=0.197\
    `x=197mV`

After running .op if we use shift+L we can obtain Vth (along with body effect). \
x is the amplitude to be given in transient analysis to obtain maximum input swing. 

![IMG-20250303-WA0016.jpg](https://github.com/user-attachments/assets/61ed9c81-b712-48e6-9571-1544ac0ada97)

- Gain obtained is -8.813dB\
  -3dB frequency is found out to be 1.2GHzHz

#### Inference 

- The differential amplifier with a resistive load has the highest gain and highest -3dB frequency, making it suitable for high-frequency applications but with moderate power consumption and gain.

- The configuration with a tail current source (current source biasing) resulted in a lower gain and -3dB frequency, which may be beneficial for achieving more stable operation, but at the cost of reduced amplification and bandwidth.

- The MOSFET current source produced the lowest gain and bandwidth, suggesting that the choice of current source can significantly affect both the frequency response and the amplification characteristics of the differential amplifier.

- This experiment demonstrates the trade-offs between different configurations of MOS differential amplifiers and highlights the importance of balancing gain, bandwidth, and stability in analog circuit design.



  

