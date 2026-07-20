---
title: "Primeros pasos con Fedora"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/instalacion_fedora_43.md
tags: [fedora, linux, instalación, configuración]
---

# Primeros pasos con Fedora

Pasos esenciales para configurar una instalación limpia de Fedora. (instalacion_fedora_43, 2026)

## Actualización del sistema

    sudo dnf upgrade --refresh -y

## Programas esenciales

    sudo dnf install ranger neovim git chromium tmux -y
    sudo dnf install tlp tlp-rdw -y

## Gestión de batería (laptop)

1. Deshabilitar el gestor de energía nativo de GNOME:
    sudo systemctl mask power-profiles-daemon
2. Habilitar TLP:
    sudo systemctl enable tlp --now

3. Configurar límite de carga en /etc/tlp.conf (START_CHARGE_THRESH_BAT0=75, STOP_CHARGE_THRESH_BAT0=80)
4. Aplicar: sudo tlp start

## Cifrado de archivos sensibles

1. Cifrar: gpg -c file_name
2. Eliminar original de forma segura: shred -u file_name
3. Descifrar: gpg -d file_name.gpg > file_name

## Relaciones

- Fedora es una distribución Linux (ver [[fedora]] y [[linux]])
- Herramientas instaladas incluyen [[git]], neovim, tmux
- TLP gestión de energía
- Relacionado con [[guia-virtualbox-fedora]] (VirtualBox en Fedora)

