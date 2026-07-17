---
title: "Verificador de Sistemas Lineales"
source: "algebra_lineal_act1.pdf"
type: homework
---

# Verificador de Sistemas Lineales

Rosendo Camal
Álgebra Lineal
07 de febrero de 2026

## Evidencias del código

```python
# Código del verificador
```

1. En tu código usaste un operador lógico (como and). ¿Por qué no basta con usar or? ¿Qué pasaría matemáticamente si el programa aceptará la solución cuando sólo una de las ecuaciones es correcta?

No se puede usar el operador "or" por qué en el código implica validar de manera forzada los dos valores ingresados por el usuario sean iguales a los valores de las ecuaciones lineales y dicho operador, si bien lo valida con esta condición, también puede validar cuando al menos una sea correcta. Y esto último no lo deseamos ni necesitamos porque significa aceptar valores correctos como incorrectos. Por lo que el operador "and" cumple con validar la condición de si ambos datos introducidos por el usuario son correctos (claramente si está bien implementado).

2. Gráficamente, cada ecuación es una línea. Si tu programa dice "¡Correcto!", ¿qué está pasando con esas dos líneas en el espacio geométrico en ese punto exacto?

Los valores ingresados de (x, y) es el punto de intersección (las coordenadas) en el plano cartesiano bidimensional de las dos ecuaciones representadas como rectas.

3. Tú le diste los valores a la computadora. Si quisieras que la computadora encontrará la respuesta sola probando números del 0 al 10, ¿qué estructura de control (que ya vimos en clase) necesitarás agregarle al código?

Lo más sencillo es implementar un ciclo for y dentro de ella las condiciones if-else donde se compare ya no el dato introducido por el usuario sino por los valores de la variable i del ciclo for.

Ejemplo:

```python
for i in range(11):
    # Condición if-else que compara con i los resultados de las ecuaciones
```

4. Imagina un sistema de GPS que necesita saber tu ubicación. Recibe datos de 3 satélites (3 ecuaciones). ¿Por qué es crítico que el sistema verifique que tu posición cuadre con los 3 satélites y no solo con 1?

Considero que para tener mayor precisión y redundancia por errores por si un satélite falla.
