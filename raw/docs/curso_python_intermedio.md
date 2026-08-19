# Curso Python Intermedio

| Fecha de inicio | Fecha de finalización | Fecha de actualización |
|-----------------|-----------------------|------------------------|
| 2026-08-18      |                       | -                      |

## Fechas

Para importar el módulo de fechas tenemos dos vías.

```python
# 1. Primera manera.
import datetime


# 2. Segunda manera.
from datetime import datetime
```

Para obtener la fecha y hora actual:

```python
datetime.now()
```

Y acceder a cada uno de los atributos de la fecha y hora actual:

```python
datetime.now().year
datetime.now().month
datetime.now().day
datetime.now().hour
datetime.now().minute
datetime.now().second
datetime.now().microsecond
```

Obtener la representación única de la fecha y hora actual:

```python
datetime.now().timestamp()
```

Para guardar una fecha y hora actual y concreta se utiliza una variable. Ejemplo:

```python
now = datetime.now()
```

Crear una fecha con objeto de `datetime` (se requiere agregar *año*, *mes* y *día*):

```python
date = datetime(2026, 8, 18)
```
