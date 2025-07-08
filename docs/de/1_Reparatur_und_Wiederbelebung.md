# Kapitel I: Reparatur und Wiederbelebung

Alles begann nach einem fehlgeschlagenen Versuch, ein Betriebssystem (Brunch OS) zu installieren. Das Tablet konnte beim Start weder Windows laden noch mit der Installation fortfahren; es landete entweder in einer Endlosschleife der "Automatischen Reparatur" oder direkt im UEFI Shell-Bildschirm. Das Gerät war softwareseitig "gebrickt" und unbrauchbar geworden.

## Fehlerdiagnose: Ein systematischer, beweisbasierter Ansatz

Um die Ursache des Problems zu finden, verfolgte ich eine einfache, aber effektive Methode: Ich testete die Hardware auf zwei verschiedenen Ebenen – einmal mit einem Betriebssystem-Kernel und einmal mit der geräteeigenen Firmware.

| **Ebene 1: Hardware-Test mit Linux-Kernel** | **Ebene 2: Geräte-Test mit UEFI-Firmware** |
| :---: | :---: |
| Als ich das System mit einem Linux Mint Live-USB startete, erkannte die `GParted`-Anwendung den 64GB eMMC-Speicher des Tablets problemlos. Ich konnte Partitionen erstellen und formatieren. Dies war der eindeutige und klare Beweis, dass der Speicherchip physisch intakt war. | Im UEFI Shell-Bildschirm hingegen zeigte der Befehl `map -r`, der die Geräte auflistet, keinen einzigen Eintrag (`blkX`) für die eMMC-Speichereinheit an. Dies zeigte, dass das UEFI, das Gehirn des Tablets, den physisch intakten Speicher auf Hardware-Ebene nicht erkennen konnte. |
| <img src="../../assets/images/thumbnail_17477595295231327780041398629873.jpg.jpg" width="450"> | <img src="../../assets/images/Outlook-qgcwu443.png" width="450"> |
| *GParted sagte, der eMMC-Chip sei am Leben. Das Problem war nicht die Hardware.* | *Der `map -r`-Befehl bewies, dass das UEFI denselben Speicher nicht sehen konnte.* |

**Endgültige Diagnose:** Obwohl die Ergebnisse dieser beiden Tests widersprüchlich erschienen, wiesen sie tatsächlich genau auf das Problem hin: Das Problem lag nicht am eMMC-Chip selbst, sondern an einer Konfigurationsbeschädigung in der UEFI-Firmware oder im NVRAM. Die fehlgeschlagene Installation hatte die Softwareebene beschädigt, die es dem Gerät ermöglicht, seine eigene Hardware zu erkennen.

## Die Lösung: Überwindung der Ein-Port-Beschränkung

Als ich diese klaren Beweise dem technischen Support der Wortmann AG vorlegte, bestätigten sie, dass dies ein bekanntes Problem sei und die Lösung darin bestehe, das BIOS neu zu flashen. Sie stellten mir die erforderliche BIOS-Datei und die Anweisungen zur Verfügung.

Allerdings gab es eine erhebliche Hardware-Einschränkung: das Gerät hatte nur **einen einzigen USB-Port**. Für den Flash-Vorgang benötigte ich gleichzeitig eine USB-Tastatur, um die Befehle einzugeben, und einen USB-Stick, auf dem sich die Dateien befanden.

Um dieses Problem zu lösen, entwickelte ich eine Methode mit den folgenden Schritten:

1.  **Befehl in den Speicher laden:** Zuerst schloss ich die USB-Tastatur an. Ich gab den Befehl `Flash.nsh` in die EFI Shell ein und drückte Enter (die Fehlermeldung ignorierte ich). Dadurch wurde der Befehl im temporären Verlaufsspeicher der Shell gespeichert.
2.  **Geräte austauschen:** Ich zog die Tastatur ab und steckte den USB-Stick mit den BIOS-Dateien an.
3.  **Befehl zurückrufen:** Ohne Tastatur navigierte ich mit den physischen **Lauter/Leiser-Tasten** des Tablets durch den Befehlsverlauf. Als der Befehl `Flash.nsh` wieder auf dem Bildschirm erschien, drückte ich einmal die **Power-Taste** (die als Enter fungiert), um den Befehl auszuführen.

Dank dieser unkonventionellen Methode wurde der Flash-Vorgang erfolgreich abgeschlossen, und das Gehirn des Tablets erkannte seinen vergessenen Speicher wieder. Das Gerät war aus dem Koma erwacht und wieder zum Leben erweckt worden.

### Benötigte Dateien

*   **Terra Pad 1062 BIOS-Datei:** Sie können die vom Hersteller bereitgestellte BIOS-Flash-Datei über den folgenden Link herunterladen.
    *   [Download-Link für TERRAPAD1062_BIOS_FLASH.zip](https://github.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/raw/refs/heads/main/TERRAPAD1062_BIOS_FLASH.zip)
    *   **Warnung:** Ein BIOS-Update ist ein riskanter Vorgang. Die gesamte Verantwortung für die Verwendung dieser Datei liegt bei Ihnen. Stellen Sie sicher, dass die Stromversorgung des Geräts während des Vorgangs nicht unterbrochen wird.

---
**[Nächstes Kapitel: Hardware-Evolution →](./2_Hardware_Evolution.md)**