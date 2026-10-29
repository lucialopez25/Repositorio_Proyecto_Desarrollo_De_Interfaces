# 2.1 Usabilidad y Accesibilidad

Para garantizar una experiencia intuitiva, fluida y universal dentro de la aplicación, el diseño de la interfaz se ha estructurado siguiendo principios consolidados de interacción persona-ordenador (IPO) y normativas internacionales.

## 2.1.1 Usabilidad (Decálogo de Jakob Nielsen)[1]
El diseño de las diferentes pantallas se alinea con las 10 heurísticas de usabilidad para reducir la fricción durante la toma de decisiones en grupo:

*   **Visibilidad del estado del sistema:**
    *   Uso de una animación de carga (*spinner*) en la Pantalla 3 con el texto "Sincronizando la sala".
    *   Indicación visual del progreso mediante un contador de tarjetas restantes en la sesión de votación.
    *   Retroalimentación (*feedback*) inmediata al votar: el borde del panel cambia de color y la tarjeta se desplaza según la acción realizada.
*   **Relación entre el sistema y el mundo real:** Empleo de vocabulario familiar para el público objetivo y la industria del entretenimiento, tales como "Match", "Lista de seguimiento", "Salas de votación" o "Tráiler". Los mensajes de error evitan códigos técnicos e indican el problema de forma explícita.
*   **Control y libertad del usuario:** Inclusión de un botón de cierre explícito (❌) en la esquina superior derecha para cancelar salas o regresar a la pantalla de inicio en cualquier momento previo a la confirmación final.
*   **Consistencia y estándares:** Curva de aprendizaje reducida mediante patrones de diseño ampliamente adoptados:
    *   *Benchmarking* de interacción tipo *Swipe* (deslizar a la derecha para "Me gusta" / izquierda para "No me gusta").
    *   Simbología coherente (❌, 📽️, 🎮) basada en las guías de estilo *Material Design* de Google[2] y *Human Interface Guidelines* de Apple[3].
*   **Reconocer antes que recordar:** Minimización de la carga cognitiva haciendo visibles los objetos y acciones principales. En las salas privadas se muestran los avatares de los usuarios conectados en tiempo real para mantener la visibilidad del grupo.
*   **Prevenir los errores:** 
    *   Restricción del campo de entrada del PIN exclusivamente a caracteres numéricos, manteniendo desactivado el botón "Entrar" hasta completar los dígitos requeridos.
    *   Diálogos de confirmación antes de eliminar o abandonar una sala activa.
