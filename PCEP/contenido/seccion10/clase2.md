# Operaciones básicas sobre las listas

## Accediendo al contenido de la lista

La **indexación** nos permite acceder a los elementos de una lista. Por ejemplo podemos imprimir el primer elemento de la lista:

```
print(numeros[0]) # Accediendo al primer elemento de la lista.
```

* Para indexar un elemento de la lista indicamos la posición del elemento (**índice**) dentro de los corchetes.
* Para indicar el índice podemos indicar cualquier expresión (literales, variables, operaciones, ...)

También podemos imprimir la lista completa utilizando la función `print()`:

```
print(numeros)  # Imprimiendo la lista completa.
```

Python decora la salida de una manera que sugiere que todos los valores presentados forman una lista. La salida del fragmento de ejemplo anterior se ve así:

```
[10, 5, 7, 2, 1]
```

Tenemos que tener en cuanta que los índices negativos son válidos, vemos distintos ejemplos:

* Un elemento con un índice igual a -1 es el último en la lista: `print(numeros[-1])`
* Del mismo modo, el elemento con un índice igual a -2 es el penúltimo en la lista: `print(numeros[-2])`.
* Así sucesivamente.

## Modificando el valor de un elemento de la lista

Por medio de la **indexación** también podemos modificar el valor de un determinado elemento de la lista. Veamos un ejemplo:

```
numeros = [10, 5, 7, 2, 1]
print("Contenido de la lista original:", numeros)  # Imprimiendo contenido de la lista original.

numeros[0] = 111
print("\nPrevio contenido de la lista:", numeros)  # Imprimiendo contenido de la lista anterior.

numeros[1] = numeros[4]  # Copiando el valor del quinto elemento al segundo elemento.
print("Nuevo contenido de la lista:", numeros)  # Imprimiendo el contenido de la lista actual.
```


* Hemos asignado un nuevo valor de 111 al primer elemento en la lista. 
* Hemos copiado el valor del quinto elemento al segundo elemento. 

## La función len()

La longitud de una lista puede variar durante la ejecución. Se pueden agregar nuevos elementos a la lista, mientras que otros pueden eliminarse de ella. Esto significa que la lista es una **estructura dinámica**.

La función `len()` (su nombre proviene de length - longitud) nos devuelve la longitud de la lista, la cantidad de elementos que almacena.

La función toma el nombre de la lista como un argumento y devuelve el número de elementos almacenados actualmente dentro de la lista (en otras palabras, la longitud de la lista).

Indicar también que la función `len()` se puede usar con las cadenas de caracteres, en este caso de vuelve el número de caracteres que posee la cadena:

```
cadena = Informática"
print(len(cadena))
```

## Eliminando elementos de una lista

Cualquier elemento de la lista puede ser eliminado en cualquier momento, esto se hace con una instrucción llamada `del` (eliminar). Hay que tener en cuenta  que es una instrucción, no una función.

Para su utilización indexamos el elemento que queremos eliminar:

```
del numeros[1]
```

La ejecución de esta instrucción hace que **la longitud de la lista se reducirá en uno**.

En general si intentamos indexar un elemento que no existe nos devolverá un error, en este caso como hemos borrado un elemento, el elemento que está en la posición 4, no existe:

```
print(numeros[4])
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list index out of range

numbers[4] = 1
numeros[4]=1
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
IndexError: list assignment index out of range
```

## Ejemplo

Veamos un ejemplo de todo lo aprendido hasta ahora:

```
numeros = [10, 5, 7, 2, 1]
print("Contenido de la lista original:", numeros) # Imprimiendo el contenido de la lista original.

numeros[0] = 111
print("\nContenido de la lista con cambio:", numeros) # Imprimiendo contenido de la lista con 111.

numeros[1] = numeros[4] # Copiando el valor del quinto elemento al segundo elemento.
print("Contenido de la lista con intercambio:", numeros) # Imprimiendo contenido de la lista con intercambio.

print("\nLongitud de la lista:", len(numeros)) # Imprimiendo la longitud de la lista.

del numeros[1]  # Eliminando el segundo elemento de la lista.
print("Longitud de la nueva lista:", len(numeros))  # Imprimiendo nueva longitud de la lista.
print("\nNuevo contenido de la lista:", numeros)  # Imprimiendo el contenido de la lista actual.
```

