# Funciones que trabajan con cadenas de caracteres

## La función `len()`

La función `len()` empleada en las cadenas devuelve el número de caracteres que contiene el argumento. 

Ejemplo:

```
# Ejemplo 1

word = "Python"
print(len(word))


# Ejemplo 2

empty = ''
print(len(empty))


# Ejemplo 3

cadena = 'Monty Python's Flying Circus'
print(len(cadena))

# Ejemplo 4

multilinea = '''Línea #1
Línea #2'''

print(len(multilinea))
```

## La función `ord()`

Esta función devuelve el valor del punto de código ASCII/UNICODE de un carácter específico. La función necesita una cadena de un carácter como argumento,  incumplir este requisito provoca una excepción `TypeError`, y devuelve un número que representa el punto de código del argumento.

```
# Demostración de la función ord ().
char_1 = 'a'
char_2 = ' '  # espacio

print(ord(char_1))
print(ord(char_2))
```

## La función `chr()`

Si conoces el punto de código y deseas obtener el carácter correspondiente, puedes usar la función llamada `chr()`. La función toma un punto de código y devuelve su carácter. Invocándolo con un argumento inválido (por ejemplo, un punto de código negativo o inválido) provoca las excepciones `ValueError` o `TypeError`.

```
# Demostración de la función chr.

print(chr(97))
print(chr(945))
```

## La función `min()`

Como hemos indicado, recordamos que las cadenas son secuencias. La función `min()` encuentra el elemento mínimo de la secuencia pasada como argumento. Existe una condición, la secuencia (cadena o lista) no puede estar vacía, de lo contrario obtendrás una excepción `ValueError`.

Para encontrar el carácter mínimo se busca el que tiene un código UNICODE/ASCII más pequeño. Ejemplo:

```
# Demonstrando min() - Ejemplo 1:
print(min("aAbByYzZ"))

# Demonstrando min() - Ejemplo 2 y 3:
t = 'Los Caballeros Que Dicen "¡Ni!"'
print('[' + min(t) + ']')

t = [0, 1, 2]
print(min(t))
```
## La función `max()`

En este caso, la función `max()` nos devuelve el elemento más grande de la secuencia (lista o cadena). Ejemplo:

```
# Demostración de max() - Ejemplo 1:
print(max("aAbByYzZ"))


# Demostración de max() - Ejemplo 2 & 3:
t = 'Los Caballeros Que Dicen "¡Ni!"'
print('[' + max(t) + ']')

t = [0, 1, 2]
print(max(t))
```

## La función `list()`

La función `list()` toma su argumento (una cadena, tupla, diccionario,...) y crea una nueva lista que contiene todos los caracteres de la cadena, uno por elemento de la lista. Ejemplo:

```
cadena = "aAbByYzZ"
lista = list(cadena)
print(lista)
```