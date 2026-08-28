# Curso de Python enfocado en Backend

| Fecha de inicio | Fecha de finalización | Fecha de actualización |
|-----------------|-----------------------|------------------------|
| 2026-08-24      | 2026-08-24            | 2026-08-28             |

`Backend` `Python` `FastAPI` `MongoDB` `OAuth2` `JWT` `HTTP`

## Primeros pasos

Para instalar `FastAPI` con `pip`:

```bash
pip install "fastapi[standard]
```

Creamos un archivo `main` con Python:

```python
from fastapi import FastAPI

app = FastAPI()

@app.get("/")
async def root():
    return "¡Hola, FastAPI!"
```

Después abrimos el servidor local:

```bash
fastapi dev
```

### Otros conceptos a revisar

- **Routers**
- **Recursos estáticos**
- **Autorización OAuth2**

## OAuth2 JWT

Para usar `JWT` requerimos instalar `python-jose`:

```bash
pip install "python-jose[cryptography]"
```

También debemos instalar `passlib`:

```bash
pip install "passlib[bcrypt]"
```

Se puede generar números aleatorios en hexadecimal para una `semilla` (secreto):
```bash
openssl rand -hex 32
```

## MongoDB

Instalación de **MongoDB Community Edition** en Linux Fedora:

```bash
touch /etc/yum.repos.d/mongodb-org-8.3.repo
```

Y agregar el siguiente contenido en el archivo recién creado:
```bash
[mongodb-org-8.3]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/9/mongodb-org/8.3/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://pgp.mongodb.com/server-8.0.asc
```

Instalar **MongoDB Community Server**:

```bash
sudo yum install -y mongodb-org
```

Comenzar **MongoDB**:

```bash
sudo systemctl start mongod
sudo systemctl daemon-reaload
```

Revisa que haya iniciado con éxito:

```bash
sudo systemctl status mongod
sudo systemctl enable mongod
```

Para finalizar el servicio de MongoDB:

```bash
sudo systemctl stop mongod
```

Para reinicar el servicio de MongoDB:

```bash
sudo systemctl restart mongod
```

Para usar MongoDB:

```bash
mongosh
```

## Otros puntos

Para ingresar a nuestra documentación automática podemos utilizar `http://127.0.0.1/docs` o `http://127.0.01/redoc`.

