---
title: "Dominio y Rango de Funciones"
source: "dominio_rango_funciones.pdf"
type: homework
---

# Dominio y Rango de Funciones

## Introducción

El dominio de una función corresponde a los valores reales que puede tomar la variable independiente, representados en el eje $x$ del plano cartesiano. El rango, por su parte, son los valores posibles de la variable dependiente, ubicados en el eje $y$. Ambos conceptos son fundamentales para comprender el comportamiento de las funciones y sus restricciones.

En este trabajo se analizarán cinco funciones distintas con el propósito de determinar su dominio y rango, graficarlas y justificar los valores que no pueden ser admitidos.

## Conceptos

En una función, el dominio son todos los valores posibles del conjunto de números reales que se pueden asignar a la variable independiente. En términos del plano cartesiano, son los valores que corresponden al conjunto de valores en el eje $x$ o de las abscisas que pueda admitir la función como valor de entrada. El dominio se representa simbólicamente $D_f$.

El rango de una función son todos los posibles valores del conjunto de números reales que pueda tomar la variable dependiente en tanto la variable independiente va cambiando de valor. En el plano cartesiano, son los valores posibles que corresponden al eje $y$ o de las ordenadas. Su representación simbólica es $R_f$.

En el estudio de las funciones, el dominio y el rango son conceptos fundamentales y por ello se realizará lo siguiente con cinco funciones a modo de ejemplificación:

1. Determinar el dominio y el rango.
2. Realizar las gráficas correspondientes, señalando de manera clara los valores que pertenecen al dominio y al rango.
3. Explicación y justificación de qué valores no puede tomar cada función (si aplica).

Las funciones son las siguientes:

1. $f(x) = 2x + 3$
2. $g(x) = x^2 - 4$
3. $h(x) = \dfrac{1}{x - 2}$
4. $k(x) = \sqrt{x + 5}$
5. $m(x) = |x - 3|$

## Función $f(x) = 2x + 3$

Dado que $2x + 3$ puede permitir cualquier valor del conjunto de números reales, los valores posibles para el dominio son todos los números reales. De igual manera, los valores posibles del rango de la función son todos los números reales.

Tomando en cuenta que $f(x)$ es una función lineal, no tiene restricciones en el dominio, y por tanto, aplica lo mismo para el rango.

- **Dominio:** $(-\infty, +\infty)$
- **Rango:** $(-\infty, +\infty)$

## Función $g(x) = x^2 - 4$

Los valores posibles del dominio, al ser una función cuadrática, son todos los números reales. Sin embargo, no ocurre lo mismo para el rango. Los valores resultantes de $g(x)$ están restringidos por el término cuadrático: cada valor de $x$ elevado al cuadrado, tanto si es positivo como negativo, produce un resultado positivo. Con esto se determina que el rango únicamente se conforma por números reales positivos.

El número cero no es positivo ni negativo, así que evaluamos la función con este valor. El cero elevado al cuadrado sigue siendo cero y a ello le restamos cuatro, por lo que el valor dependiente $y$ es $-4$.

$$\text{Si } g(x) = x^2 - 4 \text{ y } x = 0, \text{ entonces } g(0) = 0^2 - 4 = -4$$

### Tabulación

| $x$ | $g(x) = x^2 - 4$ |
|---|---|
| $-3$ | $(-3)^2 - 4 = 5$ |
| $-2$ | $(-2)^2 - 4 = 0$ |
| $-1$ | $(-1)^2 - 4 = -3$ |
| $0$ | $0^2 - 4 = -4$ |
| $1$ | $1^2 - 4 = -3$ |
| $2$ | $2^2 - 4 = 0$ |
| $3$ | $3^2 - 4 = 5$ |
| $4$ | $4^2 - 4 = 12$ |

Con la tabulación anterior, el valor mínimo de salida para $g(x)$ es $-4$ cuando $x$ es $0$. Por lo que el rango de $g(x)$ son los números reales a partir de $-4$ hacia la derecha (visualizando la recta numérica), o sea el intervalo semiabierto $[-4, +\infty)$.

- **Dominio:** $(-\infty, +\infty)$
- **Rango:** $[-4, +\infty)$

## Función $h(x) = \dfrac{1}{x - 2}$

Tenemos una restricción importante: la división por cero. La variable independiente $x$ no puede tomar cualquier valor del conjunto de números reales, dado que el denominador de la fracción cuando es $0$ la función queda indefinida.

$$\text{Si el denominador es } x - 2 \text{ y buscamos que sea cero, entonces } x - 2 = 0$$
$$\text{Despejando: } x = 2$$

