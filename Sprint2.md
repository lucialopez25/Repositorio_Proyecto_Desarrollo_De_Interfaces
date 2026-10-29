# 2.1 Usabilidad y Accesibilidad

## 2.1.1 Usabilidad ( Decalogo de Jakob Nielsen)

### 1. Visibilidad del estado del sistema
● Mostrar animación de carga(spinner) al acceder a una sala privada si fuese necesario.  
● Indicar con un contador las tarjetas restantes en la sesión.  
● Al elegir las tarjetas , inidicar visualmente si se ha dado a me gusta o no me gusta. Dar "feeback".

### 2. Relación entre el sistema y el mundo real
Emplear términos propios de la industria de entretenimiento como "Match", "Lista de seguimiento", "Salas de votación" o "Tráiler". En caso de sacar mensajes de error , indicar con texto cual es el problema.

### 3. Control y libertad del usuario
Implementar botones de cierre (❌ ) intuitivos para cada pestaña (arriba a la derecha). Facilitar el cierre de una sala privada , al acceder antes de poner el pin/QR y cuando se está escogiendo tarjetas también.

### 4. Consistencia y estándares
Diseñar la app con curva de aprendizaje muy rápida :  
● "Benchmarking" de la elección de tarjetas(como el swipe en Tinder) :  
  * hacia la derecha (sí/me gusta)  
  * hacia la izquierda (no/no me gusta)  
● Usar iconos parecidos en todas las pestañas ❌, 📽️ , 🎮 (buscar iconos en Flaticon,Iconfinder...)  
● Hacer uso de las guias de estilo de iconos (Human Interface Guidelines de Apple y Material Design de Google)

### 5. Reconocer antes que recordar
Minimizar la carga de memoria del usuario haciendo que los objetos, las acciones y las opciones estén visibles.  
En las salas privadas, mostrar avatares de los miembros conectados en tiempo real para recordar quiénes están participando.

### 6. Prevenir los errores
Al ingresar el PIN de una sala privada, limitar el teclado a solo caracteres numéricos y bloquear el botón "Entrar" hasta que se hayan completado los digitos requeridos. Solicitar confirmación antes de eliminar una sala privada.

### 7. Flexibilidad y eficiencia de uso
Ofrecer facilidades para los nuevos usuarios , como atajos de teclado mediante combinación de teclas.

### 8. Estética y diseño minimalista
Uso mínimo de la paleta de color , solo 3 colores : Fondo Negro, Gris Carbón y Violeta Eléctrico, cumpliendo con contraste marcado.  
* **#8F00FF ●** : Color para contrastar, resaltar visualmente y marcar botones .  
* **#000000 ●** : Color base.  
* **#36454F ●** : Color de contraste ligero.  
Usar fuentes legibles como Inter,Roboto,Open sans.

### 9. Ayudar en el diagnóstico del error
Ser claro y conciso con los mensajes para el usuario:  
● Si falla la conexión al introducir el PIN de una sala, mostrar un mensaje claro como "PIN incorrecto o la sala ha caducado."  
● "El enlace específico no existe o ya no está disponible en esa dirección." en vez de "Error 404: Not Found"

### 10. Ayuda y documentación
Implementar una opción de FAQs (Frequently Asked Questions) o simbolo de (❓) cerca de algunas opciones.

---

## 2.1.2 Accesibilidad
Para implementar estos puntos en código Java Swing, utilizar la Java Accessibility API (JAAPI) y las directrices de la Web Content Accessibility Guidelines (WCAG)  
El gesto de elección de tarjetas debe traducirse a una interacción por teclado fluida, estándar y totalmente accesible.  
Para la función de unirse a una sala privada con PIN, los campos de entrada deben tener etiquetas vinculadas correctamente mediante la API de accesibilidad.

