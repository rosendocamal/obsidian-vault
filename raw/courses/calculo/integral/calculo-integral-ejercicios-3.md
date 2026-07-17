---
title: "Cálculo Integral — Integrales Inmediatas (Ejercicios 3)"
date: 2026-03-26
type: homework
---

# Cálculo Integral — Integrales Inmediatas

**Instrucciones:** Calcular las siguientes integrales inmediatas.

## Ejercicio 1

$$\int \sqrt{25x} \, dx$$

Desarrollamos la integral:

$$
\int \sqrt{25x} \, dx
&= 5 \int \sqrt{x} \, dx \\
&= 5 \cdot \frac{x^{\frac{3}{2}}}{\frac{3}{2}} + C \\
&= 5 \cdot \frac{2}{3} \cdot x^{\frac{3}{2}} + C \\
&= \frac{10}{3} x \sqrt{x} + C
$$

Comprobamos:

$$
\sqrt{25x} &= \frac{d}{dx} \left( \frac{10}{3} x \sqrt{x} + C \right) \\
&= \frac{d}{dx} \left( \frac{10}{3} x^{\frac{3}{2}} + C \right) \\
&= \frac{10}{3} \cdot \frac{3}{2} x^{\frac{1}{2}} \\
&= 5\sqrt{x}
$$

Y como $\sqrt{25x} = 5\sqrt{x}$, queda verificado.

**Resultado:**

$$\int \sqrt{25x} \, dx = \frac{10}{3} x \sqrt{x} + C$$

## Ejercicio 2

$$\int \frac{2}{\sqrt{x^{4}}} \, dx$$

Desarrollamos la integral:

$$
\int \frac{2}{\sqrt{x^{4}}} \, dx
&= 2 \int x^{-2} \, dx \\
&= -2x^{-1} + C
$$

Comprobamos:

$$
\frac{2}{\sqrt{x^{4}}} &= \frac{d}{dx} \left( -2x^{-1} + C \right) \\
&= -2 \left( -x^{-2} \right) \\
&= 2x^{-2}
$$

Y como $\frac{2}{\sqrt{x^{4}}} = \frac{2}{x^{2}} = 2x^{-2}$, queda verificado.

**Resultado:**

$$\int \frac{2}{\sqrt{x^{4}}} \, dx = -2x^{-1} + C$$

## Ejercicio 3

$$\int \left( 3x^{3} + 5x^{2} - x \right) \, dx$$

Desarrollamos la integral:

$$
\int \left( 3x^{3} + 5x^{2} - x \right) \, dx
= \frac{3}{4} x^{4} + \frac{5}{3} x^{3} - \frac{1}{2} x^{2} + C
$$

Comprobamos:

$$
3x^{3} + 5x^{2} - x &= \frac{d}{dx} \left( \frac{3}{4} x^{4} + \frac{5}{3} x^{3} - \frac{1}{2} x^{2} + C \right) \\
&= 3x^{3} + 5x^{2} - x
$$

**Resultado:**

$$\int \left( 3x^{3} + 5x^{2} - x \right) \, dx = \frac{3}{4} x^{4} + \frac{5}{3} x^{3} - \frac{1}{2} x^{2} + C$$
