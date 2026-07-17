---
title: "Proyecto Integrador — Álgebra Lineal"
type: homework
---

# Proyecto Integrador: Álgebra Lineal

Rosendo Camal
Álgebra Lineal

## Preguntas del Proyecto Final

### ¿Cómo se relaciona el álgebra lineal con la programación?

En álgebra lineal se utilizan variables y tipos, procedimientos y se requiere pensar en la teoría matemática para llevar a cabo el entendimiento de un problema o para llegar a la resolución del problema. También, se emplea el uso de matrices, conjuntos o intervalos de datos para poder tratar varios datos o variables de un problema o conjunto de problemas de manera fácil y sobre todo rápida. En programación, surge algo igual. Aquí se suele emplear variables que necesariamente manejan un tipo de dato, muy similar a la matemática que maneja incógnitas y tipos de estructuras matemáticas como números (naturales, enteros, reales, complejos), conjuntos (intervalos, conjuntos, elementos de conjunto) y dimensiones. Otro punto, que tienen en común la programación y el álgebra lineal es el uso de las matrices (aunque no es necesariamente el único medio en programación) para llevar a cabo la reserva en memoria, el acceso a múltiples datos y a la solución de problemas con una cantidad de problemas.

### ¿Qué ventajas tiene automatizar procesos algebraicos?

Independientemente del nivel de complejidad o la facilidad para realizar procesos algebraicos con el uso de técnicas manuales como realizarlas en la mente o con lápiz y papel, llega con inevitable razón, una fatiga que provoca errores al momento de realizar múltiples cálculos uno tras otro. Si bien, es un motivo no es el principal. La razón por la cual conviene utilizar la automatización de procesos algebraicos radica en la cantidad de cálculos implicados y en la cantidad de repeticiones de los procesos algebraicos, sobre todo cuando la magnitud es tan alta que el coste en ejecutarlo de manera manual es muy alto en periodos de tiempo o es prácticamente imposible efectuarlo por la mente humana en un tiempo aceptable (según de lo que se quiera calcular).

### ¿Qué dificultades encontraste al modelar el problema?

La principal dificultad radicó en poder verificar si una ecuación es lineal o no, algo que sinceramente no logré ni de cerca efectuar por mis propios medios ni con asistencia de LLMs para generar dicho código sin recurrir al aumento de la complejidad del programa (ni siquiera lograban contemplar todos los casos posibles de entrada de datos). Puesto que solicitar al usuario (o leer una cadena de texto) una ecuación y poder evaluar si es o no una ecuación lineal es realizar un análisis sintáctico de la entrada al nivel de software de matemática como Wolfram Alpha o compiladores de lenguajes de programación.

Una de las maneras, por lo que intenté fue con el uso de RegEx (Lenguajes de Autómatas), pero es un tema que no domino y que la complejidad en su uso aumenta para absorber todos los casos posibles. Además, el tiempo de ejecución puede verse afectado en caso de una mala implementación. Otra manera, fue realizar parsing a las entradas, pero requería manejar un mapa mental con alto costo para evaluar y pensar en todos los casos posibles e implementarlos con la estructura de control if-else o similares.

El tercer método fue con el uso de la librería externa sympy y con el apoyo de la asistencia de modelos de lenguaje avanzados. Aquí se genera una variable con la expresión (entrada del usuario), con el uso de tipo de símbolos de la librería especializada se asignaba y se identifica las incógnitas y después se realiza un proceso de parsing y generación de árbol para generar relaciones de significado entre las partes de la expresión. Pero requería una complejidad adicional poder implementarlo ya que el problema radica en las diferentes entradas de usuario para representar una ecuación lineal y la variedad de casos matemáticos en los que una ecuación lineal puede estar ahí pero sin simplificarse aún. Por lo que decidí enteramente en no cumplir con dicho apartado. Preferí simplemente arrojar la definición de ecuación lineal.

Otra de las dificultades que encontré fue la decisión de usar solo la librería estándar de Python para evitar dificultades de ejecución de código en diferentes dispositivos y evitar configuraciones adicionales (el típico en mi computadora si funciona). La conexión entre los archivos de Python y el uso de los test sin usar Pytest o similares. La integración de los test que se solicitó en la actividad, fue algo complicado. No tanto, en la planeación y escritura del código, sino en la implementación de la unión del menú y las pruebas de código. Ya que en los requisitos únicamente solicitaban cuatro opciones, por lo que decidí efectuar los test antes de iniciar el menú interactivo de lo solicitado.

### ¿Qué aprendiste sobre la importancia de validar datos?

Comprender a mayor profundidad la validación de datos. Ya que se tiene que pensar en todos los tipos posibles de entrada tanto correcta e incorrecta. Una entrada de datos correcta permite que el código del programa funcione correctamente sin ningún tipo de anomalía. Sin embargo, una entrada incorrecta de datos puede llevar a estados inesperados del programa desde el mal funcionamiento, cierres por errores hasta inyecciones de código malicioso que se aprovecha de estos casos.
