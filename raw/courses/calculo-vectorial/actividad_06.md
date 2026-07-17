---
title: "Álgebra de Vectores — Ecuaciones de Rectas y Planos"
source: "actividad_06.pdf"
author: "Rosendo Camal"
type: homework
---

## Actividad 1

**Instrucciones:** Encontrar la ecuación paramétrica de la recta que pasa por $(1, 2, 3)$ y tiene dirección $(2, 4, 1)$.

**Solución:**

$$
P &= (1, 2, 3) \\
\vec{v} &= (2, 4, 1)
$$

$$
\vec{r} &= P + t\vec{v} \\
&= (1, 2, 3) + t(2, 4, 1) \\
&= (1 + 2t,\; 2 + 4t,\; 3 + t)
$$

Las ecuaciones paramétricas son:

$$
x &= 1 + 2t \\
y &= 2 + 4t \\
z &= 3 + t
$$

## Actividad 2

**Instrucciones:** Encontrar la ecuación del plano que pasa por $(2, 1, 4)$ y tiene vector normal $(3, 2, -1)$.

**Solución:**

$$
P &= (2, 1, 4) \\
\vec{n} &= (3, 2, -1)
$$

$$
3(x - 2) + 2(y - 1) - 1(z - 4) &= 0 \\
3x - 6 + 2y - 2 - z + 4 &= 0 \\
3x + 2y - z - 4 &= 0
$$

## Actividad 3

**Instrucciones:** Investigar tres aplicaciones de rectas y planos en una empresa industrial.

**Respuesta:**

**Diseño y programación de brazos robóticos:** Los brazos robóticos utilizan las ecuaciones de la recta para calcular la trayectoria más corta y precisa que debe seguir su pinza al moverse entre dos puntos en el espacio. Asimismo, se definen planos matemáticos para identificar las superficies de trabajo, asegurando que el robot ensamble o suelde las piezas exactamente en el ángulo correcto.

**Optimización de costos y producción:** En la programación lineal, las restricciones de tiempo, presupuesto y materia prima de la fábrica se representan matemáticamente como rectas y planos en el espacio. Al cruzar estas líneas y planos, los ingenieros encuentran el punto exacto de intersección que permite maximizar la producción al menor costo posible.

**Diseño de plantas y control de calidad:** Los escáneres láser industriales miden millones de puntos en el espacio para modelar tuberías mediante rectas y verificar que estén perfectamente alineadas. Además, el software procesa estos datos para recrear los suelos y paredes como planos perfectos, detectando cualquier imperfección o desnivel antes de instalar maquinaria pesada.
