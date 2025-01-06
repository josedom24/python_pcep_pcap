# Introducción a las excepciones

Cualquier cosa que pueda salir mal, saldrá mal. Esta es la Ley de Murphy, y se aplica perfectamente al mundo de la programación. Si el código puede fallar, lo hará.

Veamos un ejemplo:

```
import math

x = float(input("Ingresa x: "))
y = math.sqrt(x)

print("La raíz cuadrada de", x, "es igual a", y)
```

A primera vista, este código parece simple, pero existen al menos dos posibles puntos de fallo:

1. **Conversión de cadena a número**: El usuario puede ingresar una cadena que no se pueda convertir a un valor flotante.
    El usuario ingresa una cadena de texto en lugar de un número.
    ```
    Ingresa x: Abracadabra

    Traceback (most recent call last):
      File "sqrt.py", line 3, in <module>
        x = float(input("Ingresa x: "))
    ValueError: could not convert string to float: 'Abracadabra'
    ```

2. **Raíz cuadrada de un número negativo**: La función `sqrt()` fallará si se le pasa un valor negativo.
    El usuario ingresa un número negativo.

    ```
    Ingresa x: -1

    Traceback (most recent call last):
      File "sqrt.py", line 4, in <module>
        y = math.sqrt(x)
    ValueError: math domain error
    ```

## ¿Qué ocurre cuando se produce un error en nuestro programa?

Cada vez que tu código intenta realizar algo incorrecto, irresponsable o inaplicable, Python responde de dos maneras:

1. **Detiene la ejecución del programa**.
2. **Genera un tipo especial de dato**, llamado excepción.

Este proceso se denomina **"generar una excepción"**. Básicamente, Python lanza una excepción cuando no sabe cómo proceder con el código. 

* La excepción espera que algo la detecte y actúe en consecuencia.
* Si no se maneja la excepción, el programa finalizará abruptamente, y Python mostrará un mensaje de error en la consola.
* Si la excepción es manejada correctamente, el programa puede continuar su ejecución normalmente.

Python cuenta con herramientas poderosas para observar, identificar y manejar estas excepciones de manera eficiente. Cada excepción tiene un nombre específico, lo que facilita su identificación y manejo.

## Ejemplos de excepciones

### Ejemplo 1

Ya has visto algunas excepciones. Por ejemplo, en el mensaje de error:

```bash
ValueError: math domain error
```

Aquí, `ValueError` es el nombre de la excepción. Este es solo un ejemplo; hay muchas otras excepciones con las que te puedes familiarizar.

### Ejemplo 2

Veamos otro ejemplo:

```
value = 1
value /= 0
```

Al ejecutar este código obtenemos otra excepción:

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ZeroDivisionError: division by zero
```

### Ejemplo 3

```
my_list = []
x = my_list[0]
```

Al ejecutar este código nos aparece la siguiente excepción:

```
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range
```
