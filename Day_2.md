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

