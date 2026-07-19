# Wiki Log

## [2026-07-16] setup | Estructura inicial

- Created directory structure: `raw/`, `wiki/`, `wiki/{overview,entities,concepts,sources,queries}`
- Moved existing content into `raw/`: `docs/`, `journal/`, `texts/`
- Converted 3 LaTeX files to markdown: `relacion-dios-humanos.tex`, `relacion-nada-maldad-dios.tex`, `una-perspectiva-de-dios.tex`
- Removed original `.tex` files
- Created `AGENTS.md` schema (Karpathy LLM Wiki pattern)
- Created `wiki/index.md` with catalog of all raw sources
- Created `wiki/log.md` (this file)
- Total raw sources: 18 files (7 docs + 6 journal + 5 texts)

## [2026-07-16] cleanup | Reorganización de courses/

- Moved `raw/Classroom-*.zip` to `trash/`
- Removed empty folders (Inglés I, Inglés II, Probabilidad y Estadística) to `trash/`
- Moved 11 `.docx` having same-name `.pdf` to `trash/`
- Moved LaTeX build artifacts (`.aux`, `.log`, `.bcf`, `.bbl`, `.blg`, `.run.xml`) to `trash/`
- Moved `.exe` compile artifact to `trash/`
- Renamed `raw/Classroom/` → `raw/courses/`
- Renamed all course folders to kebab-case (e.g. `CALCULO VECTORIAL 3° ISC SAB MAT MAY-JUN` → `calculo-vectorial`)
- Merged Cálculo Diferencial + Cálculo Integral → `calculo/`
- Merged Intro Ing. Sistemas + Estructura de Datos + Fund. Investigación → `intro-ing-sistemas/`
- Updated `wiki/index.md` with Courses section
- Total raw sources: ~230 files (7 docs + 6 journal + 5 texts + 12 courses)

## [2026-07-16] conversion | Conversión masiva de cursos a Markdown

- Converted 13 `.tex` → `.md` (cálculo-vectorial, contabilidad, investigación-operaciones, etc.)
- Converted 5 `.docx` → `.md` (cálculo, cultura-empresarial, matematicas-discretas, poo)
- Converted 47 text-based `.pdf` → `.md` (álgebra lineal, cálculo, contabilidad, cultura-empresarial, fundamentos-programación, intro-ing-sistemas, matematicas-discretas)
- Moved all converted originals to `trash/` (11 `.tex`, 5 `.docx`, 10 `.pdf`)
- Scanned PDFs (imágenes) preserved as-is: química (4), exámenes de cálculo e intro-ing-sistemas (9)
- Verified no `md` files duplicate the same concept from a single source
- Updated `wiki/index.md` with accurate file counts and summaries per course
- Total raw sources: 7 docs + 6 journal + 5 texts + 67 md + 36 img + 15 py/cpp/psc/txt + 13 pdf escaneados

## [2026-07-16] ingest | Ingest de raw/texts/ (5 fuentes)

- Read all 5 source files in `raw/texts/` end-to-end
- Identified key concepts, entities, and claims across all texts
- Created 8 concept pages in `wiki/concepts/`:
  - fundamentos-conocimiento, critica-prensa, dios-como-pi, dios-nada-maldad-dios, perspectiva-dios-conjuntos, analogia-matematica-teologia, teoria-conjuntos-teologia, semejanza-divina
- Created 4 entity pages in `wiki/entities/`:
  - rosendo-camal, san-agustin, karl-barth, tomas-de-aquino
- Created 5 source pages in `wiki/sources/`:
  - fuent-cuales-son-los-fundamentos, fuente-extra-extra-la-prensa-en-inaccion, fuente-relacion-dios-humanos, fuente-relacion-nada-maldad-dios, fuente-una-perspectiva-de-dios
- Updated `wiki/index.md` with all new wiki pages (entities, concepts, sources)
- Cross-references added: every page links to ≥2 related wiki pages via [[wikilinks]]
- Claims cited with source name and year
- Contradictions and open questions flagged with callout blocks
- Total wiki pages: 4 entities + 8 concepts + 5 sources = 17 pages

