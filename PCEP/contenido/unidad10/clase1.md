# Introducción a las listas

## ¿Por qué necesitamos listas?

Puede suceder que tengas que leer, almacenar, procesar y, finalmente, imprimir docenas, quizás cientos, tal vez incluso miles de números. ¿Entonces qué? ¿Necesitas crear una variable separada para cada valor? ¿Tendrás que pasar largas horas escribiendo instrucciones como la que se muestra a continuación?

```
var1 = int(input())
var2 = int(input())
var3 = int(input())
var4 = int(input())
var5 = int(input())
var6 = int(input())
...
```

Algunos puntos que debemos recordar:

* Hasta ahora, has aprendido como declarar variables que pueden almacenar exactamente **un valor dado a la vez**. 
* Tales variables a veces se denominan **escalares** por analogía con las matemáticas.
* Es deseable poder declarar que nos permita guardar **más de un valor**.
* A este tipo de datos la denominamos **secuencias**.
* Por ejemplo, un tipo de datos secuencia en Python son las **listas**. En una variable de tipo lista puedo guardar más de un dato.

Veamos un ejemplo de un problema en que se necesita procesar varios números:

Escribe un programa que:

* Lea cinco números.
* Los imprima en orden desde el más pequeño hasta el más grande (Este tipo de procesamiento se denomina ordenamiento).

## Crear listas

Vamos a crear una variable llamada `numeros`; se le asigna no solo un número, sino que se llena con una lista que consta de cinco valores (nota: la lista comienza con un corchete abierto y termina con un corchete cerrado; el espacio entre los corchetes es llenado con cinco números separados por comas).

```
numeros = [10, 5, 7, 2, 1]
```

Algunas consideraciones:

* Podemos decir que `numeros` es una lista que consta de cinco valores, todos ellos `numeros`. 
* La variable `numeros` es una lista de longitud igual a cinco (ya que contiene cinco elementos).
* Los elementos dentro de una lista pueden tener diferentes tipos. Algunos de ellos pueden ser enteros, otros son flotantes y otros pueden ser listas.
* En Python el primer elemento ocupa la posición 0. En nuestro ejemplo el valor `10` ocupa la posición `0`, y el último elemento, el número `1` tendrá la posición `4`.
* Nuestra lista es una colección de elementos, pero cada elemento es un escalar. 

## Indexando Listas

La **indexación** nos permite obtener o cambiar el valor de un determinado elemento de una lista. Por ejemplo:

* Vamos a asignar un nuevo valor de 111 al primer elemento en la lista. Lo hacemos de esta manera:

    ```
    numeros = [10, 5, 7, 2, 1]
    print("Contenido de la lista original:", numeros)  # Imprimiendo contenido de la lista original.

    numeros[0] = 111
    print("Nuevo contenido de la lista: ", numeros)  # Contenido de la lista actual.
    ```

* Y ahora queremos copiar el valor del quinto elemento al segundo elemento. 

    ```
    numeros = [10, 5, 7, 2, 1]
    print("Contenido de la lista original:", numeros)  # Imprimiendo contenido de la lista original.

    numeros[0] = 111
    print("\nPrevio contenido de la lista:", numeros)  # Imprimiendo contenido de la lista anterior.

    numeros[1] = numeros[4]  # Copiando el valor del quinto elemento al segundo elemento.
    print("Nuevo contenido de la lista:", numeros)  # Imprimiendo el contenido de la lista actual.
    ```

Para indexar un elemento de la lista indicamos la posición del elemento (**índice**) dentro de los corchetes.

Nota: todos los índices utilizados hasta ahora son literales. Sus valores se fijan en el tiempo de ejecución, pero cualquier expresión también puede ser un índice. Esto abre muchas posibilidades.

