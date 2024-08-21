# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 3: Operadores, herramientas de manipulación de datos 
## Clase: Operadores básicos

### Exponenciación

Un signo de `**` (doble asterisco) es un operador de **exponenciación (potencia)**. El argumento a la izquierda es la base, el de la derecha, el exponente.

Las matemáticas clásicas prefieren una notación con superíndices, como el siguiente: 2<sup>3</sup>. Los editores de texto puros no aceptan esa notación, por lo tanto Python utiliza `**` en lugar de la notación matemática, por ejemplo, `2 ** 3`. Por ejemplo:

```
print(2 ** 3)
print(2 ** 3.)
print(2. ** 3)
print(2. ** 3.)
```

Nota: En los ejemplos, los dobles asteriscos están rodeados de espacios, no es obligatorio hacerlo pero hace que el código sea mas legible.

Los ejemplos muestran una característica importante de los operadores numéricos de Python.

Ejecuta el código y observa cuidadosamente los resultados que arroja. ¿Puedes observar algo?

Recuerda: Es posible formular las siguientes reglas con base en los resultados:

* Cuando la base y el exponente son enteros, el resultado es entero también.
* Cuando al menos, la base o el exponente es flotante, el resultado también es flotante.

### Multiplicación

Un símbolo de `*` (asterisco) es un operador de **multiplicación**.

Ejecuta el código y revisa si la regla de entero frente a flotante aún funciona.

```
print(2 * 3)
print(2 * 3.)
print(2. * 3)
print(2. * 3.)
```

### División

Un símbolo de `/` (diagonal) es un operador de **división**.

El valor después de la diagonal es el dividendo, el valor antes de la diagonal es el divisor.

Ejecuta el código y analiza los resultados.

```
print(6 / 3)
print(6 / 3.)
print(6. / 3)
print(6. / 3.)
```

Deberías de poder observar que hay una excepción a la regla.

El resultado producido por el operador de división siempre es flotante, sin importar si a primera vista el resultado es flotante: `1 / 2`, o si parece ser completamente entero: `2 / 1`.

¿Esto ocasiona un problema? Sí, en ocasiones se podrá necesitar que el resultado de una división sea entero, no flotante.

### División entera

Un símbolo de `//` (doble diagonal) es un operador de **división entera**. Difiere del operador estándar `/` en dos detalles:

* El resultado carece de la parte fraccionaria, está ausente (para los enteros), o siempre es igual a cero (para los flotantes); esto significa que los resultados siempre son redondeados.
* Se ajusta a la regla entero frente a flotante.

Ejecuta el ejemplo debajo y observa los resultados:

```
print(6 // 3)
print(6 // 3.)
print(6. // 3)
print(6. // 3.)
```

Como se puede observar, una división de entero entre entero da un resultado entero. Todos los demás casos producen flotantes.

Hagamos algunas pruebas mas avanzadas. Observa el siguiente fragmento de código:

```
print(6 // 4)
print(6. // 4)
```

Imagina que se utilizó `/` en lugar de `//`; ¿Podrías predecir los resultados? Si, sería 1.5 en ambos casos. Eso está claro.

Pero, ¿Qué resultado se debería esperar con una división `//`? Ejecuta el código y observa por ti mismo.

Lo que se obtiene son dos **unos**, uno entero y uno flotante.

El **resultado de la división entera siempre se redondea al valor entero inferior mas cercano del resultado de la división no redondeada**. Esto es muy importante: **el redondeo siempre va hacia abajo.**

Observa el código e intenta predecir el resultado nuevamente:

```
print(-6 // 4)
print(6. // -4)
```

Nota: Algunos de los valores son negativos. Esto obviamente afectara el resultado. ¿Pero cómo?

El resultado es un par de **dos** negativos. El resultado real (no redondeado) es -1.5 en ambo casos. Sin embargo, los resultados se redondean. El redondeo se hace hacia el valor inferior entero, dicho valor es -2, por lo tanto los resultados son: -2 y -2.0.

NOTA: La division entera también se le suele llamar en inglés **floor division**.

### Residuo (Módulo)

El siguiente operador es uno muy peculiar, porque no tiene un equivalente dentro de los operadores aritméticos tradicionales.

Su representación gráfica en Python es el símbolo de `%` (porcentaje), lo cual puede ser un poco confuso.

El resultado de la operación es el residuo (el resto) que queda de la división entera. En otras palabras, es el valor que sobra después de dividir un valor entre otro para producir un resultado entero.


Observa el fragmento de código e intenta predecir el resultado y después ejecútalo:

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

¿Cuál es el resultado?: `3.0` - no `3` (la regla aun funciona: `12 // 4.5` da `2.0`; `2.0 * 4.5` da `9.0`; `12 - 9.0` da `3.0`)

### Como no dividir

Como probablemente sabes, **la división entre cero no funciona**. Nos da un error.

No intentes:

* Dividir entre cero.
* Realizar una división entera entre cero.
* Encontrar el residuo de una división entre cero.

### Suma

El símbolo del operador de **suma** es el `+` (signo de más), el cual esta completamente alineado a los estándares matemáticos.

De nuevo, observa el siguiente fragmento de código:

```
print(-4 + 4)
print(-4. + 8)
```

El resultado no debe de sorprenderte. Ejecuta el código y revisa los resultados.

### El operador de resta, operadores unarios y binarios

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




    