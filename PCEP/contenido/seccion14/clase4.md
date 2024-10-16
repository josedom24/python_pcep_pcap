# Ejemplo 4: Números Fibonacci

La serie de Fibonacci es una secuencia de números enteros los cuales siguen una regla sencilla:

* El primer elemento de la secuencia es igual a uno (Fib_1 = 1).
* El segundo elemento también es igual a uno (Fib_2 = 1).
* Cada número después de ellos son la suman de los dos números anteriores (Fib_n = Fib_n-1 + Fib_n-2).

Aquí están algunos de los primeros números en la serie Fibonacci:

```
fib_1 = 1
fib_2 = 1
fib_3 = 1 + 1 = 2
fib_4 = 1 + 2 = 3
fib_5 = 2 + 3 = 5
fib_6 = 3 + 5 = 8
fib_7 = 5 + 8 = 13
```

Vamos a crear una función para calcular el número de la serie de Fibonacci correspondiente a la posición que se pasa como parámetro:

```
def fib(n):
    if n < 1:
        return None
    if n < 3:
        return 1

    elem_1 = elem_2 = 1
    the_sum = 0
    for i in range(3, n + 1):
        the_sum = elem_1 + elem_2
        elem_1, elem_2 = elem_2, the_sum
    return the_sum


for n in range(1, 10):  # probando
    print(n, "->", fib(n))
```

Al probar el código, se generan los siguientes resultados:

```
1 -> 1
2 -> 1
3 -> 2
4 -> 3
5 -> 5
6 -> 8
7 -> 13
8 -> 21
9 -> 34
```

