# El módulo random

El módulo `random` de Python ofrece mecanismos para trabajar con números pseudoaleatorios. Aunque estos números pueden parecer impredecibles, son generados por algoritmos deterministas y predecibles, lo que los hace "pseudo" aleatorios. La verdadera aleatoriedad solo puede surgir de procesos físicos fuera de nuestro control, como la radiación cósmica.

Un generador de números aleatorios utiliza una **semilla** inicial para producir un número "aleatorio" y luego generar una nueva semilla en un ciclo que, aunque largo, no es infinito y eventualmente se repetirá. La semilla inicial determina el orden de los números generados, y **Python aumenta la aleatoriedad estableciendo automáticamente una semilla basada en la hora actual** al importar el módulo `random`. Esto asegura que cada ejecución del programa comience con una semilla diferente, proporcionando así una mayor variedad en los números generados.

El módulo `random` de Python ofrece varias funciones para generar números pseudoaleatorios, entre ellas:

## La función `random()`

Esta función genera un número flotante en el rango (0.0, 1.0). Por ejemplo, el siguiente código produce cinco números pseudoaleatorios:

```
from random import random

for i in range(5):
    print(random())
```

**Salida de muestra**:
```
0.9535768927411208
0.5312710096244534
0.8737691983477731
0.5896799172452125
0.02116716297022092
```

Cada ejecución genera una secuencia diferente, ya que está basada en la semilla actual del sistema.

## La función `seed()`

La función `seed()` permite establecer manualmente la semilla para el generador de números aleatorios. Tiene dos variantes:

* `seed()` establece la semilla usando la hora actual.
* `seed(int_value)` usa un valor entero específico como semilla.

Si se establece una semilla fija, el programa siempre generará la misma secuencia de números. El siguiente ejemplo muestra cómo establecer la semilla a 0 para obtener la misma salida cada vez:

```
from random import random, seed

seed(0)

for i in range(5):
    print(random())
```

**Salida de muestra**:
```
0.844421851525
0.75795440294
0.420571580831
0.258916750293
0.511274721369
```

Establecer una semilla fija elimina cualquier rastro de aleatoriedad, garantizando que la secuencia de números generados siempre será la misma. Aunque puede haber ligeras variaciones dependiendo de la precisión de la aritmética en diferentes sistemas, los resultados serán similares.

## Las funciones `randrange()` y `randint()`

Estas funciones son útiles para obtener valores enteros aleatorios.

* `randrange(fin)`: genera un entero aleatorio entre 0 y `fin` (excluyendo `fin`).
* `randrange(inicio, fin)`: genera un entero aleatorio entre `inicio` y `fin` (excluyendo `fin`).
* `randrange(inicio, fin, incremento)`: genera un entero aleatorio entre `inicio` y `fin` con un incremento especificado.
* `randint(izquierda, derecha)`: es equivalente a `randrange(izquierda, derecha+1)`, generando un número entero entre `izquierda` y `derecha` (incluyendo ambos límites).

El siguiente código genera una secuencia de tres ceros, seguida de un cero o uno en el cuarto lugar:

```
from random import randrange

for i in range(3):
    print(0, end=" ")
print(randrange(2))
```

Este código utiliza la función `randrange(2)`, que genera un valor aleatorio entre 0 y 1, lo que da una variabilidad en el último número de la secuencia generada.

## Las funciones `choice()` y `sample()`

Las funciones `randrange()` y `randint()` pueden producir valores repetidos, incluso dentro de un rango limitado. Esto se debe a que estas funciones simplemente generan números aleatorios sin preocuparse por su unicidad. El siguiente código es un ejemplo de cómo esto puede suceder:

```
from random import randint

for i in range(10):
    print(randint(1, 10), end=',')
```

Para evitar la repetición y obtener valores únicos de una secuencia, Python ofrece dos funciones útiles:

* `choice(secuencia)`: elige un solo elemento aleatorio de la secuencia.
* `sample(secuencia, elementos_a_elegir=1)`: selecciona varios elementos únicos aleatorios de la secuencia. El número de elementos a elegir se especifica como segundo argumento.

En el siguiente ejemplo, `choice()` selecciona un solo valor, mientras que `sample()` devuelve una muestra de valores sin repetidos:

```
from random import choice, sample

my_list = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

print(choice(my_list))
print(sample(my_list, 5))
print(sample(my_list, 10))
```

Con `sample()`, todos los elementos seleccionados son únicos, lo que lo convierte en una opción ideal para aplicaciones como la selección de números para una lotería.