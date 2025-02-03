# El módulo math

El módulo `math` en Python ofrece una serie de funciones matemáticas. Algunas de las más comunes incluyen:

## Trigonometría básica:

* Trigonometría básica:
    * `sin(x)`: devuelve el seno de `x` (en radianes).
    * `cos(x)`: devuelve el coseno de `x`.
    * `tan(x)`: devuelve la tangente de `x`.
* También tiene las funciones inversas:
    * `asin(x)`: devuelve el arcoseno de `x`.
    * `acos(x)`: devuelve el arcocoseno de `x`.
    * `atan(x)`: devuelve el arcotangente de `x`.
* Conversión de ángulos:
    * `pi`: constante que aproxima π.
    * `radians(x)`: convierte `x` de grados a radianes.
    * `degrees(x)`: convierte `x` de radianes a grados.

El siguiente código demuestra el uso de algunas de estas funciones: trabaja con conversiones de ángulos entre grados y radianes, y muestra relaciones trigonométricas básicas como la de seno, coseno y tangente.

```
from math import pi, radians, degrees, sin, cos, tan, asin

ad = 90
ar = radians(ad)  # Convierte 90 grados a radianes
ad = degrees(ar)  # Convierte nuevamente a grados

print(ad == 90.)  # Verifica si el valor en grados sigue siendo 90
print(ar == pi / 2.)  # Verifica si el valor en radianes es pi/2
print(sin(ar) / cos(ar) == tan(ar))  # Verifica si la tangente es sin/cos
print(asin(sin(ar)) == ar)  # Verifica si el arcoseno de sin(pi/2) devuelve pi/2
```

## Funciones hiperbólicas

* Además de las funciones circulares, el módulo también incluye análogos hiperbólicos:
    * `sinh(x)`: seno hiperbólico.
    * `cosh(x)`: coseno hiperbólico.
    * `tanh(x)`: tangente hiperbólica.
* Funciones inversas: `asinh(x)`, `acosh(x)`, `atanh(x)`.

## Exponenciación

* `e`: una constante con un valor que es una aproximación del número de Euler (e).
* `exp(x)`: devuelve el valor de `e`<sup>x</sup>.
* `log(x)`: el logaritmo natural o neperiano de `x`.
* `log(x, b)`: el logaritmo de `x` con base `b`.
* `log10(x)`: el logaritmo decimal de `x` (más preciso que `log(x, 10)`).
* `log2(x)`: el logaritmo binario de `x` (más preciso que `log(x, 2)`).

Además podemos usar la siguiente función, sin necesiada de importarla:

* `pow(x, y)`: encuentra el valor de `x`<sup>y</sup>.

Ejemplo:
```
from math import e, exp, log

print(pow(e, 1) == exp(log(e)))
print(pow(2, 2) == exp(2 * log(2)))
print(log(e, e) == exp(0))
```

## Funciones de propósito general

El último grupo consta de algunas funciones de propósito general como:

* `sqrt(x)`: devuelve la raíz cuadrada de `x`.
* `ceil(x)`: devuelve el entero más pequeño mayor o igual que `x`.
* `floor(x)`: el entero más grande menor o igual que `x`.
* `trunc(x)`: el valor de `x` truncado a un entero (ten cuidado, no es equivalente a `ceil` o `floor`).
* `factorial(x)`: devuelve `x!` (`x` tiene que ser un valor entero y no negativo).
* `hypot(x, y)`: devuelve la longitud de la hipotenusa de un triángulo rectángulo con las longitudes de los catetos iguales a `x` y `y` (lo mismo que `sqrt(pow(x, 2) + pow(y, 2)`) pero más preciso.

Ejemplo:
```
from math import ceil, floor, trunc

x = 1.4
y = 2.6

print(floor(x), floor(y))
print(floor(-x), floor(-y))
print(ceil(x), ceil(y))
print(ceil(-x), ceil(-y))
print(trunc(x), trunc(y))
print(trunc(-x), trunc(-y))
```