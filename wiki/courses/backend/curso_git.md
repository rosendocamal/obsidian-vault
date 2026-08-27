# Documentación de Git

| Fecha de inicio | Fecha de finalización |
|-----------------|-----------------------|
| 2026-08-10      | 2026-08-16            |

## Configuración global de Git

Agregar nombre de usuario y correo electrónico:

```
git config --global user.name "NAME"

git config --global user.email "EMAIL"
```

## Básico

Para iniciar un proyecto con Git:

```
git init
```

Para agregar los cambios y archivos al historial de Git:

```
git add FILE
```

Para agregar los cambios realizados de varios archivos y sin discriminar ni seleccionar:

```
git add .
```

Para guardar los cambios (commit):

```
git commit -m "MESSAGE"
```

En cualquier momento podemos observar los cambios, y el estado del proyecto con:

```
git status
```

## Cambios del proyecto

Te regresa al último cambio realizado del archivo indicado, es decir, no guarda los últimos cambios realizados y te regresa a la versión anterior.

```
git checkout FILE
```

Te permite ver los archivos con cambios realizados y que puedes regresar a su cambio anterior guardado.

```
git reset
```

> Se necesita crear un archivo `.gitignore` en donde se escribe los archivos y carpetas a ignorar del proyecto.
> Si ponemos `**` dentro de una ruta lo indicaremos que no importa la ubicación y si ponemos `*` estares señalando que todo dentro del directorio no se va a agregar.

Si queremos regresar a un punto concreto del commit y nos queremos contemplar los últimos cambios podemos usar:

```
git reset --hard ID
```

Lo anterior cambia el `HEAD` a esa posición, si revisamos `log` no hallaremos los cambios posteriores a nuestra posición actual. El `HEAD` no es más que la posición final de cada proyecto, rama, la parte presente donde estamos trabajando.

Para ver el historial completo usamos `reflog` y es el historial completo de todas las interacciones con git. Así lo anterior una vez ejecutado, no se pierde. Para regresar a pesar de usar `reset --hard`, volvemos a usar este mismo comando usando un ID posterior (el que queramos o necesitemos) al anterior utilizado.

```
git reflog
```

## Ramas

Cambiar nombre de rama:

```
git brach -m NEW_NAME
```

Para crear una rama:

```
git brach NAME
```

Para cambiar la rama donde estamos trabajando para trabajar en otra:

``` 
git switch BRANCH
```

> ¿Para qué sirve `git checkout -b NEW_RAMA`?
> Mejor dicho ¿qué hace `checkout`?

# Fusionar ramas

Para fusionar ramas (de donde estamos y otra), cambiamos BRANCH por la otra rama. La fusión solo se verá en la rama que estamos trabajando y se hará un commit:

```
git merge BRANCH
```

Si tenemos un conflicto en las ramas corregimos eso, agregamos con `add` los cambios y hacemos un `commit`. Con ello el conflicto del `merge` queda resuelto y finalizamos el `merge`.

# Eliminar ramas

Para eliminar una rama se utiliza el siguiente comando:

```
git branch -d BRANCH
```

## Stash

Para hacer una especie de `commit` sin ser que sea oficialmente un `commit` usamos, solo nosotros podemos ver eso y es útil para guardar lo que hemos hecho temporalmente:

```
git stash
```

Para ver el listado de los `commit` temporales podemos usar:

```
git stash list
```

Para utilizar el `stash` en caso de regresar a ello:

```
git stash pop
```

Para eliminar un `stash` del historial de stash:

```
git stash drop
```

## Historial de commit

Para ver el historial de commits:

```
git log
```

Para ver de forma visual la evolución del historial:

```
git log --graph
```

Para ver el historial de forma simple y rápida (se ve el hash y el mensaje del commit):

```
git log --graph --pretty=oneline
```

```
git log --graph --decorate --all --oneline
```

Para moverse dentro del historial podemos utilizar el id de un commit para regresar a ese estado con:

```
git checkout ID
```

Con lo anterior nos estaremos ubicando en ese commit, o cambio, de la misma forma podremos regresar a la parte final de la rama (el estado por defecto en cualquier proyecto, que es el final donde estamos trabajando) usando el mismo comando anterior cambiando el ID por el correspondiente. Los IDs se pueden obtener con `git log`.

## Alias

Para crear un alias, una forma de flojera sofisticada no apto para principiantes para evitar repetir comandos extensos.

Ejemplo: Crear un alias con nombre de `tree` para ejecutar `git log --graph --decorate --all --oneline`:

```
git config global alias.tree "log --graph --decorate --all --oneline"
```

Aquí se guarda el alias de forma global, es decir, en todos nuestros repositorios locales de Git que tenemos. A partir de ahora,
ya se puede ejecutar el comando con `git tree` en lugar de escribir toda la extensión del comando.

