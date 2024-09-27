# Operadores de cadena

## Introducción a los operadores de cadenas

* Los operadores aritméticos `+` y `*`, nos permiten sumar y multiplicar cuando trabajamos con números.
* A continuación veremos, que esos mismos signos: `+` y `*` nos permiten realizar operaciones sobre cadenas de textos.

## Concatenación

El signo de `+`, al ser aplicado a dos cadenas, se convierte en un **operador de concatenación**:

```
string + string
```

Simplemente **concatena** (junta) dos cadenas en una. Por supuesto, puede ser utilizado más de una vez en una misma expresión, e irá uniendo las cadenas indicadas de izquierda a derecha.

En contraste con el operador aritmético, **el operador de concatenación no es conmutativo**, por ejemplo, `"ab" + "ba"` no es lo mismo que `"ba" + "ab"`.

No olvides, si se desea que el signo `+` sea un concatenador, no un sumador, solo se debe asegurar que ambos argumentos sean cadenas.

Veamos un ejemplo. Este es un programa sencillo que muestra como funciona el signo `+` como concatenador:

```
fnam = input("¿Me puedes dar tu nombre por favor? ")
lnam = input("¿Me puedes dar tu apellido por favor? ")
print("Gracias.")
print("\nTu nombre es " + fnam + " " + lnam + ".")
```

Nota: El utilizar `+` para concatenar cadenas te permite construir la salida de una manera más precisa, en comparación de utilizar únicamente la función `print()`, aún cuando se enriquezca con los argumentos `end=` y `sep=`.

## Replicación

El signo de `*` (asterisco), cuando es aplicado a una cadena y a un número (o a un número y cadena) se convierte en un operador de replicación.

```
string * number
number * string
```

Replica la cadena el numero de veces indicado por el número.

Por ejemplo:

* `"James" * 3` produce `"JamesJamesJames"`
* `3 * "an"` produce `"ananan"`
* `5 * "2"` (o `"2" * 5`) produce `"22222"` (no 10) 


Hay que tener en cuenta, que **un número menor o igual que cero produce una cadena vacía**.

Este sencillo programa "dibuja" un rectángulo, haciendo uso los operadores `+` y `*`:

```
print("+" + 10 * "-" + "+")
print(("|" + " " * 10 + "|\n") * 5, end="")
print("+" + 10 * "-" + "+")
```

Nota como se ha utilizado el paréntesis en la segunda línea de código. ¡Intenta practicar para crear otras figuras o tus propias obras de arte!.

## Conversión de tipos de datos: str()

A estas alturas ya sabes como emplear las funciones `int()` y `float()` para convertir una cadena a un número.

Este tipo de conversión no es en un solo sentido. También se puede convertir un numero a una cadena, con la función `str()`.

```
str(número)
```

Podemos volver al ejemplo del cálculo de la hipotenusa en el triángulo rectángulo. Veamos una nueva versión:

```
leg_a = float(input("Inserta la longitud del primer cateto: "))
leg_b = float(input("Inserta la longitud del segundo cateto: "))
print("La longitud de la hipotenusa es " + str((leg_a**2 + leg_b**2) ** .5))
```

Se ha modificado un poco para mostrar cómo es que la función `str()` trabaja. Gracias a esto y al uso del operador de concatenación, podemos pasar el resultado entero a la función `print()` como una sola cadena, sin utilizar las comas.

## Cuestionario

1. ¿Cuál es la salida del siguiente código?

```
x = int(input("Ingresa un número: ")) # El usuario ingresa un 2 
print(x * "5")
```

2. ¿Cuál es la salida esperada del siguiente código?

```
x = input("Ingresa un número: ") # El usuario ingresa un 2 
print(type(x))
```

## Solución cuestionario

1. Pregunta 1:

`55`

2. Pregunta 2:

`<class 'str'>`