Siendo $x$ igual a $2$, la función $h(x)$ queda indefinida, por lo tanto, $2$ no pertenece al dominio. Dado que no hay otro número para $x$ que dé como consecuencia otra división por cero, el dominio son los números reales distintos de $2$.

### Análisis del rango

Para el rango de la función, evaluamos valores cercanos de $x$ a $2$:

| $x$ | $h(x) = \frac{1}{x-2}$ |
|---|---|
| $1.8$ | $\frac{1}{-0.2} = -5$ |
| $1.9$ | $\frac{1}{-0.1} = -10$ |
| $1.99$ | $\frac{1}{-0.01} = -100$ |
| $2$ | Indefinido |
| $2.01$ | $\frac{1}{0.01} = 100$ |
| $2.1$ | $\frac{1}{0.1} = 10$ |
| $2.2$ | $\frac{1}{0.2} = 5$ |

Con lo anterior, se puede percatar que la variable dependiente disminuye a medida que $x$ se aleja de $2$. Para confirmar que $0$ no está en el rango, despejamos $x$ cuando $y = h(x)$:

$$y = \frac{1}{x - 2}$$
$$y(x - 2) = 1$$
$$x - 2 = \frac{1}{y}$$
$$x = 2 + \frac{1}{y}$$

Siendo $x = 2$:

$$2 = 2 + \frac{1}{y}$$
$$0 = \frac{1}{y}$$

Esto genera una contradicción, así que $0$ no está en el rango. Cada vez que $x$ se aleja de $2$, $y$ se acerca pero nunca llega a $0$.

- **Dominio:** $(-\infty, 2) \cup (2, +\infty)$
- **Rango:** $(-\infty, 0) \cup (0, +\infty)$

## Función $k(x) = \sqrt{x + 5}$

Tenemos otra restricción ya que el radicando debe cumplir con $x + 5 \geq 0$ porque la raíz cuadrada no existe para números reales menores a cero. Despejamos para $x$:

$$x + 5 \geq 0$$
$$x \geq -5$$

Por lo tanto, los valores de $x$ deben ser mayores o iguales a $-5$. Entonces el dominio para $k(x)$ es el intervalo semiabierto $[-5, +\infty)$.

### Análisis del rango

Para hallar el rango de la función despejamos $x$ en $k(x)$:

$$y = \sqrt{x + 5}$$
$$y^2 = x + 5$$
$$x = y^2 - 5$$

Dado que $x$ solo puede ser mayor o igual a $-5$:

$$y^2 - 5 \geq -5$$
$$y^2 \geq 0$$

Esto es cierto para todo $y$ real, y dado que la raíz cuadrada siempre produce valores no negativos, el rango son los números reales mayores o iguales a cero.

- **Dominio:** $[-5, +\infty)$
- **Rango:** $[0, +\infty)$

## Función $m(x) = |x - 3|$

Como consecuencia del valor absoluto, los valores de $y$ siempre serán positivos o iguales a $0$, por tanto el rango es el intervalo semiabierto $[0, +\infty)$. Mientras que $x$ puede ser cualquier número real, por lo que su dominio es $(-\infty, +\infty)$.

- **Dominio:** $(-\infty, +\infty)$
- **Rango:** $[0, +\infty)$

## Conclusión

En resumen, el tema de las funciones está ligado a dos conceptos importantes: el dominio y el rango. Por un lado, el dominio son todos los posibles valores que puedan asignarse a la variable independiente, y por el otro lado, el rango son los posibles valores que pueda tomar la variable dependiente en relación a los valores asignados a la variable independiente. Tanto el dominio como el rango se representan en el plano cartesiano en el eje de las abscisas y en el eje de las ordenadas, respectivamente.

El dominio y el rango, en ocasiones y en dependencia de la función, pueden tener restricciones en los valores que se puedan asignar o tomar. Si en una función la variable independiente no puede asignarse cualquier valor, esto afectará a los posibles valores que pueda tomar la variable dependiente. Esto es fundamental ya que nos permite tener una mejor comprensión del concepto de las funciones.

## Bibliografía

- Aguilar Márquez, A., Bravo Vázquez, F., Gallegos Ruiz, H., Cerón Villegas, M., & Reyes Figueroa, R. (2015). *Matemáticas simplificadas* (4ª ed.). Pearson Educación.
- Espinoza Rangel, J. (2022). *Cálculo Diferencial*. Delta Learning.
- Stewart, J. (2016). *Cálculo: Trascendentes tempranas* (8ª ed., trad. al español). Cengage Learning.
