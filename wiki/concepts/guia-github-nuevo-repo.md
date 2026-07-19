---
title: "Nuevo repositorio en GitHub"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/new_repository_github.md
tags: [git, github, inicio, configuracion]
---

# Nuevo repositorio en GitHub

Pasos para crear y conectar un repositorio local con uno remoto en GitHub.

## Flujo

```
# Si se empieza desde cero
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:user/name-repo.git
git push -u origin main

# Si se tiene un repo local ya existente
git remote add origin git@github.com:user/name-repo.git
git branch -M main
git push -u origin main
```

## Notas

- `git branch -M main` renombra la rama actual a "main"
- `-u` flag en push define el tracking remoto para futuros push sin especificar
- Utiliza SSH (no HTTPS) para evitar tener que escribir contraseña en cada push

## Relaciones

- Ver [[guia-git-configuracion]] para configurar SSH antes de este paso
- Ver [[guia-git-eliminar-archivo]] para deshacer errores
- Es la forma estándar de pushear proyectos completos

