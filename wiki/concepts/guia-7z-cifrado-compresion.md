---
title: "Compresión y cifrado con 7z"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/usar_7z.md
tags: [compresión, cifrado, 7z, linux]
---

# Compresión y cifrado con 7z

Uso avanzado de 7-Zip para compresión y cifrado de archivos desde la línea de comandos.

## Comando optimizado

```
7z a -p$(cat password.txt) -mhe=on -t7z -mx=9 -m0=lzma2 -md=64m -mmt=on -scrcsha256 [file_name] [path]
```

## Desglose de parámetros

- `-p$(cat password.txt)` — leer contraseña desde archivo
- `-mhe=on` — cifrar encabezados (no se ven nombres de archivo sin clave)
- `-t7z` — formato contenedor 7z
- `-mx=9` — compresión máxima
- `-m0=lzma2` — algoritmo de compresión LZMA2
- `-md=64m` — diccionario de 64 MB
- `-mmt=on` — multihilo (usa todos los núcleos)
- `-scrcsha256` — checksum SHA256

## Extraer

    7z x archivo.7z -p$(cat password.txt)

## Relaciones

- 7z es una herramienta de compresión (ver [[seven-zip]])
- Los principios de cifrado se relacionan con la seguridad informática
- Útil en flujos de trabajo junto con script bash en [[fedora]]
- Alternativa a [[winrar]] y [[winzip]]

