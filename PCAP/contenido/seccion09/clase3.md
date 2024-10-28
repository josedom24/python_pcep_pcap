# Comprobando la existencia de una propiedad

En Python, a diferencia de algunos lenguajes de programación, no todos los objetos de una misma clase tienen que tener los mismos atributos. Esto puede llevar a situaciones donde intentamos acceder a un atributo que no existe, lo que genera un error común llamado `AttributeError`.

Consideremos el siguiente ejemplo:

```
class ExampleClass:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

example_object = ExampleClass(1)

print(example_object.a)
print(example_object.b)
```

En este caso, la clase `ExampleClass` define dos atributos potenciales, `a` y `b`, que se asignan condicionalmente en función del valor pasado al constructor. Si el valor es impar, se asigna `a`, y si es par, se asigna `b`.

1. Se instancia un objeto `example_object` con el valor `1`, lo que provoca que se asigne el atributo `a`.
2. Al intentar imprimir `example_object.a`, Python devuelve el valor `1`, lo que indica que el atributo `a` existe.
3. Sin embargo, cuando se intenta acceder a `example_object.b`, Python lanza un error: 

```
Traceback (most recent call last):
  File "main.py", line 11, in <module>
    print(example_object.b)
AttributeError: 'ExampleClass' object has no attribute 'b'
```

Este error ocurre porque el atributo `b` nunca fue definido en el objeto cuando el valor `1` fue pasado al constructor.

## Manejando la excepción

Podemos evitar este error utilizando la instrucción `try-except`, veamos un ejemplo:

```
class ExampleClass:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

example_object = ExampleClass(1)

# Intento de acceso a atributo inexistente con manejo de excepciones
try:
    print(example_object.b)
except AttributeError:
    pass
```
## La función `hasattr()`

Python nos ofrece una solución más clara y eficiente mediante la función incorporada `hasattr()`. Esta función recibe dos argumentos: el objeto o clase a verificar y el nombre del atributo (como una cadena de texto). Retorna `True` si el atributo existe, y `False` si no es así. Usarla evita depender de excepciones para controlar el flujo del programa.

Veamos el mismo ejemplo con `hasattr()`:

```
class ExampleClass:
    def __init__(self, val):
        if val % 2 != 0:
            self.a = 1
        else:
            self.b = 1

example_object = ExampleClass(1)

# Acceso seguro usando hasattr
print(example_object.a)

if hasattr(example_object, 'b'):
    print(example_object.b)
else:
    print("El atributo 'b' no existe.")
```

## Uso de `hasattr() con clases

Además de comprobar si un atributo existe en una instancia de clase, la función `hasattr()` también puede verificar si una clase en sí contiene un atributo de clase. Esta funcionalidad es útil para determinar la disponibilidad de variables o atributos a nivel de clase, sin instanciarla.

Veamos el siguiente ejemplo:

```
class ExampleClass:
    a = 1  # Atributo de clase

    def __init__(self):
        self.b = 2  # Atributo de instancia

example_object = ExampleClass()

print(hasattr(example_object, 'b'))  # Verifica si la instancia tiene el atributo 'b'
print(hasattr(example_object, 'a'))  # Verifica si la instancia tiene acceso al atributo de clase 'a'
print(hasattr(ExampleClass, 'b'))    # Verifica si la clase tiene el atributo 'b'
print(hasattr(ExampleClass, 'a'))    # Verifica si la clase tiene el atributo de clase 'a'
```

* `print(hasattr(example_object, 'b'))`: Este atributo es definido dentro del constructor `__init__` como un atributo de instancia, por lo que el objeto `example_object` sí tiene el atributo `b`. La salida será `True`.
* `print(hasattr(example_object, 'a'))`: Aunque `a` es un atributo de clase y no un atributo de instancia, las instancias pueden acceder a los atributos de clase. Por lo tanto, este comando también devolverá `True`.
* `print(hasattr(ExampleClass, 'b'))`: Este atributo (`b`) solo existe en las instancias de la clase, no a nivel de clase. Por lo tanto, la clase `ExampleClass` no tiene el atributo `b`, y la salida será `False`.
* `print(hasattr(ExampleClass, 'a'))`: Este es un atributo de clase (`a`), por lo que la clase `ExampleClass` tiene acceso directo a él, y la salida será `True`.

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