## [2026-07-16] ingest | Ingest de raw/courses/ (53 archivos, 10 materias)

- Read all 53 source files across 10 subject directories end-to-end
- Created 10 entity pages in `wiki/entities/`:
  - george-boole, claude-shannon, gottfried-leibniz, leonhard-euler, john-venn, andrew-booth, linus-torvalds, grace-hopper, dennis-ritchie, miguel-quintana-pali
- Created 20 concept pages in `wiki/concepts/`:
  - algebra-booleana, teoria-conjuntos-discretas, teoria-grafos, sistema-binario, mapas-karnaugh, algoritmo-booth, simbologia-matematica, logica-computacional, analisis-foda, contabilidad-basica, algebra-lineal-programacion, vectores-geometria-analitica, calculo-integral, calculo-diferencial, fundamentos-programacion, linux, hardware-computacion, cultura-empresarial, investigacion-operaciones, programacion-orientada-objetos, linea-tiempo-lenguajes-programacion
- Created 10 source pages in `wiki/sources/`:
  - fuente-curso-algebra-lineal, fuente-curso-calculo, fuente-curso-calculo-vectorial, fuente-curso-contabilidad-financiera, fuente-curso-cultura-empresarial, fuente-curso-fundamentos-programacion, fuente-curso-intro-ing-sistemas, fuente-curso-investigacion-operaciones, fuente-curso-matematicas-discretas, fuente-curso-poo
- Updated `wiki/index.md` with new entities, concepts, sources; course table now links to source pages
- Cross-references added: every new page links to ≥2 related wiki pages via [[wikilinks]]
- Concepts from courses link to entities (historical figures) and to existing wiki pages (e.g. teoria-conjuntos-discretas ↔ teoria-conjuntos-teologia)
- Skip: ejercicio puro files (actividad_02–_13, tareas sin contenido conceptual nuevo) — cubiertos por concept + source page
- Total raw sources: 53 courses + 7 docs + 6 journal + 5 texts = 71
- Total wiki pages: 14 entities + 28 concepts + 15 sources + 1 log + 1 state = 58 páginas wiki

## [2026-07-16] state | Mitigación de desincronización entre sesiones

- Created `wiki/STATE.md`: snapshot del vault con conteos, últimas operaciones y pending items
- Added "On Session Start" section to `AGENTS.md` pointing to `wiki/STATE.md`
- Updated `wiki/index.md` count to include STATE.md
- Total wiki pages: 14 entities + 28 concepts + 15 sources + 1 log + 1 state = 59

## [2026-07-17] ingest | Ingest raw/docs/ y raw/journal/

- Leídos 7 archivos en `raw/docs/` (guías técnicas: Git, Fedora, VirtualBox, 7z, Diskpart) y 6 en `raw/journal/`
- Creadas 4 entities: git, fedora, virtualbox, seven-zip
- Creados 12 concepts:
  - 7 desde docs: guia-git-configuracion, guia-git-eliminar-archivo, guia-github-nuevo-repo, guia-fedora-primeros-pasos, guia-virtualbox-fedora, guia-7z-cifrado-compresion, guia-diskpart-usb
  - 5 desde journal: reflexion-identidad-eternidad, aprendizaje-vs-entretenimiento, problemas-fundamentales-sociedad, salud-y-economia-farmaceutica, plan-algoritmia
- Creadas 4 source pages: fuente-tech-guides (docs), fuente-journal-filosofia, fuente-journal-calculo, fuente-journal-algoritmos (journal)
- Actualizado concept `calculo-diferencial` añadiendo fuente `raw/journal/2025-01-26.md`
- Actualizado `wiki/index.md` con nuevas entidades, conceptos y fuentes
- Cross-references añadidas: cada página enlaza a ≥2 páginas wiki relacionadas
- Total raw sources: 71 (sin cambios)
- Total wiki pages: 18 entities + 40 concepts + 19 sources + 1 log + 1 state = 79 páginas wiki