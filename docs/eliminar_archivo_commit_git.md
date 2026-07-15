# ELIMINAR ARCHIVO INDEBIDO SUBIDO A GITHUB Y REVERTIR LA SITUACIÓN

| Autor         | Fecha      |
| ------------- | ---------- |
| Rosendo Camal | 2026-07-15 |

## Objetivo

Siempre que subamos archivos que no debamos a GitHub, por ser sensibles, basura, etc., debemos poder revertir la situación y saber hacerlo. Para este caso, he preparado esta guía para manejar esta situación si y solo si fue el último commit del historial. Siguiendo este procedimiento podemos arreglar nuestro error y que no haya filtraciones a tráves del historial de versiones.

## Procedimiento

Si el archivo es muy importante lo tenemos que retirar de nuestro repositorio antes de ejecutar los siguientes comandos y regresarlo a su ubicación cuando finalicemos. 

> [!IMPORTANT]
> Estos pasos solo aplican si fue el último commit, de lo contrario, será en vano ejecutarlos.

1. Sacamos el archivo del control de Git (sin eliminarlo de la computadora). El fragmento `[FILE]` debe ser sustituido por el nombre del archivo correspondiente.

```
git rm --cached [FILE]
```

2. Añadimos el nombre del archivo archivo a `.gitignore` para que Git no intente subirlo.

3. Ahora modificaremos el último commit para «reescribir» el historial local y fusionar el borrado con el commit anterior:

```
git add .gitignore
git commit --amend --no-edit
```

4. Subimos los cambios a GitHub a la fuerza para sobreescribir el historial remoto. El fragmento `[BRANCH]` lo debes cambiar por el nombre de la rama correspondiente.

```
git push origin [BRANCH] --force
```

5. Verificamos en GitHub, por tranquilidad mental, que efectivamente ya no esté lo indebido en el repositorio así como en el historial.

## Resultado

Siguiendo estas instrucciones podemos eliminar el archivo que subimos al repositorio de GitHub y del historial de control de versiones, de esta manera no haya filtraciones adicionales derivado de nuestro error.
