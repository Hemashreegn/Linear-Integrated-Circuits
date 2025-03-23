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

### COMPARISION 

## Comparison Table for Different L Values

| **Parameter** | **Case 1: L = 180nm** | **Case 2: L = 500nm** | **Case 3: L = 1µm** |
|-------------|----------------|----------------|----------------|-----------|
| **I_ref(Reference Current)** | 0.2778µA | 0.2778µA | 0.2778µA | 
| **I_d(Expected Drain Current)** | 0.2778µA | 0.2778µA | 0.277801µA | 
| **I_d(Obtained Drain Current)** | 0.2778µA | 0.275951µA | 0.274898µA | 
| **(W/L)of M1(Common-source amplifier NMOS transisto)** | 180nm/18.255682um | 180nm/18.255682um | 180nm/18.255682um |
| **(W/L)of M2(Current mirror load PMOS transistor)** | 180nm/50nm | 500nm/50nm | 1um/50nm | 
| **(W/L) of M3(Diode-connected reference transistor)** | 180nm/50nm | 500nm/nm | 1u/50n | 
| **V_out1(Output Voltage across M3)** | 1.1581V | 1.13825V | 0.931431V |
| **V_out2(Output Voltage across M2)** | 1.1581V |   1.06536V  | 1.12669V | 
| **Remarks** | High λ effect,Poor mirroring, low output resistance, lower gain | Improved mirroring, moderate gain | Best mirroring, highest gain, lowest bandwidth |


### TRANSIENT ANALYSIS 










  


        


