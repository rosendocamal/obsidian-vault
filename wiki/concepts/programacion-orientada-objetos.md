---
title: "Programación Orientada a Objetos"
type: concept
created: 2026-07-16
updated: 2026-07-16
sources:
  - raw/courses/poo/rosendo-camal-evaluacion-final.md
tags: [poo, python, programacion, objetos]
---

# Programación Orientada a Objetos

Paradigma de programación que organiza el código en "objetos" que representan entidades del mundo real. Cada objeto tiene atributos (datos) y métodos (comportamiento).

## Conceptos clave

- **Clase**: plantilla para crear objetos
- **Objeto**: instancia de una clase con estado y comportamiento
- **Atributos**: datos que describen el objeto
- **Métodos**: funciones que definen el comportamiento
- **Herencia**: una clase puede heredar atributos y métodos de otra
- **Encapsulamiento**: ocultación de detalles internos
- **Polimorfismo**: un método puede comportarse diferente según el objeto

## Ejemplo documentado: sistema de búsqueda de propiedades (Python)

Programa que ayuda a clientes a encontrar casas dentro de su presupuesto. El precio se calcula como:

$$precio = (superficie \times 1200 + cuartos \times 4000 + estacionamiento \times 18000) \times (1 - \frac{2025 - año}{100}) \times (1.3 \text{ si sector B})$$

## Relaciones

- Uno de los paradigmas de [[fundamentos-programacion]]
- Python, el lenguaje usado, aparece en [[linea-tiempo-lenguajes-programacion]]
- Las propiedades del mundo real se modelan como objetos
- Conecta con [[algebra-lineal-programacion]] en el uso de atributos y métodos