### Navegación e Interacción por Teclado (InputMap y ActionMap)
En la Web y Apps (UNE-EN 301549 → WCAG 2.1):  
Si se exige cumplir la UNE-EN 301549, en la práctica se comprueba que el sitio cumpla las pautas WCAG 2.1 en su nivel AA (como el contraste de color, la navegación completa mediante teclado o la presencia de alternativas textuales.

---

# 2.2 Medidas de usabilidad y accesibilidad

### Medidas accesibilidad :
Estandar de referencia WCAG(Web Content Accesibility Guidelines)  
Con tres niveles de conformidad: A(fundamentos básicos), AA(estandar global) y AAA(estandar más alto). Relevante para España y la UE .  
* **[1]UNE-EN 301549** : Norma que fija los requisitos de accesibilidad para productos y servicios TIC. Pertenece a la normalización española.  
  - doble click accidental no debería votar dos tarjetas  
  - evitar combinaciones complejas(si vamos a permitir atajos en la app)  
* **Ley 11/2023** : Base técnica de referencia heredada de la Directiva europea que obliga a que las aplicaciones de las empresas sean accesibles.  
  - mensajes de error perceptibles y comprensibles.  
  - texto e imagenes claras.

### Medidas usabilidad :
Son los criterios e indicadores que sirven para evaluar qué tan fácil, eficiente y satisfactorio es usar un producto.  
* **[2]UNE-EN ISO 9241-11** : Parte de la familia ISO 9241(Ergonomia interaccion hombre-sistema) que define la usabilidad.  
  - tiempo de acceso sala privada < 5s  
  - tiempo elección por tarjeta <= 3s  
* **Decálogo de Jakob Nielsen** : (más info en 2.1)

### Herramientas auditoría :
Programas o servicios que analizan automática o manualmente un sitio para detectar problemas. Usar :  
Java Accesibility Utilities(clases e interfaces) , FlatLafInspector(inspectores/herramientas debugging)  
(AWTEventMonitor SwingEventMonitor AccessibilityEventMonitor EventQueueMonitor EventID AccessibilityListenerList Translator)

### Referencias :
* **[1]UNE-EN 301549:2022** Requisitos de accesibilidad para productos ....https://www.une.org/encuentra-tu-norma/busca-tu-norma/norma?c=N0068037  
* **[2]UNE-EN ISO 9241-11:2018 (Ratificada)** Ergonomía de la interacci....https://www.une.org/encuentra-tu-norma/busca-tu-norma/norma?c=N0060329

---

# 2.3. SEGUIMIENTO, MODIFICACIÓN Y DOCUMENTACIÓN DE LOS ESQUEMAS (WIREFRAMES) Y MAQUETAS (MOCKUPS)

## 2.3.1. Metodología de Prototipado e Historial de Iteración
La transición entre esquemas de baja fidelidad y maquetas definitivas se ha guiado por los resultados de las pruebas de usabilidad y la aplicación de la Evaluación Heurística de Jakob Nielsen. Esta metodología consiste en un sistema de inspección de usabilidad donde se evalúa la interfaz frente a un decálogo de principios o "heurísticas" de diseño de interacción (como la visibilidad del estado del sistema, el control y libertad del usuario, la prevención de errores o la consistencia). Su objetivo es identificar, categorizar y resolver problemas de usabilidad de forma rápida y sistemática durante la fase de diseño, garantizando una experiencia intuitiva sin depender de pruebas complejas con usuarios finales en etapas tempranas.

## 2.3.2. Registro y Documentación de Modificaciones (Changelog de UI/UX)
A continuación se detallan las modificaciones específicas realizadas sobre la interfaz tras la revisión de usabilidad y accesibilidad:

### 1. Navegación Global y Cabecera Persistente
* **Interactividad del Branding:** Se eliminó el botón independiente con icono de casa (Home) situado en la esquina superior izquierda. En su lugar, el logotipo/marca de agua de texto "CoSwipe" se convirtió en un componente interactivo permanente; al hacer clic en él desde cualquier pantalla, redirige al usuario a la pantalla de inicio.
* **Acceso de Salida Global (Botón Cierre ❌):** Se sustituyó el texto plano "Leave Room" (ubicado originalmente abajo a la izquierda) por un botón destacado de color rojo con un icono de "X" blanca en la esquina superior derecha. Este botón es visible en todas las pantallas excepto en la de inicio, ofreciendo una vía de escape rápida e intuitiva.
* **Depuración de Elementos Redundantes:** Se eliminó el texto "No account needed" de la esquina superior derecha en la pantalla inicial para limpiar la cabecera.
* **Selector de Idioma Interactivo:** Se integró en la cabecera un control desplegable (Globe / Flag icon) permanente e interactivo que permite alternar la interfaz entre Español (ES) e Inglés (EN) en tiempo real.

### 2. Pantalla de Configuración y Creación de Sala (Create Room)
* **Canales de Compartición Social:** Se reemplazaron los iconos genéricos junto al botón "Copy Link" por los logotipos oficiales de WhatsApp y Discord, facilitando el reconocimiento inmediato por parte de los usuarios
* **Filtros Dinámicos por Categoría:**
  * **Películas y Series:** Se integró un selector de plataformas de streaming (Netflix, Prime Video, Disney+, Max, Hulu, Apple TV, Movistar) y un filtro secundario desplegable por géneros (Acción, Comedia, Drama, Sci-Fi, etc.).
  * **Videojuegos:** Se habilitó un selector de plataformas específicas (PlayStation, Epic Games, Nintendo, Steam) complementado con un filtro de géneros y modos (Co-Op, Multijugador, RPG, Shooter, etc.).
* **Eliminación de Filtros Complejos:** Se eliminó por completo la casilla de selección "How much time do you have?" para agilizar la configuración inicial y reducir la carga mental del anfitrión.

### 3. Pantalla de Votación Gestual (Swipe Deck)
* **Rediseño Tipográfico del Encabezado:** Se aumentó significativamente el tamaño y peso visual del bloque de texto principal ("Movie night / What's the verdict? / Swipe right if you're in. We'll find the one everyone loves.") para mejorar la jerarquía visual y la legibilidad en entornos oscuros.
* **Controles de Acción "PASS" y "LIKE":** Se escalaron las etiquetas de texto "PASS" (Rojo #EF4444) y "LIKE" (Verde #22C55E) situadas en los botones de votación para garantizar una respuesta clara e inconfundible.
* **Limpieza de Interfaz:** Se retiró el contador de tarjetas restantes ("pick lefts") de la esquina superior derecha para no generar ansiedad de tiempo durante el proceso de elección.

### 4. Pantalla de Coincidencia (Match Screen) y Transiciones
* **Simplificación de la Card Ganadora:** En la pantalla de resultado (Match), se eliminó la puntuación numérica/estrellitas ("★ 8.5/10") enfocando la atención del usuario en la carátula, el título y la plataforma de consumo inmediato.
* **Incorporación de Pantallas de Carga (Loading Overlay):** Se implementó un estado intermedio de carga con una animación síncrona (spinner en tono Violeta Eléctrico #7C3AED sobre fondo #0D0E12) con una duración de 800ms a 1200ms para simular de forma realista la sincronización entre dispositivos

## 2.3.3. Documentación Estructural de las Maquetas Definitivas
La interfaz de CoSwipe se estructura en torno a una disposición fija y persistente propia de una aplicación de escritorio, organizada en modo oscuro nativo bajo el sistema cromático 60-30-10 (#0D0E12 Fondo base, #1A1C23 Tarjetas/Superficies, #7C3AED Acento/CTAs). El diseño contempla una barra de navegación superior fija en todas las pantallas. En el extremo izquierdo se ubica el logotipo interactivo "CoSwipe" que actúa como retorno al inicio, mientras que en el extremo derecho se sitúan el selector de idioma y el botón global de cierre (❌). Debajo de esta cabecera persistente se despliega el área de trabajo central, la cual transmuta dinámicamente según la fase de uso en la que se encuentre la sesión: la bienvenida, el panel de configuración de filtros, la sala de espera o lobby, la mesa interactiva de votación por deslizamiento y la pantalla de coincidencia unánime.

### Descripción de Pantallas Clave
* **Pantalla 1: Welcome / Home Screen**
  * **Controles:** Marca interactiva "CoSwipe", selector de idioma EN/ES, botón primario "Create Room" (#7C3AED), botón secundario "Join with PIN", y lector QR.
  * **Objetivo:** Garantizar acceso Zero-Friction en menos de 5 segundos sin registro.
* **Pantalla 2: Room Creation & Filter Setup**
  * **Controles:** Selector de categoría (Películas, Series, Videojuegos), rejilla de chips para plataformas (Netflix, Steam, etc.), desplegable de géneros, botón de copiado de enlace con accesos directos a WhatsApp/Discord.
  * **Objetivo:** Acotar el catálogo de forma visual y rápida.
* **Pantalla 3: Active Lobby Screen**
  * **Controles:** Código PIN de 4 dígitos en formato destacado, código QR visible para escaneo presencial, lista dinámica de avatares conectados y botón "Start Swiping Now".
* **Pantalla 4: Interactive Swipe Deck Screen**
  * **Controles:** Encabezado con tipografía adaptada, tarjeta central con carátula e información relevante (sin indicador de cartas restantes), botones inferiores circulares de "PASS" (Rojo) y "LIKE" (Verde) con etiquetas aumentadas, y botón global de salida (❌) en la esquina superior derecha.
* **Pantalla 5: Unanimous Match Screen**
  * **Controles:** Tarjeta destacada con el título ganador (sin estrellas de valoración), distintivo de unanimidad 100%, indicación directa de la plataforma disponible y botón de acción principal para ir al contenido.

## 2.3.4. Trazabilidad entre Modificaciones y Estándares de Usabilidad/Accesibilidad
Para fundamentar el trabajo de refinamiento de la interfaz de CoSwipe, cada una de las decisiones de diseño y modificación visual se ha articulado directamente en torno a los principios teóricos de la Evaluación Heurística de Jakob Nielsen, garantizando una experiencia de usuario sólida, intuitiva y coherente.

En primer lugar, la transformación del logotipo de texto "CoSwipe" en un elemento interactivo permanente que actúa como enlace de retorno a la pantalla inicial aplica de forma directa la heurística de Consistencia y Estándares (Nielsen #4), al respetar el modelo mental y el comportamiento de navegación universal al que están habituados los usuarios en las aplicaciones informáticas modernas. Asimismo, la integración global del botón de salida mediante una "X" blanca sobre fondo rojo en la esquina superior derecha proporciona una "salida de emergencia" clara y accesible en todo momento, satisfaciendo la heurística de Control y Libertad del Usuario (Nielsen #3) al permitir abandonar o cancelar una sesión sin generar incertidumbre.

En segundo lugar, la sustitución de los iconos genéricos de compartir por los logotipos oficiales de WhatsApp y Discord se respalda en la heurística de Relación entre el Sistema y el Mundo Real (Nielsen #2), la cual establece que el sistema debe expresarse mediante conceptos, símbolos y marcas familiares para el usuario en lugar de gráficos abstractos. De igual manera, la reorganización del panel de creación de sala mediante filtros agrupados dinámicamente por plataformas y géneros satisface la heurística de Reconocer antes que recordar (Nielsen #5), al reducir la carga de memoria del usuario exponiendo las opciones disponibles de forma clara y organizada.

Por último, el rediseño tipográfico de las acciones centrales "PASS" y "LIKE", incrementando su tamaño de fuente y asegurando un alto contraste cromático en tonos rojo y verde, se apoya en la heurística de Estética y Diseño Minimalista (Nielsen #8) al eliminar ambigüedades visuales y enfocar la atención en la toma de decisiones. Finalmente, la incorporación del estado de carga con una animación de spinner en las transiciones entre ventanas da respuesta a la heurística de Visibilidad del Estado del Sistema (Nielsen #1), ofreciendo al usuario una retroalimentación visual continua sobre la latencia y la sincronización de la sesión compartida en tiempo real.

---

# 2.4. PAUTAS DE DISEÑO ESTRUCTURAL: MENÚS, VENTANAS, CUADROS DE DIÁLOGO Y ATAJOS DE TECLADO

El diseño estructural de CoSwipe establece el marco visual, navegacional y organizativo de la aplicación de escritorio desarrollada en Java Swing con el tema FlatLaf Dark. Su objetivo principal es ofrecer una experiencia utilitaria de baja carga cognitiva, predecible y optimizada para la toma de decisiones grupales en tiempo real.

---

## 2.4.1. Estructura de Ventanas y Arquitectura Modular (5 JFrame Forms)

Para garantizar un desarrollo mantenible, modular y fiel al prototipo pixel-perfect diseñado en Figma, la aplicación de escritorio se estructura en 5 formularios de ventana independientes (JFrame Form), cada uno correspondiente a un hito clave dentro del flujo de usuario:

```text
CoSwipe (Aplicación Desktop Swing)
├── 1. Pantalla de Inicio y Bienvenida (JFrame Form)
├── 2. Pantalla de Configuración y Filtros de Sala (JFrame Form)
├── 3. Pantalla de Carga y Lobby de Espera (JFrame Form)
├── 4. Pantalla de Elección y Mesa de Votación (JFrame Form)
└── 5. Pantalla de Resultado Unánime / Match (JFrame Form)
```

### Patrón Estructural Homogéneo
Todas las ventanas implementan una maquetación jerárquica estandarizada mediante la combinación de gestores de diseño nativos de Swing (BorderLayout, BoxLayout y GridBagLayout):

1. **Panel de Cabecera Superior:**
   * **Gestor de Diseño:** BorderLayout.
   * **Ubicación:** Posición NORTH fija en el contenedor principal (JFrame Form).
   * **Contenido:**
     * **Zona Izquierda (WEST):** Logotipo interactivo de la aplicación mediante una etiqueta (JLabel) estilizada con tipografía en negrita e icono representativo.
     * **Zona Derecha (EAST):** Panel contenedor (JPanel) que aloja un selector desplegable (JComboBox) para la alternancia de idioma y, a partir de la segunda pantalla, el botón global de abandono/salida (JButton) resaltado en color rojo (#EF4444) con un icono de cierre (❌). En pantallas específicas como la Mesa de Votación, integra adicionalmente un indicador visual de participantes activos.

2. **Panel Cuerpo Central:**
   * **Gestor de Diseño:** GridBagLayout en el nivel externo para garantizar el centrado automático absoluto respecto a la resolución del monitor, combinado con BoxLayout (eje vertical Y_AXIS) en los subpaneles internos.
   * **Organización en Subpaneles Funcionales:**
     * **Panel Encabezado / Hero (JPanel):** Contiene etiquetas informativas (JLabel) destinadas al distintivo de categoría, títulos principales y descripciones explicativas.
     * **Panel Tarjeta Principal (JPanel):** Ficha contenedora con bordes redondeados y fondo de contraste elevado (#1A1C23) que agrupa la interacción principal (formularios de código, pósteres de contenido, rejillas de opciones o códigos QR).
     * **Panel Pie de Acción (JPanel):** Espacio inferior reservado para etiquetas de notas informativas (JLabel), separadores decorativos (JLabel) y botones de comando primarios/secundarios (JButton).

---

## 2.4.2. Documentación Detallada de las 5 Pantallas de CoSwipe

### 1. Pantalla de Inicio / Bienvenida (JFrame Form)
<img width="1100" height="829" alt="image" src="https://github.com/user-attachments/assets/a401690a-4704-4f09-b5f3-56e0f45b5f70" />

* **Objetivo:** Permitir el acceso inmediato introduciendo un PIN de sala de 6 dígitos o iniciando la creación de una sala instantánea.
* **Estructura de Layouts:**
  * **Panel Superior (BorderLayout):** Muestra la etiqueta del logotipo (JLabel) y el selector desplegable de idioma (JComboBox). Se excluye deliberadamente el botón de salida, ya que en esta etapa inicial no existe una sesión activa que abandonar.
  * **Panel Central (GridBagLayout + BoxLayout):** Tarjeta central centrada de 560×430 px.
* **Componentes Principales:**
  * **Etiqueta Distintiva (JLabel):** Etiqueta superior con el texto "DECIDE TOGETHER, INSTANTLY".
  * **Campo de Texto PIN (JTextField):** Campo de entrada estilizado con tipografía monospaced de gran formato para la inserción del código numérico (0 0 0 0 0 0).
  * **Botón Escanear QR (JButton):** Botón secundario para la alternativa de acceso mediante código.
  * **Botón Unirse a Sala (JButton):** Botón primario destacado en Violeta Eléctrico (#7C3AED) para procesar el acceso a la sesión.
  * **Botón Crear Sala Instantánea (JButton):** Botón con borde resaltado para iniciar una nueva sesión directa.

### 2. Pantalla de Creación de Sala (JFrame Form)
<img width="1910" height="993" alt="image" src="https://github.com/user-attachments/assets/fe4f4c97-6b68-43dc-832d-67b255c9c6fa" />
<img width="1897" height="995" alt="image" src="https://github.com/user-attachments/assets/6d02a81d-e2e1-4db6-bd5c-c88006489611" />

* **Objetivo:** Configurar los parámetros de la sesión mediante la selección de tipo de contenido, catálogo de plataformas y filtros de género.
* **Estructura de Layouts:**
  * **Panel Superior (BorderLayout):** Incluye un botón de retorno al inicio (JButton), la etiqueta del logotipo (JLabel) y el botón rojo de salida (JButton).
  * **Panel Central (BoxLayout vertical):** Organizado en bloques temáticos delimitados dentro de paneles contenedores.
* **Componentes Principales:**
  * **Contenedor de Categorías (JPanel con FlowLayout):** Agrupa botones conmutables (JToggleButton) para alternar entre "Películas", "Series" y "Videojuegos".
  * **Contenedor de Plataformas (JPanel con GridLayout):** Rejilla de fichas interactivas (JPanel o JToggleButton) con los logos y nombres de plataformas disponibles (Netflix, Prime Video, HBO Max, Disney+, Steam, etc.).
  * **Desplegable de Género (JComboBox):** Menú desplegable contextual para la filtración por géneros (Acción, Terror, Sci-Fi, Comedia).
  * **Botón Iniciar Sesión (JButton):** Comando primario de gran tamaño para generar la sala y avanzar al Lobby.

### 3. Pantalla de Carga / Lobby de Espera (JFrame Form)
<img width="1075" height="710" alt="image" src="https://github.com/user-attachments/assets/1b85d9cb-068d-4d09-83f3-1e064c8b847c" />

* **Objetivo:** Mostrar el punto de encuentro previo a la votación, proporcionando el código PIN de acceso y el código QR visual de la sesión.
* **Estructura de Layouts:**
  * **Panel Superior (BorderLayout):** Muestra la cabecera activa con el identificador de la sala creada.
  * **Panel Central (GridBagLayout):** Mantiene en el centro la tarjeta receptora de participantes.
* **Componentes Principales:**
  * **Contenedor de Código QR (JLabel con ImageIcon):** Renderizado del código QR generado para su escaneo desde dispositivos móviles.
  * **Etiqueta de PIN (JLabel):** Muestra el código de la sala en formato texto resaltado para su fácil lectura o copia.
  * **Lista de Participantes (JList / JPanel con BoxLayout):** Muestra el listado de miembros conectados a la sala en tiempo real.
  * **Botón Iniciar Votación (JButton):** Botón habilitado para el anfitrión (Host) que desencadena el inicio sincronizado de la selección.

### 4. Pantalla de Elección / Mesa de Votación (JFrame Form)
<img width="1045" height="838" alt="image" src="https://github.com/user-attachments/assets/243ed579-594e-46bf-802c-09685f283a57" />

* **Objetivo:** Presentar las fichas individuales de contenido e integrar los controles informativos y de interacción gestual (Swipe).
* **Estructura de Layouts:**
  * **Panel Superior (BorderLayout):** Cabecera enriquecida que incluye el logotipo (JLabel), la etiqueta del contador de participantes en vivo (JLabel) y el botón de salida (JButton).
  * **Panel Central (BorderLayout / GridBagLayout):** Aloja la tarjeta multimedia central y los botones inferiores de decisión.
* **Componentes Principales:**
  * **Tarjeta Multimedia (JPanel con BorderLayout):** Contenedor de la carátula o póster (JLabel), título del contenido (JLabel), sinopsis y metadatos (JLabel).
  * **Botón Descartar / PASS (JButton):** Botón circular de gran formato ubicado a la izquierda, estilizado en color Rojo Error (#EF4444).
  * **Botón Aceptar / LIKE (JButton):** Botón circular de gran formato ubicado a la derecha, estilizado en color Verde Éxito (#22C55E).

### 5. Pantalla de Resultado Unánime / Match (JFrame Form)
<img width="1126" height="852" alt="image" src="https://github.com/user-attachments/assets/8652b0b6-d5c5-4c57-8314-9b51d07016dd" />

* **Objetivo:** Celebrar la coincidencia del grupo al alcanzar el 100% de votos positivos sobre una misma opción.
* **Estructura de Layouts:**
  * **Panel Superior (BorderLayout):** Cabecera estándar de sesión activa.
  * **Panel Central (GridBagLayout):** Presentación centrada de la tarjeta ganadora reforzada con elementos de felicitación visual.
* **Componentes Principales:**
  * **Etiqueta de Coincidencia (JLabel):** Etiqueta festiva con el mensaje "IT'S A MATCH!".
  * **Póster Ganador (JLabel):** Imagen a alta resolución del contenido seleccionado de forma unánime.
  * **Botón Abrir Plataforma (JButton):** Botón primario de acceso directo para reproducir o ver el contenido en la plataforma correspondiente.
  * **Botón Nueva Ronda (JButton):** Botón secundario para iniciar una nueva selección sin abandonar el grupo.

---

## 2.4.3. Estructura de Menús, Acciones y Distribución Contextual
En cumplimiento del principio de usabilidad Zero-Friction, la interfaz elimina las barras de menús flotantes o desplegables tradicionales, redistribuyendo las acciones de forma contextual y directamente visible en pantalla:
* **Acciones de Navegación Global:** Concentradas en la barra superior del panel principal. La etiqueta del logotipo (JLabel) permite el retorno a la pantalla inicial, el menú desplegable (JComboBox) aplica la traducción inmediata de la UI mediante recursos i18n, y el botón de cierre (JButton) proporciona una vía explícita de salida en cualquier punto del flujo de uso.
* **Acciones de Selección y Filtro:** Organizadas en barras de botones conmutables (JToggleButton) y menús desplegables (JComboBox) integrados directamente en las tarjetas de la pantalla de creación.
* **Acciones de Decisiones Cruciales:** Representadas mediante botones de comando (JButton) de alto contraste visual (colores semánticos Rojo #EF4444 y Verde #22C55E), posicionados de manera fija en el pie de las tarjetas para minimizar la distancia de desplazamiento del cursor (Ley de Fitts).

---

## 2.4.4. Cuadros de Diálogo y Notificaciones Modales
Los cuadros de diálogo (ventanas modales JDialog estilizadas con el tema oscuro FlatLaf) se limitan estrictamente a situaciones de confirmación de alto impacto o resolución de incidencias:
* **Diálogo de Confirmación de Salida (Leave Room Modal):** Se dispara al presionar el botón rojo de cierre (❌). Bloquea la interacción con la ventana principal hasta que el usuario confirme o cancele la acción, evitando desconexiones involuntarias en mitad de una votación.
* **Gestión de Notificaciones y Estado de Red:** Ante eventualidades como la introducción de un código de sala inexistente, pérdida de conexión con el servidor o expiración de la sesión, el sistema despliega cuadros modales informativos (JDialog) redactados con lenguaje claro y orientado a soluciones humanas, excluyendo trazas de error de software o códigos técnicos incomprensibles.
* **Aclaración sobre el Uso de Códigos QR:** La aplicación de escritorio proyecta visualmente el código QR en la pantalla del Lobby para facilitar la incorporación de participantes desde dispositivos móviles. La función interactiva de captura mediante cámara web se deshabilita deliberadamente en la versión de escritorio por restricciones de hardware y usabilidad, reservándose para el cliente móvil.

---

## 2.4.5. Navegación e Interacción por Teclado (Atajos y Accesibilidad)
En consonancia con las pautas WCAG 2.1 (Nivel AA) y la norma europea UNE-EN 301549, la interfaz garantiza la operatividad completa mediante teclado utilizando las colecciones InputMap y ActionMap de Java Swing:
* **Flecha Izquierda (←) / Tecla A:** En la Mesa de Votación, ejecuta la acción de descartar o votar de forma negativa sobre la tarjeta de contenido activa (equivalente al botón PASS).
* **Flecha Derecha (→) / Tecla D:** En la Mesa de Votación, ejecuta la acción de aceptar o votar de forma positiva sobre la tarjeta de contenido activa (equivalente al botón LIKE).
* **Tecla Enter:** En formularios y cuadros modales, confirma la acción primaria por defecto (unirse a la sala tras ingresar el código, confirmar la creación o aceptar un mensaje informativo).
* **Tecla Escape (Esc):** En toda la aplicación, abre el diálogo modal de confirmación de salida o cierra cuadros modales emergentes activos.
* **Tecla Tab / Shift + Tab:** En todos los formularios y pantallas, recorre de forma secuencial y ordenada cada uno de los elementos interactivos (campos de texto, botones y desplegables), destacando el foco visual mediante un borde resaltado en tono Violeta Eléctrico (#7C3AED).

---

# 2.5 Pautas de aspecto

Para el diseño visual de la aplicación hemos optado por un enfoque oscuro. Nuestro estudio de usuario demuestra que reduce la fatiga visual en sesiones nocturnas y encaja con la estética de las plataformas gaming (Discord, Steam) que usa nuestro público.

### Paleta de Colores (Regla 60-30-10)[1]
* **Principal (60%) ● #0D0E12:** Negro profundo. Fondo general y detrás de las tarjetas.
* **Secundario (30%) ● #4a4a4a:** Gris oscuro. Bordes de los paneles, barras de navegación y botones inactivos.
* **Acento (10%) ● #8F00FF:** Violeta neón. Destaca el logo, los botones principales, los estados activos (check) y la puntuación.
* **Legibilidad (WCAG AA)[2]:** Todo el texto sobre fondo oscuro es blanco (#FFFFFF) o gris claro para garantizar el contraste. El rojo se reserva exclusivamente para acciones de descarte/cancelación.

### Tipografía
Uso de fuentes sans-serif geométricas (estilo Inter o Roboto):
* **Negrita:** Para títulos principales ("Stop scrolling", "Dune: Part Two") y botones principales
* **Semi-negrita:** Para Subtítulos y etiquetas de estado ("Room Code", "Live")
* **Regular:** Para texto de descripción, detalles de la película y textos secundarios en gris

### Iconografía
Iconos lineales, sencillos y de trazo fino.
* **Acciones:** Cruz (✗) para indicar que no le gusta,corazón para indicar que te gusta "Like", iconos de QR y enlaces para compartir.
* **Navegación:** El logo de la app y la X roja situada en la esquina derecha actuan como botón de "Inicio" (Home) para volver a la primera pantalla
* **Estado:** Puntos verdes para indicar que la sala está abierta y que los usuarios están conectados

### Distribución (Layout)
Diseño basado en una tarjeta para mantener la atención del usuario
* **Pantalla 1 (Acceso):** Centrada verticalmente con el título principal, subtítulo y una tarjeta (Card) central que agrupa el campo de código PIN, el botón de escanear QR y el botón de crear sala
* **Pantalla 2 (Configuración):** Columna izquierda con el código de la sala y botones de compartir (enlace, WhatsApp, Discord, panel principal dividido en pasos numerados para filtrar (1. Categoría, 2. Plataformas). En la esquina superior derecha hay una X roja que cancela la sala y devuelve al usuario a la pantalla de inicio
* **Pantalla 3 (Carga):** Pantalla de transición centrada, que muestra el logo de la app con un efecto de brillo y un indicador circular de carga y el texto Sincronizando la sala
* **Pantalla 4 (Swipe):** Enfocada en la tarjeta de contenido, arriba se muestra el estado de los usuarios en la sala y abajo hay dos botones flotantes (X y Corazón) y el texto de ayuda que indica que el corazón es para decir que te gusta y la X para decir que no te gusta
* **Pantalla 5 (Match):** Aparece al coincidir todos los votos que centra una tarjeta con el texto ¡Hay match!, el póster del título elegido, su información y la plataforma donde está disponible. El fondo incluye un efecto de confeti sutil, arriba a la derecha hay una X para cerrar esta pantalla

### Diseño de componentes
* **Paneles/Tarjetas:** Fondos oscuros con un borde sutil gris para delimitar las zonas y esquinas redondeadas (radio de 12 a 16 px).
* **Botones:** Bordes redondeados (8 px) con el botón principal que tiene fondo violeta, los secundarios son transparentes con borde gris y los de acción (X, Corazón) son circulares
* **Selecciones (Check):** Al elegir una categoría o plataforma, el borde del panel se vuelve violeta y aparece un círculo con un check en la esquina
* **Interacción Swipe:** La tarjeta de contenido muestra la plataforma en la esquina superiore y al deslizar, se intuye el cambio a la siguiente tarjeta con un efecto de desvanecimiento

### Referencias
* **[1]** “La regla 60-30-10 en diseño UX | Torresburriel Estudio”. Blog - UX Torresburriel Estudio. Accedido el 20 de octubre de 2026. [En línea]. Disponible: https://torresburriel.com/weblog/la-regla-60-30-10-en-diseno-ux/
* **[2]** “Web Inclusion GmbH”. Eye-Able. Accedido el 21 de octubre de 2026. [En línea]. Disponible: https://eye-able.com/es/blog/wcag-a-aa-aaa

---

# 2.6. Pautas de componentes visuales

Los componentes visuales de CoSwipe se organizarán según las funciones de cada pantalla, manteniendo un diseño homogéneo y una navegación sencilla. Se utilizarán botones, tarjetas, campos de texto, indicadores de carga y elementos interactivos que permitan a los usuarios crear salas y decidir en grupo qué películas, series o videojuegos quieren elegir.

## 2.6.1. Pantalla de inicio

### Propiedades y métodos:
* **Botones:** Permitirán acceder a las opciones principales de la aplicación, como crear una sala o unirse a una existente. Su texto y estado podrán actualizarse según la acción realizada.
* **Campos de texto:** Se utilizarán para introducir los datos necesarios para acceder a una sala, cuando corresponda.
* **Elementos visuales:** El logotipo, los textos y los iconos mantendrán la imagen corporativa definida en el Sprint 1.

### Eventos y acciones:
* **Clics:** Al pulsar un botón, se abrirá la pantalla correspondiente.
* **Validación:** Antes de continuar, se comprobará que los datos introducidos sean válidos y que no estén vacíos cuando sean obligatorios.
* **Mensajes:** Se mostrarán avisos claros cuando falte algún dato o se produzca un error.

### Persistencia:
* **En memoria:** Se conservará temporalmente la información necesaria para mantener el estado de la navegación.
* **En Firebase:** No será necesario guardar cada acción realizada en la pantalla de inicio. Los datos se almacenarán cuando el usuario realice operaciones que requieran persistencia.

## 2.6.2. Pantalla de creación de sala

Esta pantalla permitirá configurar una sala y seleccionar el tipo de contenido que se utilizará durante la votación: videojuegos o películas y series.

### Propiedades y métodos:
* **Botones:** Permitirán seleccionar el tipo de contenido y confirmar la creación de la sala. Su apariencia cambiará para indicar la opción seleccionada.
* **Campos de selección:** Facilitarán la elección entre videojuegos y películas o series.
* **Campos de configuración:** Recogerán los datos necesarios para preparar la sala, según las opciones definidas en el diseño.
* **Código o PIN:** Una vez creada la sala, se mostrará el código necesario para que otros participantes puedan unirse.

### Eventos y acciones:
* **Selección:** Al pulsar una opción, se actualizará el tipo de contenido seleccionado.
* **Clics:** Al confirmar la creación, se validarán los datos y se solicitará a Firebase la creación de la sala.
* **Confirmación:** Si la operación se completa correctamente, se mostrará el código de acceso y se permitirá continuar al siguiente paso.
* **Errores:** Si falla la conexión o no se puede crear la sala, se mostrará un mensaje y se permitirá volver a intentarlo.

### Persistencia:
* **En memoria:** Se conservarán temporalmente las opciones seleccionadas mientras se configura la sala.
* **En Firebase:** Se guardarán los datos necesarios de la sala en Cloud Firestore, incluido el tipo de contenido y el código de acceso, para que los participantes puedan recuperarlos.

## 2.6.3. Pantalla de decisión

Esta será la pantalla principal de votación. Mostrará tarjetas con el contenido disponible y permitirá indicar si gusta o no mediante gestos o botones.

### Propiedades y métodos:
* **Tarjetas:** Mostrarán la imagen, el título y la información principal de cada película, serie o videojuego. Podrán desplazarse, ocultarse o sustituirse después de votar.
* **Botones de votación:** Permitirán aceptar o rechazar el contenido mediante iconos reconocibles, como un corazón para indicar que gusta y una X para rechazarlo.
* **Indicadores de estado:** Mostrarán información sobre el progreso de la votación o las acciones realizadas cuando resulte necesario.
* **Controles de navegación:** Permitirán abandonar la votación o volver a la pantalla anterior cuando corresponda.

### Eventos y acciones:
* **Swipe:** Al pulsar y arrastrar una tarjeta, se detectará la dirección del movimiento. Al soltarla, un desplazamiento hacia la derecha representará un Like y uno hacia la izquierda un Dislike.
* **Clics:** Los botones de votación ejecutarán la misma acción que los gestos.
* **Actualización:** Después de registrar un voto, la tarjeta actual desaparecerá y se mostrará el siguiente contenido.
* **Control de acciones:** Se evitará registrar varias veces el mismo voto por pulsaciones repetidas o gestos duplicados.
* **Sincronización:** Se actualizará la información de la sala para que las decisiones de los participantes puedan tenerse en cuenta al determinar el resultado común.

### Persistencia:
* **En memoria:** Se mantendrán temporalmente los datos de la tarjeta actual y el estado de la interfaz para evitar reiniciar la pantalla con cada acción.
* **En Firebase:** Los votos se asociarán a la sala y al contenido correspondiente en Cloud Firestore, permitiendo conservarlos y sincronizarlos entre los participantes.
* **Recuperación:** Si un usuario vuelve a entrar en la sala, se consultará la información guardada para continuar la votación según el estado disponible.

## 2.6.4. Pantalla de carga

La pantalla de carga aparecerá durante las operaciones que necesiten tiempo, como la creación de una sala, la recuperación de sus datos o la preparación del contenido que se va a mostrar.

### Propiedades y métodos:
* **Indicador de carga:** Informará visualmente de que la aplicación está realizando una operación.
* **Texto de estado:** Explicará de forma breve qué está ocurriendo, evitando que el usuario piense que la aplicación se ha bloqueado.
* **Controles:** Se desactivarán temporalmente las acciones que puedan provocar solicitudes duplicadas mientras se completa una operación.

### Eventos y acciones:
* **Inicio de carga:** Se mostrará el indicador cuando comience una operación que requiera esperar una respuesta.
* **Finalización:** Cuando la operación termine correctamente, se abrirá la pantalla correspondiente.
* **Gestión de errores:** Si se produce un fallo de conexión o una operación no puede completarse, se mostrará un mensaje claro y, cuando sea posible, una opción para reintentar.
* **Control de navegación:** Se evitará que el usuario inicie varias veces la misma operación mientras continúa pendiente.

### Persistencia:
* **En memoria:** Se conservará el estado de la operación mientras esté en curso.
* **En Firebase:** La pantalla no almacenará información propia de forma permanente. Los datos se guardarán en el servicio correspondiente cuando la operación lo requiera.
* **Recuperación:** Si la operación se interrumpe, se consultará el estado guardado antes de continuar, cuando sea posible.

## 2.6.5. Pantalla de match

Esta pantalla mostrará el resultado de la votación cuando se encuentre una coincidencia entre las preferencias de los participantes, siguiendo las reglas de decisión definidas para CoSwipe.

### Propiedades y métodos:
* **Tarjeta de resultado:** Mostrará la imagen, el título y la información principal del contenido seleccionado.
* **Mensajes:** Informarán de que se ha encontrado una coincidencia.
* **Botones:** Permitirán continuar con la experiencia o volver a la pantalla correspondiente, según las opciones previstas en el diseño.
* **Actualización visual:** Los datos del resultado se cargarán a partir de la información disponible en la sala.

### Eventos y acciones:
* **Detección de coincidencia:** Cuando se cumplan las condiciones de votación establecidas, se actualizará el estado de la sala.
* **Visualización:** Al recibir el resultado, se mostrará la información del contenido coincidente.
* **Clics:** Los botones ejecutarán las acciones de navegación correspondientes.
* **Sincronización:** Se comprobará que los participantes reciban el mismo resultado y que la pantalla no muestre coincidencias duplicadas.

### Persistencia:
* **En memoria:** Se conservará temporalmente el resultado para mostrarlo correctamente durante la navegación.
* **En Firebase:** Se guardará el resultado de la sala cuando sea necesario para que los participantes puedan consultarlo y evitar que se pierda al cerrar o actualizar la pantalla.
* **Recuperación:** Si se vuelve a acceder a la sala, se podrá consultar el resultado almacenado siempre que siga disponible.

### Referencias
* **[3]** Google. Cloud Firestore. Firebase Documentation. Disponible en: https://firebase.google.com/docs/firestore
* **[4]** Google. Add Firebase to your Android project. Firebase Documentation. Disponible en: https://firebase.google.com/docs/android/setup
* **[5]** Google. Read and write data on Android. Firebase Documentation. Disponible en: https://firebase.google.com/docs/firestore/quickstart#kotlin+ktx

---

# 2.7.Pautas de la secuencia de control de la aplicación

La secuencia de control de CoSwipe define el orden de las acciones y cómo responde la aplicación a las decisiones de los usuarios, desde que se abre hasta que se obtiene un resultado o se cierra la sesión.

El objetivo es ofrecer un funcionamiento sencillo, rápido e intuitivo que facilite la elección grupal de películas, series o videojuegos. Para ello, la aplicación debe guiar a los participantes durante cada fase y gestionar correctamente las acciones y posibles errores.

## 2.7.1. Inicio de la aplicación
Al abrir CoSwipe, el usuario accede a una pantalla principal desde la que puede crear una sala o unirse a una existente.  
No es necesario registrarse ni iniciar sesión, lo que simplifica el acceso y evita solicitar datos personales. Las dos opciones deben mostrarse claramente para facilitar la navegación sin pasar por menús adicionales.

## 2.7.2. Creación o acceso a una sala
El usuario puede iniciar una sesión o incorporarse a otra para participar en una votación conjunta.  
* **Crear sala:** el anfitrión selecciona el tipo de contenido (películas, series o videojuegos) y las plataformas disponibles. Después, la aplicación genera un código de acceso, un código QR y un enlace para compartir.  
* **Unirse a una sala:** los participantes acceden mediante el código, escaneando el QR o utilizando el enlace compartido.  
Antes de permitir la entrada, la aplicación comprueba que la sala sea válida. Todos los participantes deben estar en la misma sesión para que sus votos se registren correctamente.

## 2.7.3. Preparación de la votación
Una vez preparada la sala, la aplicación carga las tarjetas según los filtros establecidos por el anfitrión, como el tipo de contenido y las plataformas seleccionadas.  
Todos los participantes deben recibir las mismas opciones para poder comparar sus preferencias correctamente. Cada tarjeta representa una película, serie o videojuego y muestra la información necesaria para valorarlo sin consultar otros catálogos manualmente.  
Si ocurre un problema de conexión o no se pueden cargar los contenidos, la aplicación muestra un mensaje explicativo que permita al usuario identificar el problema e intentarlo de nuevo.

## 2.7.4. Votación mediante tarjetas
Cuando las tarjetas están cargadas, comienza la votación. Cada participante utiliza su dispositivo para valorar las opciones mediante gestos táctiles:  
* **Deslizar a la derecha:** indica que le gusta el contenido y estaría dispuesto a elegirlo.  
* **Deslizar a la izquierda:** descarta el contenido porque no le interesa.  
Cada voto se envía al sistema para compararlo con las decisiones del resto de participantes. Los votos permanecen privados durante la votación para evitar influencias o presiones del grupo.  
Todos los usuarios deben valorar el mismo conjunto de tarjetas, garantizando una comparación coherente de sus preferencias. Este sistema busca reducir el tiempo dedicado a decidir qué hacer y aprovecharlo mejor en la actividad de ocio.

## 2.7.5. Comprobación de coincidencias
El sistema analiza los votos recibidos para comprobar si existe una coincidencia entre todos los participantes. Según los resultados, pueden darse tres situaciones:  
* **Coincidencia unánime:** si todos aceptan el mismo contenido, la votación se detiene y aparece la pantalla de Match, que destaca la opción elegida y la información disponible sobre la plataforma donde verla o jugar.  
* **Sin coincidencia:** la votación continúa con las tarjetas restantes hasta encontrar una opción aceptada por todos o agotar el catálogo.  
* **Catálogo agotado sin unanimidad:** la aplicación propone el contenido con mayor puntuación según el sistema de valoración del proyecto, ofreciendo una alternativa final basada en las preferencias registradas.  
La comprobación debe coordinarse entre todos los participantes. Cuando se detecta una coincidencia, la votación se detiene y se muestra el resultado para evitar que se sigan procesando nuevos votos.  
Este mecanismo permite tomar decisiones grupales de forma más rápida e imparcial, reduciendo la necesidad de debatir cada opción.

## 2.7.6. Visualización del resultado
Al terminar la votación, todos los participantes ven el resultado de la sesión. La pantalla muestra el título seleccionado y la información disponible sobre las plataformas donde se puede ver la película o serie o jugar al videojuego.  
El contenido ganador debe destacarse sin añadir información innecesaria, para que todos identifiquen rápidamente la decisión final.  
Si existe unanimidad, se muestra un Match. Si se agotan las tarjetas sin conseguirla, aparece la opción con mayor puntuación. Así, el grupo puede pasar directamente a la actividad elegida sin seguir buscando en diferentes catálogos.

## 2.7.7. Finalización de la sesión
La sesión termina cuando se obtiene un resultado o cuando el anfitrión decide cerrar la sala.  
Si se obtiene un resultado, la aplicación deja de comprobar nuevos votos y muestra el contenido seleccionado. Si el anfitrión cierra la sala antes, la votación se interrumpe y se dejan de aceptar nuevas decisiones.  
Al finalizar, se cierra la interacción compartida y se impide enviar votos a una sala inactiva.  
Esta última fase completa la secuencia de control de CoSwipe, desde el acceso inicial hasta la elección final o el cierre voluntario, manteniendo un funcionamiento organizado y sin pasos innecesarios.

---

# 2.8. Cronograma de ejecución

## 2.8.1. Fases del sprint
* **Análisis:** durante esta primera fase se revisarán las interfaces propuestas en el Sprint 1 para identificar los elementos que funcionan correctamente y aquellos que necesitan mejoras. Se estudiará la distribución de las pantallas, la organización de los componentes y los pasos necesarios para completar las principales acciones de la aplicación. También se establecerán los criterios de usabilidad y accesibilidad que se aplicarán durante el sprint. El objetivo es detectar posibles dificultades desde el principio y conseguir que los usuarios comprendan fácilmente las opciones disponibles y puedan navegar sin complicaciones.
* **Diseño:** una vez terminado el análisis, se actualizarán los wireframes y mockups de CoSwipe para mejorar la disposición de los elementos, la organización de la información y la conexión entre las distintas pantallas. Se mantendrá la identidad visual definida para el proyecto, respetando su planteamiento original y sus funcionalidades principales. Los cambios estarán orientados a conseguir una interfaz más clara, ordenada y coherente, de manera que los usuarios puedan identificar las opciones y comprender el funcionamiento de la aplicación antes de comenzar la maquetación.
* **Maquetación:** en esta fase se prepararán las principales pantallas de CoSwipe siguiendo las decisiones tomadas durante el análisis y el diseño. Se trabajará en las interfaces de creación y unión a salas, configuración de filtros, votación mediante tarjetas y visualización de resultados. Cada pantalla deberá incluir los componentes necesarios para realizar su función y mantener una distribución similar al resto de la aplicación. También se tendrá en cuenta la continuidad de la navegación, permitiendo que los usuarios pasen de una pantalla a otra de forma lógica y siguiendo la secuencia de funcionamiento definida para el proyecto.
* **Revisión de usabilidad y accesibilidad:** cuando las interfaces estén preparadas, se comprobarán los aspectos que pueden afectar a la facilidad de uso. Entre ellos se encuentran la legibilidad de los textos, el contraste entre los colores, la distribución de los elementos y la facilidad para localizar las diferentes opciones. También se revisará que los componentes estén organizados de forma comprensible y que la información más importante destaque correctamente. Esta fase permitirá detectar posibles dificultades de navegación o comprensión y realizar los ajustes necesarios para mejorar la experiencia de los usuarios.
* **Pruebas y validación:** durante esta fase se revisará el prototipo para comprobar que las pantallas mantienen una estructura coherente y que el recorrido por la aplicación resulta comprensible. Se analizará el proceso completo, desde el acceso inicial hasta la creación o unión a una sala, la preparación de la votación, la interacción con las tarjetas y la presentación del resultado. Durante las pruebas se buscarán posibles errores de diseño, elementos poco claros o pasos que puedan dificultar el uso de la aplicación. Los resultados obtenidos permitirán comprobar si el prototipo cumple los criterios establecidos en las fases anteriores y si es necesario realizar nuevas modificaciones.
* **Ajustes y documentación:** en la última fase se corregirán los problemas detectados durante las pruebas y se incorporarán las mejoras necesarias en las interfaces. Se comprobará que las modificaciones mantengan la coherencia visual y funcional de CoSwipe y que respeten los criterios de usabilidad y accesibilidad definidos al comienzo del sprint. Además, se recopilarán las evidencias del trabajo realizado y se preparará la documentación necesaria para la entrega y presentación del Sprint 2. En ella se recogerán las decisiones adoptadas, los cambios realizados y los resultados obtenidos, facilitando la explicación del trabajo desarrollado por el equipo.

## 2.8.2 Diagrama de Gantt
<img width="501" height="242" alt="image" src="https://github.com/user-attachments/assets/fbb6ff65-3ce4-4136-9da3-34373d27b176" />
