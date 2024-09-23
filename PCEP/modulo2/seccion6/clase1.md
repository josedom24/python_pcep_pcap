# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 6: Interacción con el usuario
## Clase: La función input()

## La función input()

Vamos a introducir una nueva función, que parece opuesta a la función `pint()`. ¿Por qué?

* Como hemos estudiado, `print()` envía datos a la consola.
* Nuestra nueva función obtiene datos de ella.

La función se llama `input()`, y es capaz de leer datos que fueron introducidos por el usuario y pasar esos datos al programa en ejecución. Por lo tanto, esta función devuelve datos que vamos a utilizar en nuestro programa, consiguiendo que el programa pueda manipular los datos, haciendo que el código sea verdaderamente interactivo.

La mayoría de los programas leen y procesan datos. Veamos un ejemplo:

```
print("Dime algo...")
anything = input()
print("Mmm...", anything, "...¿en serio?")
```

* El programa **solicita al usuario que inserte algún dato** desde la consola (seguramente utilizando el teclado, aunque también es posible introducir datos utilizando la voz o alguna imagen).
* La función `input()` es invocada sin argumentos (es la manera mas sencilla de utilizar la función); la función **pondrá la consola en modo de entrada**; aparecerá un cursor que parpadea, y podrás introducir datos con el teclado, al terminar presiona la **tecla Enter**; todos los datos introducidos serán **enviados al programa** a través del resultado de la función.
* El resultado debe ser asignado a una variable; esto es crucial, si no se hace los datos introducidos se perderán.
* Después se utiliza la función `print()` para mostrar los datos que se obtuvieron, con algunas observaciones adicionales.

Intenta ejecutar el código y permite que la función te muestre lo que puede hacer.

## La función input() con un argumento

La función `input()` puede hacer algo más: puede mostrar un mensaje al usuario sin la ayuda de la función `print()`.

Se ha modificado el ejemplo un poco, observa el código:

```
anything = input("Dime algo...")
print("Mmm...", anything, "...¿En serio?")
```

* La función `input()` se llamaa con un argumento, que es una cadena con un mensaje.
* El mensaje será mostrado en consola antes de que el usuario tenga oportunidad de escribir algo.
* Después de esto `input()` hará su trabajo.

Esta variante de la invocación de la función `input()` simplifica el código y lo hace más claro.

## El resultado de la función input()

Se ha dicho antes, pero hay que decirlo sin ambigüedades una vez más: el resultado de la función `input()` **es una cadena**.

Una cadena que contiene todos los caracteres que el usuario introduce desde el teclado. No es un entero ni un flotante.

Esto significa que **no se debe utilizar como un argumento para operaciones matemáticas**, por ejemplo, no se pueden utilizar estos datos para elevarlos al cuadrado, para dividirlos entre algo o por algo.

```
anything = input("Inserta un número: ")
something = anything ** 2.0
print(anything, "al cuadrado es", something)
```

## La función input() - operaciones prohibidas

Si ejecutamos el programa anterior, insertaremos un número y, ¿qué es lo que ocurre?. Python debió haberte dado la siguiente salida:

```
Traceback (most recent call last):
File ".main.py", line 4, in <module>
something = anything ** 2.0
TypeError: unsupported operand type(s) for ** or pow(): 'str' and 'float'
```


La última línea lo explica todo, se intentó aplicar el operador `**` a `str` (una cadena) y a un `float` (valor flotante). Esto está prohibido. 

¿Habremos llegado a un punto muerto? ¿Existirá alguna solución? Claro que la hay.
