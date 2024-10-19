# Ejemplo 5: Recursividad


La **recursividad** es una técnica donde una función se llama a si misma.

Tanto el factorial como la serie Fibonacci, son las mejores opciones para ilustrar esta técnica,.

## Cálculo de la serie de Fibonacci de forma recursiva

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

## Cálculo del factorial de forma recursiva

El factorial también tiene un lado recursivo. Observa:

`n! = 1 × 2 × 3 × ... × n-1 × n`

Esto se puede expresar de forma recursiva de la siguiente manera:
```
n! = (n-1)! × n
```

Y podemos reescribir la función de forma recursiva:

```
def factorial(n):
    if n < 0:
        return None
    if n < 2:
        return 1
    return n * factorial(n - 1)
```
En este caso, el caso base que se hace que se termine la recursión es cuando `n` es igual a 1 que se devuelve un 1.

## Cuestionario

1. ¿Qué ocurrirá al intentar ejecutar el siguiente fragmento de código y por qué?

    ```
    def factorial(n):
        return n * factorial(n - 1)
    
    
    print(factorial(4))
    ```

2. ¿Cuál es la salida del siguiente fragmento de código?
    ```
    def fun(a):
        if a > 30:
            return 3
        else:
            return a + fun(a + 3)


    print(fun(25))
    ```

## Solución cuestionario

1. Pregunta 1

    La función no tiene una condición de terminación, por lo tanto Python arrojara una excepción `RecursionError: maximum recursion depth exceeded`. 

2. Pregunta 2

    `56`


