# DESIGN & ANALYSIS OF DIFFERENTIAL FOLDED CASCODE OTA FOR LOW-POWER BIOMEDICAL SIGNAL AMPLIFICATION

## ABSTRACT
  This repository presents the design of a low-power, high-gain Operational Transconductance Amplifier (OTA) for biomedical devices.The OTA is designed using a folded cascode topology in order to have the desired gain with minimal power 
consumption. The sizes of transistors and bias voltages are computed for a 0.18um technology node to have a gain of more than 70dB with a supply voltage of 1.8V. The design considerations involved in obtaining the 
desired performance such as stability and output swing are discussed. 

**Keywords** — OTA, biomedical, low-power, high-gain, folded cascode, amplifier design.

## I. INTRODUCTION

This paper presents the design and analysis of a differential folded cascode Operational Transconductance Amplifier (OTA) tailored for low-power biomedical signal amplification. Operational Transconductance 
Amplifiers (OTAs) play important roles in high-performance analog circuits, requiring high DC gain as well as unity gain bandwidth. Deep sub-micron technologies have challenges of high DC gain with reduced 
transistor intrinsic gain. In this paper, the issue is tackled for biomedical signal amplification. The folded cascode OTA topology is used and benefits from high gain and appropriate output swing behavior 
in low-voltage CMOS processes.

This is implemented in a 0.18um CMOS technology. This technology node is a good balance of transistor performance, power dissipation, and cost, which makes it apt for biomedical applications. In particular, 
0.18um CMOS provides the capability to fabricate transistors with adequate speed and gain to amplify biomedical signals, and also allows the integration of other circuitry required on the same die. In addition, 
the comparatively low leakage currents in this technology help in achieving the overall low-power consumption of the OTA, which is important in extending the battery life of portable medical devices.

## II. REAL-TIME BIOMEDICAL APPLICATIONS OF OTAS

Operational Transconductance Amplifiers (OTAs) are vital building blocks in a vast range of biomedical devices, with a central role to play in the acquisition and processing of critical physiological signals. 
Such signals, which tend to have very small amplitudes and are naturally prone to noise contamination, require cautious amplification and filtering to recover useful information for reliable diagnosis and 
effective monitoring.

- **Real-time ECG Monitoring**: Continuous tracking of heart activity, enables long-term monitoring via wearable devices. Also supports heart rate variability analysis, arrhythmia detection, and ST-segment monitoring.
- **Continuous EEG Monitoring**: Applications in epilepsy management and sleep studies and also facilitates detection of abnormal brain activity.
- **Wearable EMG Sensors**: Real-time monitoring of muscle activity, applications in rehabilitation, prosthetics control, and sports performance.
- **Intraoperative Monitoring**: Monitoring of patient's physiological signals during surgery.
- **Closed-Loop Drug Delivery Systems**: Amplification of signals from biosensors, enables real-time adjustment of drug delivery.
- **Fetal Monitoring**: Monitors fetal heart rate and other vital signs in real-time.

## III. DIFFERENTIAL FOLDED CASCODE OTA

An OTA (Operational Transconductance Amplifier) converts an input differential voltage into an output current. The folded cascode topology improves gain, input common-mode range, and output swing—particularly 
valuable in modern low-voltage CMOS technologies.

### A. Features

- **High Gain**: Uses cascoding to boost output impedance and hence gain.
- **Wide Input Range**: Differential input supports common-mode signal rejection.
- **Wide Output Swing**: Achieved due to folded structure.
- **Low Voltage Operation**: Works efficiently with sub-1V supplies.
- **Low Power**: Can be optimized for sub-µW operation in biomedical applications.

### B. Circuit Diagram

