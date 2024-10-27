# La instrucción yield


El protocolo iterador en Python es bastante directo, pero puede volverse inconveniente cuando necesitas manejar el estado de la iteración, como en el ejemplo del iterador Fibonacci, donde se almacena con precisión el lugar en el que se detuvo la última invocación (es decir, el número evaluado y los valores de los dos elementos anteriores).  Esto hace que el código sea más complejo y menos legible.

Afortunadamente, Python proporciona una solución mucho más eficiente y elegante para escribir iteradores: la palabra clave **`yield`**.

`yield` se puede ver como una versión más avanzada de `return`, pero con una diferencia crucial: cuando una función utiliza `yield`, **no pierde su estado entre llamadas**. Esto significa que puedes **pausar** la ejecución de la función, devolver un valor y, al reanudar la función, continuar justo donde se dejó, con todas las variables preservadas.

## Comparación entre `return` y `yield`

Veamos este ejemplo de función que utiliza `return`:

```
def fun(n):
    for i in range(n):
        return i  # Se ejecuta solo una vez y termina el ciclo
```

En este código, el bucle `for` se interrumpe inmediatamente tras la primera ejecución debido a la sentencia `return`. Esto significa que la función no puede guardar ni restaurar su estado en invocaciones posteriores, por lo que no puede ser usada como generador.


Ahora, reemplazamos la palabra **`return`** con **`yield`**:

```
def fun(n):
    for i in range(n):
        yield i  # Pausa y reanuda la ejecución, recordando el estado
```

Esta pequeña modificación convierte la función en un **generador**. Ahora, cada vez que la función se llama, produce el siguiente valor del ciclo, pero **sin perder el estado de las variables locales**. Esto permite que el ciclo continúe desde el punto en que se pausó en la última ejecución de `yield`.

## ¿Cómo funciona un Generador con `yield`?

El generador que acabamos de escribir no se comporta como una función tradicional. En lugar de devolver un valor inmediatamente, devuelve un **objeto generador** que puede ser recorrido utilizando un bucle `for`, o llamando a `next()` manualmente. El generador no se ejecuta completamente de una vez, sino que produce valores de uno en uno según sea necesario.

Veamos el generador en uso:

```
def fun(n):
    for i in range(n):
        yield i  # Devuelve cada valor de 'i', uno a la vez

# Iterando sobre el generador
for v in fun(5):
    print(v)
```

`yield` **no es una función convencional**: Un generador no se puede invocar de la misma manera que una función normal. Llamar a una función generadora simplemente devuelve un **objeto generador**, no el resultado de la ejecución. Para obtener los valores, necesitas recorrerlo, por ejemplo, con un bucle `for`.

