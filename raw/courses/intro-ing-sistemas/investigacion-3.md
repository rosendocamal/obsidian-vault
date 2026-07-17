---
title: "Investigación 3 — Compuertas Lógicas y Lenguaje de Máquina"
type: homework
---

# Investigación: Compuertas Lógicas y Lenguaje de Máquina

Rosendo Camal

Las compuertas lógicas son la base de los circuitos digitales que realizan operaciones con valores binarios (0 y 1). Las compuertas básicas son AND, que produce 1 solo si todas sus entradas son 1; OR, que produce 1 si al menos una de sus entradas es 1; y NOT, que invierte el valor de su única entrada (0 se convierte en 1, y viceversa). El lenguaje máquina es el código de bajo nivel que utilizan los procesadores, escrito en binario, y se obtiene al traducir instrucciones de lenguaje de programación de alto nivel.

## Compuertas Lógicas

### Compuerta AND

Su función es una multiplicación lógica. La salida es alta (1) solo si todas las entradas son altas (1). Si alguna entrada es baja (0), la salida será baja (0).

**Ejemplo:** Imagina un sistema de alarma con dos sensores de puerta. La alarma (salida 1) se activa solo si ambos sensores (entradas 1 y 1) detectan que la puerta está abierta. Si solo uno de los sensores detecta la apertura, la alarma permanece desactivada.

### Compuerta OR

Su función es una suma lógica. La salida es alta (1) si al menos una de sus entradas es alta (1). La salida solo será baja (0) si todas las entradas son bajas (0).

**Ejemplo:** Un semáforo. Puede estar en verde si el sensor de tráfico para el coche está activado (entrada 1) o si el sensor para peatones ha pulsado el botón (otra entrada 1). Si ninguno de los dos sensores se activa (entradas 0 y 0), el semáforo permanecerá en rojo.

### Compuerta NOT (Inversor)

Su función es invertir el valor de entrada. Si la entrada es 1, la salida es 0, y si la entrada es 0, la salida es 1.

**Ejemplo:** Un interruptor de luz con un solo botón. Al presionar el botón, la luz se enciende (1), y al presionarlo de nuevo, se apaga (0). Es como un interruptor que invierte su estado cada vez que se activa.

## ¿Qué son las compuertas lógicas? ¿Para qué sirven?

El procesador de una computadora está lleno de compuertas lógicas. Estas compuertas se usan para realizar operaciones matemáticas, de comparación y de control. Son fundamentales en la arquitectura de cualquier sistema digital.

## Lenguaje de Máquina

Es el lenguaje de programación de más bajo nivel, escrito en código binario (0s y 1s), que la unidad central de procesamiento (CPU) puede ejecutar directamente. Cada instrucción de bajo nivel (como sumar dos números o mover datos de un lugar a otro) tiene una representación específica en lenguaje máquina. Debido a su complejidad, los humanos no escriben directamente en lenguaje máquina. En su lugar, usan lenguajes de programación de alto nivel (como Python, C++, Java) que son más comprensibles. Estos lenguajes de alto nivel se traducen (compilan o interpretan) en lenguaje máquina antes de que la computadora pueda ejecutarlos.
