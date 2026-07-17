---
title: "Evaluación Final — POO"
author: "Rosendo Camal"
course: "poo"
type: homework
---

# Evaluación Final

## Pregunta 1

**¿Qué problema resuelve este programa?**

Ayudar al cliente a encontrar casas que estén dentro de su presupuesto con las condiciones que él quiera (si es posible).

## Pregunta 2

**¿Cómo se calcula el precio de una propiedad?**

```python
precio = (superficie * 1200 + cuartos * 4000 + estacionamiento * 18000) * (1 - (2025 - anio) / 100) * (1.3 if (sector == 'B') else 1)
```

Se calcula el valor base, se multiplica por la depreciación y por último se multiplica por 1.3 si es del sector B, sino por 1 (o se deja así tal cual).

## Pregunta 3

**¿Por qué es importante usar funciones en este sistema?**

Para organizar el código, que sea más fácil identificar los errores y sea más fácil llevar mejoras.

## Pregunta 4

**¿Qué pasaría si todas las propiedades fueran del mismo sector?**

Todas las opciones serían más baratas y el usuario podría tener más opciones dentro del presupuesto.
