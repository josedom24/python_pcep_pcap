# Comprobando la existencia de una propiedad

En Python, a diferencia de algunos lenguajes de programación, no todos los objetos de una misma clase tienen que tener los mismos atributos. Esto puede llevar a situaciones donde intentamos acceder a un atributo que no existe, lo que genera un error común llamado `AttributeError`.

Consideremos el siguiente ejemplo:

```
class ClaseEjemplo:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

objeto = ClaseEjemplo(1)

print(objeto.a)
print(objeto.b)
```

En este caso, la clase `ClaseEjemplo` define dos atributos potenciales, `a` y `b`, que se asignan condicionalmente en función del valor pasado al constructor. Si el valor es impar, se asigna `a`, y si es par, se asigna `b`.

1. Se instancia un objeto `objeto` con el valor `1`, lo que provoca que se asigne el atributo `a`.
2. Al intentar imprimir `objeto.a`, Python devuelve el valor `1`, lo que indica que el atributo `a` existe.
3. Sin embargo, cuando se intenta acceder a `objeto.b`, Python lanza un error: 

```
Traceback (most recent call last):
  File "main.py", line 11, in <module>
    print(objeto.b)
AttributeError: 'ClaseEjemplo' object has no attribute 'b'
```

Este error ocurre porque el atributo `b` nunca fue definido en el objeto cuando el valor `1` fue pasado al constructor.

## Manejando la excepción

Podemos evitar este error utilizando la instrucción `try-except`, veamos un ejemplo:

```
class ClaseEjemplo:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

objeto = ClaseEjemplo(1)

# Intento de acceso a atributo inexistente con manejo de excepciones
try:
    print(objeto.b)
except AttributeError:
    print("El atributo 'b' no existe.")
```
## La función `hasattr()`

Python nos ofrece una solución más clara y eficiente mediante la función incorporada `hasattr()`. Esta función recibe dos argumentos: el objeto o clase a verificar y el nombre del atributo (como una cadena de texto). Retorna `True` si el atributo existe, y `False` si no es así. Usarla evita depender de excepciones para controlar el flujo del programa.

Veamos el mismo ejemplo con `hasattr()`:

```
class ClaseEjemplo:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

objeto = ClaseEjemplo(1)

# Acceso seguro usando hasattr
print(objeto.a)

if hasattr(objeto, 'b'):
    print(objeto.b)
else:
    print("El atributo 'b' no existe.")
```

## Uso de hasattr() con clases

Además de comprobar si un atributo existe en una instancia de clase, la función `hasattr()` también puede verificar si una clase en sí contiene un atributo de clase. Esta funcionalidad es útil para determinar la disponibilidad de variables o atributos a nivel de clase, sin instanciarla.

Veamos el siguiente ejemplo:

```
class ClaseEjemplo:
    a = 1  # Atributo de clase

    def __init__(self):
        self.b = 2  # Atributo de instancia

objeto = ClaseEjemplo()

print(hasattr(objeto, 'b'))  # Verifica si la instancia tiene el atributo 'b'
print(hasattr(objeto, 'a'))  # Verifica si la instancia tiene acceso al atributo de clase 'a'
print(hasattr(ClaseEjemplo, 'b'))    # Verifica si la clase tiene el atributo 'b'
print(hasattr(ClaseEjemplo, 'a'))    # Verifica si la clase tiene el atributo de clase 'a'
```

* `print(hasattr(objeto, 'b'))`: Este atributo es definido dentro del constructor `__init__` como un atributo de instancia, por lo que el objeto `objeto` sí tiene el atributo `b`. La salida será `True`.
* `print(hasattr(objeto, 'a'))`: Aunque `a` es un atributo de clase y no un atributo de instancia, las instancias pueden acceder a los atributos de clase. Por lo tanto, este comando también devolverá `True`.
* `print(hasattr(ClaseEjemplo, 'b'))`: Este atributo (`b`) solo existe en las instancias de la clase, no a nivel de clase. Por lo tanto, la clase `ClaseEjemplo` no tiene el atributo `b`, y la salida será `False`.
* `print(hasattr(ClaseEjemplo, 'a'))`: `a` es un atributo de clase, por lo que la clase `ClaseEjemplo` tiene acceso directo a él, y la salida será `True`.

## Cuestionario

1. ¿Cuáles de las propiedades de la clase Python son variables de instancia y cuáles son variables de clase? ¿Cuáles de ellos son privados?
    ```
    class Python:
        population = 1
        victims = 0
        def __init__(self):
            self.length_ft = 3
            self.__venomous = False
    ```

2. Vas a negar la propiedad `__venomous` del objeto `version_2`, ignorando el hecho de que la propiedad es privada. ¿Cómo vas a hacer esto?
    ```
    version_2 = Python()
    ```
3. Escribe una expresión que compruebe si el objeto `version_2` contiene una propiedad de instancia denominada `constrictor` (¡si, `constrictor`!).

## Solución cuestionario

1. Ejercicio 1

    `population` y `victims` son variables de clase, mientras que `length` y `__venomous` son variables de instancia (esta última también es privada).

2. Ejercicio 2

    `version_2._Python__venomous = not version_2._Python__venomous`

3. Ejercicio 3

    `hasattr(version_2, 'constrictor')`
