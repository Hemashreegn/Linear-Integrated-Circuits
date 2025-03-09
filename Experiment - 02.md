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
| **Load Resistance (Rd)** |  Rd = (Vdd - Vo(cm))/Id               | 3.6kΩ            |
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
  `Vin(min) = 0.95V` , `Vout(max) = 1.00V` and `Vout(p-p) swing = 1.05V`\
  `Vout(min) = 0.655V` , `Vout(max) = 1.535V` and `Vout(p-p) swing = 0.9V`
  
![image](https://github.com/user-attachments/assets/745ed452-305d-4c43-abff-5fdcc857bb04)

- If we calculate gain using Vout and Vin is, Av=Vout/Vin=(1.535-0.655)/(1.05-0.95)=0.88/0.1=8.8V/V\
  `Av=8.8V/V`


 - When **Vin(cm)_min = 0.897** is given as Vin1=1V with amplitude=-103mV and frequency=1kHz and input Vin2=1V with amplitude=-103mV and frequency=1kHz with phi(deg)=180 we obtained maximum swing.

![image](https://github.com/user-attachments/assets/dbc0cefc-2110-4d05-8581-c01f3afa4de3)


 - When **Vin(cm)_max = 1.597** is given as Vin1=1V with amplitude=597mV and frequency=1kHz and input Vin2=1V with amplitude=597mV and frequency=1kHz with phi(deg)=180 we obtained minimum swing.

![image](https://github.com/user-attachments/assets/156ee029-adb0-4f21-bba8-012b6a4b2f2b)


 ### AC ANALYSIS
![image](https://github.com/user-attachments/assets/c3d11d86-02e1-4ff7-a442-e9ce777a1d9f)

- Gain obtained is 19.5dB\
-3dB frequency (19.5db-3dB=16.5dB) is found out to be 4.316GHz.
- **Bandwidth=4.316Ghz**


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
- No changes will be caused by change in resistor load to current source as both MOSFETs balances the values. 

### TRANSIENT ANALYSIS
![IMG_20250303_135129.jpg](https://github.com/user-attachments/assets/205ec111-bf04-4652-8462-0c88cc481ee7)

- Gain obtained using Vout and Vin is, Av=Vout/Vin=(1.535-0.655)/(1.05-0.95)=0.88/0.1=8.8V/V\
  `Av=8.8V/V`

### AC ANALYSIS
![Screenshot 2025-03-09 192041](https://github.com/user-attachments/assets/511910b5-5274-4940-8a64-df70ccc1a8f5)

- Gain obtained is 19.5dB\
- 3dB frequency (19.5db-3dB=16.5dB) is found out to be 4.316GHz.
- **Bandwidth=4.316Ghz** 
- There is no change in gain from circuit 1.
  

### **CIRCUIT - 3 { NMOS TAIL CURRENT SOURCE DIFFERENTIAL AMPLIFIER }** 
![image](https://github.com/user-attachments/assets/ee734e2c-6f2a-43ce-aa77-458c4c4ea927)

  The above figure shows the MOS differential-pair configuration with current source replaced by MOSFET. It consists of two matched transistors, M1 and M2, whose sources are joined together and biased by a 180nm technology MOSFET M3. 

### DC ANALYSIS
  - Connect the circuit.
  - Adjust the length and width of both M1 and M2 transistors to obtain operating point.
  - Run simulation. 

![Screenshot 2025-03-09 195244](https://github.com/user-attachments/assets/3e48bed9-6234-429c-a6da-947fd4df50e3)

- Operating point (1.1V , 0.25mA) is obtained at length=180nm & width=19.3625um for both the MOSFETs M1 & M2
- Length=180nm & width=14.15791um for MOSFET M3 to obtain Q-point.
- Vb is calculated as follows:
  Vgd<=Vth (Condition for M3 to be in saturation region)\
  Vb-Vp<=Vth\
  Vb<=Vth+Vp\
  Vb<=0.497+0.4\
  Vb<=0.897V
  So at `Vb=0.682V`(Vb<0.897) we can obtained the operating point.

 ### TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/ea675250-16d1-4808-9302-735959327848)

- Gain obtained using Vout and Vin is, Av=Vout/Vin=(1.535-0.655)/(1.05-0.95)=0.88/0.1=8.8V/V\
 `Av=8.8V/V`

### AC ANALYSIS
![image](https://github.com/user-attachments/assets/6838bcb6-bc38-4022-bf9c-d4d7897f6e56)

- Gain obtained is 19.5dB\
- 3dB frequency (19.5db-3dB=16.5dB) is found out to be 4.316GHz.
- **Bandwidth=4.316Ghz** 
- There is no change in gain from circuit 1 & 2.

### **CIRCUIT - 4 { ACTIVE LOAD DIFFERENTIAL AMPLIFIER }**

  The above figure shows the MOS differential-pair configuration with current source replaced by NMOSFET. It consists of two matched transistors, M1 and M2, whose sources are joined together and biased by a 180nm technology NMOSFET M3.Also load resistor(Rd) is replaced by a 180nm technology PMOSFET M4 and M5. 

### DC ANALYSIS
  - Connect the circuit.
  - Adjust the length and width of both M1 and M2 transistors to obtain operating point.
  - Run simulation. 

![Screenshot 2025-03-09 210712](https://github.com/user-attachments/assets/f73e5de9-ccd2-47bb-99fd-1e3ce4d266b0)  ![Screenshot 2025-03-09 210731](https://github.com/user-attachments/assets/8fc1cb1a-2082-49e5-b4a8-d9b3934ec7c9)

- Operating point (1.1V , 0.25mA) is obtained at length=180nm & width=19.3625um for both the MOSFETs M1 & M2
- Length=180nm & width=14.15791um for MOSFET M3 to obtain Q-point.
- Vb is calculated as follows:
  Vsg>=Vth (Condition for M3 to be in saturation region)\
  Vs-Vg>=Vth\
  -Vg<=Vth-Vs\
  -Vg<=0.497-2\
  -Vb<=-1.503V\
  Vb<=1.503V\
  So at `Vb=0.59V`(Vb<1.503) we can obtained the operating point.

 ### TRANSIENT ANALYSIS
![image](https://github.com/user-attachments/assets/aa2a0467-5a54-49d9-8217-9552da52baaa)

-We can observe there is more shift in shape of output in this stage.

### AC ANALYSIS
![Screenshot 2025-03-09 222054](https://github.com/user-attachments/assets/5fea6d7b-0dfd-4a30-9a1a-50c4f5baf2dc)

- Gain obtained is 22dB\
- 3dB frequency (22db-3dB=19dB) is found out to be 1.477GHz.
- **Bandwidth=1.477Ghz**
- Gain increases as , **gm** is proportional to **\( I_d \)**  √I_D.

#### Inference 
This table compares the **DC, Transient, and AC Analysis** for different types of Differential Amplifiers.

| **Amplifier Type**                         | **DC Analysis**                                              | **Transient Response**                                       | **AC Gain (\(A_v\))**                                    | **Common-Mode Rejection (CMRR)**                          | **Bandwidth**                                           |
|-------------------------------------------|------------------------------------------------------------|------------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------|
| **Resistive Load Differential Amp**       | High power dissipation, requires precise resistor matching. | Slower response due to large resistor values, higher time constants. | Low gain due to small output resistance (\(R_D\)).       | Poor CMRR since resistor matching is difficult.          | Limited bandwidth due to resistive load.                 |
| **Current Mirror Tail Current Source**    | More stable due to constant current biasing. Requires matched transistors. | Faster than resistive load but still limited by tail current. | Moderate gain, better than resistive load but still limited. | Better CMRR, but affected by mismatch in current mirrors. | Moderate bandwidth, limited by current mirror characteristics. |
| **NMOS Tail Current Source**              | Good bias stability, requires proper NMOS biasing.          | Faster transient response due to lower resistance.          | High gain due to higher output resistance.               | High CMRR as NMOS tail helps reject common-mode signals.  | Higher bandwidth due to NMOS current source.             |
| **Active Load Differential Amp**          | Best biasing stability, least power consumption.            | Fastest transient response due to high output impedance.   | Highest gain due to active load (large \(R_{out}\)).     | Best CMRR as active loads provide high impedance.        | Highest bandwidth due to active load with high impedance. |





  

