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

