# Propiedades comunes en clases y objetos

Cada clase y objeto de Python tiene por defecto una serie de propiedades. Ya hemos trabajado con algunas:

## `__dict__`

`__dict__` es un diccionario que contiene las propiedades y sus valores de las clases y los objetos. Ejemplo:

```
class Clase:
    varia = 1
    def __init__(self):
        self.var = 2

    def metodo(self):
        pass

    def __oculto(self):
        pass


objeto = Clase()

print(objeto.__dict__)
print(Clase.__dict__)
```

## `__name__`

La propiedad contiene el nombre de la clase. El atributo `__name__` **está ausente del objeto, existe solo dentro de las clases**.

Si deseas encontrar la clase de un objeto en particular, puedes usar una función llamada `type()`, la cual es capaz (entre otras cosas) de encontrar una clase que se haya utilizado para crear instancias de cualquier objeto.

Ejemplo:

```
class Clase:
    pass


print(Clase.__name__)
objeto = Clase()
print(type(objeto).__name__)
```

## `__module__`

`__module__` es una cadena, **almacena el nombre del módulo que contiene la definición de la clase**. Ejemplo:

```
class Clase:
    pass


print(Clase.__module__)
objeto = Clase()
print(objeto.__module__)
```

Como sabes, cualquier módulo llamado `__main__` en realidad no es un módulo, sino es el archivo actualmente en ejecución.

## `__bases__`

`__bases__` es una tupla. La **tupla contiene clases** (no nombres de clases) que son superclases directas de la clase. El orden es el mismo que el utilizado dentro de la definición de clase. Solo las clases tienen este atributo, los objetos no.

Hemos definido una función llamada printBases(), diseñada para presentar claramente el contenido de la tupla:

```
class SuperUno:
    pass


class SuperDos:
    pass


class Sub(SuperUno, SuperDos):
    pass


def printBases(clase):
    print('( ', end='')

    for x in clase.__bases__:
        print(x.__name__, end=' ')
    print(')')


printBases(SuperUno)
printBases(SuperDos)
printBases(Sub)
```

La salida será:

```
( object )
( object )
( SuperUno SuperDos )
```

Una clase sin superclases explícitas apunta a `object` (una clase de Python predefinida) como su antecesor directo.



