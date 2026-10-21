# 2.5 Pautas de aspecto

Para el diseño visual de la aplicación hemos decidido darle un enfoque oscuro, ya que nuestro estudio de usuario ha hecho que nos demos cuenta de que reduce la fatiga visual en las sesiones de sofá o de noche, y se alinea perfectamente con la estética de las plataformas de gaming (como Discord o Steam) que usa nuestro perfil principal 

Para organizar la interfaz, aplicamos la regla de de color del 60-30-10[1]:

*   **Color Principal (60%) $\color{#0D0E12}{{●}}$ — `#0D0E12`:** Es nuestro "lienzo". Un negro profundo que se utiliza en el fondo general de la aplicación y detrás de las tarjetas. Ya que es el color más utilizado en el mundo de los videojuegos.
*   **Color Secundarios (30%) $\color{#4a4a4a}{{●}}$ — `#4a4a4a`:** Un gris oscuro empleado para crear jerarquía visual. Se usa en barras de navegación, menús secundarios y en el fondo de los botones que no están seleccionados, permitiendo separar elementos sin romper la estética oscura.
*   **Color de Acento (10%) $\color{#8F00FF}{{●}}$ — `#8F00FF`:** Un tono violeta, porque es un color que se relaciona con el gaming.

** Reglas de legibilidad y contraste:**
Para garantizar que la interfaz sea usable y accesible (Norma WCAG AA)[2], establecemos que todo el texto sobre el fondo oscuro debe ser de color **blanco (`#FFFFFF`)** ya que no es ideal utilizar texto oscuro o rojo directamente sobre el fondo negro para evitar problemas de lectura

# 2.6 Pautas de componentes visuales

**Propiedades y Métodos:**[3]
*   **Botones:** Métodos para cambiar el texto y bloquearse después devotar
*   **Listas:** Método para leer el filtro seleccionado
*   **Tarjetas:** Métodos para moverse en pantalla (Swipe) y ocultarse

**Eventos y Acciones:**[4]
*   **Swipe:** Eventos de ratón al pulsar, arrastrar y soltar, Al soltar, se calcula la dirección para decidir Like (Derecha) o Dislike (Izquierda)
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

