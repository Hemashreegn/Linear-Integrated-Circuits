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


#### 1:1 CURRENT MIRROR
![dc_1](https://github.com/user-attachments/assets/af6f0faf-06fd-4dbd-b556-b407191ca364)
 




  


        


