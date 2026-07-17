---
title: "Investigación — Introducción a la Ingeniería de Sistemas"
type: homework
---

# Investigación: Introducción a la Ingeniería de Sistemas

Rosendo Camal

## 1.1 Máquinas digitales y analógicas

Las máquinas analógicas usan valores continuos (señales de onda continua) para procesar datos, mientras que las digitales usan valores discretos (ceros y unos). La elección depende del uso: las analógicas son para problemas específicos con datos continuos, como simulación de vuelo, y las digitales son para propósito general y cálculos de alta precisión, como computadoras modernas.

**Máquinas analógicas:**

- **Enfoque:** Diseñadas para un propósito específico y resolver un problema particular.
- **Procesamiento:** Trabajan con datos continuos, utilizando fenómenos físicos como el voltaje o la presión para representar los datos.
- **Ventajas:** Pueden ser muy rápidas para simular sistemas complejos en tiempo real.
- **Desventajas:** Generalmente menos precisas y tienen un rango de aplicación limitado.

**Máquinas digitales:**

- **Enfoque:** Propósito general, programables para realizar una gran variedad de tareas.
- **Procesamiento:** Trabajan con datos discretos (en forma de dígitos binarios, 0 y 1).
- **Ventajas:** Son precisas, versátiles y se pueden almacenar y procesar datos fácilmente.
- **Desventajas:** No pueden simular sistemas continuos de forma tan eficiente como las analógicas sin un proceso de conversión.

## 1.2 Hardware y software

El hardware son los componentes físicos de una computadora o dispositivo, como el teclado, la pantalla o el procesador. El software son las instrucciones, programas y datos intangibles que controlan el hardware y le permiten realizar tareas. Ambos son inseparables; el hardware es el cuerpo y el software es la mente o el cerebro que lo dirige.

**Hardware:**

- **Definición:** Conjunto de partes físicas y tangibles de un dispositivo, como componentes eléctricos, electrónicos y electromecánicos.
- **Ejemplos de entrada:** Teclado, ratón, micrófono.
- **Ejemplos de salida:** Monitor, impresora, altavoces.
- **Procesamiento y almacenamiento:** Procesador (CPU), memoria RAM, disco duro o unidad de estado sólido, tarjeta madre.

**Software:**

- **Definición:** Conjunto de programas, instrucciones y reglas informáticas que indican al hardware cómo funcionar.
- **Sistema operativo:** El software base que gestiona el hardware y permite la ejecución de otros programas (ej. Windows, macOS, Android).
- **Software de aplicación:** Programas que se utilizan para tareas específicas, como navegadores web, procesadores de texto, videojuegos o redes sociales.
- **Software de programación:** Herramientas para desarrollar otros programas, como editores de código y compiladores.

**Relación entre hardware y software:**

- **Interdependencia:** El software no puede funcionar sin el hardware, ya que necesita un soporte físico donde ejecutarse. A su vez, el hardware no puede hacer nada útil sin las instrucciones del software que le digan qué hacer.
- **Complementariedad:** El software se adapta al hardware y ambos están diseñados para trabajar juntos, logrando que los dispositivos sean funcionales y cumplan su propósito.

## 1.3 Componentes: circuitos lógicos, procesador y memoria

Los circuitos lógicos, el procesador y la memoria son los componentes fundamentales de cualquier sistema informático. Aunque cada uno tiene una función específica, trabajan en conjunto para ejecutar las tareas y operaciones necesarias.

**Circuitos lógicos:**

Son la base de la electrónica digital y manipulan información en forma binaria (1 y 0). Están formados por compuertas lógicas que combinan o seleccionan señales de forma controlada.

Compuertas lógicas — son los bloques de construcción de los circuitos lógicos. Las más comunes son:

- **AND (Y):** La salida es 1 solo si todas las entradas son 1.
- **OR (O):** La salida es 1 si al menos una de las entradas es 1.
- **NOT (No):** Invierte la entrada (si la entrada es 1, la salida es 0).
- **NAND, NOR, XOR, XNOR:** Combinaciones de las compuertas básicas.

Función: Permiten el procesamiento de información binaria en dispositivos que van desde pequeños aparatos hasta complejos sistemas informáticos.