## Comparar cambios

Para comparar cambios (para ver qué hemos cambiado) sin necesidad de guardar el código porque aún no queremos (o no podemos, o no debemos):

```
git diff
```

## Etiquetas

Para marcar algunos commits que consideremos importante y no requerir usar los IDs (por su extensión y díficil referencia) podemos emplear etiquetas en lugar de hacer referencia con su ID. Los tags lo podemos ver en `log`. La nomenclatura usada para escribir las etiquetas es que deben ser en minúsculas y sin espacios (usando underscore). Para añadir una etiqueta en donde estamos trabando en Git es:

```
git tag TAG
```

Para listar los tags:

``` 
git tag
```

También puedes utilizar los tags para cambiar el `HEAD` usando `checkout`:

```
git checkout tag/TAG
```

## Eliminar commit

Investigar sobre `revert` cuando más adelante tengamos experiencia ya que es muy peligroso y drástico.

---

# Documentación de GitHub

## Crear llave SSH para autenticación con GitHub (para Linux, distro Fedora)

Primero se crea la llave SSH:

```
ssh-keygen -t ed25519 -C "correo@dominio.com"
```

Después se agrega la llave al ssh-agent:

```
eval "$(ssh-agent -s)"
```

```
ssh-add ~/.ssh/id_ed25519
```

## Subir la llave pública a GitHub (web browser, Linux)

Copias la llave pública y lo pegas donde corresponda en la sección de la web de GitHub:

```
cat ~/.ssh/id_ed25519.pub | wl-copy
```

## Comprobación conexión con el servidor de GitHub

Utiliza el comando:

```
ssh -T git@github.com
```

> En ocasiones, tienes que ejecutar el comando una vez más dado que el primero pudiera dar error.

## Repositorios en la nube (servidor de GitHub)

Si se ha creado un nuevo repositorio:

```
echo "# new-repo" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:user/new-repo.git
git push -u origin main
```

O para enviar archivos de un repositorio ya creado:

```
git remote add origin git@github.com:user/new-repo.git
git branch -M main
git push -u origin main
```

## Subir archivos y actualizaciones de proyecto a GitHub

Para subir archivos se sigue el orden de los comandos `add`, `commit` y `push`.

Si hay conflictos al hacer `push` se procede de la siguiente manera:

### Comandos de Git: Fetch y Pull

El siguiente comando se descarga de GitHub el historial de cambios, no descargo los archivos:

```
git fetch
```

Luego procedo con `log` y el alias `tree` (que hemos creado anteriormente) para ver cual fue el problema.

Procedemos con `pull`:

```
git pull origin main
```

```
git merge origin main
```

```
git config pull.rebase false # Hay otras configuraciones, este hace un merge
```

```
git pull origin main
```

```
git push
```

## Clonar repositorios

Para clonar un repositorio necesitamos la url para SSH del repositorio:

```
git clone git@github.com:user/new-repo.git
```

## Git Fork, sincronizaión, pull request, issues.

En la web de GitHub está la opción del `Fork` en el repositorio que queremos modificar y que no tengamos acceso.

Clonas el repositorio y posteriormente realizas lo que tengas que realizar de manera local y luego realizas lo subes a tu `fork` de tu cuenta de GitHub.

En ese repositorio `fork` en nuestro GitHub tenemos las opciones de `Sync repo` y `Contribute` (`Open Pull Request`). Con el `pull request` envías tus cambios personales al repositorio oficial del que no tienes acceso para hacer colaboración.

Para sincronizar nuestro repositorio con el repositorio oficial, seleccionamos `Sync repo` y actualizamos.

## GitHub Markdown

## Herramientas gráficas para Git y GitHub

* `GitHub Desktop`
* `GitKraken`
* `Source Tree`
* `Git Fork`

## Git & GitHub Workflows

* `git-flow`

## cherry-pick & rebase (comandos delicados y avanzados)

**Cherry-pick**: Consiste (en términos sencillos y vagos) en traer un `commit` concreto a una rama que queramos.

```
git cherry-pick ID
```

Para avanzar con el cherry-pick:

```
git cherry-pick --continue
```

Para parar el proceso si nos equivocamos o algo sale mal:

```
git cherry-pick --abort
```

**Rebase**: Sirve para adelantar los commits o la rama arriba de nuestro `HEAD`, como si fuera lo último que se ha hecho (sin importar lo que estamos trabajando) y encima sin realizar alguna especie de `merge`. Es como poner los commits seleccionados a la parte final, como adelanto de nuestra posición del proyecto.

```
git rebase -i
```
```
git rebase --continue
```
```
git rebase --abort
```

## GitHub Pages

Hay documentación original de GitHub Pages.

## GitHub Actions

Hay documentación original de GitHub Actions.
