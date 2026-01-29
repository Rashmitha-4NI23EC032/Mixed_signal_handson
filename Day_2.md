## BGR Circuit design in Cadence Tool
## Purpose of the session:
<p>The primary objective of today’s session was to develop a technical understanding of analog circuit design methodologies using the Cadence design environment, with a focused study on Bandgap Reference (BGR) circuits. The session covered schematic capture, pre-layout simulation, and performance analysis of analog circuits within Cadence. Emphasis was placed on analyzing different BGR topologies to understand the generation of temperature-independent and supply-insensitive reference voltages through the combination of PTAT and CTAT components. This knowledge forms a fundamental requirement for the design of precision CMOS analog and mixed-signal integrated circuits, where stable biasing and reference generation are critical.</p>

## Circiut design 
<img width="903" height="731" alt="Image" src="https://github.com/user-attachments/assets/749f936e-f9c4-43ff-9b7b-ffd827d7c911" />


**Design Specification**

Circuit Type: CMOS inverter / common-source amplifier
- Design Tool: Cadence Virtuoso
- Technology Node: 45 nm CMOS
- Supply Voltage (VDD): 1 V

 **Transistors Used:**
- 1 × PMOS 
- 1 × NMOS 

 **Input Signal (Vin):**
- Type: Small-signal AC source
- Amplitude: 50 mV
- Frequency: 1 kHz
- Output Node: Vout (common drain connection)
- Analysis Performed: DC, AC (gain), and transient analysis

## DC Analysis
<img width="996" height="813" alt="Image" src="https://github.com/user-attachments/assets/c84f22ca-af7f-4410-ab8c-1d48b7aeb5d8" />

**Short Observation:**

* As the NMOS width (**w2**) increases, the **output voltage (Vout)** increases gradually.
* The input voltage (**Vin**) remains constant, indicating that the change in Vout is due to transistor sizing.
* This shows that NMOS width directly influences the **DC operating point** of the circuit.
## Transient Analysis 
<img width="994" height="794" alt="Image" src="https://github.com/user-attachments/assets/53b0f82f-5550-40e9-a406-7e32715203b3" />

**Short Observation:**

* The input signal (**Vin**) is a sinusoidal waveform applied to the circuit.
* The output voltage (**Vout**) follows the input with **reduced amplitude and phase shift**, indicating amplification and inversion behavior.
* The waveform confirms the **dynamic (transient) response** of the CMOS common-source/inverter configuration.

## AC Analysis 
<img width="1000" height="799" alt="Image" src="https://github.com/user-attachments/assets/ae663b0a-feda-4406-9815-20517bbec529" />

**Short Observation:**

* The AC response shows a **nearly constant gain** at low and mid frequencies.
* At higher frequencies, the **output magnitude decreases**, indicating the presence of a cutoff frequency.
* This behavior confirms the **bandwidth limitation** of the CMOS inverter / common-source amplifier due to parasitic capacitances.

  ## Circuit 3
  <img width="742" height="698" alt="Image" src="https://github.com/user-attachments/assets/472ff161-22ee-497b-9840-309f666b77a1" />
  
  **Design Specifications**

* **Circuit Type:** CMOS inverter / common-source amplifier (biased configuration)
* **Technology Node:** 45 nm CMOS
* **Supply Voltage (VDD):** 1 V
* **PMOS (PM0):**
  * Channel Length: 45 nm
  * Width: w = w2
  * Bias Voltage (Gate): 500 mV
* **NMOS (NM0):**
  * Channel Length: 45 nm
  * Width: 120 nm
* **Input Signal (Vin):**
  * Type: Small-signal AC
  * Amplitude: 50 mV
  * Frequency: 1 kHz
* **Output Node:** Vout
* **Analyses Performed:** DC, AC, and transient analysis

  ## DC Analysis
  <img width="995" height="830" alt="Image" src="https://github.com/user-attachments/assets/d32b38cb-c378-4d7f-bfed-84f85834c939" />

  ## Transient Analysis
  <img width="999" height="836" alt="Image" src="https://github.com/user-attachments/assets/a3542a1b-163d-4ca7-b312-c32bf73d5d69" />

## Ac Analysis
<img width="991" height="813" alt="Image" src="https://github.com/user-attachments/assets/2bb99cba-cc5c-4952-ad73-7323129a9150" />

**Observations from graph**

- The input magnitude (Vin) remains constant at 1 V across all frequencies.
- The output magnitude (Vout) remains almost constant at ~7.5 V in the low-frequency region.
- A flat mid-band region is observed up to approximately 10⁸–10⁹ Hz.
- Beyond this frequency, the output magnitude drops sharply, indicating gain reduction.
- At very high frequencies (>10¹⁰ Hz), the output magnitude approaches near zero.
- The response clearly shows a single-pole roll-off characteristic.
- Av=-gm3(ro3||ro4)

## Comparision table 

