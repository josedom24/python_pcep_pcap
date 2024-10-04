# Errores en la programación

* Los buenos programadores siempre quieren escribir programas de calidad que funcionen bien, sin errores.
* Si estás empezando a programar, pronto te darás cuenta que es complicado escribir código sin errores.
* Aunque seamos muy cuidadosos y escribamos un código de calidad, siempre tendremos varias fuentes que nos pueden causar errores en nuestros programas.

## Fuentes de errores

Tenemos dos fuente de errores principalmente:

* **Los datos son incorrectos**: Los datos que introducimos a nuestro programa provocan que el programa no funcione bien. Por ejemplo, esperas que se ingrese al código un valor entero, pero tu usuario descuidado ingresa algunas letras al azar.
Por defecto estos tipos de errores producen que el programa termine mostrando un mensaje de error no muy claro para el usuario, aprenderemos a gestionar estos errores para que el usuario tenga una mejor experiencia.
* **El código es incorrecto**: Los errores de programación se revela cuando ocurre un comportamiento no deseado del programa debido a errores que se cometieron cuando se estaba escribiendo el código. Este tipo de error se denomina comúnmente **"bug"** (bicho en inglés).

## Errores en Python

En Python, existe una distinción entre dos tipos de errores:

* **Errores de sintaxis**, que ocurren cuando el analizador encuentra una sentencia de código que no es correcta. Por ejemplo:

    ```
    print("Hola, ¡Mundo!)
    ```
    Provoca en error de tipo: `SyntaxError: EOL while scanning string literal`.
* **Excepciones**, ocurren incluso cuando el código es correcto sintácticamente.una sentencia o expresión es sintácticamente correcta. Estos son los errores que se detectan durante la ejecución, cuando tu código da como resultado un error que no es incondicionalmente fatal.

## Errores de datos

Escribamos un fragmento de código extremadamente trivial: leerá un número natural (un entero no negativo) e imprimirá su inverso. De esta forma, 2 se convertirá en 0.5 (1/2) y 4 en 0.25 (1/4). Aquí está el programa:

```
value = int(input('Ingresa un número natural: '))
print('El recíproco de', value, 'es', 1/value)
```

¿Qué puede provocar un error en este código?

Ingresar datos que no sean un número entero (que también incluye ingresar nada). en este caso el error que se produce es:
```
Traceback (most recent call last):
  File "code.py", line 1, in 
    value = int(input('Ingresa un número natural: '))
ValueError: invalid literal for int() with base 10: ''
```

La última línea nos explica qué ha pasado: en este caso nos indica `ValueErorror` que es el nombre de la **excepción** que se ha producido. En la misma línea nos muestra el detalle del error que se ha producido.

Frente a este tipo de errores podemos hacer dos cosas:

* Dentro del programa verificar si los datos introducidos son correctos, y no hacer nada hasta que nos se indiquen de forma correcta. De esta manera podríamos comprobar si el dato es de tipo entero. 
* La solución preferida será gestionar los errores producidos, que llamaremos **excepciones** como veremos en la siguiente clase.

