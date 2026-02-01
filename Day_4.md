## Day4: Basics of Semiconductor Fabrication and Analog Layout

 **Objective:**
 To understand the fundamentals of semiconductor fabrication, including doping techniques and IC manufacturing steps, and to gain insight into analog layout design flow, process technologies, partial layout implementation, and common layout patterns used in IC design.
## CMOS Structure Overview 
NMOS is fabricated on a p-type silicon substrate with n⁺ source and drain regions.

- A thin gate oxide separates the substrate from the polysilicon gate, which controls channel formation.
- PMOS is fabricated in an n-well with p⁺ source and drain regions.
- The polysilicon gate in PMOS also controls carrier flow through the channel.
- The complementary use of NMOS and PMOS forms the basis of CMOS technology.
<img width="326" height="155" alt="image" src="https://github.com/user-attachments/assets/741da717-a8c1-4211-a1ae-987c35e4d2a4" />

**Key Steps in CMOS Fabrication**

- **Wafer Preparation & Oxidation**: High-purity silicon wafer is used; SiO₂ is grown for insulation and isolation.
- **Photolithography**: Photoresist and masks define device patterns on the wafer.
- **Ion Implantation & Doping**: Dopants create n-type and p-type regions for wells, source, and drain.
- **Deposition & Etching**: Polysilicon and metal layers are deposited and patterned to form devices.
- **Contacts & Metallization**: Contact holes and metal interconnects provide electrical connections.
- **Testing & Packaging**: Functional dies are tested, separated, and packaged.
  ## Analog layout flow chart
  
<img width="434" height="614" alt="image" src="https://github.com/user-attachments/assets/d3a9a3ef-d7b1-4d14-b0cd-512a54a64216" />

## Matching and layout technique
<img width="1271" height="636" alt="image" src="https://github.com/user-attachments/assets/b8992ab5-c368-4fa4-ab82-95a2179c6f68" />

## Fingers and Multipliers

| Aspect | Fingers | Multipliers |
|------|---------|-------------|
| Basic Meaning | Splits a single transistor into multiple gate fingers | Replicates the same transistor multiple times |
| Purpose | Improves layout quality and matching | Scales current and effective device size |
| Effect on Layout | Directly affects physical layout structure | Indirect effect; layout tool decides implementation |
| Gate Resistance | Reduced due to parallel gate fingers | No direct reduction in gate resistance |
| Parasitics | Lower and more controlled parasitics | Parasitics may be higher |
| Matching | Better matching in analog circuits | Limited matching improvement |
| Usage | Preferred in analog and high-speed designs | Commonly used for quick schematic sizing |

## Steps to Use Cadence for Layout Design

**1. Launching Layout**

* Go to **Launch → Layout XL**.
* Select **New** for a fresh layout or **Existing → Automatic** for an existing design.
* Click **OK**, then choose **Generate All from Source** and enable **PR Boundary**.

**2. Block Alignment**

* Right-click near the toolbar area → **Toolbar → Enable Align**.
* Group required blocks and use **Align Top**.
* Go to **Create → Group**, then apply **Align Vertical** for proper spacing.

**3. Running DRC**

* Navigate to **Assura → Technology**.
* Click the three dots and browse to **Install → Foundry → Analog → 45nm_REV**.
* Select **assura_tech.lib** and click **OK**.
* Set technology to **GPDK045_AV**, configure switches, apply changes, and **run DRC**.
* Press **K** to check the layout **scale**.

<img width="1345" height="769" alt="image" src="https://github.com/user-attachments/assets/9c05bc1c-3c73-4bea-b2c5-b68975f16ec7" />
<img width="1344" height="703" alt="image" src="https://github.com/user-attachments/assets/2ce8f426-7bab-4367-88f3-1744c166e0a7" />
<img width="1340" height="744" alt="image" src="https://github.com/user-attachments/assets/a4640754-ee76-44c0-9602-a34164b8326b" />
<img width="1291" height="751" alt="image" src="https://github.com/user-attachments/assets/8681abb8-20a0-46eb-a285-46558ee244f5" />
<img width="1337" height="747" alt="image" src="https://github.com/user-attachments/assets/5e9c1091-01ef-4252-aed4-3928e58f2e23" />

## Conclusion 
 Day 4 focused on semiconductor fabrication and analog layout design, linking device physics with physical IC implementation. CMOS fabrication steps, NMOS/PMOS structures, and isolation techniques such as LOCOS and STI were discussed, with emphasis on the advantages of STI. The session also covered the analog layout flow, including simulations, parasitic extraction, DRC, and LVS, highlighting how proper layout practices impact circuit performance and reliability.


