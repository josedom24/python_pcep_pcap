# Usos de funciones lambdas

## Lambdas y la función map()

La función `map()` toma una función y uno o más iterables como argumentos, aplicando la función a cada elemento del iterable y devolviendo un iterador con los resultados. En combinación con lambdas, `map()` se vuelve muy poderosa para transformaciones rápidas y expresivas de datos.

Veamos un ejemplo:

```
list_1 = [x for x in range(5)]
list_2 = list(map(lambda x: 2 ** x, list_1))
print(list_2)

for x in map(lambda x: x * x, list_2):
    print(x, end=' ')
print()
```

* Creamos la lista `list_1` que contiene valores generados por la comprensión de listas.
* Usamos `map()` con la primera lambda: `map()` toma como función una lambda que eleva 2 a la potencia de cada valor en `list_1`. Esta operación se aplica a todos los elementos de la lista, generando `list_2`.
* Usamos `map()` con la segunda lambda:  `map()` toma una lambda que simplemente eleva al cuadrado cada elemento de `list_2`. 

El uso de lambdas en este contexto te permite evitar tener que definir funciones explícitas por separado para elevar al cuadrado o calcular una potencia. Sin las lambdas, el código sería más largo, ya que tendrías que definir funciones como esta:

```
def elevar_potencia(x):
    return 2 ** x

def cuadrado(x):
    return x * x

list_2 = list(map(elevar_potencia, list_1))
for x in map(cuadrado, list_2):
    print(x, end=' ')
```

## Lambdas y la función filter()

La función `filter()` en Python es muy útil cuando necesitas seleccionar ciertos elementos de una lista o cualquier otro iterable, en base a una condición. Junto con lambdas, puedes escribir código muy conciso y claro para filtrar datos sin la necesidad de escribir funciones explícitas.

La función `filter()` recibe dos argumentos:
1. Una función que devuelve `True` o `False` para cada elemento del iterable.
2. Un iterable (lista, tupla, etc.).

`filter()` devuelve un iterador que contiene solo los elementos que hacen que la función devuelva `True`.

Veamos un ejemplo:

```
from random import seed, randint

seed()
data = [randint(-10,10) for x in range(5)]
filtered = list(filter(lambda x: x > 0 and x % 2 == 0, data))

print(data)
print(filtered)
```

* Generamos  la lista `data`: se genera una lista de 5 números enteros aleatorios entre -10 y 10 usando la función `randint()` del módulo `random`. El generador de números aleatorios se inicializa con la función `seed()` para garantizar que los resultados sean aleatorios.
* Filtramos la lista: la función `filter()` toma una lambda que evalúa si un número es mayor que 0 y es par (`x % 2 == 0`). Esta lambda se aplica a cada elemento de `data`.


Sin lambdas, tendrías que definir una función explícita como esta:

```
def es_par_y_positivo(x):
    return x > 0 and x % 2 == 0

filtered = list(filter(es_par_y_positivo, data))
```

Aunque este enfoque también funciona, es más largo y, para casos simples, menos legible.

