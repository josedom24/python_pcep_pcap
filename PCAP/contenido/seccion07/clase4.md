# Propagación de excepciones

Las excepciones generadas dentro de una función pueden manejarse de dos maneras:

1. **Dentro de la función**: La propia función captura y maneja la excepción.
2. **Fuera de la función**: La excepción se propaga fuera de la función para ser manejada por el invocador.

## Ejemplo de manejo dentro de la función

```
def bad_fun(n):
    try:
        return 1 / n
    except ArithmeticError:
        print("¡Problema Aritmético!")
        return None

bad_fun(0)
print("FIN.")
```

Aquí, la excepción **`ZeroDivisionError`** es capturada dentro de la función `bad_fun()`, y la función misma la maneja. 

## Ejemplo de manejo fuera de la función

Si dejamos que la excepción se propague fuera de la función:

```
def bad_fun(n):
    return 1 / n

try:
    bad_fun(0)
except ArithmeticError:
    print("¿Qué pasó? ¡Se generó una excepción!")

print("FIN.")
```

En este caso, la excepción no se maneja dentro de `bad_fun()`, sino que se deja que el invocador de la función (en este caso, el bloque `try-except` fuera de la función) se encargue de manejar la excepción.


* Una excepción generada dentro de una función puede "viajar" hacia afuera, buscando en la cadena de invocación un bloque `except` que la maneje.
* Si no encuentra un bloque `except` adecuado, Python detendrá el programa y emitirá un mensaje de diagnóstico.

Este comportamiento permite que las excepciones puedan ser capturadas y manejadas en cualquier nivel de la ejecución del programa, ya sea en la función o fuera de ella.

## Uso de la instrucción `raise`

La instrucción `raise` se utiliza para generar excepciones específicas de manera programática, como si estas excepciones hubieran ocurrido de manera natural. Su sintaxis es:

```
raise exc
```

Donde `exc` es el nombre de la excepción que deseas generar. Esta es una palabra clave reservada en Python.

La instrucción `raise` te permite:

1. **Simular excepciones reales**: Esto es útil para probar tu estrategia de manejo de excepciones sin necesidad de provocar errores reales en el código.
2. **Manejo parcial de excepciones**: Puedes capturar una excepción en un bloque de código y luego usar `raise` para permitir que otra parte del código se encargue del manejo de esa excepción.

A continuación, se muestra un ejemplo de cómo utilizar `raise`:

```
def bad_fun(n):
    raise ZeroDivisionError

try:
    bad_fun(0)
except ArithmeticError:
    print("¿Qué pasó? ¿Un error?")

print("FIN.")
```

* En la función `bad_fun(n)`, se utiliza `raise ZeroDivisionError` para generar la excepción de división entre cero de manera programática.
* Al llamar a `bad_fun(0)` dentro del bloque `try`, la excepción es lanzada.
* El bloque `except ArithmeticError` captura la excepción generada y ejecuta la línea que imprime el mensaje: "¿Qué pasó? ¿Un error?".

Este enfoque permite probar el manejo de excepciones sin tener que ejecutar código que provoque errores reales, lo que es particularmente útil en pruebas y depuración.

## Uso de `raise` sin especificar la excepción

La instrucción `raise` puede usarse sin especificar una excepción de la siguiente manera:

```
raise
```

* **Uso limitado**: Esta forma de `raise` solo puede ser utilizada dentro de un bloque `except`. Intentar usarla fuera de este contexto resultará en un error.
* **Re-generación de excepciones**: Cuando se usa `raise` de esta manera, volverá a generar la misma excepción que se está manejando actualmente. Esto permite distribuir el manejo de excepciones entre diferentes partes del código.

Veamos un ejemplo de cómo funciona esta instrucción:

```
def bad_fun(n):
    try:
        return n / 0
    except:
        print("¡Lo hice otra vez!")
        raise

try:
    bad_fun(0)
except ArithmeticError:
    print("¡Ya veo!")

print("FIN.")
```

1. **Función `bad_fun(n)`**:
   * Se intenta realizar una división entre cero (`n / 0`), lo que genera una excepción `ZeroDivisionError`.
   * Esta excepción es capturada por el bloque `except`, que imprime "¡Lo hice otra vez!".
   * Luego, se usa `raise` para volver a lanzar la misma excepción que fue capturada.

2. **Bloque `try-except`**:
   * En el bloque `try`, se llama a `bad_fun(0)`, lo que provoca la excepción.
   * La excepción es manejada en el bloque `except` que sigue, donde se imprime "¡Ya veo!".

