# Capítulo I: Reparación y Resurrección

Todo comenzó después de un intento fallido de instalar un sistema operativo (Brunch OS). La tableta, al encenderse, no podía iniciar Windows ni continuar con la instalación; entraba constantemente en un bucle de "Reparación Automática" o caía directamente en la pantalla de la UEFI Shell. El dispositivo se había convertido en un "brick" de software, completamente inútil.

## Diagnóstico del Fallo: Un Enfoque Sistemático Basado en Evidencia

Para encontrar la fuente del problema, seguí un método simple pero efectivo: probar el hardware en dos niveles diferentes, el kernel del sistema operativo y el propio firmware del dispositivo.

| **Nivel 1: Prueba de Hardware con el Kernel de Linux** | **Nivel 2: Prueba de Dispositivo con el Firmware UEFI** |
| :---: | :---: |
| Al iniciar el sistema con una USB de Linux Mint Live, la aplicación `GParted` reconoció sin problemas el almacenamiento eMMC de 64GB de la tableta. Podía crear particiones y formatearla. Esta era una prueba clara y definitiva de que el chip de almacenamiento estaba físicamente intacto. | En la pantalla de la UEFI Shell, el comando `map -r`, que lista los dispositivos, no mostraba ninguna entrada (`blkX`) correspondiente a la unidad de almacenamiento eMMC. Esto revelaba que el propio cerebro de la tableta, la UEFI, no podía reconocer a nivel de hardware la memoria que estaba físicamente sana. |
| <img src="../../assets/images/thumbnail_17477595295231327780041398629873.jpg.jpg" width="450"> | <img src="../../assets/images/Outlook-qgcwu443.png" width="450"> |
| *GParted decía que el chip eMMC estaba vivo. El problema no era de hardware.* | *El comando `map -r` demostraba que la UEFI no podía ver esa misma memoria.* |

**Diagnóstico Final:** Aunque los resultados de estas dos pruebas parecían contradictorios, en realidad señalaban el problema con precisión: el problema no estaba en el chip eMMC en sí, sino en el firmware de la UEFI o en una corrupción de la configuración en la NVRAM. La instalación fallida había dañado la capa de software que permite al dispositivo reconocer su propio hardware.

## La Solución: Superando la Restricción de un Solo Puerto

Cuando comuniqué la situación al soporte técnico de Wortmann AG con estas pruebas claras, confirmaron que era un problema conocido y que la solución era flashear nuevamente el BIOS. Compartieron el archivo de BIOS necesario y las instrucciones.

Sin embargo, había una seria limitación de hardware: el dispositivo solo tenía **un único puerto USB**. Para el proceso de flasheo, necesitaba simultáneamente un teclado USB para escribir los comandos y una memoria USB que contuviera los archivos.

Para superar este problema, desarrollé un método siguiendo estos pasos:

1.  **Guardar el Comando en Memoria:** Primero, conecté el teclado USB. Escribí el comando `Flash.nsh` en la EFI Shell y presioné Enter (sin importar que diera un error). Esto guardó el comando en el historial temporal de la Shell.
2.  **Cambiar Dispositivos:** Desconecté el teclado y conecté la memoria USB que contenía los archivos del BIOS.
3.  **Llamar al Comando:** Sin el teclado, utilicé las **teclas físicas de Subir/Bajar Volumen** de la tableta para navegar por el historial de comandos. Cuando el comando `Flash.nsh` apareció de nuevo en la pantalla, presioné una vez el **Botón de Encendido** (que funciona como Enter) para ejecutarlo.

Gracias a este método poco convencional, el proceso de flasheo se completó con éxito, y el cerebro de la tableta volvió a reconocer la memoria que había olvidado. Con esta operación, el dispositivo salió del coma y volvió a la vida.

### Archivos Necesarios

*   **Archivo de BIOS para Terra Pad 1062:** Puedes acceder al archivo de flasheo de BIOS proporcionado por el fabricante en el siguiente enlace.
    *   [Enlace de Descarga de TERRAPAD1062_BIOS_FLASH.zip](https://github.com/semsyekeler/hardware-hacking-terrapad1062-windows-tablet/raw/refs/heads/main/TERRAPAD1062_BIOS_FLASH.zip)
    *   **Advertencia:** La actualización del BIOS es un proceso arriesgado. La responsabilidad total de usar este archivo es tuya. Asegúrate de que no se corte la energía del dispositivo durante el proceso.

---
**[Siguiente Capítulo: Evolución del Hardware →](./2_Evolucion_del_Hardware.md)**