| Feature / Observation           | Circuit 4                                      | Circuit 3                                   |
|---------------------------------|-----------------------------------------------|-----------------------------------------------|
| Input Voltage (Vin)             | Constant DC (~0.6 V) or small sinusoidal (~100 mV p-p) | Constant DC (~0.6 V)                          |
| Output Voltage (Vout)           | Increases with PMOS width, non-linear rise   | Increases with PMOS width, non-linear rise   |
| Phase Relationship              | 180° out of phase with Vin                    | 180° out of phase with Vin (inverting)       |
| Output Waveform                 | Smooth, continuous, no clipping   | Smooth, continuous, no clipping   |
| DC Operating Point               | ~550–600 mV                                  | ~540 mV                                      |
| Amplitude                        | Large swing (880–900 mV max, 220–250 mV min)| Reduced compared to input                     |
| Gain (Av)                        |      -gm3(ro3||ro4)                                     |             -gm1 / gm2                       |
| Key Behavior                     | Inverting, smooth sinusoidal amplification  | Inverting amplifier, limited small-signal gain |


## Circuit 5 : Differential Amplifier 
**Diagram Design**
<img width="902" height="710" alt="Image" src="https://github.com/user-attachments/assets/35cbdaa9-8fe4-4966-bba3-ff46faaf0ef2" />


**Technical Specification (Very Short)**

* **Circuit**: CMOS differential amplifier
* **Technology**: 45 nm CMOS
* **VDD**: 1.0 V
* **Input**: Differential, 250 mV, 1 kHz
* **Output**: Single-ended
* **NMOS**: W/L = 120 nm / 45 nm
* **PMOS**: W/L = 45 nm / 45 nm
* **Bias (Vb)**: ~0.6V
* **Gain**: 20–40 dB
## Transient Analysis


**Observation**
<img width="992" height="790" alt="Image" src="https://github.com/user-attachments/assets/798d02f7-965e-4866-96fa-5c9074ebedfb" />

* `Vinp` and `Vinn` are sinusoidal, equal amplitude, and 180° out of phase.
* Output (`Vout1`) is a clean amplified sinusoid.
* Output is phase-shifted relative to inputs, confirming differential operation.
* No visible clipping → transistors operate in saturation.
* Stable response at 1 kHz, indicating proper biasing and linear operation.
## AC Analysis
<img width="995" height="810" alt="Image" src="https://github.com/user-attachments/assets/fdc6b419-9e67-4927-ab53-6fb5626d0f9d" />

**Observation**

* Low-frequency gain ≈ **13–14 V/V** (~22–23 dB).
* Flat midband response indicates stable biasing.
* −3 dB bandwidth in the **GHz range**.
* Single-pole roll-off observed at high frequency.
* Suitable for low-frequency / moderate-bandwidth analog applications.
## Steps to creating the Symbol 
1. **Create Cell View and Schematic**
 - Go to Create → Cell View, open a new schematic, and design the required circuit.
 - Remove all the power supply sources from the schematic.
2. **Creating Pins**
- Click Create Pin or press B.
- In the pop-up window, enter the pin name, select the direction (input/output/ground), set Usage as Schematic, and Signal Type as Signal.
- For VDD, select Signal Type as Power; for VSS, select Ground; for VOUT, set Direction as Output and Signal Type as Signal.
3. **Generating Symbol View**
- Go to Create → Cell View → Run Cell View.
- Ensure the library name and cell name match the schematic and click OK.
- Assign pins to left, right, top, and bottom as required.
4. **Modify Symbol Shape**
- Use the Create Polygon option to change the shape of the pins or symbol if needed.
5. **Test the Symbol**
Open a new schematic cell view, add the created symbol, connect power supplies, and run simulations such as DC, Transient, and AC analysis.

## Pin diagram 

<img width="895" height="726" alt="Image" src="https://github.com/user-attachments/assets/e0ebd5e6-50f0-416d-bec8-ea7aee12cb06" />
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/894e5c18-c735-476e-8153-33dcb0f93191" />
<img width="898" height="723" alt="Image" src="https://github.com/user-attachments/assets/1f0afdbd-41bc-4c85-ba29-44cd5e800b7c" />
## Transient Analysis
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/a8476ccd-f25f-404c-a08a-2be950bc82e8" />
## AC Analysis
<img width="1600" height="900" alt="Image" src="https://github.com/user-attachments/assets/9c74c4d2-d41f-440b-94be-1ac3b94ed9c3" />


**Observation**

* The frequency sweep spans from **0.1 Hz to 10¹¹ Hz**.
* Both input signals maintain a constant magnitude of approximately **1 V** throughout the sweep.
* At low frequencies, the output voltage magnitude is around **13–14 V**.
* The amplifier exhibits a **mid-band gain of about 13–14 V/V**.
* Gain remains nearly constant up to the **hundreds of MHz range (≈10⁸–10⁹ Hz)**.
* A noticeable gain reduction begins beyond **~10⁹ Hz** due to high-frequency effects.
* At higher frequencies, the output magnitude drops sharply, indicating bandwidth limitation.

## Conclusion 
The Day 2 session significantly strengthened practical knowledge of CMOS analog circuit design using the Cadence environment through hands-on design and simulation. DC analysis was used to ensure correct biasing and proper operating regions of the devices, while transient analysis confirmed stable time-domain performance, including correct phase behavior and signal amplification. AC analysis offered a clear understanding of gain characteristics, bandwidth, and high-frequency roll-off caused by parasitic effects. The differential amplifier implementation validated effective differential operation with stable and reliable gain. In addition, developing and validating custom schematic symbols enhanced design efficiency and workflow proficiency. Overall, the session provided a solid foundation for designing advanced analog blocks, particularly Bandgap Reference (BGR) circuits and mixed-signal integrated systems.










