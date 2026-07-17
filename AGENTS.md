# Personal Wiki — Schema

## Purpose

Personal knowledge base (CS, filosofía, teología, diario personal).
LLM maintains `wiki/`. Humans curate `raw/` sources and ask questions.
You write the wiki; I read it.

## Directory Layout

```
raw/docs/       → Documentación técnica (git, fedora, virtualbox, 7z)
raw/journal/    → Entradas de diario personales
raw/texts/      → Ensayos filosóficos/teológicos

wiki/index.md   → Catálogo de todas las páginas, actualizado en cada ingest
wiki/log.md     → Registro cronológico append-only
wiki/overview/  → Síntesis general y tesis evolutiva
wiki/entities/  → Personas, herramientas, organizaciones
wiki/concepts/  → Ideas, técnicas, filosofía, términos
wiki/sources/   → Resumen de cada fuente raw
wiki/queries/   → Respuestas archivadas
```

## Conventions

1. Filenames: lowercase, kebab-case, sin espacios (ej. `relacion-dios-humanos.md`)
2. Every page starts with YAML frontmatter:

```yaml
---
title: "Page Title"
type: entity | concept | source | query | overview
created: YYYY-MM-DD
updated: YYYY-MM-DD
sources: [raw/filename.md]
tags: [relevant tags]
---
```

3. Cross-reference using `[[wiki-link]]` syntax (Obsidian compatible)
4. Every page links to ≥2 related wiki pages
5. Claims cite source: `(Source Name, YYYY)`
6. Flag contradictions with `> **CONTRADICTION**` callout block
7. Flag open questions with `> **OPEN QUESTION**` callout block
8. Preserve author's original voice and writing style from raw sources

## Ingest Workflow

When a new raw source is added:

1. Read the raw source end-to-end
2. Identify key concepts, entities, claims
3. For each: create or update the relevant wiki page
4. Add/update cross-references (`[[wikilinks]]`)
5. Update `wiki/index.md` (add new pages, update summaries)
6. Append entry to `wiki/log.md`

A single source may touch 10–15 wiki pages.

## Query Workflow

1. Read `wiki/index.md` to locate relevant pages
2. Drill into specific pages
3. Synthesize answer with citations back to wiki pages
4. If answer is worth keeping, file it as a new page in `wiki/queries/`

## Lint Workflow

Periodic health check:

- [ ] Every page in `wiki/` appears in `wiki/index.md`
- [ ] Every `[[wikilink]]` resolves to a real file
- [ ] No two pages cover the same concept
- [ ] Conflicting claims are flagged, not silently overwritten
- [ ] Orphan pages resolved
- [ ] Stale sources marked superseded if updated versions exist

## On Session Start

Read `wiki/STATE.md` first for the current vault state snapshot.