# Tuplas

Una tupla es una secuencia inmutable. Se puede comportar como una lista pero no puede ser modificada en el momento.
Lo primero que distingue una lista de una tupla es la sintaxis empleada para crearlas. Las tuplas utilizan paréntesis, mientras que las listas usan corchetes, aunque también es posible crear una tupla tan solo separando los valores por comas.

Observa el ejemplo:

```
tuple_1 = (1, 2, 4, 8)
tuple_2 = 1., .5, .25, .125

print(tuple_1)
print(tuple_2)
```

Se definieron dos tuplas, ambas contienen cuatro elementos y se imprimieron dando este resultado:
```
(1, 2, 4, 8)
(1.0, 0.5, 0.25, 0.125)
```
Cada elemento de una tupla puede ser de distinto tipo (punto flotante, entero, cadena, o cualquier otro tipo de dato).

## ¿Cómo crear una tupla?

Podemos crear una tupla vacía:
```
empty_tuple = ()
```

Y si queremos una tupla de un solo elemento, es necesario indicar la coma:

```
one_element_tuple_1 = (1, )
one_element_tuple_2 = 1.,
```

También se puede crear una tupla utilizando la función integrada de Python `tuple()`. Esto es particularmente útil cuando se desea convertir una secuencia (por ejemplo, una lista, rango, cadena, etcétera) en una tupla:

```
my_tuple = tuple((1, 2, "cadena"))
print(my_tuple)

my_list = [2, 4, 6]
print(my_list)    # salida: [2, 4, 6]
print(type(my_list))    # salida: <class 'list'>
tup = tuple(my_list)
print(tup)    # salida: (2, 4, 6)
print(type(tup))    # salida: <class 'tuple'>
```

De la misma manera, cuando se desea convertir un iterable en una lista, se puede emplear la función integrada de Python denominada `list()`:
```
tup = 1, 2, 3, 
my_list = list(tup)
print(type(my_list))    # salida: <class 'list'>
```

## ¿Cómo utilizar un tupla?

Si deseas leer los elementos de una tupla, lo puedes hacer de la misma manera que se hace con las listas. Ejemplo:

```
my_tuple = (1, 10, 100, 1000)

print(my_tuple[0])
print(my_tuple[-1])
print(my_tuple[1:])
print(my_tuple[:-2])

for elem in my_tuple:
    print(elem)
```
Como vemos podemos indexar la lista, realizar rebanadas y recorrerla. Lo que no podemos hacer es modificaciones en la tupla.
Las siguientes instrucciones nos darían errores:
```
my_tuple = (1, 10, 100, 1000)

my_tuple.append(10000)
del my_tuple[0]
my_tuple[1] = -10
```

El error que obtendremos será: `AttributeError: 'tuple' object has no attribute 'append'`.

## Más operaciones de tuplas

Además de la indexación, rebanadas y recorridos, podemos ejecutar las siguientes operaciones a las tuplas:

* La función `len()` acepta tuplas, y devuelve el número de elementos contenidos dentro.
* El operador `+` puede unir tuplas (ya se ha mostrado esto antes).
* El operador `*` puede multiplicar las tuplas, así como las listas.
* Los operadores `in` y `not in` funcionan de la misma manera que en las listas.

Veamos un ejemplo:

```
my_tuple = (1, 10, 100)

t1 = my_tuple + (1000, 10000)
t2 = my_tuple * 3

print(len(t2))
print(t1)
print(t2)
print(10 in my_tuple)
print(-10 not in my_tuple)
```

Una de las propiedades de las tuplas más útiles es que pueden aparecer en el lado izquierdo del operador de asignación. Este fenómeno ya se vio con anterioridad, cuando fue necesario encontrar una manera de intercambiar los valores entre dos variables.

Observa el siguiente fragmento de código:

```
var = 123

t1 = (1, )
t2 = (2, )
t3 = (3, var)

t1, t2, t3 = t2, t3, t1

print(t1, t2, t3)
```

Estamos intercambiando los valores almacenados en estas tuplas. `t1` se convierte en `t2`, `t2` se convierte en `t3`, y `t3` se convierte en `t1`.

Además hay que indicar que los elementos de una tupla pueden ser variables o expresiones, no solo literales. 
