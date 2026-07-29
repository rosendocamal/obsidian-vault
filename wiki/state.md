---
title: "Vault State"
type: overview
created: 2026-07-16
updated: 2026-07-29
sources: [AGENTS.md]
tags: [meta, estado, vault]
---

# Vault State

*Snapshot del vault al momento del último commit.*

## Última actualización

- **Fecha:** 2026-07-29
- **Commit:** `6b0816d` — metadata: frontmatter YAML en raw sources + sync en wiki source pages

## Raw Sources

| Directorio | Archivos | Detalle |
|------------|----------|---------|
| `raw/courses/` | 56 | 13 materias (13 dirs: algebra-lineal, calculo, calculo-vectorial, capacitate-para-el-empleo, contabilidad-financiera, coursera-santander, cultura-empresarial, fundamentos-programacion, intro-ing-sistemas, investigacion-operaciones, matematicas-discretas, poo, santander) |
| `raw/docs/` | 7 | Documentación técnica (git, fedora, virtualbox, 7z, diskpart) |
| `raw/journal/` | 6 | Entradas de diario (2025-01-26 a 2026-07-10) |
| `raw/texts/` | 5 | Ensayos filosóficos/teológicos originales |
| **Total** | **74** | |

## Wiki Pages

| Categoría | Activas | Detalle |
|-----------|---------|---------|
| `entities/` | 32 | 18 originales + 14 adicionales |
| `concepts/` | 44 | 8 teológicos + 24 cursos + 7 guías docs + 5 reflexiones journal |
| `sources/` | 22 | 5 texts + 13 courses + 1 docs + 3 journal |
| `queries/` | 0 | *(vacíos)* |
| `overview/` | 0 | *(vacíos)* |
| **Páginas** | **100** | *(32 entities + 44 concepts + 22 sources + 1 log + 1 state)* |

## Git

- **Último commit:** `6b0816d`
- **Remote:** `git@github.com:rosendocamal/obsidian-vault.git`
- **Branch:** `master`

## Pending

- [ ] Lint wikilinks (verificar que todos los `[[wikilinks]]` resuelvan)
- [ ] Generate overview/synthesis page (`wiki/overview/`)
- [ ] Archive user queries when asked (`wiki/queries/`)

## Cambios en esta sesión

1. Corregido conteo de `index.md`: 44 concepts + 22 sources = 100 pages (era 42/21/97)
2. Corregido `state.md`: commit real `6b0816d`, raw 74, pages 100
3. Corregido `fuente-curso-contabilidad-financiera.md`: Archivos: 3 → 4 (incluye borrador.md)
4. Corregido `fuente-curso-cultura-empresarial.md`: filename exacto (`mapeo-organizacional-de-la-universida-1.md`)
5. Eliminadas blank lines finales en `curso_ofimatica.md` (notas Excel)

## Post-commit checklist

Después de cada commit, verificar:
- [ ] `index.md` bottom line refleja conteos reales de disco
- [ ] `state.md` fecha y commit actualizados
- [ ] Ningún archivo dirty queda sin commit

## Instructions for Next Session

1. Read `AGENTS.md` first (schema, conventions, workflows)
2. Read this file (`wiki/state.md`) for current snapshot
3. Read `wiki/log.md` for chronological operation history
4. Read `wiki/index.md` for the full catalog
5. Check `git log --oneline -3` for latest changes
6. Run `git status` before committing to verify no dirty files
7. Proceed with pending items above or answer user query