*   **Flexibilidad y eficiencia de uso:** Inclusión de atajos de teclado (flecha derecha para *Like*, flecha izquierda para *Dislike*, tecla *Esc* para salir) para acelerar la navegación de usuarios experimentados.
*   **Estética y diseño minimalista:** Interfaz limpia sin elementos distractores. La paleta cromática se limita estrictamente a tres tonos (Negro profundo $\color{#0D0E12}{{●}}$, Gris oscuro $\color{#4A4A4A}{{●}}$ y Violeta neón $\color{#8F00FF}{{●}}$) para centrar la atención en la tarjeta de contenido.
*   **Ayudar en el diagnóstico de errores:** Mensajes claros y descriptivos. Por ejemplo, en lugar de un código de red indeterminado, se muestra: *"PIN incorrecto o la sala ha caducado"*.
*   **Ayuda y documentación:** Presencia de una sección de Preguntas Frecuentes (FAQs) y accesos directos de ayuda (❓) junto a opciones complejas como el filtrado de plataformas.

## 2.1.2 Accesibilidad (Java Accessibility API y WCAG)
La aplicación traslada las interacciones gestuales a mecanismos alternativos accesibles para garantizar su uso mediante tecnologías de asistencia:

*   **Navegación por teclado completa:** La interacción por *Swipe* se mapea mediante las clases `InputMap` y `ActionMap` de Java Swing, permitiendo alternar opciones y votar mediante tabulación y cursores sin necesidad de ratón.
*   **Etiquetado accesible:** Los campos de entrada (como el código PIN) y los botones iconográficos (Corazón, X) cuentan con etiquetas descriptivas accesibles vinculadas mediante la Java Accessibility API (JAAPI)[4].
*   **Cumplimiento WCAG 2.1 (Nivel AA) / UNE-EN 301549[6]:**
    *   Garantía de alto contraste entre texto e interfaz (relación mínima 4.5:1).
    *   Alternativas textuales para todos los elementos visuales y pósters de películas.
    *   Sin dependencia exclusiva del color para comunicar estado o errores (uso combinado de iconos y texto).

# 2.2 Medidas de usabilidad y accesibilidad

Para validar la calidad del software se han fijado estándares normativos, métricas cuantitativas y herramientas especializadas de auditoría.

## Marco Normativo y Estándares
*   **UNE-EN 301549 / Ley 11/2023[6]:** Requisitos de accesibilidad para productos y servicios TIC en la Unión Europea. Obliga a presentar contenidos perceptibles y comprensibles, evitando interacciones accidentales (ej. la aplicación ignora el *doble clic* rápido para evitar votos dobles involuntarios).
*   **UNE-EN ISO 9241-11[7]:** Marco de referencia para evaluar la usabilidad en términos de eficacia, eficiencia y satisfacción del usuario.

## Métricas e Indicadores de Rendimiento (KPIs)
*   **Tiempo de acceso a sala privada:** Objetivo $\le 5$ segundos desde la introducción del PIN o escaneo de QR.
*   **Tiempo de decisión por tarjeta:** Objetivo $\le 3$ segundos por elemento mediante interacción fluida.
*   **Tasa de error de entrada:** Reducción a $0\%$ en la inserción del PIN mediante el bloqueo por máscara de entrada.

## Herramientas de Auditoría y Pruebas
*   **Java Accessibility Utilities / Accessibility Inspector[4]:** Utilidad para verificar la jerarquía de componentes y comprobar que los lectores de pantalla leen correctamente los paneles de Java Swing.
*   **NVDA (NonVisual Desktop Access)[7]:** Lector de pantalla en entorno Windows utilizado para validar la simulación de navegación por voz e invidentes.
*   **FlatLafInspector:** Herramienta de inspección en tiempo real para verificar márgenes, contrastes cromáticos y escalado de fuentes en la interfaz gráfica.


# 2.5 Pautas de aspecto

Para el diseño visual de la aplicación hemos optado por un enfoque oscuro. Nuestro estudio de usuario demuestra que reduce la fatiga visual en sesiones nocturnas y encaja con la estética de las plataformas gaming (Discord, Steam) que usa nuestro público.

## Paleta de Colores (Regla 60-30-10)[1]
*   **Principal (60%) $\color{#0D0E12}{{●}}$ `#0D0E12`:** Negro profundo. Fondo general y detrás de las tarjetas.
*   **Secundario (30%) $\color{#4a4a4a}{{●}}$ `#4a4a4a`:** Gris oscuro. Bordes de los paneles, barras de navegación y botones inactivos.
*   **Acento (10%) $\color{#8F00FF}{{●}}$ `#8F00FF`:** Violeta neón. Destaca el logo, los botones principales, los estados activos (check) y la puntuación.
*   **Legibilidad (WCAG AA)[2]:** Todo el texto sobre fondo oscuro es blanco (`#FFFFFF`) o gris claro para garantizar el contraste. El rojo se reserva exclusivamente para acciones de descarte/cancelación.

## Tipografía
Uso de fuentes sans-serif geométricas (estilo Inter o Roboto):
*   **Negrita:** Para títulos principales ("Stop scrolling", "Dune: Part Two") y botones principales
*   **Semi-negrita:** Para Subtítulos y etiquetas de estado ("Room Code", "Live")
*   **Regular:** Para texto de descripción, detalles de la película y textos secundarios en gris

## Iconografía
Iconos lineales, sencillos y de trazo fino.
*   **Acciones:** Cruz (✗) para indicar que no le gusta,corazón para indicar que te gusta "Like", iconos de QR y enlaces para compartir.
*   **Navegación:** El logo de la app y la X roja situada en la esquina derecha actuan como botón de "Inicio" (Home) para volver a la primera pantalla
*   **Estado:** Puntos verdes para indicar que la sala está abierta y que los usuarios están conectados

## Distribución (Layout)
Diseño basado en una tarjeta para mantener la atención del usuario
* Pantalla 1 (Acceso): Centrada verticalmente con el título principal, subtítulo y una tarjeta (Card) central que agrupa el campo de código PIN, el botón de escanear QR y el botón de crear sala
* Pantalla 2 (Configuración): Columna izquierda con el código de la sala y botones de compartir (enlace, WhatsApp, Discord, panel principal dividido en pasos numerados para filtrar (1. Categoría, 2. Plataformas). En la esquina superior derecha hay una X roja que cancela la sala y devuelve al usuario a la pantalla de inicio
*  Pantalla 3 (Carga): Pantalla de transición centrada, que muestra el logo de la app con un efecto de brillo y un indicador circular de carga y el texto Sincronizando la sala
* Pantalla 4 (Swipe): Enfocada en la tarjeta de contenido, arriba se muestra el estado de los usuarios en la sala y abajo hay dos botones flotantes (X y Corazón) y el texto de ayuda que indica que el corazón es para decir que te gusta y la X para decir que no te gusta
* Pantalla 5 (Match): Aparece al coincidir todos los votos que centra una tarjeta con el texto ¡Hay match!, el póster del título elegido, su información y la plataforma donde está disponible. El fondo incluye un efecto de confeti sutil, arriba a la derecha hay una X para cerrar esta pantalla

## Diseño de componentes
*   **Paneles/Tarjetas:** Fondos oscuros con un borde sutil gris para delimitar las zonas y esquinas redondeadas (radio de 12 a 16 px).
*   **Botones:** Bordes redondeados (8 px) con el botón principal que tiene fondo violeta, los secundarios son transparentes con borde gris y los de acción (X, Corazón) son circulares
*   **Selecciones (Check):** Al elegir una categoría o plataforma, el borde del panel se vuelve violeta y aparece un círculo con un check en la esquina 
*   **Interacción Swipe:** La tarjeta de contenido muestra la plataforma en la esquina superiore y al deslizar, se intuye el cambio a la siguiente tarjeta con un efecto de desvanecimiento

# 2.6 Pautas de componentes visuales

**Propiedades y Métodos:**[3]
*   **Botones:** Métodos para cambiar el texto y bloquearse después de votar
*   **Listas:** Método para leer el filtro seleccionado
*   **Tarjetas:** Métodos para moverse en pantalla (Swipe) y ocultarse

**Eventos y Acciones:**[4]
*   **Swipe:** Eventos de ratón al pulsar, arrastrar y soltar, al soltar, se calcula la dirección para decidir Like (Derecha, corazón) o Dislike (Izquierda, X)
*   **Clics:** Eventos en botones para leer datos (como el PIN) y actualizar la app

**Persistencia:**[5]
*   **En memoria:** Los votos de la sala se guardan en el modelo para no perderse al cambiar de ventana
*   **En disco:** Perfiles y *matches* se guardan en un archivo local para recuperarlos al abrir la app

# Referencias
[1]“La regla 60-30-10 en diseño UX | Torresburriel Estudio”. Blog - UX Torresburriel Estudio. Accedido el 20 de octubre de 2026. [En línea]. Disponible: https://torresburriel.com/weblog/la-regla-60-30-10-en-diseno-ux/

[2]“Web Inclusion GmbH”. Eye-Able. Accedido el 21 de octubre de 2026. [En línea]. Disponible: https://eye-able.com/es/blog/wcag-a-aa-aaa

[3]“Lesson: Using Swing Components (The Java™ Tutorials > Creating a GUI With Swing)”. Moved. Accedido el 21 de octubre de 2026. [En línea]. Disponible: https://docs.oracle.com/javase/tutorial/uiswing/components/index.html

[4]“Lesson: Writing Event Listeners (The Java™ Tutorials > Creating a GUI With Swing)”. Moved. Accedido el 21 de octubre de 2026. [En línea]. Disponible: https://docs.oracle.com/javase/tutorial/uiswing/events/index.html

[5]“Reading, Writing, and Creating Files (The Java™ Tutorials > Essential Java Classes > Basic I/O)”. Moved. Accedido el 21 de octubre de 2026. [En línea]. Disponible: https://docs.oracle.com/javase/tutorial/essential/io/file.html

[6]“UNE-EN 301549:2022 Requisitos de accesibilidad para productos y servicios TIC,” *Asociación Española de Normalización (UNE)*. Accedido el 20 de octubre de 2026. [En línea]. Disponible: https://www.une.org/encuentra-tu-norma/busca-tu-norma/norma?c=N0068037

[7]“UNE-EN ISO 9241-11:2018 Ergonomía de la interacción persona-sistema. Parte 11: Usabilidad,” *Asociación Española de Normalización (UNE)*. Accedido el 20 de octubre de 2026. [En línea]. Disponible: https://www.une.org/encuentra-tu-norma/busca-tu-norma/norma?c=N0060329
