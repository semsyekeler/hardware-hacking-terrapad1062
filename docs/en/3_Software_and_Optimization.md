# Chapter III: Software and Optimization

After completing the hardware modifications, the next stage was to establish the most suitable software ecosystem for this hardware and turn it into an efficient workstation.

## A. The Quest for an Operating System: A Challenging Adventure

*   **Problem:** A low-power processor like the Intel Atom Z8500 can easily struggle under modern operating systems. My goal was to find the system that offered the smoothest experience for both media consumption and productivity.
*   **Experiments and Results:**
    *   **The Ubuntu Adventure:** During installation, the screen would randomly turn off at intervals, which not only disrupted the installation process but also indicated that stable usage would be impossible.
    *   **The Debian (Net Install) Trial:** With the aim of dual-booting, I performed the most minimal Debian installation possible. My goal was to create an ultra-lightweight Linux environment for media consumption. However, the result was an experience that was extremely slow, clunky, and detached from the tablet's hardware features—a stark contrast to Windows 10, amounting to torture.
*   **Final Decision:** The tests conclusively proved that for this specific hardware combination, **Windows 10** was the most stable, compatible, and performant platform. The seamless integration of drivers for the touchscreen, pen, and sensors was the deciding factor.

<p align="center">
  <img src="../../assets/images/debian%20net%20install%20kde%20plasma%20denerken%20kod%20ekrani%20açık.jpg" width="550">
</p>
<p align="center">
  <i>Just one of many experiments in the Linux world. Each distribution presented a different challenge in terms of hardware compatibility.</i>
</p>

## B. Critical Software Choices: Speed and Stability

The following software, which runs best on this hardware and transforms the tablet into a true portable workstation, are those that are **fast to launch and stable in use**:

| Category | Selected Software | Description and Download Link |
| :--- | :--- | :--- |
| **On-Screen Keyboard**| **Comfort On-Screen Keyboard Pro** | A professional alternative that replaces Windows's laggy built-in keyboard. It opens instantly, works without lag, and its ability to appear automatically on text-field clicks, be moved anywhere, and be **dynamically resized** makes tablet use incredibly fluid. <br> *[Official Website](https://www.comfort-software.com/)* |
| **Coding** | **Sublime Text** | Its incredibly lightweight nature allows it to open instantly and provide a smooth experience without stuttering, even with the largest code files. <br> *[Official Website](https://www.sublimetext.com/)* |
| **PDF** | **PDF-XChange Editor** | Unlike heavy alternatives like Adobe Reader, it opens very quickly and provides stable performance without lagging, even when navigating large PDFs. <br> *[Official Website](https://www.tracker-software.com/product/pdf-xchange-editor)* |
| **Office** | **SoftMaker FreeOffice** | The fastest and lightest alternative to Microsoft Office. It opens and edits Word, Excel, and PowerPoint files with surprising speed. <br> *[Official Website](https://www.freeoffice.com/en/)* |
| **E-Mail**| **Wino Mail** | It combines a modern and clean interface with a lightweight structure that doesn't consume system resources. <br> *[Microsoft Store](https://apps.microsoft.com/detail/9ncrcvjc50wl?hl=en-us&gl=us)* |
| **Remote Desktop**| **Parsec** | Its low-latency technology allows you to connect remotely to your main computer and perform even heavy tasks smoothly from this tablet. <br> *[Official Website](https://parsec.app/)* |

<p align="center">
  <img src="../../assets/images/programs.jpg" width="700">
</p>
<p align="center">
  <i>Lightweight and powerful software that unlocks the device's potential.</i>
</p>

## C. Daily Use Optimizations

| YouTube Problem and Solution | OneNote and Stylus Solution |
| :---: | :---: |
| <img src="../../assets/images/freetube.jpg" width="350"> | <img src="../../assets/images/one%20note%20for%20windows%2010%20tablet%20dış%20çekim.jpg" width="350"> |
| **Problem:** Watching YouTube in a browser meant constant stuttering and audio/video desync. <br><br> **Solution:** The **[FreeTube](https://freetubeapp.io/)** client, which bypasses the browser, was installed. This single application completely transformed the tablet's media consumption capability, providing a zero-stutter, ad-free, and smooth experience. | **Problem:** Lack of a fluid note-taking app and a stylus. <br><br> **Solution:** The fastest version, `OneNote for Windows 10` (from the Microsoft Store), was combined with the **[VirtualTablet](https://www.sunnysidesoft.com/virtualtablet/)** app. VirtualTablet connects a phone to the PC as a graphics tablet, allowing me to use my phone's stylus in OneNote. |

### Browser Optimization and Touchscreen Tips
*   **The Fastest Browser:** In my quest to find the best browser for this hardware, I tested all popular alternatives. The results clearly showed that **Microsoft Edge** was the browser that consumed the least system resources and offered the smoothest performance.
*   **General Media Consumption:** Apart from YouTube, the device has no issues with video playback from the browser, such as watching movies or series. The optimized Edge browser can play such content smoothly.
*   **Critical Touchscreen Issue in Chromium-Based Browsers and Its Solution:**
    *   **Problem:** In browsers like Chrome and Brave, when tapping the "open new tab" (+) button, the system would misinterpret the precise location of the touch and act as if the adjacent "close tab" (X) button was pressed.
    *   **Solution:** To overcome this issue, instead of just tapping the button, you need to **press and hold briefly with each click**. This small delay gives the system enough time to correctly register the proper location.
### Virtual Touchpad for Fine Control
*   **Problem:** A touchscreen can sometimes be inadequate for fine-tuned tasks that require a mouse, like clicking small buttons or selecting text precisely.
*   **Solution:** Windows 10 offers a built-in solution. Right-click the taskbar and enable the **"Show touchpad button"** option. This adds a touchpad icon to your taskbar. When clicked, it opens a virtual touchpad that you can move anywhere on the screen, allowing you to control the mouse cursor with precision using your finger.

Thanks to this software and these optimizations, the tablet was transformed into a full-fledged portable Windows system, overcoming all the disadvantages imposed by its hardware.

---
**[← Previous Chapter: Hardware Evolution](./2_Hardware_Evolution.md) | [Next Chapter: Beyond the Limits - New Capabilities →](./4_Beyond_The_Limits.md)**
