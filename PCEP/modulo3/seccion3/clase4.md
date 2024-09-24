# Resumen y cuestionario

## Resumen

1. Python es compatible con los siguientes operadores lógicos:

    * `and`: si ambos operandos son verdaderos, la condición es verdadera, por ejemplo, `True and True = True`.
    * `or`: si alguno de los operandos es verdadero, la condición es verdadera, por ejemplo, `True or False = True`.
    * `not`: devuelve `False` si el resultado es verdadero y devuelve `True` si es falso, por ejemplo, `not True = False`.

2. Puedes utilizar operadores bit a bit para manipular bits de datos individuales. Si tenemos las siguientes dos variables:

    * `x = 15`: en binario `0000 1111`.
    * `y = 16`: en binario `0001 0000`.

    Los operadores bit a bit son los siguientes:

    * `&` hace un **bit and bit**, por ejemplo, `x & y = 0` (`0000 0000` en binario).
    * `|` hace un **bit or bit**, por ejemplo, `x | y = 31` (`0001 1111` en binario).
    * `~` hace un **not bit**, por ejemplo,  `~x = 240`, (`1111 0000` en binario).
    * `^` hace un **bit xor bit**, por ejemplo, `x ^ y = 31`, (`0001 1111` en binario).
    * `>>` hace un **desplazamiento bit a bit a la derecha**, por ejemplo, `y >> 1 = 8` (`0000 1000` en binario).
    * `<<` hace un **desplazamiento bit a bit a la izquierda**, por ejemplo, `y << 3 = -16` (`1000 0000` en binario). El número negativo -16 se representa como complemento a dos, puedes leer más acerca de la operación [Complemento a dos](https://es.wikipedia.org/wiki/Complemento_a_dos).

## Cuestionario

1. ¿Cuál es el resultado del siguiente fragmento de código?

```
x = 1
y = 0
 
z = ((x == y) and (x == y)) or not(x == y)
print(not(z)) 
```

2. ¿Cuál es el resultado del siguiente fragmento de código?

``` 
x = 4
y = 1
 
a = x & y
b = x | y
c = ~x  # ¡difícil!
d = x ^ 5
e = x >> 2
f = x << 2
 
print(a, b, c, d, e, f) 
```

## Solución cuestionario

1. Pregunta 1:

```
False
```

2. Pregunta 2:

```
0 5 -5 1 1 16
```