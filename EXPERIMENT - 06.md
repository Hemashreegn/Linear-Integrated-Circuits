# LINEAR INTEGRATED CIRCUITS

## EXPERIMENT - 06 {CURRENT MIRROR CIRCUIT}

### OBJECTIVE
  To design and analyze a current mirror circuit as an active load in a common-source amplifier. The experiment aims to study the effect of channel length (L) variations on the current mirror accuracy, output resistance, and voltage gain using LTspice simulations.

### DESIGN PARAMETERS
 A) Design and analyze current mirror circuit as active load in common source amplifier circuit.

 ![Screenshot 2025-03-23 223630](https://github.com/user-attachments/assets/b47c2297-334c-4920-9d6d-6c4f73bea3f4)

  - **Gain(Av)** > -10V/V
  - **Power supply(Vdd)** = 1.8V
  - **Power(P)** <= 1mW

### CIRCUIT & CALCULATION
 - PMOS current mirror (M2, M3) as an active load.
 - NMOS common-source amplifier (M1).
 - Golden reference current source (I_ref) for biasing.
 - Vin design (of NMOS),\
    - Condition 1 : Vin >= Vth\
      Vgs > 0.4V\
      Vg - Vs >= 0.4V\
      `Vg >= 0.4V`
    - Condition 2 : Vgd <= Vth\
      Vg - Vd <= Vth\
      Vg <= Vth + Vd\
      Vg <= 0.4 + 1.15V\
      `Vg <= 1.55V`
      Therefore Vg lies between 0.4V < Vg < 1.55V.\
      Vg selected as 0.6 to obtain the req output parameters.

![Current_mirror](https://github.com/user-attachments/assets/4fdb0a0a-4930-428f-bfa9-f101cf96256e)

#### DESIGN FOR 1:1 CURRENT MIRROR RATIO

| Current Name | Symbol   | Value     | Description                          |
|-------------|---------|-----------|--------------------------------------|
| Total Current | I_total = I_ref + Id | 0.5556mA  | Total circuit current               |
| Reference Current | I_ref =  I_total/2    | 0.2778mA   | Reference current for the mirror    |
| Drain Current | Id = I_total/2    | 0.2778mA   | Drain current of M1 and M2                |

#### DESIGN FOR 1:2 CURRENT MIRROR RATIO

| Current Name | Symbol   | Value     | Description                          |
|-------------|---------|-----------|--------------------------------------|
| Total Current |  I_total = I_ref + Id  | 0.5556mA  | Total circuit current               |
| Reference Current | I_ref =  I_total/2   | 0.185185mA   | Reference current for the mirror    |
| Drain Current | Id = I_total/2    | 0.37037mA   | Drain current of M1 and M2                |

### DC ANALYSIS
- Make the circuit as per the designed specifications.
- Give the length and width for the MOSFETS M1, M2, M3.
- Go to the simulation ->operating point ->place the .op extension.
- Run the simulation.
- You will find all the voltages and current flowing in the circuit, adjust the width untill obtaining the required operating point.
- Compare the obtained result with the designed values and ensure if the values match for the given length and width of the MOSFET.
 
### 1:1 CURRENT MIRROR
 The current present in M2 transistor will be same as M3 transistor with same (W/L) ratio for both MOSFETs and (W/L) ratio will be different for M1 transistor to obtain the required current.
 
![image](https://github.com/user-attachments/assets/b7a6af4b-f1b3-4641-9608-adaac89313f8)

![dc_2](https://github.com/user-attachments/assets/c98c969f-7eb6-4dac-a082-3ff067a917fc)

- Operating point **(1.1585V , 0.22778mA)** is obtained at **length=180nm and width=50um** for MOSFET **M2 & M3** and **length=180nm and width=18.255682um** for MOSFET **M1**.
- I_ref & Id obtained are same as theoretical values.

### 1:2 CURRENT MIRROR
 The current present in M3 transistor will be doble the current in M2 transistor with 1:2 (W/L) ratio for the MOSFETs and (W/L) ratio will be different for M1 transistor to obtain the required current.
 
![2_1_dc1](https://github.com/user-attachments/assets/1b665334-51c0-44ea-a076-24a855b11e7b)

![2_1_dc2](https://github.com/user-attachments/assets/a979bd1c-183f-4f56-a11a-d767d7441f7e)

- The **1:2** ratio current is obtained at **length=180nm and width=50um** for MOSFET **M3**, **length=180nm and width=100um** for MOSFET **M2** and **length=180nm and width=24.3142um** for MOSFET **M1**.
- Id is twice of I_ref, currents are obtained same as expected values.

### WHAT IF LENGTH IS CHANGED?

 - If length is increased from 180nm to 500nm for M2 & M3 then we can observe slight variation in current and output voltage.
  ![length_500n](https://github.com/user-attachments/assets/61e9e9d9-3a89-4827-a0b9-ae6697f66ca7)

 - If length is increased from 500nm to 1um for M2 & M3 then we can observe slight variation in current and output voltage.
  ![Length_1u](https://github.com/user-attachments/assets/ecfee0ad-8ad4-4fb2-a84f-3fd611aad7a2)

### TRANSIENT ANALYSIS 
 - After getting the required operating points from the DC Analysis, right click on the input voltages ->advanced ->sinusoidal and give the specified DC voltage, amplitude and frequency.
 - Go the transient analysis part and give the required stop time as 3ms.
 - Run the simulation.
 - Calculate Vout/Vin./

#### For LENGTH = 180nm

 ![transient_1](https://github.com/user-attachments/assets/fa2230d7-9be2-4b62-8b32-b7f9419a8908)

 - For length = 180nm ,width = 50um for M2 & M3 and length = 180nm, width = 18.255682um for M2 the input and output voltage is as above.
 - We can calculate gain as, Vout/Vin = (1.4 - 0.9)/(0.61 - 0.59) = 25V/V
 - `Av = 25 V/V`
 - `Av(dB) = 20log(25) = 27.958 dB`

#### For LENGTH = 500nm

 ![image](https://github.com/user-attachments/assets/3ef47447-5c7d-4534-a501-2e2e7203e969)

 - For length = 500nm ,width = 50um for M2 & M3 and length = 180nm, width = 18.255682um for M2 the input and output voltage is as above.
 - We can calculate gain as, Vout/Vin = (1.435 - 0.818)/(0.61 - 0.59) = 25V/V
 - `Av = 25 V/V`
 - `Av(dB) = 20log(25) = 27.958 dB`

#### For LENGTH = 1um

![image](https://github.com/user-attachments/assets/6fbca038-c026-4aed-9e77-758d6fea120d)

 - For length = 1um ,width = 50um for M2 & M3 and length = 180nm, width = 18.255682um for M2 the input and output voltage is as above.
 - We can calculate gain as, Vout/Vin = (1.435 - 0.784)/(0.61 - 0.59) = 30.85V/V
 - `Av = 30.85 V/V`
 - `Av(dB) = 20log(30.85) = 29.785 dB`

### AC ANALYSIS
 - Right click on the voltage ->Advanced, give AC amplitude as 1.
 - Go to the AC analysis part and run the simulation.
 - The frequency response will appear and calculate 3dB bandwidth.

#### For LENGTH = 180nm

 ![gain_180nm](https://github.com/user-attachments/assets/d4d07824-71f7-4baa-8e0c-17b047eb79c1)
 - Gain obtained is 28.032dB
 - 3dB frequency (28.032db-3dB=25.032dB) is found out to be 308.87MHz./
  `Bandwidth = 308.87MHz`

#### For LENGTH = 500nm

 ![gain_500nm](https://github.com/user-attachments/assets/d754f6a0-f8ea-4964-a0ac-4e10b87c3d26)
 - Gain obtained is 30.062dB
 - 3dB frequency (30.062-3dB=27.062dB) is found out to be 214.17MHz./
  `Bandwidth = 214.17MHz`

#### For LENGTH = 1um

 ![gain_1u](https://github.com/user-attachments/assets/beced9c2-a377-453f-9769-83ed6acd998a)
 - Gain obtained is 30.834dB
 - 3dB frequency (30.834-3dB=27.834dB) is found out to be 190.807MHz./
  `Bandwidth = 190.807MHz`
  
#### COMPARISION TABLE

## Comparison Table for Different L Values

| **Parameter**                                  | **Case 1: L = 180nm** | **Case 2: L = 500nm** | **Case 3: L = 1µm** |
|-----------------------------------------------|----------------------|----------------------|----------------------|
| **I_ref (Reference Current)**                 | 0.2778µA             | 0.2778µA             | 0.2778µA             |
| **I_d (Expected Drain Current)**              | 0.2778µA             | 0.2778µA             | 0.277801µA           |
| **I_d (Obtained Drain Current)**              | 0.2778µA             | 0.275951µA           | 0.274898µA           |
| **(W/L) of M1 (Common-source amplifier NMOS)**| 180nm / 18.255682µm  | 180nm / 18.255682µm  | 180nm / 18.255682µm  |
| **(W/L) of M2 (Current mirror load PMOS)**    | 180nm / 50nm         | 500nm / 50nm         | 1µm / 50nm           |
| **(W/L) of M3 (Diode-connected reference PMOS)** | 180nm / 50nm      | 500nm / 50nm         | 1µm / 50nm           |
| **V_out1 (Output Voltage across M3)**         | 1.1581V              | 1.13825V             | 0.931431V            |
| **V_out2 (Output Voltage across M2)**         | 1.1581V              | 1.06536V             | 1.12669V             |
| **Gain (Av) in dB**                           | 28.032dB             | 30.062dB             | 30.834dB             |
| **Bandwidth**                                 | 308.87MHz            | 214.17MHz            | 190.807MHz           |
| **Remarks**                                   | High λ effect, poor mirroring, low output resistance, lower gain | Improved mirroring, moderate gain | Best mirroring, highest gain, lowest bandwidth |


### HOW CURRENT MIRRORS FOR DIFFERENT RATIOS

#### 1:3 

![image](https://github.com/user-attachments/assets/ab9ae78e-e500-425c-82e6-08623488d04e)
Obtained the exact mirroring at L=180nm, W=50um for M3, L=180nm, W=150um for M2 & L=180nm, W=55.7455um for M1.

#### 1:4

![image](https://github.com/user-attachments/assets/1d40786e-3ae3-493b-8693-5fbd576918cb)
Obtained the exact mirroring at L=180nm, W=50um for M3, L=180nm, W=200um for M2 & L=180nm, W=74.63um for M1.

#### 1:5 

![Screenshot 2025-03-24 110143](https://github.com/user-attachments/assets/cf3313c3-647a-4875-b1b3-b38f4057819f)
Obtained the exact mirroring at L=180nm, W=50um for M3, L=180nm, W=200um for M2 & L=180nm, W=93.232um for M1.

#### 2:1

![image](https://github.com/user-attachments/assets/f65162bb-7e39-459b-a91e-200117f0b9be)
Obtained the exact mirroring at L=180nm, W=100um for M3, L=180nm, W=50um for M2 & L=180nm, W=18.1952um for M1.

### DESIGN PARAMETERS
 B) Design differential amplifier using same design specifications as exp-3 for current mirror circuit.Perform DC, Transient and AC analysis of differential amplifier with the following specifications using LT Spice.
  
  ![image](https://github.com/user-attachments/assets/d7efe9e9-a191-44fa-ac67-a03d50921342)

 - **Vdd** = 2V
 - **Vin** = 1V
 - **Power budget** = 1mW
 - **Vo,cm** = 1.1V
 - **Vp** = 0.4V

### CIRCUIT & CALCULATION

 ![Screenshot 2025-03-24 093047](https://github.com/user-attachments/assets/fb5d5d4b-bf91-4261-bed3-4cc1ef931429)

 - Tail Current (Iss),\
   Iss = P/Vdd\
   `Iss = 0.5mA`

 - Drain Current (Id),{current across MOSFETs M1, M2, M5, M6}\
   Id = Iss/2\
   `Id = 0.25mA`

 - Reference current(I_ref),\
   I_ref = Iss\
   `I_ref = 0.5mA`


   
  










  


        


