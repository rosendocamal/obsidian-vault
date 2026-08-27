# Curso de Docker

| Inicio | Fin | Actualización |
|-|-|-|
| 2026-08-24 | 2026-08-25 | |

## Conceptos

* Contenedor
* Imagen
* Repositorios de contenedores
    - Docker Hub
* Virtualización
    - Paravirtualización
    - Virtualización parcial
    - Virtualización completa
    - Diferencias de Docker y Virtualización
* Docker Desktop
    - Docker Compose
* Variables de entorno
* _Port mapping_

## Instalación de Docker Desktop

> [!IMPORTANT]
> Guía (**dockerdocs**) para instalar [**Docker Desktop**](https://docs.docker.com/desktop/setup/install/linux/fedora/) en Fedora.

## Uso de Docker

Para ver si tenemos imágenes:

```bash
docker images
```

Descargar una imagen, en este ejemplo `node`:

```bash
docker pull node
```

Descargar una imagen con una versión específica (ejemplo con `node v18` y `v16`):

```bash
docker pull node:16
docker pull node:18
```

Igual podemos descargar de esta manera otras imagenes:

```bash
docker pull mysql
```

De manera similar, podemos emplear un comando para realizar lo anterior con una ligera diferencia (indicando la plataforma a usar):

```bash
docker pull --platform linux/x86_64 mysql
```

Para eliminar imagenes descargadas:

```bash
docker image rm node
docker image rm mysql
docker image rm node:18
docker image rm node:16
```

Para crear un contenedor utilizamos el comando `docker create IMAGE`:

```bash
docker pull mongo

docker create mongo
```

> [!TIP]
> Podemos utilizar `wl-copy` mediante **pipes** y así capturar el **ID** que utilizaremos más adelante para levantar el contenedor. Para pegar el **ID**, utilizaremos el atajo de teclas `CTRL`, `SHIFT` más `V`.

El comando `docker create IMAGE` es una versión corta de:

```bash
docker container create IMAGE
```

Corremos nuestro contenedor:

```bash
docker docker ID
```

Para ver si está ejecutándose nuestro contenedor:

```bash
docker ps
```

Con el comando de Docker `ps` obtendremos otro **ID** del contenedor en ejecución, si queremos detenerlo haremos uso de ese **ID**:

```bash
docker stop ID
```

Para mostrar todos los contenedores que existen en nuestro sistema:

```bash
docker ps -a
```

Usando `ps` podemos observar que cada contenedor se le asigna tanto un **ID** como un **NAME**. Haremos uso del **NAME** para eliminar un contenedor (no detener su servicio, es eliminarlo):

```bash
docker rm NAME
```

> [!IMPORTANT]
> Antes de eliminar cualquier contenedor, no debería estar ejecutándose. Primero debes detener el servicio.

Nosotros podemos asignar un nombre al contenedor con el siguiente comando:

```bash
docker create --name NAME IMAGE
```

> [!TIP]
> Ya no es necesario capturar el **ID** al momento de crear el contenedor, podemos ya referenciarlo por el **NAME** que nosotros le hemos asignado mediante este comando.

Para el _port mapping_ podemos crear el contenedor de esta manera, reemplazando **HOST** por el puerto de nuestro equipo y **CONTENEDOR** por el puerto del contenedor:

```bash
docker create -pHOST:CONTENEDOR --name NAME IMAGE
```

Lo anterior se puede realizar de la siguiente manera, donde solo asignamos el puerto del **CONTENEDOR** y Docker se encargaría de asignar el puerto del **HOST**:

```bash
docker create -pCONTENEDOR --name NAME IMAGE
```

Si queremos saber si nuestro contenedor se está ejecutando de forma correcta, le podemos hechar un vistazo a los `logs` (usando el **ID**):

```bash
docker logs ID
```

O mediante el uso del **NAME** asignado:

```bash
docker logs NAME
```

Para mantener en tiempo real los `logs` podemos escuchar y esperar de esta forma:

```bash
docker logs --follow NAME
```

Una manera de realizar rápido las acciones de `pull`,  `create`, `start` y `logs --follow` es usando lo siguiente:

```bash
docker run IMAGE
```

El problema de `run` es que para salirnos de `logs --follow`, tendríamos que emplear `CRTL` más `C` y eso llevaría a detener el contenedor. Así para ejecutar `run` en modo _DeHached_ haremos lo siguiente:

```bash
docker run -d IMAGE
```

Con `run` podemos asignar el **NAME** del contenedor en servicio y el _port mapping_:

```bash
docker run --name NAME -pHOST:CONTENEDOR -d IMAGE
```

## Ejemplo práctico

Creamos el siguiente archivo en `JavaScript`:

```javascript
import express from 'express'
import mongoose from 'mongoose'

const Animal = mongoose.model('Animal', new mongoose.Schema({
	tipo: String,
	estado: String,
}))

const app = express()

mongoose.connect('mongodb://user:password@localhost:27017/miapp?authSource=admin')

app.get('/', async (_req, res) => {
	console.log('Listando...')
	const animales = await Animal.find();
	return res.send(animales)
})
app.get('/crear', async (_req, res) => {
	console.log('Creando...')
	await Animal.create({ tipo: 'Changuito', estado: 'Feliz' })
	return res.send('ok')
})

app.listen(3000, () => console.log('Escuchando...'))
```

Descargamos la imagen de `mongo`:

```bash
docker pull mongo
```

Creamos la imagen con el mapeo de puestos, le asignamos nombre al contenedor y le añadimos las **variables de entorno** (cada imagen se configura distinto):

```bash
docker create -p27017:27017 --name example -e MONGO_INITDB_ROOT_USERNAME=user -e MONGO_INITDB_ROOT_PASSWORD=password mongo
```

Levantamos el contenedor:

```bash
docker start example
```

Ahora vamos a ejecutar el archivo `js`:

```bash
node index.js
```

> [!NOTE]
> Si surge un error, primero hay que instalar **NodeJS** y descargar con `npm install express && npm install mongoose` las librerías a utilizar. Una vez realizado lo dicho, se vuelve a ejecutar el archivo `js` con `node index.js`.

Al ejecutar el comando, debemos ver el siguiente _input_:

```bash
Escuchando...
```

De ser así, está en ejecución y podremos ir al navegador a la ruta `localhost:3000`, luego irnos a `localhost:3000/crear` y por último regresar a la ruta raíz `localhost:3000/`. Y regresamos a la ventana de la terminal y podemos notar los siguientes `logs`:

```bash
Listando...
Creando...
Listando...
```

Cancelamos la operación con `CTRL` más `C` del archivo `js` con `nodejs`. Y ahora vamos a realizar la versión usando **Docker**.

---
Para listar las redes configuradas en **Docker**:

```bash
docker network ls
```

Para crear una red:

```bash
docker network create RED_NAME
```

Para eliminar una red:

```bash
docker newtork rm RED_NAME
```
---

Ahora creamos una red:

```bash
docker network create mired
``` 

En el archivo `js` modificamos la línea:

```javascript
mongoose.connect('mongodb://user:password@localhost:27017/miapp?authSource=admin')
```

Por la siguiente línea (`localhost` por el nombre del contenedor, `example`):

```javascript
mongoose.connect('mongodb://user:password@example:27017/miapp?authSource=admin')
```

Creamos un archivo con nombre obligatorio `Dockerfile`:

```dockerfile
FROM node:18

RUN mkdir -p /home/app

COPY . /home/app

EXPOSE 3000

CMD ["node", "/home/app/index.js"]
```

Y pasamos a crear nuestra imagen de Docker:

```bash
docker build -t miapp:1 .
```

> En el comando de arriba, `miapp` es el nombre de la imagen que le vamos a dar, `1` el número de versión o control que le daremos, y el punto es la ruta donde está los recursos para hacer la imagen.

No usamos el contenedor Docker de líneas arriba, sin embargo, vamos a eliminarlo y crear otro asignando el nombre de la red y las variables de entorno.

```bash
docker create -p27017:27017 --name example --network mired -e MONGO_INITDB_ROOT_USERNAME=user -e MONGO_INITDB_ROOT_PASSWORD=password mongo
```

Y también:

```bash
docker create -p3000:3000 --name ejemplo --network mired miapp:1
```

Iniciamos los contenedores:

```bash
docker start example && docker start ejemplo
```

Realizamos las accciones en la dirección de `localhost:3000` como la vez anterior. Y luego checamos los `logs`:

```bash
docker logs ejemplo
```

Y el _output_ debe ser:

```bash
Escuchando...
Listando...
Creando...
Listando...
```

Ahora pasamos a la automatización de los pasos anteriores con `Docker Compose`.

Creamos el archivo `docker-compose.yml`:

```yml
version: "3.9"
services:
  ejemplo:
    build: .
    ports:
      - "3000:3000"
    links:
      - example
  example:
    image: mongo
    ports:
      - "27017:27017"
    environment:
      - MONGO_INITDB_ROOT_USERNAME=user
      - MONGO_INITDB_ROOT_PASSWORD=password
```

Y ejecutamos:

```bash
docker compose up
``` 

Y para eliminar todo los contenedores e imágenes creadas por `compose` usamos:

```bash
docker compose down
```

Para el uso de **volumes** modificamos el archivo `docker-compose.yml`:

```yml
version: "3.9"
services:
  ejemplo:
    build: .
    ports:
      - "3000:3000"
    links:
      - example
  example:
    image: mongo
    ports:
      - "27017:27017"
    environment:
      - MONGO_INITDB_ROOT_USERNAME=user
      - MONGO_INITDB_ROOT_PASSWORD=password
    volumes:
      - mongo-data:/data/db

volumes:
  mongo-data:
```

Y ejecutamos `docker compose up`.

Volvemos a ejecutar `docker compose down`.

Ahora pasamos al entorno de desarrollo y el producción, ahora para manejar de forma distinta los entornos. Creamos dos archivos: `Dockerfile.dev` y `docker-compose-dev.yml`. 

`Dockerfile.dev`:

```
FROM node:18

RUN npm i -g nodemon
RUN npm install express
RUN npm install mongoose
RUN mkdir -p /home/app

WORKDIR /home/app

EXPOSE 3000

CMD ["node", "index.js"]
```

`docker-compose-dev.yml`:

```yml
version: "3.9"
services:
  ejemplo:
    build:
      context: .
      dockerfile: Dockerfile.dev
    ports:
      - "3000:3000"
    links:
      - example
    volumes:
      - .:/home/app
  example:
    image: mongo
    ports:
      - "27017:27017"
    environment:
      - MONGO_INITDB_ROOT_USERNAME=user
      - MONGO_INITDB_ROOT_PASSWORD=password
    volumes:
      - mongo-data:/data/db

volumes:
  mongo-data:
```

Ahora ejecutamos:

```bash
docker compose -f docker-compose-dev.yml up
```

De esta manera tendremos dos ambientes: el de producción y el de desarrollo.
## Recursos adicionales

- Sitio oficial de [**Docker**](https://www.docker.com/).
- Repositorios [**Docker Hub**](https://hub.docker.com/).
