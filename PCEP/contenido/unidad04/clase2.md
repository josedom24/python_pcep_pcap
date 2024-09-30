# Operadores básicos

## Suma

El símbolo del operador de **suma** es el `+` (signo de más), y funciona igual que en las matemáticas.

```
print(-4 + 4)
print(-4. + 8)
```

## El operador de resta, operadores unarios y binarios

El símbolo del operador de **resta** es obviamente `-` (el signo de menos), sin embargo debes notar que este operador tiene otra función: **puede cambiar el signo de un número**.

Esta es una gran oportunidad para mencionar una distinción muy importante entre **operadores unarios y binarios**.

En aplicaciones de resta, el operador de resta espera dos argumentos: el izquierdo (un minuendo en términos aritméticos) y el derecho (un sustraendo).

Por esta razón, el operador de resta es considerado uno de los operadores binarios, así como los demás operadores de suma, multiplicación y división.

Pero el operador negativo puede ser utilizado de una forma diferente, observa la ultima línea de código del siguiente fragmento:

```
print(-4 - 4)
print(4. - 8)
print(-1.1)
```

Por cierto: también hay un **operador `+` unario**. Se puede utilizar de la siguiente manera:

```
print(+2)
```

El operador conserva el signo de su único argumento, el de la derecha. Aunque dicha construcción es sintácticamente correcta, utilizarla no tiene mucho sentido, y sería difícil encontrar una buena razón para hacerlo.

## Multiplicación

Un símbolo de `*` (asterisco) es un operador de **multiplicación**.

```
print(2 * 3)
print(2 * 3.)
print(2. * 3)
print(2. * 3.)
```

## División

Un símbolo de `/` (diagonal) es un operador de **división**.

El valor después de la diagonal es el dividendo, el valor antes de la diagonal es el divisor.



```
print(6 / 3)
print(6 / 3.)
print(6. / 3)
print(6. / 3.)
```

Deberías de poder observar que hay una excepción a la regla.

El resultado producido por el operador de división **siempre es flotante**, sin importar si a primera vista el resultado es flotante: `1 / 2`, o si parece ser completamente entero: `2 / 1`.

**La división entre cero no funciona**, produce un error. Esto es aplicable a este operador y a los dos próximos.

## División entera

Un símbolo de `//` (doble diagonal) es un operador de **división entera**. En este caso **el resultado carece de la parte fraccionaria**:
* Está ausente cuando hago una división entera entre enteros. 
* O siempre es igual a cero para divisiones enteras cuando uno de los operandos es flotante. 
* Esto significa que los resultados siempre son redondeados.

Ejemplos:

```
print(6 // 3)
print(6 // 3.)
print(6. // 3)
print(6. // 3.)
```

Veamos otro ejemplo:

```
print(6 / 4)
print(6. / 4)

print(6 // 4)
print(6. // 4)
```

* La división normal, el resultado es `1.5` en los dos casos.
* La división entera devuelve `1` y `1.0` por lo que hemos dicho anteriormente.

El **resultado de la división entera siempre se redondea al valor entero inferior mas cercano del resultado de la división no redondeada**. Esto es muy importante: **el redondeo siempre va hacia abajo.**

Veamos otr ejemplo:

```
print(-6 / 4)
print(6. / -4)

print(-6 // 4)
print(6. // -4)
```

* La división normal, el resultado es `-1.5` en los dos casos.
* La división entera devuelve `-2` y `-2.0`. El redondeo se hace hacia el valor inferior entero, dicho valor es -2.

La división entera también se le suele llamar en inglés **floor division**.

## Residuo (Módulo)

El siguiente operador es uno muy peculiar, porque no tiene un equivalente dentro de los operadores aritméticos tradicionales.

Su representación gráfica en Python es el símbolo de `%` (porcentaje), lo cual puede ser un poco confuso.

El resultado de la operación es el residuo (el resto) que queda de la división entera. En otras palabras, es el valor que sobra después de dividir un valor entre otro para producir un resultado entero.


Veamos un ejemplo:

```
print(14 % 4)
```

Como puedes observar, el resultado es **dos**. Esta es la razón:

* `14 // 4` da como resultado un 3: esta es la parte entera, es decir el cociente.
* `3 * 4` da como resultado 12: como resultado de la multiplicación entre el cociente y el divisor.
* `14 - 12` da como resultado 2: este es el residuo o resto.


El siguiente ejemplo es un poco más complicado:

```
print(12 % 4.5)
```

¿Cuál es el resultado?: `3.0`, no `3` (la regla aun funciona: `12 // 4.5` da `2.0`; `2.0 * 4.5` da `9.0`; `12 - 9.0` da `3.0`)

## Exponenciación

Un signo de `**` (doble asterisco) es un operador de **exponenciación (potencia)**. El argumento a la izquierda es la base, el de la derecha, el exponente.

Las matemáticas clásicas prefieren una notación con superíndices, como el siguiente: 2<sup>3</sup>. Escribir superíndices en los editores de texto es complicado por lo que sintaxis es `2 ** 3`. Por ejemplo:

```
print(2 ** 3)
print(2 ** 3.)
print(2. ** 3)
print(2. ** 3.)
```

* Cuando la base y el exponente son enteros, el resultado es entero también.
* Cuando al menos, la base o el exponente es flotante, el resultado también es flotante.


    