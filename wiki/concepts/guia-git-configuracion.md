---
title: "Configurar Git y conectar con GitHub"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/configurar_git_conectar_github.md
tags: [git, github, ssh, configuracion]
---

# Configurar Git y conectar con GitHub

Pasos para configurar Git y conectar a GitHub mediante SSH, en un sistema Fedora (o cualquier Linux). (configurar_git_conectar_github, 2026)

## Configuración de Git

- `git config --global user.name "Your name"` — establecer el nombre de usuario
- `git config --global user.email mail@domain.com` — establecer el email
- `git config --list` — verificar la configuración actual

## Conexión SSH

1. Revisar claves existentes: `ls -al ~/.ssh`
2. Generar clave SSH: `ssh-keygen -t ed25519 -f ~/.ssh/git_workshop -C "mail@domain.com"`
3. Iniciar ssh-agent: `eval $(ssh-agent -s)`
4. Añadir clave al agente: `ssh-add ~/.ssh/git_workshop`
5. Configurar el archivo `~/.ssh/config` con el bloque `Host github.com ... IdentityFile ~/.ssh/git_workshop`
6. Establecer permisos correctos: `chmod 600 ~/.ssh/config`
7. Copiar la clave pública: `cat ~/.ssh/git_workshop.pub | xclip -sel clip` (o manualmente)
8. Agregar clave en GitHub: Settings → SSH and GPG Keys → New SSH Key
9. Verificar conexión: `ssh -T git@github.com`

## Clonar repositorio

```
git clone git@github.com:user/repo.git
````

## Relaciones

- Git es obra de [[linus-torvalds]] (ver [[git]])
- Plataforma remota [[github]]
- Guías relacionadas: [[guia-git-eliminar-archivo]], [[guia-github-nuevo-repo]]

