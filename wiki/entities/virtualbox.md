---
title: "VirtualBox"
type: entity
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/virtualbox_fedora_43.md
tags: [herramienta, virtualización, oráculo, codigo-abierto]
---

# VirtualBox

Programa de virtualización de código abierto, originalmente desarrollado por Innotek, posteriormente adquirido por Sun Microsystems y ahora por Oracle. Permite ejecutar sistemas operativos invitados dentro de un sistema anfitrión. (virtualbox_fedora_43, 2026)

## Componentes clave

- **Hypervisor tipo 2**: se ejecuta sobre el sistema operativo existente
- **Extension Pack**: añade soporte para USB 2.0/3.0, RDP y PXE
- **Guest Additions**: controladores para mejor integración con el anfitrión

## Instalación en Fedora

- Dependencias: kernel-headers, kernel-devel, dkms, build tools
- Repositorio oficial: añadir archivo `.repo` en `/etc/yum.repos.d/`
- Firma de módulos: necesario si Secure Boot está activado (MOK — Machine Owner Key)
- Grupo vboxusers: el usuario debe pertenecer a este grupo para acceder a dispositivos

## Relaciones

- Se ejecuta sobre un sistema anfitrión como [[fedora]] o Windows
- Es una alternativa a [[vmware]] y [[hyper-v]]
- Se utiliza en contextos educativos y de pruebas

