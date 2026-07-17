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