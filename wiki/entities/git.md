---
title: "Git"
type: entity
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/configurar_git_conectar_github.md
  - raw/docs/eliminar_archivo_commit_git.md
  - raw/docs/new_repository_github.md
tags: [herramienta, control-versiones, vcs, colaboracion]
---

# Git

Sistema de control de versiones distribuido, creado por [[linus-torvalds]] en 2005. Permite rastrear cambios en archivos, coordinar trabajo entre múltiples personas y gestionar proyectos de software.

## Uso básico

- `git init` — iniciar repositorio local
- `git add`, `git commit` — guardar cambios en el historial
- `git push`, `git pull` — sincronizar con remoto
- `git clone` — copiar repositorio remoto
- `git branch`, `git merge` — gestionar líneas de desarrollo

## Flujo de trabajo SSH

Para conectar con GitHub sin contraseña, se genera una clave SSH (`ssh-keygen`), se añade a ssh-agent y se registra la clave pública en la configuración de GitHub.

## Eliminar archivo del último commit

Cuando se sube un archivo no deseado, se puede usar `git rm --cached`, añadirlo a `.gitignore`, enmendar el último commit (`git commit --amend`) y forzar el push (`git push --force`).

## Relaciones

- Creado por [[linus-torvalds]], el mismo de [[linux]]
- Esencial para [[guia-git-configuracion]], [[guia-git-eliminar-archivo]], [[guia-github-nuevo-repo]]
- Junto con [[github]] constituye el ecosistema de control de versiones más usado del mundo
