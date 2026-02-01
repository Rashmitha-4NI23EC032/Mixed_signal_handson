## Day5: Placement, FloorPlanning, Routing in Analog Layout Design


 **Objective:**
 To understand and implement proper analog layout practices including floorplanning, placement, guard ring insertion, routing, and DRC verification, using efficient tool shortcuts, in order to minimize parasitics, ensure substrate isolation, and achieve a fabrication-ready and reliable IC layout.

Here’s the **same content rewritten in clear, concise language**, suitable for a lab report or documentation:


## Placement

During placement, circuit blocks and device instances were organized systematically within the layout area while ensuring symmetry, proper alignment, and adherence to design rules. Careful placement helped reduce routing complexity and minimize parasitic effects. To prevent substrate noise and reverse current flow, guard rings were incorporated at this stage. Guard rings provide electrical isolation for sensitive devices, improving overall circuit robustness and reliability.

**Steps to Apply Guard Rings**

* Select all blocks → press **Q** → choose **Instances only** → click **OK**
* Navigate to **Create → MPP Guard Ring**
* Apply **P-TAP** for p-substrate regions
* Apply **N-TAP** for n-substrate regions
* Hide unnecessary layers or views after placement for better clarity

## Shortcuts Used

Hierarchical navigation and editing were efficiently performed using shortcut keys:

* **X** – Descend hierarchy in place
* **Shift + X** – Descend with view change
* **Shift + B** – Move up one hierarchy level
* **Shift + C** – Ascend to top level
* **A → F3** – Align selected blocks as per user-defined space
* **F4** – Partial selection
* **R** – Draw rectangle
* **F3** – Copy layout
* **E** – Open display options

## Floor Planning

Floor planning defined the overall layout structure prior to routing. Functional blocks were arranged to minimize interconnect lengths and enhance signal integrity. Partial and rectangular selection techniques were used for efficient region handling, and display settings were adjusted to improve layout visibility and ease of editing.

## Routing

Routing established electrical connections between placed components using appropriate metal layers. Attention was given to:

* Minimizing routing congestion
* Maintaining spacing and width constraints
* Achieving clean, symmetric routing
* Using cross-coupled routing for matched devices to reduce mismatch and parasitic effects

## DRC Error Clearance

After routing, Design Rule Checks (DRC) were performed to ensure compliance with fabrication constraints. Issues related to spacing, enclosure, and metal widths were identified and resolved. Guard rings, P-TAPs, and N-TAPs were verified for correct substrate isolation. Successful DRC clearance confirmed that the layout was ready for fabrication.

<img width="1340" height="752" alt="image" src="https://github.com/user-attachments/assets/a4518f89-1f9a-410a-9723-bed341a5e8a5" />

<img width="1339" height="752" alt="image" src="https://github.com/user-attachments/assets/2d2c6e3f-b68d-4918-9703-dd768f37a115" />
<img width="1336" height="743" alt="image" src="https://github.com/user-attachments/assets/6dd2fd27-f34b-42d3-a605-d99fafbeaed1" />


 **Conclusion:**
 
 The session successfully demonstrated the complete analog layout workflow, from floorplanning and placement to routing and DRC clearance. Proper use of guard rings, symmetry, and matching techniques helped reduce parasitic effects and substrate noise. Efficient use of layout tools and shortcuts improved productivity and accuracy. Clearing all DRC errors confirmed that the layout met fabrication rules, reinforcing the importance of careful layout practices in achieving reliable and high-performance analog IC designs.




