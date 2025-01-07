# Funciones lambda

Las **funciones lambda** en Python ofrecen una forma rápida y concisa de definir funciones que pueden ser útiles en ciertos contextos específicos. A diferencia de las funciones normales, las funciones lambdas **no tienen nombre** y son más simples y se utilizan cuando se necesita una función corta y **anónima** que se pueda definir en una sola línea. Si bien pueden parecer reemplazables por funciones normales, tienen algunos beneficios clave en términos de simplicidad y claridad en ciertos casos.

Las funciones lambda son útiles cuando:

1. **Se necesita una función pequeña y simple**: Si una función realiza una operación sencilla y no necesita ser utilizada repetidamente con un nombre propio, una lambda es una forma compacta de definirla.
2. **Mayor legibilidad en contextos breves**: En situaciones donde una función anónima se pasa como argumento o se usa dentro de otra función (por ejemplo, con `map()`, `filter()`, o `sorted()`), usar una lambda puede hacer el código más fácil de entender porque la lógica de la función está inmediatamente visible.
3. **Uso temporal de funciones**: Si solo necesitas una función para una operación puntual y no tiene sentido definirla por separado, puedes definir una lambda sobre la marcha sin la necesidad de escribir varias líneas de código.

La estructura básica de una función lambda es:

```
lambda parámetros: expresión
```

* **Parámetros**: Estos son los argumentos que la función lambda toma. Puede haber cero, uno o más parámetros.
* **Expresión**: Esta es una única expresión cuyo valor se devuelve cuando se ejecuta la función lambda.

En el ejemplo siguiente, usamos lambdas con nombres para ilustrar cómo funcionan:

```
dos = lambda: 2
raiz_cuadrada = lambda x: x * x
potencia = lambda x, y: x ** y

for a in range(-2, 3):
    print(raiz_cuadrada(a), end=" ")
    print(potencia(a, dos()))
```

* **`dos = lambda: 2`**: Esta función lambda no toma parámetros y siempre devuelve el valor `2`. Aunque normalmente sería anónima, la hemos asignado a la variable `dos`, por lo que podemos llamarla con `dos()`.
* **`raiz_cuadrada = lambda x: x * x`**: Esta función lambda toma un parámetro (`x`) y devuelve su cuadrado. Igual que con la anterior, la asignamos a `raiz_cuadrada`, que se puede invocar como una función normal.
* **`potencia = lambda x, y: x ** y`**: Esta lambda toma dos parámetros (`x` y `y`) y devuelve el resultado de elevar `x` a la potencia de `y`.

## Uso de las funciones lambda

El verdadero poder de las **funciones lambda** en Python se manifiesta cuando se utilizan para escribir funciones rápidas y anónimas que no necesitan ser definidas explícitamente. Son especialmente útiles cuando quieres evitar la creación de funciones adicionales que solo se usarán una vez.

Imaginemos que necesitamos una función que imprima los resultados de evaluar una segunda función con un conjunto de valores de entrada. Este es un ejemplo clásico donde una función lambda puede ser muy útil.

Aquí está la función `print_function()`, que recibe una lista de argumentos y una función para evaluar cada uno de esos argumentos:

```
def print_function(args, fun):
    for x in args:
        print('f(', x, ')=', fun(x), sep='')
```

Ahora, definimos una función llamada `poly()` que toma un argumento y devuelve el valor de un polinomio:

```
def poly(x):
    return 2 * x**2 - 4 * x + 2
```

Finalmente, llamamos a `print_function()` pasando una lista de valores (de `-2` a `2`) y la función `poly()`:

```
print_function([x for x in range(-2, 3)], poly)
```

Este ejemplo lo podemos simplificar usando una función lambda:

En lugar de definir la función `poly()` por separado, puedes usar una **lambda** directamente al pasar la función a `print_function()`. Esto hace que el código sea más compacto y claro:

```
print_function([x for x in range(-2, 3)], lambda x: 2 * x**2 - 4 * x + 2)
```
