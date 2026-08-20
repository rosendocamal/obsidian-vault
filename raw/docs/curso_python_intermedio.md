# Curso Python Intermedio

| Fecha de inicio | Fecha de finalización | Fecha de actualización |
|-----------------|-----------------------|------------------------|
| 2026-08-18      |                       | -                      |

## Fechas

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

Para escribir una función **lambda** tenemos la siguiente sintaxis de declaración y su uso:

```python
sum_two_values = lambda a, b: a + b

print(sum_two_values(5, 5)) # Output: 10
```

```python
is_false = lambda value: True if value else False

print(is_false(0)) # Output: False
```

## Higher Order Functions

Podemos utilizar una función y pasarla como parámetro a otra función.

```python
def sum_five(value):
    return value + 5

def sum_two_values(value_1, value_2, function_sum):
    return function_sum(value_1 + value_2)

print(sum_two_values(5, 5, sum_five)) # Output: 15
```

## Closures

Es crear como crear una función dentro de otra función.

```python
def sum_ten():
    def add(value):
        return value + 10
    return add

add_closure = sum_ten()
add_closure(15)
```

```python
def sum_ten(original_value):
    def add(value):
        return value + 10 + original_value
    return add

add_closure = sum_ten(1) # Se pasa el valor original_value
print(add_closure(5)) # Se suma al 5 los valores de (10 + original_value)
```

## Built-in Higher Order Function

Función de **map**:

```python
# Ejemplo 1
numbers = [i**2 for i in range(1, 7)]

def multiply_two(number):
    return number * 2
print(list(map(multiply_two, numbers)))

# Ejemplo 2
numbers = [i**2 for i in range(1, 7)]

print(list(map(lambda number: number * 2, numbers)))
```

Función de **filter**:

```python
# Ejemplo 1
numbers = [i**2 for i in range(1, 7)]

def filter_greater_than_ten(number):
    if number > 10:
        return True
    return False

print(list(filter(filter_greater_than_ten, numbers)))

# Ejemplo 2
numbers = [i**2 for i in range(1, 7)]

print(list(filter(lambda number: number > 10, numbers)))
```

Función de **reduce**. La función `reduce` hace que se sume los parámetros con los valores entregados más la suma acumulativa, es decir (suma acumulativa + un elemento de la lista ingresada):

```python
from functools import reduce

numbers = [i**2 for i in range(1, 7)]

print(reduce(lambda a, b: a + b, numbers))
```

## Error Types

Para usar en la estructura `try-except`:

- **SyntaxError**.
- **NameError**.
- **IndexError**.
- **ModuleNotFounderError**.
- **AttributeError**.
- **KeyError**.
- **TypeError**.
- **ImportError**.
- **ValueError**.
- **ZeroDivisionError**.

## File Handing

- **Python files mode**: `r`: leer; `w`: escribir; `r+`: leer y escribir; `w+`: leer, escribir y sobreescribir si existe.

Archivos de `texto`:

```python
txt_file = open("file.txt", "r+") # Abrir fichero

txt_file.read() # Leer todo el archivo

for line in txt_file.readlines(): # Leer línea por línea
    print(line)

txt_files.write("\New text") # Escribir en el fichero

txt_file.close() # Cerrar fichero
```

Archivos `json`:

```python
import json

json_file = open("file.json", "w+")

json_test = {
    "name": "Baruch",
    "surname": "Spinoza",
    "age": 35,
    "language": "Latin"
}

json.dump(json_test, json_file)
json.dump(json_test, json_file, indent = 4)

json_file.close()

with open("file.json") as f_json: # Context manager
    for line in f_json.readlines():
        print(line)

json_dict = json.load(open("file.json"))
print(json_dict)
print(type(json_dict))
print(json_dict["name"])
```

Archivos `csv`:

```python
import csv

csv_file = open("file.csv", "w+")

csv_writer = csv.writer(csv_file)
csv_writer.writerow(["name", "surname", "age", "languages", "website"])
csv_writer.writerow(["Baruch", "Spinoza", 35, "Latin", "NA"])

csv_file.close()

with opne("file.csv") as f_csv:
    for line in f_csv.readlines():
        print(line)
```

Archivos `xlsx`:

```python
import xlrd # Debe instalarse el módulo
```

Archivos `xml`:

```python
import xml
```

## Expresiones Regulares

```python
import re

string = "Esta es una oración con el número 1."

re.match()
```
