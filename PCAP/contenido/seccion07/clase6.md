
# Excepciones integradas

A continuación, te mostramos algunas de las excepciones más comunes en Python, con sus descripciones y ejemplos prácticos.

## ArithmeticError
**Ubicación en el árbol de excepciones:** `BaseException ← Exception ← ArithmeticError`

Es una excepción abstracta que engloba los errores relacionados con operaciones aritméticas, como división entre cero o dominio inválido de un argumento.


## AssertionError
**Ubicación:** `BaseException ← Exception ← AssertionError`

Se lanza cuando una expresión `assert` evalúa a falso. Es útil para verificar condiciones críticas.

```
from math import tan, radians
angle = int(input('Ingresa un ángulo entero en grados: '))
# Asegúrate de que angle != 90 + k * 180
assert angle % 180 != 90
print(tan(radians(angle)))
```
En este caso, `AssertionError` se genera si el ángulo es inválido para la operación `tan()`.


## BaseException
**Ubicación:** `BaseException`

Es la excepción más general en Python. Todas las demás excepciones derivan de esta.

## IndexError
**Ubicación:** `BaseException ← Exception ← LookupError ← IndexError`

Se genera cuando intentas acceder a un índice que no existe en una secuencia, como listas o tuplas.


```
lista = [1, 2, 3, 4, 5]
indice = 0
continua = True

while continua:
    try:
        print(lista[indice])
        indice += 1
    except IndexError:
        continua = False
print('Listo')
```
Aquí, cuando `indice` supera la longitud de la lista, se lanza un `IndexError`.

## KeyboardInterrupt
**Ubicación:** `BaseException ← KeyboardInterrupt`

Se lanza cuando el usuario interrumpe la ejecución de un programa mediante un atajo de teclado, como `Ctrl-C`.


```
from time import sleep

segundos = 0
while True:
    try:
        print(segundos)
        segundos += 1
        sleep(1)
    except KeyboardInterrupt:
        print("¡No hagas eso!")
```
Este código captura la interrupción y continúa ejecutándose.

## LookupError
**Ubicación:** `BaseException ← Exception ← LookupError`

Una excepción abstracta que agrupa errores relacionados con accesos inválidos a colecciones, como listas o diccionarios.

## MemoryError
**Ubicación:** `BaseException ← Exception ← MemoryError`

Se lanza cuando el sistema no tiene suficiente memoria para completar una operación.


```
cadena = 'x'
try:
    while True:
        cadena = cadena + cadena
        print(len(cadena))
except MemoryError:
    print('¡Esto no es gracioso!')
```
Este código puede generar un `MemoryError` si la cadena crece demasiado.

## OverflowError
**Ubicación:** `BaseException ← Exception ← ArithmeticError ← OverflowError`

Se lanza cuando una operación produce un número demasiado grande para ser manejado.


```
from math import exp

ex = 1
try:
    while True:
        print(exp(ex))
        ex *= 2
except OverflowError:
    print('El número es demasiado grande.')
```
Este código causa un `OverflowError` cuando el número generado es demasiado grande.

## ImportError
**Ubicación:** `BaseException ← Exception ← ImportError`

Se genera cuando falla una operación de importación de un módulo.


```
try:
    import math
    import time
    import abracadabra  # Esto fallará
except ImportError:
    print('Una de tus importaciones ha fallado.')
```

## KeyError
**Ubicación:** `BaseException ← Exception ← LookupError ← KeyError`

Se genera cuando se intenta acceder a una clave inexistente en un diccionario.


```
diccionario = {'a': 'b', 'b': 'c', 'c': 'd'}
clave = 'a'

try:
    while True:
        clave = diccionario[clave]
        print(clave)
except KeyError:
    print('No existe tal clave:', clave)
```

Para más información sobre excepciones, puedes consultar la [documentación oficial de Python](https://docs.python.org/3.6/library/exceptions.html).

## Cuestionario

1. ¿Cuál de las excepciones se utilizará para proteger al código de ser interrumpido por el uso del teclado?
2. ¿Cuál es el nombre de la más general de todas las excepciones de Python?
3. ¿Cuál de las excepciones será generada a través de la siguiente evaluación fallida?
    ```
    huge_value = 1E250 ** 2
    ```

## Solución cuestionario

1. Pregunta 1

    `KeyboardInterrupt`

2. Pregunta 2

    `BaseException`

3. Pregunta 3

    `OverflowError`