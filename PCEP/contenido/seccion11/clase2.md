# Operación de rebanada de listas

## Rebanadas (slice) de listas

Una **rebanada** es una operación que podemos realizar sobre una lista que nos permite **hacer una copia nueva de una lista, o partes de una lista**. En realidad, copia el contenido de la lista, no el nombre de la lista.

Por lo que la forma más fácil de copiar una lista en otra sería:

```
lista1 = [1,2,3]
lista2=lista1[:]
lista1[1] = 10
print(lista2) # [1, 2, 3]
```

Con la expresión `[:]` estamos realizando una rebanada que produce una lista completamente nueva.

También podemos crear nuevas sublistas de la lista, es decir partes de la lista, para ello de forma general podemos usar la siguiente sintaxis:

```
my_list[start:end]
```

* `start` es el índice del primer elemento **incluido en la rebanada**.
* `end` es el índice del primer elemento **no incluido en la rebanada**.

Es decir, crearemos una nueva lista que contendrán los elementos de la lista original desde el elemento en la posición indicada por `start` hasta el elemento en la posición `end - 1`.

Veamos un ejemplo:

```
my_list = [10, 8, 6, 4, 2]
new_list = my_list[1:3]
print(new_list)
```

La lista `new_list` contendrá `start - end` (3 - 1 = 2) elementos y son los que tienen índices iguales a 1 y 2 (pero no 3).

La salida del fragmento es: [8, 6]

## Rebanadas con índices negativos

Es posible utilizar valores negativos tanto para el inicio como para el fin (al igual que en la indexación):

```
my_list = [10, 8, 6, 4, 2]
new_list = my_list[1:-1]
print(new_list)
```

El resultado de este ejemplo sería `[8, 6, 4]`.

Hay que tener en cuenta que el índice indicado por `start` debe corresponder a un elemento que está colocado antes que el elemento especificado con el índice `end`, por lo tanto es posible que si esto no se cumple se creen listas vacías:

```
my_list = [10, 8, 6, 4, 2]
new_list = my_list[-1:1]
print(new_list)
```

En este ejemplo la salida es: `[ ]`.

## Más detalles sobre las rebanadas

Si omites el índice `start` en tu rebanada, se supone que deseas obtener un segmento que comienza en el elemento con índice 0.

Veamos un ejemplo:
```
my_list = [10, 8, 6, 4, 2]
new_list = my_list[:3]
print(new_list)
```

Es por esto que su salida es: `[10, 8, 6]`.

Del mismo modo, si omites el índice `end` en tu rebanada, se supone que deseas que el segmento termine en el elemento con el índice `len(my_list)`, es decir hasta el último elemento:

```
my_list = [10, 8, 6, 4, 2]
new_list = my_list[3:]
print(new_list)
```

En este caso la salida es: `[4, 2]`.

## Rebanadas junto a la instrucción del

La instrucción `del` puede eliminar más de un elemento de la lista a la vez usando rebanadas. Veamos algunos ejemplos:

```
my_list = [10, 8, 6, 4, 2]
del my_list[1:3]
print(my_list)
```

En este caso, la rebanada no produce ninguna lista nueva. El efecto es la eliminación de la lista de los elementos que había seleccionado la rebanada, es decir la salida del programa sería: `[10, 4, 2]`.

Vemos otros ejemplo. Podemos eliminar todos los elementos de la lista de la siguiente manera:

```
my_list = [10, 8, 6, 4, 2]
del my_list[:]
print(my_list)
```

La salida del programa sería `[ ]`.

Este último ejemplo es distinto a usar la instrucción `del` con la el nombre de la lista:

```
my_list = [10, 8, 6, 4, 2]
del my_list
print(my_list)
```

En este caso, la instrucción `del` eliminará la lista, no su contenido y la instrucción `print()` provocará un error de ejecución:

```
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    print(my_list)
NameError: name 'my_list' is not defined
```
