# **LINEAR INTEGRATED CIRCUITS**

## **EXPERIMENT - 03** {ANALYSIS OF MOS DIFFERENTIAL AMPLIFIER}

### THEORY
![image](https://github.com/user-attachments/assets/a7429c17-48c7-4f08-ba66-3bb71cc7896d)

A **differential amplifier** amplifies the difference between two input signals while rejecting common-mode noise. It consists of a **matched transistor pair (NMOS)** sharing a common current source, with outputs taken from the drain nodes. The circuit improves **signal integrity, gain, and bandwidth**, making it essential in analog and mixed-signal designs.

- **Types Of Differential Amplifiers**
  
  - **Resistive Load Differential amplifier**
     - Uses **load resistor** for biasing and signal amplification.
     - **Moderate gain** with low output impedance.
     - Increasing gain with a larger resistor reduces the output voltage swing, limiting the amplifier's signal range.

  - **Current Mirror Source(Tail current) Differential Amplifier**
     - Uses **active current mirror** instead of resistor.
     - **High gain** with high input impedance.
     - Higher gain reduces output swing because the active load transistors limit voltage headroom.

  - **NMOS Tail Current Source Differential Amplifier**
     - Uses **NMOS as current source** instead of current source.
     - **Gain increases** because the NMOS current source reduces degeneration, and output impedance is higher due to the active current source.
     - Improves bias stability, gain, and common-mode rejection, but reduces output swing due to the voltage headroom required by the NMOS current source.

  - **Active Load Differential Amplifier**
     - Replaces Rd resistors with **180nm** technology **PMOS as load** .
     - **Higher gain** with higher input impedance.
     - Higher gain comes at the cost of reduced output swing due to limited voltage headroom from the active load 
      transistors.

### **AIM**
  Perform  DC, Transient and AC analysis of differential amplifier with the following specifications using LT Spice      

- **Vdd** = 2V 
- **Vin** = 1V 
- **Power budget** = 1mW 
- **Vo,cm** = 1.1V 
- **Vp** = 0.4V 

Also extract the following parameters:
- **DC operating point**
- **Input and output maximum swing**
- **Gain**  

### CALCULATIONS

- Both M1 and M2 transistors are **nMOS** transistors with **180nm** technology.

| **Calculation**        | **Formula**                             | **Value**            |
|-----------------------|-------------------------------------------------|------------------|
| **Tail Current (Iss)**  |  Iss = P/Vdd                 | 0.5mA           |
| **Tail Resistance (Rss)** |  Rss = Vp/Iss               | 800Ω            |
| **Drain Current (Id)**  |  Id = Iss/2                     | 0.25mA          |
| **Load Resistance (Rd)** |  Rd = Vdd - Vo(cm)/Id               | 3.6kΩ            |
| **Overdrive Voltage (Vov)** |  Vov = Vgs - Vth              | 0.2V            |
| **Transconductance (gm)** | gm = 2Id/Vov                 | 2.5mS           |
| **Voltage Gain (Av)** | Av = - gm * Rd                  | -9 V/V          |
| **Gain in dB (Av dB)** | Av(dB) = 20(log(Av))             | 19.08 dB        |


 
### CIRCUIT - 1 { RESISTIVE LOAD DIFFERENTIAL AMPLIFIER }
![Screenshot 2025-03-06 195034](https://github.com/user-attachments/assets/049080c4-bcfb-4a86-a378-5e590e05fa77)

Above circuit depecits the two common source amplifier having same Vdd connected to a single resistor Rss this constitutes differential amplifier with resistive load.

### DC ANALYSIS
  - Connect the circuit.
  - Adjust the length and width of both M1 and M2 transistors to obtain operating point.
  - Run simulation. 

![Screenshot 2025-03-06 214828](https://github.com/user-attachments/assets/6c9b253a-8b4b-4e34-9f8d-fa41f9123316)

- Operating point **(1.1V , 0.25mA)** is obtained at **length=180nm** and **width=19.3625um** for both the MOSFETs.
- Id1 , Id2 , Iss are obtained same as theoretical values.

Now increase Vin(cm) as 1.1V

![Screenshot 2025-03-07 223629](https://github.com/user-attachments/assets/90d05a4c-4340-4ef6-ace9-4048702184b4)

- We can observe increase in current Iss across resistor Rss leading to increase in drain current Id and decrease in output voltage Vout.

Further increase Vin(cm) as 1.2V

![Screenshot 2025-03-07 223905](https://github.com/user-attachments/assets/d1270841-5d15-444a-a959-2d70389074f7)

- Here Iss and Id current increases more and Vout decreases more.

#### Comparision Table for Different Vin(cm)

| **\( Vin(cm) \) (V)** | **\( Iss \) (mA)** | **\( Id1 \) (mA)** | **\( Id2 \) (mA)** | **\( Vout1 \) (V)** | **\( Vout2 \) (V)** |
|------------------|-------------|--------------|--------------|--------------|--------------|
| 1.0              | 0.000500    | 0.000250    | 0.000250    | 1.1          | 1.1          |
| 1.1              | 0.0005988   | 0.000299    | 0.000299    | 0.922        | 0.922        |
| 1.2              | 0.000693    | 0.0003465   | 0.0003465   | 0.7522       | 0.7522       |

- This proves that **Current(Iss/Id)** is dependent on **Vgs** in saturation region and **Vout** decreases as **current** increases.


### TRANSIENT ANALYSIS

- When input Vin1=1V with amplitude=50mV and frequency=1kHz and input Vin2=1V with amplitude=50mV and frequency=1kHz with phi(deg)=180.i.e.,
  Then we get,\
  `Vout(min) = 0.65V` , `Vout(max) = 1.55V` and `Vout(p-p) swing = 0.9V`
  
![image](https://github.com/user-attachments/assets/745ed452-305d-4c43-abff-5fdcc857bb04)


 - When **Vin(cm)_min = 0.897** is given as Vin1=1V with amplitude=-103mV and frequency=1kHz and input Vin2=1V with amplitude=-103mV and frequency=1kHz with phi(deg)=180 we obtained Vout(min) =     V , Vout(max) =     V and Vout(p-p) swing =    V.

![image](https://github.com/user-attachments/assets/dbc0cefc-2110-4d05-8581-c01f3afa4de3)


 - When **Vin(cm)_max = 1.597** is given as Vin1=1V with amplitude=597mV and frequency=1kHz and input Vin2=1V with amplitude=597mV and frequency=1kHz with phi(deg)=180 we obtained Vout(min) =     V , Vout(max) =     V and Vout(p-p) swing =    V.

![image](https://github.com/user-attachments/assets/156ee029-adb0-4f21-bba8-012b6a4b2f2b)


 ### AC ANALYSIS
![image](https://github.com/user-attachments/assets/2236ef15-54a3-4e92-9d57-2e6a49b46954)

- Gain obtained is 20dB\
-3dB frequency (20db-3dB=17dB) is found out to be 3.592GHz.


### **CIRCUIT - 2 { TAIL CURRENT SOURCE DIFFERENTIAL AMPLIFIER }** 
![Screenshot 2025-03-06 194805](https://github.com/user-attachments/assets/f240bb5b-edb0-4def-a937-57f6fedb8ba9)

 The above figure shows the basic MOS differential-pair configuration. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a constant-current source I.\  
The differential pair is all about balance. Thus, for optimal performance the resistors and MOSFETs must be matched. This means that the channel dimensions of both FETs must be the same and that R1 must equal R2. The resistance value chosen for the two resistors will be referred to as RD (for drain resistance).

### DC ANALYSIS
  - Connect the circuit.
  - Adjust the length and width of both M1 and M2 transistors to obtain operating point.
  - Run simulation.
  - 
![Uploading Screenshot 2025-03-07 014917.png…]()

- Operating point (1.1V , 0.25mA) is obtained at length=180nm and width=19.3625um for both the MOSFETs.
- No changes will be caused by change in resistor load to current source.  

### TRANSIENT ANALYSIS
![IMG_20250303_135129.jpg](https://github.com/user-attachments/assets/205ec111-bf04-4652-8462-0c88cc481ee7)

### AC ANALYSIS

- Gain obtained is 20dB\
- 3dB frequency (20db-3dB=17dB) is found out to be 3.720GHz.
- There is no change in gain from circuit 1.
  

### **CIRCUIT - 3 { NMOS TAIL CURRENT SOURCE DIFFERENTIAL AMPLIFIER }** 
![Screenshot 2025-03-09 124502](https://github.com/user-attachments/assets/7c0e296f-429b-42d2-834b-bdb1a1a66654)

  The above figure shows the MOS differential-pair configuration with current source replaced by MOSFET. It consists of two matched transistors, Q1 and Q2, whose sources are joined together and biased by a 180nm technology MOSFET M3. 

### DC ANALYSIS
  - Connect the circuit.
  - Adjust the length and width of both M1 and M2 transistors to obtain operating point.
  - Run simulation. 

![Screenshot 2025-03-09 131039](https://github.com/user-attachments/assets/5ed2e84b-db3f-483e-8622-93cb6d4144dc)

- Operating point (1.1V , 0.25mA) is obtained at length=180nm & width=19.3625um for both the MOSFETs M1 & M2
- Length=180nm & width=14.15645um for MOSFET M3 to obtain Q-point.
- Vb is calculated as follows:
  Vgd<=Vth (Condition for M3 to be in saturation region)\
  Vb-Vp<=Vth\
  Vb<=Vth+Vp\
  Vb<=0.497+0.4\
  Vb<=0.897V
  So at `Vb=0.682V`(Vb<0.897) we can obtained the operating point.

 ### TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/ea675250-16d1-4808-9302-735959327848)


### AC ANALYSIS
![image](https://github.com/user-attachments/assets/6838bcb6-bc38-4022-bf9c-d4d7897f6e56)


- Gain obtained is 20dB\
- 3dB frequency (20db-3dB=17dB) is found out to be 4.170GHz.
- There is no change in gain from circuit 1 & 2.
  
#### Inference 

- The differential amplifier with a resistive load has the highest gain and highest -3dB frequency, making it suitable for high-frequency applications but with moderate power consumption and gain.

- The configuration with a tail current source (current source biasing) resulted in a lower gain and -3dB frequency, which may be beneficial for achieving more stable operation, but at the cost of reduced amplification and bandwidth.

- The MOSFET current source produced the lowest gain and bandwidth, suggesting that the choice of current source can significantly affect both the frequency response and the amplification characteristics of the differential amplifier.

- This experiment demonstrates the trade-offs between different configurations of MOS differential amplifiers and highlights the importance of balancing gain, bandwidth, and stability in analog circuit design.



  

