---
title: "Vault State"
type: overview
created: 2026-07-16
updated: 2026-07-19
sources: [AGENTS.md]
tags: [meta, estado, vault]
---

# Vault State

*Snapshot del vault al momento del último commit. Actualizado cada vez que se modifican archivos en `wiki/` o `raw/`.*

## Última actualización

- **Fecha:** 2026-07-19
- **Commit:** `pending` — Conformidad completa: citas, voz del autor, open questions

## Raw Sources

| Directorio | Archivos | Detalle |
|------------|----------|---------|
| `raw/courses/` | 55 | 12 materias (algebra-lineal, calculo, calculo-vectorial, contabilidad-financiera, cultura-empresarial, fundamentos-programacion, intro-ing-sistemas, investigacion-operaciones, matematicas-discretas, poo, coursera-santander, santander) |
| `raw/docs/` | 7 | Documentación técnica (git, fedora, virtualbox, 7z, diskpart) |
| `raw/journal/` | 6 | Entradas de diario (2025-01-26 a 2026-07-10) |
| `raw/texts/` | 5 | Ensayos filosóficos/teológicos originales |
| **Total** | **73** | |

## Wiki Pages

| Categoría | Activas | Detalle |
|-----------|---------|---------|
| `entities/` | 32 | 18 originales + 14 nuevos (augustus-de-morgan, github, red-hat, gnu, microsoft, apple, bjarne-stroustrup, john-backus, john-mccarthy, john-von-neumann, vmware, hyper-v, winrar, winzip) |
| `concepts/` | 42 | 40 originales + 2 nuevos (cultura-organizacional + fuente-curso-ofimatica como concepto) |
| `sources/` | 21 | 19 originales + 2 nuevos (fuente-curso-ofimatica, fuente-curso-proteccion-datos) |
| `queries/` | 0 | *(vacíos)* |
| `overview/` | 0 | *(vacíos)* |
| **Páginas** | **97** | *(98 archivos md en wiki/ + index.md)* |

## Git

- **Último commit:** `pending`
- **Remote:** `git@github.com:rosendocamal/obsidian-vault.git`
- **Branch:** `master`

## Pending

- [ ] Generate overview/synthesis page (`wiki/overview/`)
- [ ] Archive user queries when asked (`wiki/queries/`)

## Relaciones

- Este snapshot depende de [[index]] para el catálogo completo
- El historial operativo está en [[log]]

## Changes This Session

1. Added inline citations `(Source, YYYY)` to all 74 entity + concept pages
2. Renamed `diskpart_recuperación_unidad_usb.md` to ASCII + updated all references
3. Restored author's voice in 5 pages (fundamentos-conocimiento, critica-prensa, reflexion-identidad-eternidad, plan-algoritmia, salud-y-economia-farmaceutica)
4. Flagged 3 OPEN QUESTIONs from raw sources (paternidad, salud-farmaceutica, teología)
5. Added cross-reference to theological contradictions in san-agustin.md
6. Consolidated duplicate OPEN QUESTION with cross-reference to semejanza-divina + dios-como-pi

## Instructions for Next Session

1. Read `AGENTS.md` first (schema, conventions, workflows)
2. Read this file (`wiki/state.md`) for current snapshot
3. Read `wiki/log.md` for chronological operation history
4. Read `wiki/index.md` for the full catalog
5. Check `git log --oneline -3` for latest changes
6. Proceed with pending items above or answer user query
