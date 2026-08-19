# Curso Python Intermedio

| Fecha de inicio | Fecha de finalización | Fecha de actualización |
|-----------------|-----------------------|------------------------|
| 2026-08-18      |                       | -                      |

## Fechas
---

Para importar el módulo de fechas tenemos dos vías.

```python
import datetime
```

Para obtener la fecha y hora actual:

```python
from datetime import datetime

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
from datetime import time

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

Con el submódulo `time` podemos hacer algo similar, pero solo con el manejo de horas:

```python
time(23, 8, 18)

# Igual podemos iniciar el objeto vacío, sin parámetros
time()
```

Para acceder a la hora, los minutos y los segundos podemos emplear:

```python
time(23, 8, 18).hour
time(23, 8, 18).minute
time(23, 8, 18).second
```

Con el submódulo `date` podemos hacer algo similar, pero solo con el manejo de la fecha:

```python
from datetime import date

# Requerimos agregar los parámetros
date(2026, 8, 18) 
```

Y podemos acceder al *año*, *mes* y *día* con los siguiente sintaxis:

```python
date(2026, 8, 18).year
date(2026, 8, 18).month
date(2026, 8, 18).day
```

Para capturar la fecha de hoy se usa:

```python
date.today()
```

Está permitido hacer operaciones con el acceso a los atributos cuando se pasan como parámetros del objeto `date`.

```python
current_date = date.today()

current_date = date(current_date.year, current_date.month + 1, curent_date.day)
```

Para otras operaciones con fechas podemos realizar esto:

```python
date_1 = date(2026, 8, 18)
date_2 = date(2026, 8, 31)

diff = date_2 - date_1

print(diff)
```

> Para efectuar las operaciones de fechas y horas requerimos que sean del mismo tipo de objeto o tipo de dato.

Para manejo de espacios de tiempo, digamos plazos, podemos usar el submódulo `timedelta`.

```python
from datetime import timedelta

start_timedelta = timedelta(weeks = 10, seconds = 100, microseconds = 100)
end_timedelta = timedelta(weeks = 13, seconds = 200, microseconds = 180)

# Y hacer operaciones de suma, resta y división

print(end_timedelta - start_timedelta)
print(end_timedelta + start_timedelta)
print(end_timedelta / start_timedelta)
```

## List Comprehension
---

Se puede crear un rango (de clase `range`):

```python
my_range = range(81)

print(my_range) # Output: range(0, 81)
```

La sintaxis para la *list comprehension* es:

```python
my_list = ["item" for _ in my_range]
```

## Retos de programación
---

> Los retos son soluciones de menos de cinco minutos. No incluyen las instrucciones, solo la solución.

**Fizzbuzz**:

```python
def fizzbuzz() -> None:
    for i in range(1, 101):
        if i % 3 == 0:
            print('fizz')
        elif i % 5 == 0:
            print('buzz')
        elif i % 15 == 0:
            print('fizzbuzz')
        else:
            print(i)
        print()
         
fizzbuzz()
```

**¿Es anagrama?**:

```python
def is_anagram(word_1: str, word_2: str) -> bool:
    if word_1.lower().strip() == word_2.lower().strip():
        return False
    sort_1 = sorted(word_1.lower().strip())
    sort_2 = sorted(word_2.lower().strip())
    if sort_1 == sort_2:
        return True
    return False
     
is_anagram("hello ", " OLLEh ")

is_anagram("hello", "hello")
```


**Fibonacci**:

```python
def fibonacci():
    a_0 = 0
    a_1 = 1

    for i in range(1, 51):
        print(a_0)
        a_2 = a_0 + a_1
        a_0 = a_1
        a_1 = a_2

fibonacci()
```

**Números primos del 1 al 100**:

```python
def is_prime(number):
    from math import sqrt

    if number <= 1:
        return False

    number_sqrt  = int(sqrt(number))
    
    for i in range(2, number_sqrt + 1):
        if number % i == 0:
        return False
    return True

for i in range(1, 101):
    print(f"{str(i).zfill(3)} -> ¿Es primo? -> {'Sí' if is_prime(i) else 'No'}")
```

**Inviriendo cadenas sin funciones nativas**:

```python
def reversed_str(string):
    return string[::-1]

reversed_str("Hola, mundo.")
```

## Lambdas
---

