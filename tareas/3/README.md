# Profundizando en la administración de memoria

    Tarea creada: 2021.01.19
	Entrega: 2021.01.26

La administración de memoria es un campo muy rico y complejo de los
sistemas operativos, y en clase alcanzamos únicamente a arañar sus
definiciones básicas. Por eso, dejo nuevamente un conjunto de
artículos a su consideración, y los invito a que los revisen, elijan
uno de ellos, y lo lean con detenimiento.

Como entrega, les voy a pedir un *control de lectura* (un *mapa
conceptual*) del artículo que elijan. En esta ocasión, la tarea se
realizará de forma _individual_.

## Los artículos

Los temas que cubre esta unidad pueden dividirse en la organización de
memoria _dentro_ de un proceso y lo que hace el sistema operativo,
repartir el espacio disponible entre los distintos procesos.

### Dentro del proceso

- [How to create your own malloc
  library](https://medium.com/a-42-journey/how-to-create-your-own-malloc-library-b86fedd39b96),
  de Jean-Baptiste Terrazzoni, explica cómo funciona la asignación de
  memoria dentro del _espacio de libres_ o _heap_. En lenguajes que
  sin gestión automática de memoria, como C, estamos acostumbrados a
  considerar a las funciones `malloc()`, `free()`, `calloc()` y
  `realloc()` para recibir asignaciones dinámicas de memoria tamaño
  arbitrario. Pero... En realidad, el sistema operativo ofrece
  únicamente `mmap()` / `munmap()`. ¿Cómo funciona la asignación de
  memoria dentro de este espacio?

- [Inside memory
  management](https://developer.ibm.com/tutorials/l-memory/), de
  Jonathan Bartlett, parte de un planteamiento similar al del artículo
  anterior (detallar cómo funciona la familia de funciones
  `malloc()`), pero su enfoque principal es el de presentar otras
  alternativas a la adminsitración de memoria manual dentro de un
  proceso: Explica cómo funcionan las estrategias (automatizadas) de
  conteo de referencias, recolector de basura, y otros más.

- [Techniques for memory debugging: Demistifying C's greatest
  difficulty](https://www.ibm.com/developerworks/aix/library/au-memorytechniques.html),
  de Cameron Laird, resultará interesante para aquellos que disfrutan
  de tener _manos de estómago_ y siempre les gusta intentar romper las
  cosas: Analiza los principales causantes de error derivados de un
  uso incorrecto o _creativo_ de la administración de
  memoria. Presenta además algunas recomendaciones respecto a
  herramientas que pueden ayudarnos a ubicar y prevenir estos
  problemas.

### Entre los distintos procesos

- [Beginners guide on linux memory
  management](https://www.golinuxcloud.com/tutorial-linux-memory-management-overview/),
  de GoLinuxCloud (no me fue posible ubicar al nombre del autor), hace
  un gran trabajo para _anclar_ a la realidad del sistema operativo
  Linux buena parte de los temas que abordamos en esta unidad:
  Funcionamiento del administrador de memoria, sobre-compromiso de
  memoria, sobre-asignación y el /asesino OOM (out-of-memory)/,
  monitoreo y caché de páginas, y todo un interesante etcétera.

- [Exploring Swap on FreeBSD: Free Memory is Wasted Memory, or How to
  Make the Best Use of
  Swap](https://klarasystems.com/articles/exploring-swap-on-freebsd/),
  de Mark Johnston, estudia la razón y el significado del uso de
  memoria virtual (_swap_) en el sistema libre tipo-Unix
  [FreeBSD](https://freebsd.org), partiendo del preguntarse qué tan
  válida es hoy la experiencia histórica de administradores de
  sistemas Unix, en el sentido de que se ve a un alto uso del _swap_
  como síntoma de que algo anda mal... Porque la llegada de las
  unidades de estado sólido (_SSDs_) ponen en jaque todo el balance de
  valoraciones a que estábamos acostumbrados. ¿Cómo funciona la
  paginación a memoria virtual? ¿Debo aumentar, reducir, deshabilitalo
  en mi unidad?


