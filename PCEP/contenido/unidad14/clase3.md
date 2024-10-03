# Ejemplo 3: Factoriales

La siguiente función a definir calcula factoriales. ¿Recuerdas cómo se calcula un factorial?

0! = 1 
1! = 1
2! = 1 * 2
3! = 1 * 2 * 3
4! = 1 * 2 * 3 * 4
...
n! = 1 * 2 ** 3 * 4 * ... * n-1 * n

Se expresa con un signo de exclamación, y es igual al producto de todos los números naturales previos al número dado.

Escribimos una función que calcule el factorial:

```
def factorial(n):
    if n < 0:
        return None
    if n < 2:
        return 1
    
    product = 1
    for i in range(2, n + 1):
        product *= i
    return product


for n in range(1, 6):  # probando
    print(n, factorial(n))
```

Estos son los resultados obtenidos del código de prueba:

```
1 1
2 2
3 6
4 24
5 120
```



