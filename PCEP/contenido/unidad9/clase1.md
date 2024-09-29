# Bucle while

## Estructura repetitiva while 



Las estructuras repetitivas o bucles nos permiten repetir un conjunto de instrucciones. En concreto el bucle `while` permite repetir un conjunto de instrucciones mientras se cumpla una condición. En lenguaje natural sería parecida a esta sentencia:

```
mientras ocurra algo
    haz una tarea
    haz otra tarea
    ...
```

Hay que tener en cuenta que si no *ocurre nada* no se realiza ninguna tarea.

La instrucción `while` ejecuta una secuencia de instrucciones mientras una condición sea verdadera.

```
while <condición>:
    <instrucciones>
```

* Una instrucción o conjunto de instrucciones ejecutadas dentro del `while` se llama el **cuerpo del ciclo o bucle**.
* Al ejecutarse esta instrucción, la condición es evaluada. Si la condición resulta verdadera, se ejecuta una vez la secuencia de instrucciones que forman el cuerpo del ciclo. Al finalizar la ejecución del cuerpo del ciclo se vuelve a evaluar la condición y, si es verdadera, la ejecución se repite. Estos pasos se repiten mientras la condición sea verdadera.
* Se puede dar la circunstancia que las instrucciones del bucle **no se ejecuten nunca**, si al evaluar por primera vez la condición resulta ser falsa.
* Si la condición siempre es verdadera, al ejecutar esta instrucción se produce un **ciclo infinito**. A fin de evitarlo, las instrucciones del cuerpo del ciclo deben contener alguna instrucción que **modifique la o las variables involucradas en la condición**, de modo que ésta sea falsificada en algún momento y así finalice la ejecución del ciclo.
* Es es parecido  a la estructura alternativa con `if`: sólo cambia la palabra `if` por `while`, pero el comportamiento es totalmente diferente: cuando se cumple la condición, `if` realiza sus sentencias sólo una vez; `while` repite la ejecución siempre que la condición se evalúe como `True`.
* Las instrucciones del cuerpo del bucle hay que indicarlas con una **sangría**.

## Un bucle infinito

Un **bucle infinito**, también denominado bucle sin fin, es una secuencia de instrucciones en un programa que se repite indefinidamente (bucle sin fin).

Este es un ejemplo de un bucle que no puede finalizar su ejecución:

```
while True:
    print("Estoy atrapado dentro de un bucle.")
```

Este bucle imprimirá infinitamente `"Estoy atrapado dentro de un bucle"`. En la pantalla.

## Ejemplo: Encontrar el número más grande

Volvamos a ver el ejemplo que estudiamos un apartado anterior: Hay que buscar el número más grande de los que vamos introducción, para terminar introducimos el número -1. Analiza el programa cuidadosamente. Localiza donde comienza el bucle  y descubre como se sale del cuerpo del bucle:

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
```

## Otro ejemplo de bucle while

Veamos otro ejemplo utilizando el bucle `while`. Programa que lee una secuencia de números y cuenta cuántos números son pares y cuántos son impares. El programa termina cuando se ingresa un cero.

```
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

En el programa anterior, la **condición de salida del bucle** es que introduzcamos un número determinado, en este caso el 0. En el siguiente ejemplo vamos a usar una variable `counter` para salir del bucle, de tal manera que el bucle haga 5 iteraciones.

Observa el fragmento de código a continuación:

```
counter = 5
while counter != 0:
    print("Dentro del bucle.", counter)
    counter -= 1
print("Fuera del bucle.", counter)
```

Este código está destinado a imprimir la cadena `"Dentro del bucle."` y el valor almacenado en la variable `counter` durante un bucle dado exactamente cinco veces. Una vez que la condición se haya cumplido (la variable `counter` ha alcanzado 0), se sale del bucle y aparece el mensaje `"Fuera del bucle".` así como también el valor almacenado en `counter` se imprime.

De forma más compacta, podríamos escribir el mismo programa de la siguiente forma, modificando la condición del bucle. ¿Puedes ver la diferencia?:

```
counter = 5
while counter:
    print("Dentro del bucle.", counter)
    counter -= 1
print("Fuera del bucle.", counter)
```
¿Es más compacto que antes? Un poco. ¿Es más legible? Eso es discutible.

