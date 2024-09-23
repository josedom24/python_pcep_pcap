# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 2: Bucles en Python
## Clase: Bucle while

## Bucles (ciclos) en el código con while

¿Estás de acuerdo con la sentencia presentada a continuación?

```
mientras haya algo que hacer
    hazlo
```

Toma en cuenta que este registro también declara que, si no hay nada que hacer, nada ocurrirá.

En general, en Python, un **bucle** se puede representar de la siguiente manera:

```
while conditional_expression:
    instruction
```

Aunque es parecido sintacticamente a la estructura alternativa con `if`: sólo cambia la palabrá `if` por `while`), la diferencia semántica es más importante: cuando se cumple la condición, `if` realiza sus sentencias sólo una vez; `while` repite la ejecución siempre que la condición se evalúe como `True`.

Observa el algoritmo a continuación:

```
while conditional_expression:
    instruction_one
    instruction_two
    instruction_three
    :
    :
    instruction_n
```

Ahora, es importante recordar que:

* Si deseas ejecutar más de una sentencia dentro de un `while`, debes (como con `if`) poner **sangría** a todas las instrucciones de la misma manera.
* Una instrucción o conjunto de instrucciones ejecutadas dentro del `while` se llama el **cuerpo del bucle**.
* Si la condición es `False` tan pronto como se compruebe por primera vez, el cuerpo **no se ejecuta ni una sola vez** (ten en cuenta la analogía de no tener que hacer nada si no hay nada que hacer).
* El cuerpo debe poder **cambiar el valor de la condición**, porque si la condición es `True` al principio, el cuerpo podría funcionar continuamente hasta el infinito. Observa que hacer una cosa generalmente disminuye la cantidad de cosas por hacer.

## Un bucle infinito

Un **bucle infinito**, también denominado bucle sin fin, es una secuencia de instrucciones en un programa que se repite indefinidamente (bucle sin fin).

Este es un ejemplo de un bucle que no puede finalizar su ejecución:

```
while True:
    print("Estoy atrapado dentro de un bucle.")
```

Este bucle imprimirá infinitamente `"Estoy atrapado dentro de un bucle"`. En la pantalla.

NOTA: Si deseas ver cómo se comporta un bucle infinito, inicia IDLE, crea un nuevo archivo, copia y pega el código anterior, guarda tu archivo y ejecuta el programa. Lo que verás es la secuencia interminable de cadenas impresas de *"Estoy atrapado dentro de un bucle".* en la ventana de la consola de Python. Para finalizar tu programa, simplemente presiona **Ctrl-C**. Esto provocará la excepción *KeyboardInterrupt* y permitirá que tu programa salga del bucle. Hablaremos de ello más adelante en el curso.



## Ejemplo: Encontrar el número más grande

Volvamos a ver el ejemplo que estudiamos en la sección anterior: Hay que buscar el número más grande de los que vamos introducción, para terminar introducimos el número -1. Analiza el programa cuidadosamente. Localiza donde comienza el bucle  y descubre como se sale del cuerpo del bucle:

```
# Almacena el actual número más grande aquí.
largest_number = -999999999

# Ingresa el primer valor.
number = int(input("Introduce un número o escribe -1 para detener: "))

# Si el número no es igual a -1, continuaremos
while number != -1:
    # ¿Es el número más grande que el valor de largest_number?
    if number > largest_number:
        # Sí si, se actualiza largest_number.
        largest_number = number
    # Ingresa el siguiente número.
    number = int(input("Introduce un número o escribe -1 para detener: "))

# Imprime el número más grande
print("El número más grande es:", largest_number)
``

Comprueba como funciona este programa utilizando un bucle `while`.

## Otro ejemplo de bucle while

Veamos otro ejemplo utilizando el bucle `while`. Sigue los comentarios para descubrir la idea y la solución.

```
# Un programa que lee una secuencia de números
# y cuenta cuántos números son pares y cuántos son impares.
# El programa termina cuando se ingresa un cero.

odd_numbers = 0
even_numbers = 0

# Lee el primer número.
number = int(input("Introduce un número o escribe 0 para detener: "))

# 0 termina la ejecución.
while number != 0:
    # Verificar si el número es impar.
    if number % 2 == 1:
        # Incrementar el contador de números impares odd_numbers.
        odd_numbers += 1
    else:
        # Incrementar el contador de números pares even_numbers.
        even_numbers += 1
    # Leer el siguiente número.
    number = int(input("Introduce un número o escribe 0 para detener: "))

# Imprimir resultados.
print("Cuenta de números impares:", odd_numbers)
print("Cuenta de números pares:", even_numbers)
```

Ciertas expresiones se pueden simplificar sin cambiar el comportamiento del programa. Intenta recordar cómo Python interpreta la verdad de una condición y ten en cuenta que estas dos formas son equivalentes: 

* `while number != 0:` 
* `while number:`.

De la misma manera, la condición que verifica si un número es impar también puede codificarse en estas formas equivalentes:

* `if number % 2 == 1:` 
* `if number % 2:`

En el programa anterior, la **condición de salida del bucle** es que introduzcamos un número determinado, en este caso el -1. En el siguiente ejemplo vamos a usar una variable `counter` para salir del bucle, de tal manera que el bucle haga 5 iteraciones.

Observa el fragmento de código a continuación:

```
counter = 5
while counter != 0:
    print("Dentro del bucle.", counter)
    counter -= 1
print("Fuera del bucle.", counter)
```

Este código está destinado a imprimir la cadena `"Dentro del bucle."` y el valor almacenado en la variable counter durante un bucle dado exactamente cinco veces. Una vez que la condición se haya cumplido (la variable counter ha alcanzado 0), se sale del bucle y aparece el mensaje `"Fuera del bucle".` así como también el valor almacenado en counter se imprime.

De forma más compacta, podríamos escribir el mismo programa de la siguiente forma, modificando la condición del bucle. ¿Puedes ver la diferencia?:

```
counter = 5
while counter:
    print("Dentro del bucle.", counter)
    counter -= 1
print("Fuera del bucle.", counter)
```

¿Es más compacto que antes? Un poco. ¿Es más legible? Eso es discutible.

No te sientas obligado a codificar tus programas de una manera que siempre sea la más corta y la más compacta. La legibilidad puede ser un factor más importante. Mantén tu código listo para un nuevo programador. 

