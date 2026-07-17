---
title: "Cálculo Integral — Integrales y Sustitución"
date: 2026-04-16
type: homework
---

# Cálculo Integral — Integrales y Sustitución

## Ejercicio 1

$$\int \frac{3x^{4} + 6x^{3} + x^{2}}{x^{2}} \, dx$$

Desarrollo de la integral:

$$
\int \frac{3x^{4} + 6x^{3} + x^{2}}{x^{2}} \, dx
&= \int \frac{x^{2} \left( 3x^{2} + 6x + 1 \right)}{x^{2}} \, dx \\
&= \int \left( 3x^{2} + 6x + 1 \right) \, dx \\
&= \int 3x^{2} \, dx + \int 6x \, dx + \int 1 \, dx \\
&= 3 \int x^{2} \, dx + 6 \int x \, dx + x + C \\
&= x^{3} + 3x^{2} + x + C
$$

Comprobación de la primitiva:

$$
\frac{3x^{4} + 6x^{3} + x^{2}}{x^{2}} &= \frac{d}{dx} \left( x^{3} + 3x^{2} + x + C \right) \\
&= 3x^{2} + 6x + 1
$$

Y como $\frac{x^{2}(3x^{2} + 6x + 1)}{x^{2}} = 3x^{2} + 6x + 1$, queda verificado.

**Resultado:**

$$\int \frac{3x^{4} + 6x^{3} + x^{2}}{x^{2}} \, dx = x^{3} + 3x^{2} + x + C$$

## Ejercicio 2

$$\int 4x^{2} \left( 2x^{2} - 3 \right) \, dx$$

Desarrollo de la integral:

$$
\int 4x^{2} \left( 2x^{2} - 3 \right) \, dx
&= \int \left( 8x^{4} - 12x^{2} \right) \, dx \\
&= \int 8x^{4} \, dx - \int 12x^{2} \, dx \\
&= 8 \int x^{4} \, dx - 12 \int x^{2} \, dx \\
&= \frac{8}{5} x^{5} - 4x^{3} + C
$$

Comprobación de la primitiva:

$$
4x^{2} \left( 2x^{2} - 3 \right) &= \frac{d}{dx} \left( \frac{8}{5} x^{5} - 4x^{3} + C \right) \\
&= \frac{8}{5} \cdot 5x^{4} - 12x^{2} \\
&= 8x^{4} - 12x^{2} \\
&= 4x^{2} \left( 2x^{2} - 3 \right)
$$

**Resultado:**

$$\int 4x^{2} \left( 2x^{2} - 3 \right) \, dx = \frac{8}{5} x^{5} - 4x^{3} + C$$

## Ejercicio 3

$$\int (2x - 4)^{2} \, dx$$

Desarrollo de la integral:

$$
\int (2x - 4)^{2} \, dx
&= \int \left( (2x)^{2} + 2(-4)(2x) + (-4)^{2} \right) \, dx \\
&= \int \left( 4x^{2} - 16x + 16 \right) \, dx \\
&= \frac{4}{3} x^{3} - 8x^{2} + 16x + C
$$

Comprobación de la primitiva:

$$
(2x - 4)^{2} &= \frac{d}{dx} \left( \frac{4}{3} x^{3} - 8x^{2} + 16x + C \right) \\
&= 4x^{2} - 16x + 16 \\
&= \frac{4 \left( 4x^{2} - 16x + 16 \right)}{4} \\
&= \frac{(4x)^{2} - 16(4x) + 64}{4} \\
&= \frac{(4x - 8)(4x - 8)}{4} \\
&= \frac{2 \cdot (2x - 4) \cdot 2(2x - 4)}{4} \\
&= \frac{2^{2} \cdot (2x - 4)^{2}}{4} \\
&= (2x - 4)^{2}
$$

**Resultado:**

$$\int (2x - 4)^{2} \, dx = \frac{4}{3}x^{3} - 8x^{2} + 16x + C$$

## Ejercicio 4

$$\int \frac{4x^{3} - 1}{x^{4} - x + 4} \, dx$$

Sustitución de variable:

$$u = x^{4} - x + 4$$

$$
\frac{du}{dx} &= \frac{d}{dx} \left( x^{4} - x + 4 \right) = 4x^{3} - 1 \\
du &= \left( 4x^{3} - 1 \right) dx
$$

$$
\int \frac{4x^{3} - 1}{x^{4} - x + 4} \, dx = \int \frac{du}{u}
$$

Evaluación de la integral:

$$
\int \frac{1}{u} \, du = \ln |u| + C = \ln |x^{4} - x + 4| + C
$$

Comprobación de la primitiva:

$$
\frac{4x^{3} - 1}{x^{4} - x + 4} &= \frac{d}{dx} \left( \ln |x^{4} - x + 4| + C \right) \\
&= \frac{1}{x^{4} - x + 4} \cdot \frac{d}{dx} \left( x^{4} - x + 4 \right) \\
&= \frac{4x^{3} - 1}{x^{4} - x + 4}
$$

**Resultado:**

$$\int \frac{4x^{3} - 1}{x^{4} - x + 4} \, dx = \ln |x^{4} - x + 4| + C$$
