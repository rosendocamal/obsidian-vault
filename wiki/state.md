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
- **Commit:** `pending` — Limpieza completa: frontmatter, sources, entities, wikilinks

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
- [ ] Lint wikilinks (verificar que todos los wikilinks resuelvan)
- [ ] Archive user queries when asked (`wiki/queries/`)

## Relaciones

- Este snapshot depende de [[index]] para el catálogo completo
- El historial operativo está en [[log]]

## Changes This Session

1. Fixed broken frontmatter in `guia-virtualbox-fedora.md` and `guia-fedora-primeros-pasos.md`
2. Renamed `source:` → `sources:` in 11 source pages
3. Removed 4 duplicate entity rows from `index.md`
4. Added `state.md` to index.md Log section
5. Created 14 new entity pages (De Morgan, GitHub, Red Hat, GNU, Microsoft, Apple, Stroustrup, Backus, McCarthy, von Neumann, VMware, Hyper-V, WinRAR, WinZip)
6. Created 1 new concept page (cultura-organizacional)
7. Created 2 new source pages (coursera ofimática, proteccion datos)
8. Rewrote 3 broken wikilinks (`diagramas-de-venn` → `john-venn`, `ayuda_algoritmos` → `fundamentos-programacion`)
9. Added wikilinks to 4 files with <2 links
10. Updated `index.md` counts and entries

## Instructions for Next Session

1. Read `AGENTS.md` first (schema, conventions, workflows)
2. Read this file (`wiki/state.md`) for current snapshot
3. Read `wiki/log.md` for chronological operation history
4. Read `wiki/index.md` for the full catalog
5. Check `git log --oneline -3` for latest changes
6. Proceed with pending items above or answer user query
