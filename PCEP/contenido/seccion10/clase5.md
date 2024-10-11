# Recorrido de listas

## Recorriendo la lista con un bucle for

El bucle for nos permite posicionarnos en todos los elementos de una lista de forma consecutiva, es lo que llamamos **recorrido de listas**.

Vemos un ejemplo: Supongamos que deseas calcular la suma de todos los valores almacenados en la lista `my_list`.

1. Necesitas una variable donde vamos a ir acumulando las suma de los distintos valores de la lista, inicialmente un valor de 0 (normalmente llamamos a este tipo de variables **acumuladores**), En este ejemplo esta variable se llamará `total`.
2. Tendremos que ir posicionándonos en todos los elementos de la lista para ir sumándolos y guardar el resultado en la variable `total`. 

Veamos el programa:

```
my_list = [10, 1, 8, 3, 5]
total = 0

for i in range(len(my_list)):
    total += my_list[i]

print(total)
```

* A la lista se le asigna una secuencia de cinco valores enteros.
* La variable `i` toma los valores `0,1,2,3, y 4`, y luego indexa la lista, seleccionando los elementos siguientes: el primero, segundo, tercero, cuarto y quinto.
* Cada uno de estos elementos se agrega junto con el operador `+=` a la variable `total`, dando el resultado final al final del bucle.
* Usamos la función `len()` para que el programa funcione independientemente a la longitud de la lista., hace que el código sea independiente de cualquier posible cambio en el contenido de la lista.

Aunque está solución funciona, podemos simplificar la resolución de dicho problema, usando el recorrido de lista con el bucle for. El código sería el siguiente:

```
my_list = [10, 1, 8, 3, 5]
total = 0

for i in my_list:
    total += i

print(total)
```

* La instrucción `for` especifica la variable utilizada para navegar por la lista (`i`) seguida de la palabra clave `in` y el nombre de la lista que queremos recorrer (`my_list`).
* A la variable `i` se le asignan los valores de todos los elementos de la lista de forma consecutiva, uno detrás de otro.
* En este caso no necesitamos usar ´índices, la variable `i` va tomando los valores de los elementos de la lista.
* La función len() tampoco es necesaria aquí.

## Cuestionario

1. ¿Cuál es la salida del siguiente fragmento de código?

```
lst = [1, 2, 3, 4, 5]
lst.insert(1, 6)
del lst[0]
lst.append(1)

print(lst)
```

2. ¿Cuál es la salida del siguiente fragmento de código?

```
lst = [1, 2, 3, 4, 5]
lst_2 = []
add = 0

for number in lst:
    add += number
    lst_2.append(add)

print(lst_2)
```

3. ¿Cuál es la salida del siguiente fragmento de código?

```
lst = []
del lst
print(lst)
```

4. ¿Cuál es la salida del siguiente fragmento de código?

```
lst = [1, [2, 3], 4]
print(lst[1])
print(len(lst))
```

## Solución cuestionario

1. Pregunta 1:

```
[6, 2, 3, 4, 5, 1]
```

2. Pregunta 2:

```
[1, 3, 6, 10, 15]
```

3. Pregunta 3:

```
NameError: name 'lst' is not defined
```

4. Pregunta 4:

```
[2, 3]
3
```


