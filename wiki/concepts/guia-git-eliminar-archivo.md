---
title: "Eliminar archivo de un commit en Git"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/eliminar_archivo_commit_git.md
tags: [git, seguridad, recuperación]
---

# Eliminar archivo de un commit en Git

Procedimiento para eliminar un archivo subido indebidamente a un repositorio de GitHub, y limpiar el historial. (eliminar_archivo_commit_git, 2026)

## Restricciones

Estos pasos solo funcionan si el archivo se subió en el **último commit**. De lo contrario, se necesita una solución más compleja (como git filter-repo).

## Pasos

1. Quitar el archivo del control de versiones (pero mantenerlo en el disco): `git rm --cached [FILE]`
2. Añadir el archivo a `.gitignore` para que git no intente subirlo de nuevo.
3. Enmendar el commit: `git add .gitignore && git commit --amend --no-edit`
4. Forzar el push: `git push origin [BRANCH] --force`
5. Verificar en GitHub que el archivo y el historial estén limpios.

## Relaciones

- Git es obra de [[linus-torvalds]] (ver [[git]])
- Para limpiezas más complejas (eliminar archivos de commits antiguos) se necesita git filter-repo o BFG
- Muy relacionado con [[guia-git-configuracion]] y [[guia-github-nuevo-repo]]