Para el backend podemos emplear `Thunder Client` como extensión en `Visual Studio Code` o [`Postman`](https://www.postman.com/downloads/).

### Archivos

Estructura de los archivos realizados:

```bash
.
├── main.py
├── routers
│   ├── basic_auth_users.py
│   ├── jwt_auth_users.py
│   ├── products.py
│   └── users.py
└── static
    └── images
        └── img.webp
```

Contenido del fichero`main.py`:

```python
from fastapi import FastAPI
from routers import products, users, basic_auth_users, jwt_auth_users
from fastapi.staticfiles import StaticFiles

app = FastAPI()

# Routers
app.include_router(products.router)
app.include_router(users.router)
app.include_router(basic_auth_users.router)
app.include_router(jwt_auth_users.router)

# Recursos estáticos
app.mount("/static/", StaticFiles(directory="static"), name="static")

@app.get("/")
async def root():
    return "Hello World"

@app.get("/url")
async def url():
    return { "url_curso":"https://mouredev.com/python" }
```

El archivo `basic_auth_users.py` tiene el siguiente contenido:
```python
from fastapi import APIRouter, Depends, HTTPException, status
from pydantic import BaseModel
from fastapi.security import OAuth2PasswordBearer, OAuth2PasswordRequestForm

router = APIRouter()

oauth2 = OAuth2PasswordBearer(tokenUrl="login")

class User(BaseModel):
    username: str
    full_name: str
    email: str
    disabled: bool

class UserDB(User):
    password: str

users_db = {
        "juandev": {
            "username": "juandev",
            "full_name": "Juan del Desarrollo Español",
            "email": "juan.dev@dominio.txt",
            "disabled": False,
            "password": "qwerty"
            },
        "pedrodev": {
            "username": "pedrodev",
            "full_name": "Pedro de los Horrores",
            "email": "pedron.pedrin.dev@dominio.txt",
            "disabled": True,
            "password": "123456"
            }
        }

def search_user(username: str):
    if username in users_db:
        return UserDB(**users.db[username])

def search_user_db(username: str):
    if username in users_db:
        return User(**users_db[username])

async def current_user(token: str = Depends(oauth2)):
    user = search_user_db(token)
    if not user:
        raise HTTPException(
                status_code=status.HTTP_401_UNAUTHORIZED,
                detail="Credenciales de autenticación inválidas.",
                headers={"WWW-Authenticate": "Bearer"})

    if user.disabled:
        raise HTTPException(
                status_code=status.HTTP_400_BAD_REQUEST,
                detail="Usuario inactivo.")

    return user

@router.post("/login")
async def login(form: OAuth2PasswordRequestForm = Depends()):
    user_db = users_db.get(form.username)
    if not user_db:
        raise HTTPException(
                status_code=400, detail="El usuario no es correcto.")

    user = search_user_db(form.username)
    if not form.password == user.password:
        raise HTTPException(
                status_code=400, detail="La contraseña es incorrecta.")

    return {"access_token": user.username, "token_type": "bearer"}

@router.get("/users/me")
async def me(user: User = Depends(current_user)):
    return user 
```

El fichero `jwt_auth_users.py` contiene:

```python
from fastapi import APIRouter, Depends, HTTPException, status
from pydantic import BaseModel
from fastapi.security import OAuth2PasswordBearer, OAuth2PasswordRequestForm
from jose import jwt, JWTError
from passlib.context import CryptContext
from datetime import datetime, timedelta

ALGORITHM = "HS256"
ACCESS_TOKEN_DURATION = 1
SECRET = "3986e27dbbf9e76008b2cb44248ebbd65a0343c9f4a1405db299369ea1c884ee"

router = APIRouter()

oauth2 = OAuth2PasswordBearer(tokenUrl="login")

crypt = CryptContext(schemes=["bcrypt"])

class User(BaseModel):
    username: str
    full_name: str
    email: str
    disabled: bool

class UserDB(User):
    password: str

users_db = {
        "juandev": {
            "username": "juandev",
            "full_name": "Juan del Desarrollo Español",
            "email": "juan.dev@dominio.txt",
            "disabled": False,
            "password": "$2a$12$O/Ra1FAr9RaUdjBVJO6BR.9E1Zhea0sGL/aDt5vu3a0PyBbERxn6." # Original password: qwerty
            },
        "pedrodev": {
            "username": "pedrodev",
            "full_name": "Pedro de los Horrores",
            "email": "pedron.pedrin.dev@dominio.txt",
            "disabled": True,
            "password": "$2a$12$2d/4KjDUdTkxxCq91jSdP.Wdg1515HziVFbgE9VeJtvJOQyOY/Ezy" # Original password: 123456
            }
        }

def search_user_db(username: str):
    if username in users_db:
        return User(**users_db[username])

def search_user(username: str):
    if username in users_db:
        return User(**users_db[username])

async def auth_user(token: str = Depends(oauth2)):
    exception = HTTPException(
                status_code=status.HTTP_401_UNAUTHORIZED,
                detail="Credenciales de autenticación inválidas.",
                headers={"WWW-Autheticate": "Bearer"})

    try:
        username = jwt.decode(token, SECRET, algorithms=[ALGORITHM]).get("sub")
        if username is None:
            raise exception
    except JWTError:
        raise exception

    return search_user(username)

async def current_user(user: User = Depends(auth_user)):
    if user.disabled:
        raise HTTPException(
                status_code=status.HTTP_400_BAD_REQUEST,
                detail="Usuario inactivo.")

    return user

@router.post("/login")
async def login(form: OAuth2PasswordRequestForm = Depends()):
    user_db = users_db.get(form.username)
    if not user_db:
        raise HTTPException(
                status_code=400, detail="El usuario no es correcto.")

    user = search_user(form.username)

    crypt.verify(form.password, user.password)

    if not form.password == user.password:
        raise HTTPException(
                status_code=400, detail="La contraseña es incorrecta.")

    expire = datetime.utcnow() + timedelta(minutes=ACCESS_TOKEN_DURATION)
    access_token = {"sub": user.username, 
                    "exp": datetime.utcnow() + timedelta(minutes=ACCESS_TOKEN_DURATION)}

    return {"access_token": jwt.encode(access_token, algorithm=ALGORITHM), "token_type": "bearer"}

@router.get("/users/me")
async def me(user: User = Depends(current_user)):
    return user
```

El archivo `products.py` tiene el siguiente contenido:

```python
from fastapi import APIRouter

router = APIRouter(prefix="/products",
                   tags=["products"],
                   responses={404: {"message": "No encontrado."}})

products_list = ["Producto 1", "Producto 2", "Producto 3", "Producto 4", "Producto 5"]

@router.get("/")
async def products():
    return products_list

@router.get("/{id}")
async def products(id: int):
    return products_list[id]
```

El archivo `users.py` contiene:

```python
from fastapi import APIRouter, HTTPException
from pydantic import BaseModel

router = APIRouter(prefix="/users",
                   tags=["users"],
                   responses={404: {"message": "No encontrado."}})

# Entidad user
class User(BaseModel):
    id: int
    name: str
    surname: str
    url: str
    age: int

users_list = [User(id = 1, name = "Pedro", surname = "Spinoza", url = "https://pedrospinoza.com", age = 13),
              User(id = 2, name = "Juan", surname = "Lopez", url = "https://juanlopez.com", age = 52)]

@router.get("/usersjson")
async def usersjson():
    return [{"name": "Pedro", "surname": "Spinoza", "url": "https://pedrospinoza.com", "age": 13},
            {"name": "Juan", "surname": "Lopez", "url": "https://juanlopez.com", "age": 52}]


# Path 
@router.get("/users")
async def users():
    return users_list

@router.get("user/{id}")
async def user(id: int):
    return search_user(id)

# Query
@router.get("/user/")
async def user(id: int):
    return search_user(id)


@router.post("/user/", response_model=User, status_code=201)
async def user(user: User):
    if type(search_user(user.id)) == User:
        raise HTTPException(status_code=404, detail="El usuario ya existe")
    else:
        users_list.routerend(user)
        return user

@router.put("/user/")
async def user(user: User):

    found = False

    for index, saved_user in enumerate(users_list):
        if saved_user.id == user.id:
            users_list[index] = user
            found = True

    if not found:
        return { "error": "No se ha actualizado el usuario." }
    return user

@router.delete("/user/{id}")
async def user(id: int):
    
    found = False

    for index, saved_user in enumerate(users_list):
        if saved_user.id == user.id:
            del users_list[index]
            found = True

    if not found:
        return { "error": "No se ha eliminado al usuario." }

def search_user(id: int):
    users = filter(lambda user: user.id == id, users_list)
    try:
        return list(users)[0]
    except:
        return {"error": "No se ha encontrado el usuario."}
```

## Recursos adicionales

* [FastAPI](https://fastapi.tiangolo.com/)
* [Documentación JWT](https://www.jwt.io/)
* [Documentación MongoDB](https://www.mongodb.com/)
* [Documentación MongoDB Atlas](https://www.mongodb.com/products/platform)
* [HTTP response status code](https://developer.mozilla.org/en-US/docs/Web/HTTP/Reference/Status)