# Capítulo II: Evolución del Hardware

En este capítulo se detallan las modificaciones y mejoras de hardware que llevaron las capacidades del dispositivo más allá de su estándar.

## Ingeniería Inversa: Análisis del Puerto de Conexión (Docking Port)

*   **Objetivo:** Analizar el conector magnético **Pogo-Pin** de 5 pines ubicado en la parte inferior de la tableta, diseñado para su teclado original, y convertirlo en un puerto funcional.
*   **Método:** La estructura de los pines se verificó utilizando el esquema técnico proporcionado por el fabricante (Foto 1) y mediciones realizadas con un multímetro. Basándome en esta verificación, creé mi propio diagrama de conexión (Foto 2). Los análisis revelaron que el puerto albergaba una interfaz USB 2.0 completamente funcional.
*   **Resultado:** Con la información obtenida, se fabricó un adaptador personalizado que le dio al dispositivo un puerto USB-A externo. El adaptador fue diseñado para encajar perfectamente en la cavidad interna de la tableta, manteniendo la integridad ergonómica.

<p float="left">
  <img src="../../assets/images/thumbnail_pin_belegung_F1T.jpg" width="400" />
  <img src="../../assets/images/pin%20diyagram%20tablet.png" width="400" />
</p>
<p align="center">
  <i>Foto 1: Esquema original proporcionado por el fabricante. &nbsp;&nbsp;&nbsp;&nbsp; Foto 2: La estructura de pines que verifiqué con mis propias mediciones. (El frente es la pantalla, la parte trasera es la cubierta)</i>
</p>

### Numeración y Funciones de los Pines

La configuración de pines obtenida a través del análisis es la siguiente:

| N.º de Pin | Función                 | Equivalente en Esquema | Descripción                                                                |
| :--------: | ----------------------- | :--------------------: | -------------------------------------------------------------------------- |
| **1**      | **Alimentación +5V**    |      `+V_5P0_KB`       | Proporciona energía a accesorios externos. Cumple con los estándares USB.  |
| **2**      | **USB Datos - (DN)**    |     `USB2_MODEM_DN`    | Línea de datos negativa estándar de USB 2.0.                               |
| **3**      | **USB Datos + (DP)**    |     `USB2_MODEM_DP`    | Línea de datos positiva estándar de USB 2.0.                               |
| **4**      | **Detección de Teclado**|        `KB_DET`        | Detecta si el teclado está conectado. Se activa cuando el teclado externo lo conecta a GND (Pin 5) **a través de una resistencia de 1k Ohm**. |
| **5**      | **Tierra (GND)**        |         `GND`          | Tierra de referencia común para el circuito.                               |

<p align="center">
  <img src="../../assets/images/tablete%20ba%C4%9Flanan%20usb%20di%C5%9Fi%20k%C4%B1s%C4%B1m.jpg" width="450">
</p>
<p align="center">
  <i>El zócalo USB personalizado diseñado según la información obtenida mediante ingeniería inversa.</i>
</p>

## Antes de Empezar las Modificaciones: Abrir la Carcasa

**ADVERTENCIA:** Estos procedimientos requieren experiencia. Podrías causar daños permanentes a tu dispositivo y anular la garantía. Toda la responsabilidad recae sobre ti.

*   **Herramientas Necesarias:**
    *   Punta de destornillador Torx T4
    *   Una púa de plástico o una herramienta de palanca delgada y flexible, como una tarjeta de crédito vieja.

*   **Instrucciones de Desmontaje:**
    1.  **Quita los Tornillos Correctos:** Quita **todos los tornillos** de la cubierta trasera. Estos son los tornillos negros en el soporte (kickstand) y los tornillos blancos/plateados en la parte inferior.
    2.  **ADVERTENCIA CRÍTICA:** ¡**Absolutamente no toques** los tornillos de la bisagra donde el soporte se conecta directamente a la carcasa metálica de la tableta! Quitar estos tornillos complica el montaje del dispositivo y es un paso innecesario.
    3.  **Separa la Cubierta:** Una vez que todos los tornillos estén fuera, inserta con cuidado la púa de plástico entre la carcasa y la cubierta trasera y suelta suavemente las pestañas para separar la cubierta.

<p align="center">
  <img src="../../assets/images/tablet%20kasa.jpg" width="700">
</p>
<p align="center">
  <i>Proceso de desmontaje: Se deben quitar los tornillos que conectan el soporte a la bisagra (3x2 tornillos negros) y los que están debajo (4 tornillos plateados).</i>
</p>

*   **Consejos de Montaje:**
    *   Al colocar los tornillos inferiores cerca de las partes magnéticas, la atracción puede hacer que el tornillo se deslice de su lugar. Es posible que necesites guiarlo con el dedo.
    *   Maneja los cables planos (ribbon) con extremo cuidado; pueden romperse fácilmente.
    *   Asegúrate de que los tornillos o herramientas metálicas no entren en contacto con los componentes SMD en la placa base para evitar cortocircuitos.

## Modificación 1: Mejora del Sistema de Audio

*   **Problema:** Los altavoces originales del dispositivo tenían un sonido débil y agudo, especialmente deficiente para contenidos con diálogos.
*   **Solución:** Un par de altavoces de mayor calidad, con sus propias cámaras acústicas, extraídos de un viejo portátil, fueron soldados a las salidas de los altavoces originales de la tableta.
*   **Detalle de Ingeniería:** Los cables de los altavoces se pasaron a través de las rejillas originales de la tableta. Los altavoces se posicionaron para encajar perfectamente en la geometría de la carcasa, preservando la ergonomía y la integridad física del dispositivo. El resultado fue una mejora notable en la calidad del sonido.

<p align="center">
  <img src="../../assets/images/hoparlor_lehimlerken.jpg" width="450">
</p>
<p align="center">
  <i>Instalación del altavoz de un portátil viejo.</i>
</p>

## Modificación 2: Solución al Problema del "Teclado Fantasma"

*   **Problema:** Los pines metálicos del zócalo USB personalizado hacían contacto con el chasis de aluminio de la tableta, lo que activaba involuntariamente el pin `KB_DET` (Detección de Teclado). Esto bloqueaba funciones como la rotación automática de la pantalla. Desconectar y volver a conectar la batería resolvía el problema temporalmente, pero el error se repetía mientras el contacto persistiera.
*   **Solución:** La zona de contacto se aisló eléctricamente usando silicona caliente, que es un material no conductor, solucionando el problema de forma permanente.

## Otras Mejoras Mecánicas

*   **Reemplazo de la Lente de la Cámara:** La lente original rayada de la cámara fue reemplazada por una lente intacta, extraída con cuidado de un portátil viejo rompiendo su chasis. El adhesivo original de la lente se conservó para el montaje.
*   **Eliminación de Crujidos del Chasis:** Se añadieron piezas de soporte en el interior de los puntos flexibles de la carcasa para evitar que se hundiera, aumentando la estabilidad mecánica y eliminando por completo los crujidos.

<p align="center">
  <img src="../../assets/images/tablet%20modifiye%20edilmi%C5%9F%20hal%20i%C3%A7i.png">
</p>
<p align="center">
  <i>La disposición interna de la tableta después de completar todas las modificaciones.</i>
</p>

---
**[← Capítulo Anterior: Reparación y Resurrección](./1_Reparacion_y_Resurreccion.md) | [Siguiente Capítulo: Software y Optimización →](./3_Software_y_Optimizacion.md)**