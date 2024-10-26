# Las excepciones son clases

En Python, las excepciones no son solo simples errores; son clases que representan situaciones excepcionales en el flujo de un programa. Cuando se genera una excepción, se crea una instancia de un objeto de la clase correspondiente, el cual puede transportar información valiosa sobre la situación que provocó la excepción.

Python permite capturar y manejar excepciones utilizando bloques `try-except`. En este contexto, se puede extender la sentencia `except` para capturar la excepción en un identificador, lo que permite a los programadores analizar y actuar sobre la excepción de manera más informada.

A continuación, se muestra un ejemplo que ilustra cómo capturar y utilizar una excepción como un objeto:

```
try:
    i = int("¡Hola!")
except Exception as e:
    print(e)  # Imprime el mensaje de error
    print(e.__str__())  # Imprime la representación de la excepción
```

La cláusula `except Exception as e:` captura la excepción generada y la asigna al identificador `e`.
Se imprime el mensaje de error que describe la razón por la cual la conversión falló. Este mensaje es el resultado del método `__str__()` del objeto de excepción, que proporciona una descripción legible del error.

## La jerarquia de clases de las excepciones

En Python, todas las excepciones forman parte de una jerarquía de clases, donde cada excepción es una subclase de otra. La clase raíz de todas las excepciones en Python es `BaseException`, que se encuentra en la parte superior de esta jerarquía.

Esta jerarquía se puede visualizar como un árbol, donde cada clase de excepción puede tener subclases que representan situaciones de error más específicas. Por ejemplo, `Exception` es una subclase de `BaseException`, y a su vez tiene subclases como `ValueError`, `TypeError`, y muchas más.

A continuación, se presenta una función que recorre y muestra la jerarquía de excepciones en un formato de árbol. Esta función toma dos argumentos: la clase desde la cual empezar a recorrer y el nivel de anidación para el formato de impresión.

```
def print_exception_tree(thisclass, nest=0):
    if nest > 1:
        print(" |" * (nest - 1), end="")
    if nest > 0:
        print(" +---", end="")

    print(thisclass.__name__)

    for subclass in thisclass.__subclasses__():
        print_exception_tree(subclass, nest + 1)


# Comenzar desde la raíz del árbol de excepciones
print_exception_tree(BaseException)
```

* **Recursividad**: La función `print_exception_tree()` utiliza recursividad para recorrer las subclases de cada clase de excepción. Para cada clase, imprime su nombre y luego llama a sí misma para cada una de sus subclases.
* **Formateo de la Salida**: La impresión utiliza un nivel de indentación para mostrar la jerarquía. El argumento `nest` se incrementa en cada llamada recursiva para ajustar la visualización.
* **Uso de `__subclasses__()`**: Este método se usa para obtener una lista de todas las subclases directas de la clase actual.

## Propiedades especificas de las excepciones

En Python, las excepciones son objetos que no solo informan sobre un error, sino que también pueden transportar información adicional. Esto se logra a través de propiedades y métodos específicos. Una de las propiedades más útiles de las excepciones es `args`, que forma parte de la clase base `BaseException`.

La propiedad `args` es una tupla que contiene todos los argumentos que se pasan al constructor de la clase de excepción. Su contenido puede estar vacío si la construcción se ha invocado sin ningún argumento, o solo contiene un elemento cuando el constructor recibe un argumento (no se considera el argumento `self`), y así sucesivamente.varía según cómo se haya creado la excepción:

Veamos un ejemplo:

```
def print_args(args):
    lng = len(args)
    if lng == 0:
        print("")
    elif lng == 1:
        print(args[0])
    else:
        print(str(args))


try:
    raise Exception
except Exception as e:
    print(e, e.__str__(), sep=' : ', end=' : ')
    print_args(e.args)

try:
    raise Exception("mi excepción")
except Exception as e:
    print(e, e.__str__(), sep=' : ', end=' : ')
    print_args(e.args)

try:
    raise Exception("mi", "excepción")
except Exception as e:
    print(e, e.__str__(), sep=' : ', end=' : ')
    print_args(e.args)
```

* **Primer bloque**: Lanza una excepción sin argumentos. La salida muestra la representación de la excepción (`Exception`) y su contenido `args`, que está vacío.
* **Segundo bloque**: Lanza una excepción con un único argumento ("mi excepción"). El objeto de excepción y su representación como cadena se imprimen, seguidos del contenido de `args`, que contiene un solo elemento.
* **Tercer bloque**: Lanza una excepción con dos argumentos ("mi" y "excepción"). La salida refleja que `args` contiene ambos elementos.

