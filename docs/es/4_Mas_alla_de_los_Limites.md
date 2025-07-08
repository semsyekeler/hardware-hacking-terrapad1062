# Capítulo IV: Más Allá de los Límites - Más que una Simple Tableta

Este proyecto no es solo una historia de reparación, sino también una prueba de cuán versátil puede ser un dispositivo con un poco de creatividad. Esta tableta, reparada y optimizada, se ha convertido en un conjunto de herramientas personalizadas que van mucho más allá de un dispositivo estándar.

## 🎸 Escenario 1: Estudio de Guitarra Portátil

*   **La Idea:** Una de las mayores ventajas de una tableta basada en Windows es la flexibilidad para ejecutar aplicaciones de escritorio. Mi objetivo era usar esta flexibilidad para transformar la tableta en un estudio de guitarra eléctrica que pudiera llevar a cualquier parte.
*   **El Desafío:** Cuando conectas una guitarra eléctrica directamente a un ordenador con Windows, la alta latencia (latency) creada por los controladores de audio estándar causa un retraso perceptible entre tocar una nota y escucharla. Esto hace que sea imposible tocar rítmicamente de forma correcta.
*   **La Solución:**
    1.  **Hardware:** Se preparó un adaptador **splitter AUX** personalizado, con una entrada de guitarra (roja) en un extremo y una salida de auriculares/altavoz en el otro. Este adaptador dirige la señal de la guitarra a la entrada de micrófono del ordenador y la salida de audio del ordenador a los auriculares.
    2.  **Controlador:** En lugar del controlador ASIO4ALL, que se usa normalmente para esto, se instaló **FlexASIO GUI**, que ofrece un soporte de hardware más amplio y una interfaz fácil de usar. FlexASIO evita los lentos controladores de Windows, reduciendo la latencia a niveles imperceptibles.
        *   [Enlace de Descarga de FlexASIO GUI (v0.35)](https://github.com/flipswitchingmonkey/FlexASIO_GUI/releases/download/v0.35/FlexASIO.GUIInstaller_0.35.exe)
    3.  **Procesador:** Con el programa **Guitar Rig 7**, la tableta se convirtió en un arsenal de sonido masivo, con un número casi ilimitado de modelos de amplificadores, simulaciones de gabinetes y pedales de efectos.
*   **El Resultado:** Gracias a esta configuración, puedo añadir innumerables tonos y efectos a mi guitarra eléctrica en cualquier lugar, con una latencia casi nula.

<p align="center">
  <img src="../../assets/images/guitar_and_tablet_setup_birdview_photo.jpg" width="750">
</p>
<p align="center">
  <i>Foto 1: El sistema completo en funcionamiento con la tableta, la guitarra, los auriculares y el splitter.</i>
</p>

<p align="center">
  <img src="../../assets/images/aux_splitter_gitar_and_speaker.jpg" width="400">
</p>
<p align="center">
  <i>Foto 2: El splitter AUX personalizado que separa la señal de la guitarra (extremo rojo) y la salida de auriculares.</i>
</p>


## 💻 Escenario 2: Monitor de Codificación Inalámbrico y Táctil

*   **La Idea:** Mientras codifico, a menudo necesito una segunda pantalla para documentos de referencia o para la vista previa de la aplicación en ejecución. Esto elimina la necesidad de cambiar constantemente entre ventanas, acelerando mi flujo de trabajo.
*   **La Solución:** El programa **[Space Desk](https://www.spacedesk.net/)** convirtió la tableta en un segundo monitor inalámbrico para mi ordenador principal.
*   **La Diferencia en el Uso:** La mayor ventaja de esta configuración es que se conserva la funcionalidad táctil de la tableta. Mientras escribo código en la pantalla principal, poder desplazarme por el código de referencia en la tableta con el dedo o seleccionar un mensaje de error tocándolo directamente ha acelerado mi flujo de trabajo de manera increíble.
*   **Consejo Pro (Uso en Modo Vertical):** Para usar la tableta de manera eficiente en modo vertical, sigue estos pasos:
    1.  Activa el "Bloqueo de rotación" en la configuración de Windows de la propia tableta (desactiva la rotación automática).
    2.  Abre la aplicación Space Desk en la tableta y conéctate a tu ordenador principal. La pantalla aparecerá inicialmente en horizontal.
    3.  Ve a la Configuración de pantalla de tu ordenador principal, selecciona el segundo monitor (que representa la tableta) y cambia la "Orientación de la pantalla" a "Vertical".

<p align="center">
  <img src="../../assets/images/tablet_as_a_second_monitor.jpg" width="700">
</p>
<p align="center">
  <i>Una configuración que aumenta la productividad al proporcionar un segundo espacio de pantalla táctil y vertical mientras se codifica.</i>
</p>

## ⚡ Escenario 3: Laboratorio de Ingeniería Móvil

*   **La Idea:** Como futuro ingeniero, a menudo siento la necesidad de probar rápidamente una idea de circuito que se me ocurre o la lógica de funcionamiento de un componente.
*   **El Desafío:** El software de simulación profesional generalmente requiere potentes ordenadores de escritorio.
*   **El Resultado Sorprendente:** Lo creas o no, uno de los resultados más sorprendentes de este proyecto fue que **Proteus 8**, un programa profesional de simulación de circuitos electrónicos conocido por su consumo de recursos, funcionaba de manera fluida en esta tableta, al menos a un nivel básico.
*   **El Resultado:** Esto transformó la tableta en un "laboratorio móvil" donde puedo montar y probar rápidamente una idea de circuito que se me ocurra en la biblioteca o en una cafetería.

---
Espero que esta guía te inspire para tus propios proyectos. Gracias por leer.

 **[← Capítulo Anterior: Software y Optimización](./3_Software_y_Optimizacion.md)|[Siguiente Capítulo: Conclusión y Aprendizajes →](./5_Conclusion_y_Aprendizajes.md)**