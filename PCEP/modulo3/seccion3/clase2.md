# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 3: Operaciones lógicas y de bits en Python 
## Clase: Operadores bit a bit

### Operadores bit a bit

Sin embargo, hay cuatro operadores que le permiten manipular bits de datos individuales. Se denominan **operadores bit a bit**.

Cubren todas las operaciones que mencionamos anteriormente en el contexto lógico, y un operador adicional. Este es el operador **xor** (significa o exclusivo), y se denota como `^` (signo de intercalación).

Aquí están todos ellos:

* `&` (ampersand): conjunción a nivel de bits.
* `|` (barra vertical): disyunción a nivel de bits.
* `~` (tilde): negación a nivel de bits.
* `^` (signo de intercalación): o exclusivo a nivel de bits (xor).


Operaciones bit a bit (`&`, `|`, y `^`)


|Argumento A |Argumento B |`A & B` |`A \| B` |`A ^ B` |
-------------|------------|--------|--------|--------|
|0           |0           |	0      |0       | 0      |
|0           |1           |	0      |1       | 1      |
|1           |0           |	0      |1       | 1      |
|1           |1           |	1      |1       | 0      |


Operaciones bit a bit (`~`) 

|Argumento |~ Argumento|
-----------|-----------|
|0 |	1 |
|1 |	0 |

Hagámoslo más fácil:

* `&`: requieres exactamente dos 1s para proporcionar 1 como resultado.
* `|`: requiere al menos un 1 para proporcionar 1 como resultado.
* `^`: requiere exactamente un 1 para proporcionar 1 como resultado.

Agreguemos un comentario importante: los argumentos de estos operadores deben ser enteros. No debemos usar flotantes aquí.

La diferencia en el funcionamiento de los operadores lógicos y de bits es importante: los operadores lógicos no operan directamente con los bits de sus argumentos. Solo les interesa el valor entero final.

Los operadores bit a bit son más estrictos: tratan con cada bit por separado. Si asumimos que la variable entera ocupa 64 bits (lo que es común en los sistemas informáticos modernos), puede imaginar la operación a nivel de bits como una evaluación de 64 veces del operador lógico para cada par de bits de los argumentos. Su analogía es obviamente imperfecta, ya que en el mundo real todas estas 64 operaciones se realizan al mismo tiempo (simultáneamente).


### Operaciones lógicas frente a operaciones de bit: continuación

Ahora te mostraremos un ejemplo de la diferencia entre las operaciones lógicas y de bit. Supongamos que se han realizado las siguientes asignaciones:

```
i = 15
j = 22
```

Si asumimos que los enteros se almacenan con 32 bits, los valores binarios de las dos variables será la siguiente:

```
i: 00000000000000000000000000001111
j: 00000000000000000000000000010110
```

Se ejecuta la asignación:

```
log = i and j
```

* Estamos realizando una una conjunción lógica.  
* Ambas variables `i` y `j` no son ceros, por lo que se considerará que representan a `True`. 
* Al consultar la tabla de verdad para el operador `and`, podemos ver que el resultado será `True`. * * No se realizan otras operaciones.

Por lo tanto el resultado será que la variable `log` es igual a `True`.


Ahora estudiemos la operación a nivel de bits:

```
bit = i & j
```

El operador `&` operará con cada par de bits correspondientes por separado, produciendo los valores de los bits relevantes del resultado. Por lo tanto, el resultado será el siguiente:

```
i	00000000000000000000000000001111
j	00000000000000000000000000010110
bit = i & j	00000000000000000000000000000110
```

Estos bits corresponden al valor entero de seis.


Veamos ahora los operadores de negación. Primero el lógico:

```
logneg = not i
```

La variable `logneg` se establecerá en `False`: no es necesario hacer nada más.

La negación a nivel de bits es así:

```
bitneg = ~i
```

Puede ser un poco sorprendente: el valor de la variable `bitneg` es -16. Esto puede parecer extraño, pero no lo es en absoluto. Si deseas obtener más información, debes consultar el sistema de números binarios y las reglas que rigen los números de complemento de dos.

```
i	00000000000000000000000000001111
bitneg = ~i	11111111111111111111111111110000
```

Cada uno de estos operadores de dos argumentos se puede utilizar en forma abreviada. Estos son los ejemplos de sus notaciones equivalentes:

```
x = x & y	x &= y
x = x | y	x |= y
x = x ^ y	x ^= y
```
