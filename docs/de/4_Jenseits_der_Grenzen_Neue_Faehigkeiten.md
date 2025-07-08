# Kapitel IV: Jenseits der Grenzen - Mehr als nur ein Tablet

Dieses Projekt ist nicht nur eine Reparaturgeschichte, sondern auch ein Beweis dafür, wie vielseitig ein Gerät durch Kreativität werden kann. Dieses reparierte und optimierte Tablet ist nun weit mehr als ein Standardgerät; es hat sich in eine Reihe von Werkzeugen verwandelt, die auf meine persönlichen Bedürfnisse zugeschnitten sind.

## 🎸 Szenario 1: Das tragbare Gitarrenstudio

*   **Die Idee:** Einer der größten Vorteile eines Windows-basierten Tablets ist die Flexibilität, Desktop-Anwendungen ausführen zu können. Ich wollte diese Flexibilität nutzen, um das Tablet in ein E-Gitarren-Studio zu verwandeln, das ich überallhin mitnehmen kann.
*   **Die Herausforderung:** Wenn man eine E-Gitarre direkt an einen Windows-Computer anschließt, verursacht die hohe Latenz (latency) der Standard-Audiotreiber eine spürbare Verzögerung zwischen dem Spielen einer Note und dem Hören des Klangs. Dies macht es unmöglich, rhythmisch präzise zu spielen.
*   **Die Lösung:**
    1.  **Hardware:** Ein selbstgebauter **AUX-Splitter**-Adapter wurde angefertigt, mit einem Ende für den Gitarreneingang (rot) und dem anderen für den Kopfhörer-/Lautsprecherausgang. Dieser Adapter leitet das Gitarrensignal an den Mikrofoneingang des Computers und den Audioausgang des Computers an die Kopfhörer.
    2.  **Treiber:** Anstelle des normalerweise für diesen Zweck verwendeten ASIO4ALL-Treibers wurde **FlexASIO GUI** installiert, das eine breitere Hardwareunterstützung und eine benutzerfreundliche Oberfläche bietet. FlexASIO umgeht die langsamen Windows-Treiber und reduziert die Latenz auf ein nicht wahrnehmbares Niveau.
        *   [Download-Link für FlexASIO GUI (v0.35)](https://github.com/flipswitchingmonkey/FlexASIO_GUI/releases/download/v0.35/FlexASIO.GUIInstaller_0.35.exe)
    3.  **Prozessor:** Mit dem Programm **Guitar Rig 7** wurde das Tablet zu einem riesigen Klangarsenal mit einer nahezu unbegrenzten Anzahl von Verstärkermodellen, Boxensimulationen und Effektpedalen.
*   **Das Ergebnis:** Dank dieses Setups kann ich meiner E-Gitarre überall und mit nahezu null Latenz unzählige Sounds und Effekte hinzufügen.

<p align="center">
  <img src="../../assets/images/guitar_and_tablet_setup_birdview_photo.jpg" width="750">
</p>
<p align="center">
  <i>Foto 1: Das gesamte System in Betrieb mit Tablet, Gitarre, Kopfhörern und Splitter.</i>
</p>

<p align="center">
  <img src="../../assets/images/aux_splitter_gitar_and_speaker.jpg" width="400">
</p>
<p align="center">
  <i>Foto 2: Der selbstgebaute AUX-Splitter, der das Gitarrensignal (roter Stecker) und den Kopfhörerausgang trennt.</i>
</p>

## 💻 Szenario 2: Kabelloser und berührungsempfindlicher Coding-Monitor

*   **Die Idee:** Beim Programmieren benötige ich oft einen zweiten Bildschirm für Referenzdokumente oder die Vorschau der laufenden Anwendung. Dies beseitigt die Notwendigkeit, ständig zwischen Fenstern zu wechseln und beschleunigt den Arbeitsablauf.
*   **Die Lösung:** Das Programm **[Space Desk](https://www.spacedesk.net/)** verwandelt das Tablet drahtlos in einen zweiten Monitor für meinen Hauptcomputer.
*   **Der entscheidende Vorteil:** Der größte Vorteil dieses Setups ist, dass die Touch-Funktion des Tablets erhalten bleibt. Während ich auf dem Hauptbildschirm code, kann ich auf dem Tablet mit dem Finger durch Referenzcode scrollen oder eine Fehlermeldung direkt durch Antippen auswählen. Das hat meinen Workflow unglaublich beschleunigt.
*   **Pro-Tipp (Verwendung im Hochformat):** Um das Tablet effizient im Hochformat zu nutzen, sind folgende Schritte erforderlich:
    1.  In den Windows-Einstellungen des Tablets die "Rotationssperre" aktivieren (automatische Drehung deaktivieren).
    2.  Die Space Desk-App auf dem Tablet öffnen und mit dem Hauptcomputer verbinden. Der Bildschirm wird zunächst im Querformat angezeigt.
    3.  Zu den Anzeigeeinstellungen des Hauptcomputers gehen, den zweiten Monitor (der das Tablet repräsentiert) auswählen und die "Bildschirmausrichtung" auf "Hochformat" ändern.

<p align="center">
  <img src="../../assets/images/tablet_as_a_second_monitor.jpg" width="700">
</p>
<p align="center">
  <i>Ein Setup, das die Produktivität durch einen berührungsempfindlichen und vertikalen zweiten Bildschirm beim Programmieren erhöht.</i>
</p>

## ⚡ Szenario 3: Mobiles Engineering-Labor

*   **Die Idee:** Als angehender Ingenieur habe ich oft das Bedürfnis, eine Schaltungsidee oder die Funktionsweise eines Bauteils schnell zu testen.
*   **Die Herausforderung:** Professionelle Simulationssoftware erfordert in der Regel leistungsstarke Desktop-Computer.
*   **Das überraschende Ergebnis:** Ob Sie es glauben oder nicht, eines der erstaunlichsten Ergebnisse dieses Projekts war, dass **Proteus 8**, ein professionelles Simulationsprogramm für elektronische Schaltungen, das normalerweise für seinen Ressourcenverbrauch bekannt ist, auf diesem Tablet zumindest auf grundlegendem Niveau flüssig lief.
*   **Das Ergebnis:** Dies hat das Tablet in ein "mobiles Labor" verwandelt, in dem ich eine Schaltungsidee, die mir in den Sinn kommt, schnell in der Bibliothek oder einem Café aufbauen und testen kann.

---
Ich hoffe, diese Anleitung inspiriert Sie zu Ihren eigenen Projekten. Danke fürs Lesen.

 **[← Vorheriges Kapitel: Software und Optimierung](./3_Software_und_Optimierung.md)|[Nächstes Kapitel: Fazit und Erkenntnisse →](./5_Fazit_und_Erkenntnisse.md)**