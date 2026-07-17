---
title: "Cálculo Integral — Integrales Inmediatas (Ejercicios 2)"
date: 2026-03-15
type: homework
---

# Cálculo Integral — Integrales Inmediatas

**Instrucciones:** Calcular las siguientes integrales inmediatas.

## Ejercicio 1

$$\int \frac{9}{x^4} \, dx$$

Desarrollamos y buscamos la antiderivada:

$$
\int \frac{9}{x^4} \, dx
&= \int 9 \cdot \frac{1}{x^4} \, dx \\
&= 9 \int \frac{1}{x^4} \, dx \\
&= 9 \int x^{-4} \, dx \\
&= 9 \left[ \frac{x^{-4 + 1}}{-4 + 1} \right] + C \\
&= 9 \left[ \frac{x^{-3}}{-3} \right] + C \\
&= 9 \cdot \frac{x^{-3}}{-3} + C \\
&= 9 \cdot \left( -\frac{1}{3} \right) \cdot x^{-3} + C \\
&= -\frac{9}{3} x^{-3} + C \\
&= -3 x^{-3} + C \\
&= -\frac{3}{x^3} + C
$$

Comprobamos:

$$
\frac{9}{x^4} &= \frac{d}{dx} \left( -\frac{3}{x^3} + C \right) \\
&= \frac{d}{dx} \left( -\frac{3}{x^3} \right) + \frac{d}{dx} C \\
&= -3 \frac{d}{dx} \left( x^{-3} \right) \\
&= -3 \left( -3 x^{-4} \right) \\
&= 9 x^{-4} \\
&= \frac{9}{x^4}
$$

**Resultado:**

$$\int \frac{9}{x^4} \, dx = -\frac{3}{x^3} + C$$

## Ejercicio 2

$$\int \frac{\, dx}{x^{-2}}$$

Desarrollamos la integral y buscamos la antiderivada:

$$
\int \frac{1}{x^{-2}} \, dx
&= \int \frac{1}{\frac{1}{x^2}} \, dx \\
&= \int x^2 \, dx \\
&= \frac{x^{2 + 1}}{2 + 1} + C \\
&= \frac{x^3}{3} + C \\
&= \frac{1}{3} x^3 + C
$$

Comprobamos:

$$
\frac{1}{x^{-2}} &= \frac{d}{dx} \left( \frac{1}{3} x^3 + C \right) \\
&= \frac{1}{3} \frac{d}{dx} \left( x^3 \right) \\
&= \frac{1}{3} \left( 3 x^2 \right) \\
&= x^2
$$

Y como $\frac{1}{x^{-2}} = x^2$, queda verificado.

**Resultado:**

$$\int \frac{\, dx}{x^{-2}} = \frac{1}{3} x^3 + C$$

## Ejercicio 3

$$\int x^{\frac{2}{3}} \, dx$$

Desarrollamos la integral y buscamos la antiderivada:

$$
\int x^{\frac{2}{3}} \, dx
&= \frac{x^{\frac{2}{3} + 1}}{\frac{2}{3} + 1} + C \\
&= \frac{x^{\frac{5}{3}}}{\frac{5}{3}} + C \\
&= \frac{\sqrt[3]{x^5}}{\frac{5}{3}} + C \\
&= \frac{3\sqrt[3]{x^5}}{5} + C \\
&= \frac{3x\sqrt[3]{x^2}}{5} + C
$$

Comprobamos:

$$
x^{\frac{2}{3}} &= \frac{d}{dx} \left( \frac{3x\sqrt[3]{x^2}}{5} + C \right) \\
&= \frac{3}{5} \frac{d}{dx} \left( x \cdot x^{\frac{2}{3}} \right) \\
&= \frac{3}{5} \frac{d}{dx} \left( x^{\frac{5}{3}} \right) \\
&= \frac{3}{5} \cdot \frac{5}{3} x^{\frac{2}{3}} \\
&= x^{\frac{2}{3}}
$$

**Resultado:**

$$\int x^{\frac{2}{3}} \, dx = \frac{3x\sqrt[3]{x^2}}{5} + C$$
