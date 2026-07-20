---
title: "Recuperar USB con Diskpart"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/diskpart_recuperacion_unidad_usb.md
tags: [windows, diskpart, usb, recuperación]
---

# Recuperar USB dañada con Diskpart

Pasos para recuperar una unidad USB que no funciona usando la herramienta diskpart de Windows. (diskpart_recuperacion_unidad_usb, 2026)

## Proceso

1. Abrir terminal y ejecutar diskpart
2. list disk — para identificar el disco USB dañado
3. select disk n — seleccionar el disco USB (n es el número de disco)
4. clean — borrar todos los datos y particiones del USB
5. create partition primary — crear la partición primaria
6. select partition 1 — seleccionar la partición creada
7. active — marcar la partición como activa (arrancable si es necesario)
8. format fs=fat32 quick — formatear (fat32, ntfs o exfat; usar quick para evitar esperas)
9. label="NAME" — opcional, para nombrar la unidad
10. assign — asignar letra de unidad automáticamente

## Tabla de comandos

| Comando | Función |
|---------|---------|
| diskpart | Abre la herramienta |
| list disk | Lista los discos |
| select disk n | Selecciona el disco enésimo |
| clean | Elimina todas las particiones |
| create partition primary | Crea partición primaria |
| select partition 1 | Selecciona la partición |
| active | Marca como activa |
| format fs=fat32 quick | Formatea rápido a fat32 |
| assign | Asigna letra |

## Llamada

El protocolo diskpart es la manera más efectiva de restaurar un USB que no puede ser reconocido o formateado correctamente por el sistema operativo.

## Relaciones

- Diskpart opera en Windows, aunque los conceptos de sector y partición son universales
- Los sistemas de archivos (fat32, ntfs, exfat) aparecen también en la explicación de montaje de volumen en [[fedora]] (Linux)
- Aporta un enfoque de mantenimiento complementario a las guías de Linux: [[guia-fedora-primeros-pasos]]

