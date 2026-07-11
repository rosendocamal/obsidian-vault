# MIS PRIMEROS PASOS CON FEDORA

| Autor         | Fecha      | Actualización |
|---------------|------------|---------------|
| Rosendo Camal | 11/12/2025 | 10/07/2026    |

## Actualización de Fedora

Antes de configurar Fedora actualicé todo:

```
$ sudo dnf upgrade --refresh -y
```

Esto evitará conflictos de paquetes y errores al instalar software.

> Nota: `dnf upgrade` ya hace el trabajo de `update` y `clean all` no es estrictamente necesario al inicio.

## Instalación de programas

Una vez hecho lo anterior paso a instalar mis programas de uso con el comando `sudo dnf install [program] -y`.

En mi caso los programas que instalaré son `ranger`, `neovim`, `git`, `chromium` y `tmux`.

```
$ sudo dnf install ranger neovim git chromium tmux -y
```

También instalaré `tlp` y `tlp-rdw` para la gestión de batería.

```
$ sudo dnf install tlp tlp-rdw -y
``` 


## Límite de carga al 80%

Debido a que mi dispositivo es una Laptop Lenovo, **quise** recuperar varias opciones que me brindaba la aplicación de Lenovo Vantage y el límite de carga es uno de ellos.

> **IMPORTANTE:** Para usar TLP en Fedora sin conflictos, debemos desactivar el gestor de energía por defecto de GNOME.

```
# 1. Deshabilitar el gestor de nativo para evitar conflictos
$ sudo systemctl mask power-profiles-daemon

# 2. Habilitar TLP
$ sudo systemctl enable tlp --now
```

Verifico el estado de servicio:

```
$ tlp-stat -s
```

Si está activo, configuro el archivo en la ruta `/etc/tlp.conf`:

```
$ sudo nvim /etc/tlp.conf
```

Busco y descomento las líneas: `START_CHARGE_THRESH_BAT0=75` y `STOP_CHARGE_THRESH_BAT0=80`.

Para aplicar los cambios automáticamente de dicho archivo, ejecutamos:

```
$ sudo tlp start
```

### Cifrado

Para cifrado de archivos sensibles:

```
# 1. Cifrar el archivo (creará uno nuevo con extensión .gpg)
$ gpg -c file_name

# 2. IMPORTANTE: Borrar el original de forma segura (para que no quede expuesto)
$ shred -u file_name

# 3. Para recuperar/descifrar el archivo cuando lo necesites
$ gpg -d file_name.gpg > file_name
```

## Nota final

Estos son los comandos que requiero al momento de una instalación o reinstalación de Linux Fedora.
