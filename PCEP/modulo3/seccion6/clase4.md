# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 6: Operaciones con listas
## Clase: Programas de ejemplo de uso de listas

### Ejemplo 1

En este ejemplo vamos a realizar un programa que encuentre el valor mayor de una lista.

```
my_list = [17, 3, 11, 5, 1, 9, 7, 15, 13]
largest = my_list[0]

for i in range(1, len(my_list)):
    if my_list[i] > largest:
        largest = my_list[i]

print(largest)
```
* En esta primera versión usamos la indexación para recorrer los elementos de la lista.
* Suponemos que el número más grande, que guardamos en la variable `largest` es el primero.
* Recorremos desde el segundo elemento hasta el último.
* Si un elemento es mayor que el que tenemos guardado en la variables `largest` actualizamos el valor de esta variable porque hemos encontrado uno más grande.
* Al final del recorrido en la variable `largest` tendremos el mayor número.

Vamos a realizar ahora la versión 2. Como hicimos en un ejemplo anterior, podríamos hacer el mismo programa usando el recorrido de listas con el bucle for:

```
my_list = [17, 3, 11, 5, 1, 9, 7, 15, 13]
largest = my_list[0]

for i in my_list[1:]:
    if i > largest:
        largest = i

print(largest)
```

* La lógica del programa es similar a la de la versión anterior, pero ahora la variable `i`no es un índice, es el valor de los distintos elementos de la lista en cada iteración del bucle.
* Observa como usando la rebanada recorremos sólo desde el segundo elemento de la lista.

### Ejemplo 2

Vamos a realizar un programa que encuentre lam posición de un elemento dentro de una lista. 

```
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
to_find = 5
found = False

for i in range(len(my_list)):
    found = my_list[i] == to_find
    if found:
        break

if found:
    print("Elemento encontrado en el índice", i)
else:
    print("ausente")

```

* El valor buscado se almacena en la variable `to_find`.
* El estado actual de la búsqueda se almacena en la variable `found` (`True/False`). 
* La varaible `found` es un indicador que a principio inicializamos a `False` indicando que no se ha encontrado. 
* Si se encuentra se pone a `True` y se sale del bucle usando el `break`.

Si usamos el recorrido de listas con el bucle for, tendremos el siguiente programa:

```
my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
to_find = 5
found = False
indice = 0
for i in my_list:
    found = i == to_find
    if found:
        break
    indice+=1

if found:
    print("Elemento encontrado en el índice", indice)
else:
    print("ausente")
```

* En esta versión necesitamos otra variable `indice` que es un contador que me permite contar la posición (el índice).
* A principios se inicializa a 0, indicando que estamos en el primer elemento.
* Y cada vez que no encontremos el número buscado la incrementaremos para apuntar que estamos posicionados en el siguiente elemento.

### Ejemplo 3

En este ejemplo, vamos a suponer que has elegido los siguientes números en la lotería: 3, 7, 11, 42, 34, 49. Los números que han salido sorteados son: 5, 11, 9, 42, 3, 49. ¿Cuántos números has acertado?

El programa sería el siguiente:

```
loteria = [5, 11, 9, 42, 3, 49]
tus_numeros = [3, 7, 11, 42, 34, 49]
hits = 0

for number in tus_numeros:
    if number in loteria:
        hits += 1

print(hits)
```

* La lista `loteria` almacena todos los números que han salido en la lotería.
* La lista `tus_numeros` almacena los números con que se juega.
* La variable `hits` cuenta tus aciertos.