**Procesador (CPU):**

También conocido como la Unidad Central de Procesamiento (CPU), es el "cerebro" de la computadora, encargado de ejecutar instrucciones y procesar datos. Se trata de un circuito integrado con millones de componentes electrónicos.

- **Unidad Aritmético-Lógica (ALU):** Realiza operaciones matemáticas (suma, resta, multiplicación, etc.) y lógicas (comparaciones).
- **Unidad de Control (UC):** Interpreta las instrucciones de los programas y coordina la ejecución de las operaciones en todo el sistema.
- **Registros:** Son pequeñas unidades de almacenamiento de alta velocidad dentro del procesador que guardan datos temporalmente para un acceso rápido.
- **Núcleos e hilos:** Los núcleos son las unidades de procesamiento reales, y los hilos son subprocesos virtuales que permiten ejecutar múltiples tareas simultáneamente.
- **Memoria caché:** Un tipo de memoria muy rápida que almacena datos de uso frecuente para que el procesador pueda acceder a ellos más rápido que desde la memoria RAM.

**Memoria:**

Es el componente que almacena datos, instrucciones y programas para que el procesador pueda acceder a ellos. Existen dos tipos principales:

- **Memoria RAM (Random Access Memory):** Es una memoria de acceso aleatorio, volátil y de alta velocidad. Almacena temporalmente los datos y programas que el procesador está utilizando o necesita para operar en el corto plazo. Su contenido se borra cuando se apaga el dispositivo. Ejemplos de tecnologías: DDR4, DDR5, LPDDR.
- **Memoria ROM (Read Only Memory):** Es una memoria de solo lectura y no volátil, lo que significa que sus datos permanecen guardados aunque no haya electricidad. Contiene instrucciones permanentes, como el firmware y la BIOS/UEFI, que son necesarias para el arranque del sistema. Es más lenta que la RAM y no puede ser modificada fácilmente.

## 1.4 Dispositivos de entrada y salida

Los dispositivos de entrada permiten introducir información en un sistema, mientras que los de salida muestran el resultado de ese procesamiento. Existen también los dispositivos de entrada/salida (E/S), que pueden realizar ambas funciones.

- **Dispositivos de entrada:** Permiten ingresar datos y comandos desde el exterior al sistema. Ejemplos: teclado, mouse, micrófono, escáner, cámara web y joystick.
- **Dispositivos de salida:** Presentan la información del sistema al usuario. Ejemplos: monitor, impresora, altavoces y auriculares.
- **Dispositivos de entrada/salida (E/S):** Pueden tanto recibir datos como emitir información, funcionando de forma bidireccional. Ejemplos: pantalla táctil, impresora multifuncional, casco de realidad virtual y módem.

## 1.5 Sistemas Operativos

Un sistema operativo (SO) es el software fundamental que actúa como intermediario entre el hardware de un dispositivo y el usuario, permitiendo la ejecución de aplicaciones. Gestiona los recursos del sistema, como la memoria y el procesador, y facilita tareas como el uso de internet, la reproducción de multimedia o la escritura de documentos. Ejemplos comunes son Windows, macOS y Linux para ordenadores, y Android e iOS para dispositivos móviles.

**Funciones principales:**

- **Gestión de hardware:** Controla y coordina todos los componentes físicos del dispositivo, como el teclado, el ratón, la pantalla, el disco duro, etc.
- **Administración de memoria:** Asigna espacio en la memoria RAM para los procesos activos y gestiona el almacenamiento en el disco.
- **Ejecución de programas:** Permite que las aplicaciones se carguen y se ejecuten correctamente, asignando los recursos necesarios para cada una.
- **Interfaz con el usuario:** Proporciona una interfaz (ya sea gráfica o de línea de comandos) para que el usuario pueda interactuar con el dispositivo.

**Ejemplos de sistemas operativos:**

- **Para ordenadores:** Windows, macOS, y distribuciones de Linux como Ubuntu y Fedora.
- **Para dispositivos móviles:** Android e iOS.
- **Para servidores:** Windows Server, Linux (con distribuciones como Red Hat Enterprise Linux).
