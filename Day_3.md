## Day-3: Exploring Cadence Calculator and BGR Circuit Analysis
The objective of Day-3 was to explore and understand the Calculator features in the Cadence tool for extracting and evaluating circuit parameters, and to design a Bandgap Reference (BGR) circuit. The day also focused on performing DC analysis, calculating the PTAT and CTAT slopes, and verifying the temperature-independent reference voltage behavior of the BGR circuit.


### Steps to Use Calculator and Do Measurements in Cadence

* Open **Virtuoso** and load the schematic and testbench
* Run the required **analysis** in ADE
* Go to **Tools → Calculator**
* Select the required **function** (voltage/current/expression)
* Pick the **node or device** from the schematic
* Click **Evaluate / Plot** to obtain results
* Calculate **PTAT and CTAT slopes (ΔV/ΔT)** using temperature sweep results
## Differential Circuit its Analysis
# Circuit Diagram 
<img width="895" height="726" alt="image" src="https://github.com/user-attachments/assets/196563dc-c607-4ee5-8d80-7ce6f7014c36" />

 **Analysis using cadence tool calculator**

<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/0c7c1c84-8b3d-4107-963d-c30c70a35b11" />
**Short Observation (from Transient & Spectrum plots):**
* Measured performance parameters:

  * **SNDR ≈ 13.18 dB**
  * **SNR ≈ 23.80 dB**
  * **SFDR ≈ 13.96 dBc**
  * **ENOB ≈ 1.9 bits**
## Calculation of PTAT and CTAT using cadence tool 
Steps in Cadence:
- Open the Calculator from Tools → Calculator and select Wave mode.
- From the waveform plot window, choose Vout1 and Vout2, then apply the Subtract operation to generate the required expression.
- Navigate to the ADE (ADEL) window, select Outputs → Setup, click Get Expression, assign a suitable name such as CTAT or PTAT, and click Add.
- Return to the Calculator, set the Function Panel to All, choose Derivative, and click Evaluate to obtain the slope of the waveform.
## Circuit Diagram and its Analysis
<img width="1009" height="835" alt="image" src="https://github.com/user-attachments/assets/e137767c-3f51-4363-8ba7-3c1a3a63dc5c" />

 **DC Analysis**
<img width="940" height="797" alt="image" src="https://github.com/user-attachments/assets/aacdace4-8837-4e0a-ad12-b85647aeca1d" />

- CTAT ( Complementary to Absolute Temperature) = VBE = Negative TC.
- PTAT (Proportional to Absolute Temperature ) = ∂VBE = Positive TC.
- ∂VBE = VBE1 - VBE2 = Vo1 - Vo2
<img width="1195" height="644" alt="image" src="https://github.com/user-attachments/assets/07c62981-5c34-418d-aa92-12f289a2582a" />
<img width="1600" height="900" alt="image" src="https://github.com/user-attachments/assets/3ee57ba4-bf99-4043-9808-b10359cfe5a7" />

## BGR Circuit 
<img width="659" height="602" alt="image" src="https://github.com/user-attachments/assets/b916fc46-0435-44c2-9178-8e8a03daeb1f" />
<img width="1001" height="819" alt="image" src="https://github.com/user-attachments/assets/b2cdbf75-c47f-4048-a8c2-a6c539fc7cc2" />
<img width="995" height="837" alt="image" src="https://github.com/user-attachments/assets/6246ac70-6d20-423c-8d5e-c4fb20f74a87" />

- A basic BJT-based temperature-independent bandgap reference (BGR), also called a first-order/classic BGR, is considered.
- The reference voltage is given by Vref = VBE2 + VT * ln(n) *c
- Let R1=R2 = 10kohm
- For zero temperature coefficient (zero TC), the condition is ln(n) *(1+R2/R3)= 17.2.
taking n= 10, R2=10kohm, then R3 = 1.545kohm.
- Thus, the resistor values are designed for a temperature-independent BGR.
- Differentiating Vref with respect to temperature gives ∂Vref/ ∂T = d(CTAT)/dT + d(PTAT)/dT∂Vref/ ∂T.
- Using the Cadence calculator, the derivatives are obtained as:
- Using the Cadence calculator, the derivatives are obtained as: deriv(CTAT)= -1.7110^-3 v/celcius and deriv(PTAT)= 202.210^-6 v/celcius.
- Proper scaling of the PTAT term compensates the CTAT behavior, resulting in a zero-TC reference voltage.
<img width="992" height="826" alt="image" src="https://github.com/user-attachments/assets/06f8728f-e5ee-43c3-9359-9cbf2a73484d" />

- for R3 = 1.545Kohm , R2=10Kohm we got deriv(vref)= -1.9906 *10^-4.
- so we need to design more accurate one by varying (1+R2/R3).
- so to make deriv(vref) = 0, 0 = deriv(CTAT) + deriv(PTAT) (1+R2/R3)
- 0= -1.7110^-3 + 202.2*10^-6 * (1+R2/R3)
- (1+R2/R3) = 8.4569
- So R2 =10Kohm and R3= 1.34102 k ohm
- Now we get, deriv(vref)=-19.66 uV/celcius

  
## Conclusion 


 The Day 3 session focused on practical use of the Cadence Calculator and spectrum analysis for analog IC evaluation. Key dynamic parameters such as SNR, SFDR, SINAD, and ENOB were extracted to study the impact of non-idealities. CTAT and PTAT expressions and their temperature slopes were calculated and verified through simulation. BGR analysis showed that proper PTAT–CTAT scaling and resistor ratio optimization are essential to achieve near zero temperature coefficient.

