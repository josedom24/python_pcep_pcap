# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 5: Ordenando listas simples: el ordenamiento de burbuja
## Clase: El ordenamiento burbuja en Python

### El ordenamiento burbuja en Python

¿Cuántos pases necesitamos para ordenar la lista completa? La naturaleza de este problema nos obliga a usar dos bucles:

* Un primer bucle que nos permite repetir el proceso con los elementos restantes de la lista.
* Otro bucle para ir comparando los elementos adyacentes.

Vamos a estudiar el segundo bucle que nos permite ir comparando e intercambiando, si es necesario, los elementos adyacentes. El código sería el siguiente:

```
my_list = [8, 10, 6, 2, 4]  # lista a ordenar

for i in range(len(my_list) - 1):  # necesitamos (5 - 1) comparaciones
    if my_list[i] > my_list[i + 1]:  # compara elementos adyacentes
        my_list[i], my_list[i + 1] = my_list[i + 1], my_list[i]  # Si terminamos aquí, tenemos que intercambiar elementos.
```
* Vamos a ir recorriendo desde el primer elemento (índice `i = 0`) hasta el penúltimo elemento `len(my_list) - 1`.
* Comparamos el elemento de la posición `i` con su adyacente `i + 1`.
* Si el orden es incorrecto, intercambiamos los valores.

Con la ejecución de este bucle tendríamos bien colocado el elemento más grande en el último elemento. Tendríamos que repetir este bucle repetidamente, como hemos visto en la clase anterior para asegurarnos que la lista termina ordenada. Para ello vamos a hacer las siguientes consideraciones:

* Para simplificar el programa vamos a recorrer siempre todos los elementos adyacentes con el bucle anterior, aunque como vimos en la clase anterior no sea necesario, ya que la lista se va ordenando por los últimos elementos.
* Vamos a introducir una variable que llamaremos `swapped` que nos permitirá **indicar** si se ha producido algún intercambio:
    * Al principio la inicializamos a `False` indicando que no hay intercambios.
    * Si se produce algún intercambio la ponemos a `True`.
    Si al final del bucle la variable sigue valiendo `False` significa que no ha habido ningún intercambio y significa que la lista está ordenada.
    * El primer bucle, que nos permite repetir el proceso, se volverá a jecutar si la variable `swapped` es `True` ya que todavía no se ha ordenado de forma completa la lista.
    * Como veremos en este programa necesitamos ejecutar un bucle dentro de otro, a esta estructura la llamamos **anidamiento de bucles**.


Veamos el programa completo:

```
my_list = [8, 10, 6, 2, 4]  # lista a ordenar
swapped = True  # Lo necesitamos verdadero (True) para ingresar al bucle while.

while swapped:
    swapped = False  # no hay intercambios hasta ahora
    for i in range(len(my_list) - 1):
        if my_list[i] > my_list[i + 1]:
            swapped = True  # ¡ocurrió el intercambio!
            my_list[i], my_list[i + 1] = my_list[i + 1], my_list[i]

print(my_list)
```

### Versión interactiva del programa

Mostramos a continuación una versión completa del programa donde de forma interactiva el usuario indica el número y elementos de la lista:

```
my_list = []
swapped = True
num = int(input("¿Cuántos elementos deseas ordenar?: "))

for i in range(num):
    val = float(input("Ingresa un elemento de la lista: "))
    my_list.append(val)

while swapped:
    swapped = False
    for i in range(len(my_list) - 1):
        if my_list[i] > my_list[i + 1]:
            swapped = True
            my_list[i], my_list[i + 1] = my_list[i + 1], my_list[i]

print("\nOrdenada:")
print(my_list)
```

### Ordenación de listas usando el método sort()

Hemos explicado este sistema de ordenación para que nos sirva de ejemplo para trabajar con la manipulación de los elementos de las listas, el intercambio de variables y los bucles anidados. Sin embargo las listas de Python nos ofrecen un método que nos permite ordenar la lista. Este método se llama `sort()` y lo utilizamos de la siguiente manera:

```
my_list = [8, 10, 6, 2, 4]
my_list.sort()
print(my_list)
```

Como puedes observar los métodos de las listas, cambian los elementos de la propia lista. Profundizaremos en esta propiedad en las siguientes secciones. Para terminar, si queremos ordenar de forma descendente ejecutaremos:

```
my_list.sort(reverse=True)
```