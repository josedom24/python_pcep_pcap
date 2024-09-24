# Resumen y cuestionario

## Resumen

1. La lista es un **tipo de dato en Python** (que más adelante llamaremos **clase**) que se utiliza para almacenar múltiples objetos. Es una colección ordenada y mutable de elementos separados por comas entre corchetes, por ejemplo:

```
my_list = [1, None, True, "Soy una cadena", 256, 0]
```

2. Una invocación típica de función tiene el siguiente aspecto: `result = function(arg)`, mientras que una invocación típica de un método se ve así: `result = data.method(arg)`. Las listas tienen distintos métodos que cambian el estado de las mismas. en este apartado hemos usado dos:

    * `append()`: Toma el valor de su argumento y lo coloca al final de la lista.
    * `insert()`: Recibe dos argumentos: la posición donde que remos introducir el nuevo elemento, que se recibe como segundo argumento.

```
my_list = [1, None, True, "Soy una cadena", 256, 0]
my_list.append(23.4)
my_list.insert(0,"Hola")
```

2. Las listas se pueden indexar y actualizar , por ejemplo:

```
my_list = [1, None, True, 'Soy una cadena', 256, 0]
print(my_list[3])  # salida: Soy una cadena
print(my_list[-1])  # salida: 0

my_list[1] = '?'
print(my_list)  # salida: [1, '?', True, 'Soy una cadena', 256, 0]

my_list.insert(0, "primero")
my_list.append("último")
print(my_list)  # outputs: ['primero', 1, '?', True, 'Soy una cadena', 256, 0, 'último']
```

3. Las listas pueden estar anidadas, ese decir un elemento de la lista puede ser otra lista, por ejemplo:

```
my_list = [1, 'a', ["lista", 64, [0, 1], False]]
```

    Profundizaremos en este aspecto en un apartado posterior del curso.

4. Los elementos de la lista y las listas se pueden eliminar, por ejemplo:

```
my_list = [1, 2, 3, 4]
del my_list[2]
print(my_list)  # salida: [1, 2, 4]

del my_list  # borra la lista entera
```

5. Las listas pueden ser iteradas mediante el uso del bucle for, por ejemplo:

```
my_list = ["blanco", "purpura", "azul", "amarillo", "verde"]

for color in my_list:
    print(color)
```

6. La función `len()` se puede usar para verificar la longitud de la lista, por ejemplo:

```
my_list = ["blanco", "purpura", "azul", "amarillo", "verde"]
print(len(my_list))  # salida 5

del my_list[2]
print(len(my_list))  # salida 4
```

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


