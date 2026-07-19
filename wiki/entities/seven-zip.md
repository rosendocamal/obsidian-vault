---
title: "7-Zip (7z)"
type: entity
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/usar_7z.md
tags: [herramienta, compresión, cifrado, linux]
---

# 7-Zip (7z)

Programa de compresión de archivos libre y de código abierto. Soporta múltiples formatos (7z, ZIP, TAR, GZIP, BZIP2, etc.) y ofrece un algoritmo de compresión robusto con cifrado AES-256.

## Parámetros de compresión avanzada

- `-mx=9`: Compresión ultra
- `-m0=lzma2`: Algoritmo LZMA2
- `-md=64m`: Diccionario de 64 MB
- `-mhe=on`: Cifrado de encabezados
- `-scrcsha256`: Checksum SHA256
- `-mmt=on`: Multiprocesamiento

## Flujo de trabajo

- Compresión con contraseña: `7z a -p$(cat password.txt) -mhe=on -mx=9` etc.
- Extracción: `7z x archivo.7z -p$(cat password.txt)`
- Archivos de texto como fuente de contraseñas

## Relaciones

- Alternativa de código abierto a [[winzip]] y [[winrar]]
- Muy usado en entornos Unix/Linux
- Formato 7z permite división en volúmenes y mayor compresión que ZIP

