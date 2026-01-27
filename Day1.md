## Introduction to MOSFETs and Mixed-Signal IC Architecture – Day-1
**Purpose of the Session**
<p>The primary objective of the session was to revisit the <b>fundamental concepts of MOSFETs</b>, focusing on device equations and operating conditions. Subsequently, an introduction to <b>mixed-signal ICs</b> was provided, highlighting why the integration of analog and digital blocks is essential in contemporary electronic systems. Finally, the session introduced the <b>Cadence tool</b>, marking the transition from theoretical understanding to practical IC design.</p>

## **Why MOSFETs are prefered over the BJTs in the Mixed-Signal ICs**
<p>Although integrated circuits implement digital logic, every <b>transistor operates in the analog domain</b>.
A MOSFET does not abruptly switch ON or OFF; instead, its behavior depends continuously on voltages, currents, and temperature.

<b>MOSFETs are preferred in modern ICs because:</b>

 - They are voltage controlled, simplifying biasing
- Gate insulation results in negligible input current
- They scale efficiently with technology node reduction
- They allow integration of both analog and digital circuits on the same silicon substrate
  
  <b> These characteristics make MOSFETs the backbone of CMOS and mixed-signal IC design</b>.</p>
  ## **MOSFETs structure and Physcial Operation**
  <p>A MOSFET consists of:
- A <b>gate electrode</b> isolated by a thin oxide
- <b>Source and drain regions</b> formed by doping
- A <b>semiconductor substrate</b> (body)
*<b>When a voltage is applied to the gate, it creates an electric field that controls the movement of charge carriers in the channel between the source and drain. This means the current flow in a MOSFET is controlled by voltage. This is different from a BJT, where the current flow is controlled by injecting charge carriers into the device</b>*.</p>
**Regions of MOSFET Operation**
  <table>
    <tr>
      <td>Region of operation</td>
      <td>NMOS</td>
      <td>PMOS</td>
    </tr>
    <tr>
      <td>Cut of region</td>
      <td> VGS​ < VTH​ <br> ID​=0</br> </td>
      <td>VSG ​< ∣VTHp​∣ <br> ID​=0</br> </td>
    </tr>
  <tr> 
    <td>Triode Region</td>
    <td>VGS > VTH <br> VDS < VGS − VTH </br> ID = μn Cox (W/L) [ (VGS − VTH)VDS − (VDS² / 2) ] </td>
    <td>VSG​ > ∣VTHp​∣ <br>VSD​ < VSG​−∣VTHp​∣</br> ID = μp Cox (W/L) [ (VGS − VTH)VDS − (VDS² / 2) ] </td>
  </tr>
      <tr>
        <td>Saturation Region</td>
        <td>VGS > VTH <br> VDS ≥ VGS − VTH </td>br> ID = (1/2) μn Cox (W/L) (VGS − VTH)² (1 + λVDS)</td>
      <td>VSG​>∣VTHp​∣ <br> VSD​≥VSG​−∣VTHp​∣ </br> ID = (1/2) μp Cox (W/L) (VGS − VTH)² (1 + λVDS)</td>
      </tr>
  </table>
      
  **Non-Ideal Effects in MOSFETs**
  1. Channel Length Modulation
  2. Mobility Degradation
  3. Technology Node Impact
  4. Body Effect
     ## Role of BJTs in the Mixed-Signals ICs
     <p>Although MOSFETs dominate ICs, BJTs are still used due to their:
       
        - Predictable exponential current-voltage relationship
        - Well-defined temperature characteristics
BJTs are commonly used in <b>bandgap references (BGR)</b> to exploit their temperature behavior.</p>
## Fundamental Analog Blocks in Every IC
1. Bandgap Reference (BGR)
2. PLL (Phase Lock Loop)
3. LDO (Low Dropout Regulator)
   ## Fundamental Problem Every Mixed Signal Chip Faces:
   - Supply voltage varies with battery, load, temperature
   - Digital blocks inject noise
   - Temperature changes transistor behaviour
   - Process variations shift device parameters
   ## Bandgap Refernce Ciruit (BGR)
   **Block Diagram**

   
   <img width="321" height="226" alt="Image" src="https://github.com/user-attachments/assets/2b973193-6dfb-4367-a0da-2beef9b89c50" />
   
 **Temperature-Independent Reference**
 
- It Provide reference voltages/currents with <b>minimal temperature dependence</b> for analog circuits.
- <b>Key Idea : </b>Combine two quantities with</b>pposite temperature coefficients</b> with proper weighting → <b>resultant has zero or near-zero </b>temperature coefficient</br>.
- <b>Base-emitter voltage of a BJT</b> (V<sub>BE</sub>) decreases with temperature.<br>∂V<sub>BE</sub>/∂T ≈ -1.5 mV/K (negative temperature coefficient).</br>
- <b>PATA</b>: </b>Voltage generated from <b>difference of V<sub>BE</sub> of two BJTs </b> at different current densities.<br>Increases linearly with temperature (positive TC).</br>
- <b>V<sub>REF</sub> = α₁·V<sub>BE</sub> + α₂·(VT·ln(n))</b>
-  Properly choosing α₂·ln(n) cancels the CTAT slope of V<sub>BE</sub> → temperature-independent reference
  
  


     
