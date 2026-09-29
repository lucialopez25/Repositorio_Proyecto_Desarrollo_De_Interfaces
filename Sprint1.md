## Benchmarking

### Mecánica central: el gesto de swipe
[1][2]El gesto nació de una idea muy simple: su cofundador Jonathan Badeen se inspiró limpiando un espejo empañado, buscando fluidez al pasar de una tarjeta a otra.
La clave de diseño: una sola decisión binaria por tarjeta (izquierda/derecha), sin formularios ni fricción cognitiva.

### El "match" como refuerzo emocional
[2]El patrón de gamificación es: acción rápida (swipe) → recompensa variable e impredecible (match o no match) → refuerzo visual/sonoro inmediato. Es el mismo circuito de las tragaperras, y funciona igual de bien para "match" en gustos de cine o videojuegos.

## Product Backlog

 <img width="2720" height="1920" alt="Image" src="https://github.com/user-attachments/assets/6cac56d7-2d76-4b97-ad89-603d8923937d" />

## Sprint Backlog

### Sprint 1 (1 semana) — Objetivo: Ideación y Prototipado Base

Sprint Goal: Tener completa la documentación inicial del proyecto (descripción funcional y alcance técnico), lista como base antes de empezar a desarrollar la interfaz en el siguiente sprint.

Tarea	Descripción	Estimación	Responsable

1	Identificación del público objetivo	Definir perfil de usuario, edad, intereses y necesidades que cubre la app	

2	Objetivos principales de la interfaz	Redactar los objetivos de diseño y experiencia de usuario	

3	Benchmarking	Analizar Tinder como referente de swipe/match y extraer aprendizajes aplicables	

4	Product Backlog	Elaborar la lista priorizada de funcionalidades (interfaz, swipe, match, base de datos)	

5	Sprint Backlog	Desglosar el trabajo del sprint actual en tareas concretas	

6	Patrón de arquitectura de la aplicación gráfica	Documentar el patrón MVC y su justificación para el proyecto	

7	Librerías de componentes nativas y multiplataforma	Comparar y documentar las librerías gráficas a usar (Swing, JavaFX u otras) y sus características	

8	Componentes: características y campo de aplicación	Listar los componentes gráficos que usará la app y para qué sirve cada uno	

9	Asociación de acciones a eventos y edición del código generado	Explicar cómo se conectan los eventos a la lógica sin tocar el código autogenerado	

10	Descripción de las clases, propiedades y métodos	Documentar las clases del proyecto (Modelo, Vista, Controlador) con sus propiedades y métodos

## Patron de arquitectura de la aplicación gráfico

Modelo Vista Controlador(MVC)
Para la aplicación se adopta el patrón MVC, que separa la aplicación en tres capas con funciones distintas.

### 1. Modelo (Model)

Contiene la lógica de negocio y el acceso a los datos. No sabe nada sobre cómo se muestra la información en pantalla.

**Funciones:**

Validar y procesar los swipes (decisión "me interesa" / "no me interesa").
Calcular coincidencias (matches) entre usuarios.
Gestionar el acceso a la base de datos (usuarios, títulos, swipes, matches).

Ejemplo de clase: SwipeModel, MatchModel, LoginModel (ya usado como ejemplo en la conversación).

### 2. Vista (View)

Se encarga exclusivamente de la presentación visual: los componentes gráficos y cómo se muestran al usuario.

**Funciones:**

Mostrar las tarjetas de películas/videojuegos, pantallas de login, perfil y lista de matches.
Exponer sus componentes al controlador mediante métodos getter (por ejemplo, getBtnAcceder(), getBtnSwipeDerecha()).
No contiene lógica de negocio ni decide qué hacer con los datos, solo los presenta.

Ejemplo de clase: VistaLogin, VistaSwipe, VistaMatches (paneles Swing generados con NetBeans, como VistaLogin visto anteriormente).

### 3. Controlador (Controller)

Actúa de intermediario: escucha los eventos de la vista (clics, gestos) y decide qué hacer, apoyándose en el modelo.

# 7. Librerías de componentes nativas y multiplataforma	Comparar y documentar las librerías gráficas a usar (Swing, JavaFX u otras) y sus características
Las librerías que vamos a utilizar para realizar nuestra aplicación son:

*Swing:* Es un grupo de librerías que nos facilita el desarrollo de interfaces gráficas de usuario en Java. Esta librería se encuentra en el paquete JDK y se considera una versión avanzada de la biblioteca AWT
La biblioteca hace posible integrar y ajustar un proyecto Java mediante varios componentes como botones, campos de texto, paneles…[3]

*AWT:* La librería AWT (Abstract Window Toolkit) es una colección de recursos dentro de la biblioteca de Java. La librería AWT ayuda a los programadores a crear interfaces gráficas de usuario (GUI). Este conjunto ofrece una base de componentes como botones, ventanas y menús que se relacionan directamente con el sistema operativo en uso[4]

| Criterio | AWT | Swing |
|----------|-----|-------|
| **Componentes** | Nativos (pesados) | Propios de Java (ligeros) |
| **Dependencia del SO** | Alta | Baja |
| **Apariencia** | La del sistema operativo | Configurable (Look & Feel) |
| **Multiplataforma** | Limitada | Total |
| **Relación y estado** | Base original (en desuso) | Evolución de AWT (en mantenimiento) |


## Referencias 

[1] J. Ferrer, «Swipe left, swipe right — but why?», Medium. Accedido: 26 de septiembre de 2026. [En línea]. Disponible en: https://uxdesign.cc/swipe-left-swipe-right-but-why-tinder-ux-ui-simple-dating-mobile-app-swiping-design-4d2295d80407

[2] Paw, «Tinder Review 2026: Is It Still the Top Dating App?» Accedido: 26 de septiembre de 2026. [En línea]. Disponible en: https://www.swipestats.io/blog/tinder-review

[3] “Swing en Java”. Bahiaxip.com. Accedido el 28 de septiembre de 2026. [En línea]. Disponible: https://bahiaxip.com/entrada/swing-en-java

[4]“¿Qué es AWT (Abstract Window Toolkit)? - Top Up Grado en un año MSMK”. Top Up Grado en un año MSMK. Accedido el 28 de septiembre de 2026. [En línea]. Disponible: https://msmk.university/que-es-awt-abstract-window-toolkit/