![Screenshot 2025-05-01 152713](https://github.com/user-attachments/assets/69745c58-8d23-4053-b6db-31686960ef2c)


### C. Functions of Transistors

1. **M1, M2 – Differential Input Pair (NMOS)**
   - Sets the differential input voltage Vin+ and Vin−.
   - The difference between these input voltages determines how current from the tail current source (M11) splits between M1 and M2.
   - These transistors convert the voltage difference into a differential current.

2. **M3, M4 – Current Mirror Loads (PMOS)**
   - Mirrors the current from one branch to another within each other.
   - Helps maintain balanced operation between differential outputs.
   - Allows signal conversion from current domain to voltage domain across load impedance.

3. **M5, M6 – Folded Cascode Transistors (PMOS)**
   - The current from the input stage and current mirrors is then directed (or "folded") into the upper branches of the circuit.
   - Provide high impedance node.
   - Biased via Vbias1.

4. **M7, M8 – Cascode Devices (NMOS)**
   - Cascoding significantly increases output resistance.
   - Leads to higher voltage gain.
   - Provide isolation between outputs and input current sources.
   - Biased using Vbias2.

5. **M9, M10 – Current Sinks / Loads (NMOS)**
   - Act as biasing loads.
   - Ensures that output signal is centered.
   - Biased using Vbias3.

6. **M11 – Tail Current Source (NMOS)**
   - Provides constant bias current to M1 and M2.
   - Sets amplifier current level.
   - Biased with Vbias3.

## D. Design Calculations

- Cox = εox/tox = 8.42×10⁻³ F/m²  
- kn′ = μnCox = 2.31×10⁻⁴ A/V²  
- kp′ = μpCox = 9.74×10⁻⁵ A/V²  
- Let Vov = 0.15V, VDD = 1.8V, Tail current = 40µA, L = 180nm, Vth = 0.465V
  Using the below formula find ID, \
    `*W = (2 × ID) / (kn × Vov²) × L*`

| Transistor | Type  | ID (µA) | L (nm) | W (µm) |
|------------|-------|---------|--------|--------|
| M11        | NMOS  | 40      | 180    | 2.77   |
| M1–M2      | NMOS  | 20      | 180    | 1.38   |
| M7–M10     | NMOS  | 20      | 180    | 1.38   |
| M3–M6      | PMOS  | 20      | 180    | 3.29   |

### 2. Voltage Biasing

Let Vth = 0.465V, Vov = 0.15V 
 Using the below formula find Vgs,\
      `Vgs = Vth + Vov`

| Transistor | Type   | Vgs/Vsg (V) |
|------------|--------|--------------|
| M11        | NMOS   | 0.7          |
| M1–M2      | NMOS   | 0.8          |
| M3–M4      | PMOS   | 0.9          |
| M5–M6      | PMOS   | 0.8          |
| M7–M8      | NMOS   | 1.3          |
| M9–M10     | NMOS   | 0.7          |

## IV. ANALYSIS OF DESIGNED OTA

### 1. DC Analysis

- ID of all transistors ≈ 20μA, tail current = 40μA
- Vout ≈ 0.9V (expected and achieved)

![Screenshot 2025-05-10 204845](https://github.com/user-attachments/assets/8b88b5bc-58bd-417b-a8c1-8a3776a0e080)

### 2. Transient Analysis

- Input: Sinusoidal
- Differential output observed as expected

![Screenshot 2025-05-10 134001](https://github.com/user-attachments/assets/cdc7fe14-7baa-4b92-8a83-6f6c25e49351)

### 3. AC Analysis

- Gain > 70dB
- Actual gain: *77.2dB* (negative sign indicates phase inversion)

![Screenshot 2025-05-10 200807](https://github.com/user-attachments/assets/8492e088-4d76-4241-8af0-c71ee8bb5c3d)


## V. COMPARISON OF OTA

| Parameter             | Your Designed OTA               |
|-----------------------|----------------------------------|
| Technology Node       | 180 nm                          |
| VDD                   | 1.8 V                           |
| Tail Current          | 40 μA                           |
| Input Pair Type       | NMOS                            |
| (W/L) M1, M2          | 7.69                            |
| Gain (Target)         | >70 dB                          |
| Vov                   | 0.15 V                          |
| gm (M1, M2)           | ≈ 0.267 mS                      |
| Transconductance Gain | Moderate                        |
| Common-mode Range     | ~0.15 V to ~1.65 V (est.)       |
| Power Consumption     | ≈72 μW                          |
| Load Type             | PMOS Active Load                |
| Mirror Type           | NMOS Mirrors (M7–M10)           |
| Gain Boosting         | Not used                        |
| Design Style          | Hand-calculated, low Vov design |

## VI. CONCLUSION

The design of a fully differential folded cascode Operational Transconductance Amplifier (OTA) targeting low-power biomedical applications has been successfully completed using 0.18 µm CMOS technology. 
Operating at a 1.8 V supply, the OTA achieves the expected performance metrics—specifically, a high DC gain of over 70 dB, adequate bandwidth, and low power consumption—making it highly suitable for biosignal
processing tasks such as ECG or EEG amplification. The results validate the effectiveness of the folded cascode topology for achieving high gain with minimal power in low-voltage environments. Given its 
performance and power efficiency, the designed OTA proves to be a promising solution for energy-constrained biomedical systems, confirming its practical applicability in real-world implantable or portable
healthcare devices.

## REFERENCES

1. B. Razavi, Design of Analog CMOS Integrated Circuits, McGraw-Hill Education, 2001  
2. P. E. Allen and D. R. Holberg, CMOS Analog Circuit Design, 3rd ed., Oxford University Press, 2012  
3. N. Verma and A. P. Chandrakasan, “An ultra low energy 12-bit rate-resolution scalable SAR ADC for wireless sensor nodes,” IEEE J. Solid-State Circuits, vol. 42, no. 6, pp. 1196–1205, Jun. 2007  
4. W. M. C. Sansen, Analog Design Essentials, Springer, 2006  
5. S. Mohammadi and A. Payandeh, “A low-voltage low-power OTA for biomedical applications,” Int. J. Electron. Electr. Eng., vol. 2, no. 2, pp. 123–127, 2014  
6. M. S. Jahan and M. S. Islam, “Design of a low power OTA for ECG signal acquisition system,” in Proc. IEEE Int. Conf. Electr. Eng. Inf. Commun. Technol. (ICEEICT), Dhaka, Bangladesh, 2015  
7. R. Schreier and G. C. Temes, Understanding Delta-Sigma Data Converters, Wiley-IEEE Press, 2004
