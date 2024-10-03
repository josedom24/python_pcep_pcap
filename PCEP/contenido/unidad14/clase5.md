# Ejemplo 5: Recursividad


La **recursividad** es una técnica donde una función se llama a si misma.

Tanto el factorial como la serie Fibonacci, son las mejores opciones para ilustrar est técnica,.

La serie de Fibonacci es un claro ejemplo de recursividad. Ya te dijimos que:

Fib_n = Fib_n-1 + Fib_n-2

Para calcular un número de la serie de Fibonacci hay que volver a calcular la sería de los dos números anteriores.   

En esta versión del código se hace uso de la recursividad:

```
def fib(n):
    if n < 1:
        return None
    if n < 3:
        return 1
    return fib(n - 1) + fib(n - 2)
```

Tenemos que tener en cuenta que debe existir un caso (**caso base**)  que evite que se siga ejecutando la función, en este caso es cuando el número es menor a 3.



El factorial también tiene un lado recursivo. Observa:

n! = 1 × 2 × 3 × ... × n-1 × n


Es obvio que:

1 × 2 × 3 × ... × n-1 = (n-1)!


Entonces, finalmente, el resultado es:

n! = (n-1)! × n


Esto se empleará en nuestra nueva solución.


Aquí esta:

def factorial_function(n):
    if n < 0:
        return None
    if n < 2:
        return 1
    return n * factorial_function(n - 1)


¿Funciona? Claro que si. Pruébalo por ti mismo.

Nuestro viaje funcional esta por terminar. La siguiente sección abordara dos tipos de datos en Python: tuplas y diccionarios.

