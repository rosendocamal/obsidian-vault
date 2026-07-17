---
title: "Hardware de Computación"
type: concept
created: 2026-07-16
updated: 2026-07-16
sources:
  - raw/courses/intro-ing-sistemas/investigacion.md
tags: [hardware, computacion, cpu, memoria, circuitos]
---

# Hardware de Computación

Componentes físicos de un sistema informático. Incluye circuitos lógicos, procesador, memoria y dispositivos de entrada/salida. El hardware es el soporte físico donde se ejecuta el software.

## Componentes principales

### Circuitos lógicos (compuertas)
- AND, OR, NOT, NAND, NOR, XOR, XNOR
- Base de la electrónica digital, manipulan información binaria

### Procesador (CPU)
- **ALU (Unidad Aritmético-Lógica)**: operaciones matemáticas y lógicas
- **Unidad de Control**: interpreta instrucciones y coordina operaciones
- **Registros**: almacenamiento ultrarápido dentro del procesador
- **Núcleos e hilos**: unidades de procesamiento reales y virtuales
- **Memoria caché**: almacenamiento rápido de datos frecuentes

### Memoria
- **RAM (Random Access Memory)**: volátil, rápida, almacena datos en uso
- **ROM (Read Only Memory)**: no volátil, firmware, BIOS/UEFI

### Dispositivos E/S
- **Entrada**: teclado, mouse, micrófono, escáner
- **Salida**: monitor, impresora, altavoces
- **E/S**: pantalla táctil, impresora multifuncional, módem

## Relaciones

- Las compuertas lógicas implementan la [[algebra-booleana]]
- La ALU usa el [[algoritmo-booth]] de [[andrew-booth]]
- El sistema binario es el lenguaje del hardware (ver [[sistema-binario]])
- El software ([[fundamentos-programacion]], [[linux]]) se ejecuta sobre este hardware
- Conecta con [[logica-computacional]] y [[mapas-karnaugh]]
