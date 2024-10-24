# Explorando y modificando las clases y objetos

## Reflexión e introspección en Python

En muchos lenguajes de programación orientados a objetos, Python incluido, existen dos capacidades fundamentales que ofrecen gran flexibilidad y poder al programador: la **introspección** y la **reflexión**. Estas habilidades permiten que los programas examinen y modifiquen objetos y clases durante la ejecución, lo que abre puertas a una programación más dinámica y adaptable.

* La **introspección** es la capacidad de un programa para **examinar** las propiedades, tipo o características de un objeto **en tiempo de ejecución**. En otras palabras, permite que el código explore qué es un objeto, de qué clase es, qué atributos tiene y qué métodos puede ejecutar, todo esto mientras el programa está corriendo.
* La **reflexión** va un paso más allá que la introspección. No solo permite examinar el tipo y las propiedades de un objeto en tiempo de ejecución, sino que también otorga la capacidad de **manipular** esas propiedades y funciones **dinámicamente**.

En pocas palabras, la reflexión permite modificar el comportamiento o el estado de un objeto mientras el programa está en ejecución, sin que necesitemos saber de antemano cómo está definido el objeto.

Python proporciona varias funciones integradas que permiten la introspección:

* **`type()`**: Nos indica el tipo de un objeto.
* **`dir()`**: Devuelve una lista de atributos y métodos disponibles en un objeto.
* **`hasattr()`**: Verifica si un objeto tiene un atributo o método específico.
* **`getattr()`**: Permite obtener el valor de un atributo de un objeto.
* **`isinstance()`**: Verifica si un objeto es instancia de una clase específica.


Veamos un ejemplo: la función `incIntsI()` realiza una operación introspectiva sobre un objeto de cualquier clase, analizando sus atributos y modificando aquellos que cumplen con ciertas condiciones. Este proceso es lo que permite que el programa sea tan flexible y dinámico.

A continuación, se desglosan los pasos principales del código:
  
```
class MyClass:
    pass
obj = MyClass()
obj.a = 1
obj.b = 2
obj.i = 3
obj.ireal = 3.5
obj.integer = 4
obj.z = 5
```

Aquí, se define una clase simple `MyClass` y se crea una instancia de esta clase, `obj`. Luego, se asignan varios atributos a esta instancia, algunos de ellos enteros y otros flotantes.


```
def incIntsI(obj):
    for name in obj.__dict__.keys():
        if name.startswith('i'):
            val = getattr(obj, name)
            if isinstance(val, int):
                setattr(obj, name, val + 1)
```

* Utiliza el atributo especial `__dict__` del objeto, que es un diccionario que almacena todos los atributos de instancia del objeto. 
* Si el nombre del atributo comienza con "i", continúa el proceso.
* Se utiliza la función `getattr()` para obtener el valor del atributo. Esta función toma el objeto y el nombre del atributo (como cadena) y devuelve el valor asociado.
* Verifica si el valor es un entero usando `isinstance()`.
* Si la comprobación es positiva, usa `setattr()` para modificar el valor del atributo, incrementándolo en 1.

Vamos a ejecutar el siguiente código:

```
print(obj.__dict__)
incIntsI(obj)
print(obj.__dict__)
```

Antes de ejecutar `incIntsI()`, el diccionario de atributos es:
```
{'a': 1, 'integer': 4, 'b': 2, 'i': 3, 'z': 5, 'ireal': 3.5}
```
Después de ejecutar la función, los atributos enteros cuyo nombre comienza con "i" se han incrementado en uno:
```
{'a': 1, 'integer': 5, 'b': 2, 'i': 4, 'z': 5, 'ireal': 3.5}
```

## Las funciones `getattr()` y `setattr()`

Las funciones `getattr()` y `setattr()` son fundamentales para manipular objetos dinámicamente en Python:

* `getattr(obj, name)` permite acceder a un atributo de un objeto por su nombre, que puede ser una cadena.
* `setattr(obj, name, value)` permite cambiar el valor de un atributo dado su nombre y el nuevo valor.

## Cuestionario

1. La declaración de la clase `Snake` se muestra a continuación. Enriquece la clase con un método llamado `increment()`, el cual incrementa en 1 la propiedad `victims`.
    ```
    class Snake:
        def __init__(self):
            self.victims = 0
    ```

2. Redefine el constructor de la clase `Snake` para que tenga un parámetro que inicialice el campo `victims` con un valor pasado al objeto durante la construcción.


3. ¿Puedes predecir el resultado del siguiente código?
    ```
    class Snake:
        pass


    class Python(Snake):
        pass


    print(Python.__name__, 'es una', Snake.__name__)
    print(Python.__bases__[0].__name__, 'puede ser una', Python.__name__)
    ```

## Solución cuestionario

1. Pregunta 1
    ```
    class Snake:
        def __init__(self):
            self.victims = 0

        def increment(self):
            self.victims += 1
    ```

2. Pregunta 2
    ```
    class Snake:
        def __init__(self, victims):
            self.victims = victims	

    ```
3. Pregunta 3

    ```
    Python es una Snake
    Snake puede ser una Python
    ```