# Kapitel III: Software und Optimierung

Nach Abschluss der Hardware-Modifikationen bestand der nächste Schritt darin, das am besten geeignete Software-Ökosystem für diese Hardware zu installieren und es in eine produktive Arbeitsstation zu verwandeln.

## A. Die Suche nach dem Betriebssystem: Ein anspruchsvolles Abenteuer

*   **Problem:** Ein leistungsschwacher Prozessor wie der Intel Atom Z8500 kann unter modernen Betriebssystemen schnell an seine Grenzen stoßen. Mein Ziel war es, das System zu finden, das sowohl für den Medienkonsum als auch für die Produktivität das flüssigste Erlebnis bietet.
*   **Experimente und Ergebnisse:**
    *   **Ubuntu-Abenteuer:** Während der Installation schaltete sich der Bildschirm ständig zu zufälligen Zeiten aus, was nicht nur den Installationsprozess behinderte, sondern auch zeigte, dass eine stabile Nutzung nicht möglich sein würde.
    *   **Debian (Net Install) Versuch:** Mit dem Ziel eines Dual-Boot-Systems habe ich eine möglichst minimale Debian-Installation durchgeführt. Mein Ziel war es, eine ultraleichte Linux-Umgebung für den Medienkonsum zu schaffen. Das Ergebnis war jedoch im Vergleich zu Windows 10 eine extrem langsame, schwerfällige Erfahrung, die weit von den Hardware-Fähigkeiten des Tablets entfernt war und sich fast wie eine Folter anfühlte.
*   **Endgültige Entscheidung:** Die durchgeführten Tests haben bestätigt, dass **Windows 10** die stabilste, kompatibelste und leistungsfähigste Plattform für diese spezielle Hardwarekombination ist. Insbesondere die nahtlose Integration von Touchscreen, Stift und Sensortreibern war entscheidend.

<p align="center">
  <img src="../../assets/images/debian%20net%20install%20kde%20plasma%20denerken%20kod%20ekrani%20açık.jpg" width="550">
</p>
<p align="center">
  <i>Nur einer von unzähligen Versuchen in der Linux-Welt. Jede Distribution war eine neue Prüfung für die Hardware-Kompatibilität.</i>
</p>

## B. Kritische Software-Auswahl: Geschwindigkeit und Stabilität

Die Software, die auf dieser Hardware am besten funktionierte und das Tablet in eine echte tragbare Arbeitsstation verwandelte, zeichnete sich durch **schnelle Startzeiten und stabile Nutzung** aus:

| Kategorie | Ausgewählte Software | Beschreibung und Download-Link |
| :--- | :--- | :--- |
| **Programmieren** | **Sublime Text** | Dank seiner unglaublich schlanken Struktur startet es sofort und bietet selbst bei größten Codedateien eine flüssige Nutzung ohne Ruckler. <br> *[Offizielle Webseite](https://www.sublimetext.com/)* |
| **PDF** | **PDF-XChange Editor** | Im Gegensatz zu schwerfälligen Alternativen wie Adobe Reader startet es sehr schnell und bietet auch beim Navigieren in großen PDFs eine stabile Leistung ohne Hänger. <br> *[Offizielle Webseite](https://www.tracker-software.com/product/pdf-xchange-editor)* |
| **Office** | **SoftMaker FreeOffice** | Die schnellste und leichteste Alternative zu Microsoft Office. Es öffnet und bearbeitet Word-, Excel- und PowerPoint-Dateien mit erstaunlicher Geschwindigkeit. <br> *[Offizielle Webseite](https://www.freeoffice.com/en/)* |
| **E-Mail**| **Wino Mail** | Kombiniert eine moderne und saubere Benutzeroberfläche mit einer schlanken Struktur, die keine Systemressourcen verschwendet. <br> *[Microsoft Store](https://apps.microsoft.com/detail/9ncrcvjc50wl?hl=en-us&gl=us)* |
| **Remote-Desktop**| **Parsec** | Dank seiner Low-Latency-Technologie ermöglicht es die Fernverbindung zum Hauptrechner, sodass auch anspruchsvolle Aufgaben flüssig auf diesem Tablet erledigt werden können. <br> *[Offizielle Webseite](https://parsec.app/)* |

<p align="center">
  <img src="../../assets/images/programs.jpg" width="700">
</p>
<p align="center">
  <i>Leichte und leistungsstarke Software, die das Potenzial des Geräts freisetzt.</i>
</p>

## C. Optimierungen für den täglichen Gebrauch

| YouTube-Problem und Lösung | OneNote- und Stift-Lösung |
| :---: | :---: |
| <img src="../../assets/images/freetube.jpg" width="350"> | <img src="../../assets/images/one%20note%20for%20windows%2010%20tablet%20dış%20çekim.jpg" width="350"> |
| **Problem:** Das Ansehen von YouTube im Browser führte zu ständigen Rucklern und Audio/Video-Synchronisationsproblemen. <br><br> **Lösung:** Der **[FreeTube](https://freetubeapp.io/)**-Client wurde installiert, der den Browser umgeht. Diese eine Anwendung hat die Medienwiedergabefähigkeit des Tablets komplett verändert und ein ruckelfreies, werbefreies und flüssiges Erlebnis ermöglicht. | **Problem:** Fehlende flüssige Notizen-App und ein Stift. <br><br> **Lösung:** Die schnellste Version, `OneNote for Windows 10` (Microsoft Store), wurde mit der **[VirtualTablet](https://www.sunnysidesoft.com/virtualtablet/)**-App kombiniert. VirtualTablet verbindet das Smartphone als Grafiktablett mit dem PC, sodass ich den Stift meines Telefons in OneNote verwenden konnte. |

### Browser-Optimierung und Tipps für den Touchscreen
*   **Der schnellste Browser:** Auf der Suche nach dem besten Browser für diese Hardware habe ich alle gängigen Alternativen getestet. Die Tests zeigten eindeutig, dass **Microsoft Edge** der Browser ist, der die wenigsten Systemressourcen verbraucht und die flüssigste Leistung bietet.
*   **Allgemeiner Medienkonsum:** Abgesehen von YouTube hat das Gerät keine Probleme bei der Wiedergabe von Videos wie Filmen oder Serien über den Browser. Der optimierte Edge-Browser kann solche Inhalte flüssig wiedergeben.
*   **Kritisches Touch-Problem bei Chromium-basierten Browsern und seine Lösung:**
    *   **Problem:** In Browsern wie Chrome oder Brave führte das Antippen der Schaltfläche "Neuer Tab öffnen" (+) dazu, dass das System die genaue Position der Berührung falsch interpretierte und stattdessen die direkt daneben liegende Schaltfläche "Tab schließen" (X) als gedrückt erkannte.
    *   **Lösung:** Um dieses Problem zu umgehen, muss man die Schaltfläche nicht nur kurz antippen, sondern **bei jedem Klick kurz gedrückt halten**. Diese kleine Verzögerung gibt dem System genügend Zeit, die korrekte Position richtig zu erkennen.

Dank dieser Software und Optimierungen wurde das Tablet in ein vollwertiges, tragbares Windows-System verwandelt, das alle Nachteile seiner Hardware überwindet.

---
**[← Vorheriges Kapitel: Hardware-Evolution](./2_Hardware_Evolution.md) | [Nächstes Kapitel: Jenseits der Grenzen - Neue Fähigkeiten →](./4_Jenseits_der_Grenzen_Neue_Faehigkeiten.md)**