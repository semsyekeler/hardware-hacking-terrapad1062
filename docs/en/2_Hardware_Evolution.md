# Chapter II: Hardware Evolution

This chapter details the hardware modifications and improvements that pushed the device beyond its standard capabilities.

## Reverse Engineering: Analysis of the Docking Port

*   **Objective:** To analyze the 5-pin magnetic **Pogo-Pin connector** on the bottom of the tablet, designed for its original keyboard, and convert it into a functional port.
*   **Method:** The pinout was verified using a technical schematic provided by the manufacturer (Photo 1) and measurements taken with a multimeter. Based on this verification, I created my own connection diagram (Photo 2). The analysis revealed that the port housed a fully functional USB 2.0 interface.
*   **Result:** With the information obtained, a custom adapter was fabricated to provide the device with an external USB-A port. The adapter was designed to fit perfectly into the tablet's internal recess, maintaining ergonomic integrity.

<p float="left">
  <img src="../../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../../assets/images/pin%20diyagram%20tablet.png" width="400" />
</p>
<p align="center">
  <i>Photo 1: The original schematic provided by the manufacturer. &nbsp;&nbsp;&nbsp;&nbsp; Photo 2: The pinout I verified with my own measurements. (Front is screen, back is cover)</i>
</p>

### Pin Numbering and Functions

The pin configuration derived from the analysis is as follows:

| Pin Number | Function              | Schematic Label | Description                                                                |
| :----------: | ------------------- | :-------------: | -------------------------------------------------------------------------- |
| **1**        | **+5V Power**       |  `+V_5P0_KB`    | Provides power to external accessories. Complies with USB standards.       |
| **2**        | **USB Data - (DN)** | `USB2_MODEM_DN` | Standard USB 2.0 negative data line.                                       |
| **3**        | **USB Data + (DP)** | `USB2_MODEM_DP` | Standard USB 2.0 positive data line.                                       |
| **4**        | **Keyboard Detect** |    `KB_DET`     | Detects if a keyboard is attached. Activated when pulled to GND (Pin 5) by the external keyboard **through a 1k Ohm resistor**. |
| **5**        | **Ground (GND)**    |     `GND`       | Common reference ground for the circuit.                                   |

<p align="center">
  <img src="../assets/images/tablete%20bağlanan%20usb%20dişi%20kısım.jpg" width="450">
</p>
<p align="center">
  <i>The custom USB socket designed based on the information obtained through reverse engineering.</i>
</p>

## Before Starting Modifications: Opening the Case

**WARNING:** These procedures require experience. You can cause permanent damage to your device and void the warranty. All responsibility is yours.

*   **Required Tools:**
    *   Torx T4 screwdriver bit
    *   A thin and flexible prying tool like a plastic pick or an old credit card

*   **Disassembly Instructions:**
    1.  **Remove the Correct Screws:** Remove **all** screws on the back cover. These are the black screws on the kickstand and the white/silver screws at the bottom.
    2.  **CRITICAL WARNING:** **Do not touch** the hinge screws that connect the kickstand directly to the tablet's metal chassis! Removing these screws will complicate reassembly and is an unnecessary step.
    3.  **Separate the Cover:** Once all screws are removed, carefully insert the plastic pick between the chassis and the back cover and gently pry to release the clips, separating the cover.

<p align="center">
  <img src="../../assets/images/tablet%20kasa.jpg" width="700">
</p>
<p align="center">
  <i>Disassembly: The screws connecting the kickstand to the hinge (3x2 black ones) and the ones underneath (4 silver screws) are to be removed.</i>
</p>

*   **Assembly Tips:**
    *   When installing the bottom screws near the magnetic parts, the magnetic pull might cause the screw to slip from its socket. You may need to guide the screw with your finger.
    *   Handle ribbon cables with extreme care; they can tear easily.
    *   Be careful not to let screws or metal tools touch the SMD components on the motherboard, as this could cause a short circuit.

## Modification 1: Audio System Upgrade

*   **Problem:** The device's original speakers produced a tinny and treble-heavy sound, which was particularly inadequate for speech-heavy content.
*   **Solution:** A pair of higher-quality speakers with their own acoustic chambers, salvaged from an old laptop, were soldered to the tablet's original speaker outputs.
*   **Engineering Detail:** The speaker wires were routed through the tablet's original speaker grilles. The speakers were positioned to fit perfectly within the case geometry, preserving the device's ergonomics and physical integrity. This resulted in a significant improvement in sound quality.

<p align="center">
  <img src="../../assets/images/hoparlor_lehimlerken.jpg" width="450">
</p>
<p align="center">
  <i>Mounting the old laptop speaker.</i>
</p>

## Modification 2: Solving the "Ghost Keyboard" Issue

*   **Problem:** The metal pins of the custom-made USB socket were making contact with the tablet's aluminum chassis, inadvertently triggering the `KB_DET` (Keyboard Detect) pin. This locked functions like auto-screen rotation. Disconnecting and reconnecting the battery temporarily fixed the issue, but the error would recur as the contact persisted.
*   **Solution:** The contact area was electrically isolated using non-conductive hot glue, permanently resolving the problem.

## Other Mechanical Improvements

*   **Camera Lens Replacement:** The scratched original camera lens was replaced with a pristine lens carefully salvaged from an old laptop by breaking its chassis. The lens was installed using its original adhesive.
*   **Chassis Creak Elimination:** Support pieces were added to the inside of the case at points where it flexed, preventing it from collapsing inward. This increased mechanical stability and completely eliminated the creaking sound.

<p align="center">
  <img src="../../assets/images/tablet%20modifiye%20edilmiş%20hal%20içi.png">
</p>
<p align="center">
  <i>The internal layout of the tablet after all modifications were completed.</i>
</p>

---
**[← Previous Chapter: Repair and Resurrection](./1_Repair_and_Resurrection.md) | [Next Chapter: Software and Optimization →](./3_Software_and_Optimization.md)**
