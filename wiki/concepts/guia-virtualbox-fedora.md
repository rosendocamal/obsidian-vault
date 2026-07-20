---
title: "Instalar VirtualBox en Fedora"
type: concept
created: 2026-07-17
updated: 2026-07-17
sources:
  - raw/docs/virtualbox_fedora_43.md
tags: [virtualbox, fedora, virtualización]
---

# Instalar VirtualBox en Fedora

Pasos para instalar VirtualBox en Fedora, con soporte completo para Secure Boot. (virtualbox_fedora_43, 2026)

## 1. Instalar dependencias

    sudo dnf install @development-tools
    sudo dnf install kernel-headers kernel-devel dkms

## 2. Añadir repositorio

Crear /etc/yum.repos.d/virtualbox.repo con el contenido del repositorio oficial.

## 3. Instalar VirtualBox y Extension Pack

    sudo dnf update
    sudo dnf install VirtualBox-7.2
    # Descargar e instalar Extension Pack según la versión

## 4. Agregar usuario al grupo

    sudo usermod -a -G vboxusers $USER

Cerrar sesión y volver a entrar para que surta efecto.

## 5. Secure Boot — Firma de módulos

- Generar MOK: openssl req -new ... -out /root/module-signing/MOK.der
- Importar a BIOS: mokutil --import /root/module-signing/MOK.der
- Reiniciar, enrolar en Shìm, firmar, cargar el modulo.

## 5. Desinstalar

    sudo dnf remove VirtualBox* -y

## Descripción

VirtualBox (ver [[virtualbox]]) es una herramienta de virtualización de código abierto de Oracle, que permite ejecutar sistemas operativos huéspedes dentro de un anfitrión. Muy usada para desarrollo, pruebas y educación.

## Relaciones

- Se ejecuta sobre [[fedora]]
- VirtualBox es una alternativa a VMware (ver [[virtualbox]])
- El proceso de firma de módulos es un ejemplo de la configuración avanzada de Fedora ([[guia-fedora-primeros-pasos]])

