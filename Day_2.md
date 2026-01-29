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


**Short Observation:**

* The AC response shows a **nearly constant gain** at low and mid frequencies.
* At higher frequencies, the **output magnitude decreases**, indicating the presence of a cutoff frequency.
* This behavior confirms the **bandwidth limitation** of the CMOS inverter / common-source amplifier due to parasitic capacitances.




