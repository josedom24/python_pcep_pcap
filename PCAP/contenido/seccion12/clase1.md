# Generadores e iteradores

En Python, un **generador** es un fragmento de código diseñado para producir una serie de valores, uno a la vez, controlando el proceso de iteración. Esto es lo que los convierte, de hecho, en **iteradores**. Aunque algunos podrían hacer una distinción técnica entre generadores e iteradores, nosotros los trataremos como uno solo.

La función `range()` en Python es un ejemplo perfecto de generador. También actúa como un iterador:

```
for i in range(5):
    print(i)
```

¿Cuál es la diferencia entre una función y un generador?

* **Función**: Una función devuelve un solo valor definido y se invoca una vez, generando un resultado después de su evaluación.
  
* **Generador**: Un generador, en cambio, devuelve múltiples valores a lo largo del tiempo, siendo invocado (de forma implícita) varias veces. Cada vez que el generador es llamado, produce un nuevo valor de la secuencia.

En el ejemplo anterior, `range(5)` es un generador que se invoca seis veces, devolviendo cinco valores consecutivos (del 0 al 4) antes de terminar.

## Protocolo iterador

En Python, el **protocolo iterador** define cómo los objetos deben comportarse para ser iterables, lo que les permite ser utilizados en contextos como las sentencias `for` e `in`. Un objeto que cumple con este protocolo se llama **iterador**.

Para que un objeto sea un iterador en Python, debe implementar dos métodos esenciales:

1. **`__iter__()`**: Este método debe devolver el objeto en sí, permitiendo a Python iniciar la iteración. Se invoca una vez cuando comienza el bucle.
2. **`__next__()`**: Este método devuelve el siguiente valor de la secuencia cada vez que es invocado. Si ya no hay más valores disponibles, debe lanzar la excepción `StopIteration` para detener la iteración.

El siguiente código implementa un iterador que genera los primeros `n` números de Fibonacci:

```
class Fib:
    def __init__(self, nn):
        print("__init__")
        self.__n = nn  # Almacena el límite de la serie
        self.__i = 0   # Rastrea el índice actual
        self.__p1 = self.__p2 = 1  # Los dos números previos en la secuencia

    def __iter__(self):
        print("__iter__")
        return self  # Devuelve el propio objeto iterador

    def __next__(self):
        print("__next__")
        self.__i += 1  # Aumenta el índice
        if self.__i > self.__n:  # Si se excede el límite, se detiene
            raise StopIteration
        if self.__i in [1, 2]:  # Los primeros dos valores siempre son 1
            return 1
        ret = self.__p1 + self.__p2  # Calcula el siguiente número de Fibonacci
        self.__p1, self.__p2 = self.__p2, ret  # Actualiza los valores previos
        return ret

# Uso del iterador:
for i in Fib(10):
    print(i)
```

* El constructor `__init__` inicializa los valores necesarios. `__n` guarda el número máximo de términos a generar, mientras que `__i` rastrea la posición actual en la secuencia. `__p1` y `__p2` almacenan los dos últimos números de Fibonacci.
* El método `__iter__()` devuelve el objeto iterador en sí. Este método es obligatorio para que el bucle `for` funcione.
* El método `__next__()` genera el siguiente valor de la secuencia. Primero, incrementa el contador `__i` y, si ha alcanzado el límite, lanza `StopIteration` para terminar el proceso. Luego, si los valores corresponden a los dos primeros términos de Fibonacci, devuelve 1; en los siguientes, calcula la suma de los dos anteriores.
* El bucle `for` utiliza el objeto iterador para imprimir los números de Fibonacci.

Cosas a tener en cuenta:

* El constructor `__init__` se ejecuta al crear el objeto iterador.
* Python invoca el método `__iter__` al comenzar la iteración.
* El método `__next__` se invoca repetidamente para obtener cada número de Fibonacci hasta que se alcanza el límite.
* La iteración se detiene cuando el generador lanza `StopIteration`.


