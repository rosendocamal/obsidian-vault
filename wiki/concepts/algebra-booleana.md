---
title: "Álgebra Booleana"
type: concept
created: 2026-07-16
updated: 2026-07-16
sources:
  - raw/courses/matematicas-discretas/algebra-de-boole.md
  - raw/courses/matematicas-discretas/antecedentes-y-origen-sistema-binario.md
  - raw/courses/intro-ing-sistemas/investigacion.md
tags: [logica, computacion, matematicas-discretas, circuitos]
---

# Álgebra Booleana

Sistema lógico-matemático desarrollado por [[george-boole]] que opera con valores binarios (verdadero=1, falso=0) y operaciones fundamentales (AND, OR, NOT). Es la base teórica de la electrónica digital y la computación moderna.

## Operaciones fundamentales

- **AND (Y)**: salida 1 solo si todas las entradas son 1
- **OR (O)**: salida 1 si al menos una entrada es 1
- **NOT (NO)**: invierte la entrada
- Derivadas: NAND, NOR, XOR, XNOR

## Leyes fundamentales

- Leyes de Morgan: ¬(A ∧ B) = ¬A ∨ ¬B, ¬(A ∨ B) = ¬A ∧ ¬B ([[augustus-de-morgan]])
- Propiedades conmutativa, asociativa, distributiva, identidad, complemento

## Aplicaciones

- Diseño de compuertas lógicas en [[hardware-computacion]]
- Simplificación mediante [[mapas-karnaugh]]
- Circuitos combinacionales, microprocesadores, ALU
- Expresiones condicionales en [[fundamentos-programacion]]
- Motores de búsqueda con filtros booleanos

## Relaciones

- Fundada por [[george-boole]], aplicada por [[claude-shannon]] a circuitos
- Base del [[sistema-binario]] y la [[logica-computacional]]
- Se simplifica gráficamente con [[mapas-karnaugh]]
- Conecta con [[teoria-conjuntos-discretas]] y [[simbologia-matematica]]
