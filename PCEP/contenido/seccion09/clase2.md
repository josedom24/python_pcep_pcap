# Operadores a nivel de bits

Sin embargo, hay cuatro operadores que te permiten manipular bits de de forma individual. Se denominan **operadores a nivel de bits**.

Cubren todas las operaciones que mencionamos anteriormente en el contexto lógico, y un operador adicional. Este es el operador **xor** (significa o exclusivo), y se denota como `^` (signo de intercalación).

Aquí están todos ellos:

* `&` (ampersand): conjunción a nivel de bits.
* `|` (barra vertical): disyunción a nivel de bits.
* `~` (tilde): negación a nivel de bits.
* `^` (signo de intercalación): o exclusivo a nivel de bits (xor).


Operaciones a nivel de bits (`&`, `|`, y `^`)


|Argumento A |Argumento B |`A & B` |`A \| B` |`A ^ B` |
-------------|------------|--------|--------|--------|
|0           |0           |	0      |0       | 0      |
|0           |1           |	0      |1       | 1      |
|1           |0           |	0      |1       | 1      |
|1           |1           |	1      |1       | 0      |


Operaciones a nivel de bits (`~`) 

|Argumento |~ Argumento|
-----------|-----------|
|0 |	1 |
|1 |	0 |

Hagámoslo más fácil:

* `&`: requieres exactamente dos unos para proporcionar 1 como resultado.
* `|`: requiere al menos un 1 para proporcionar 1 como resultado.
* `^`: requiere exactamente un 1 para proporcionar 1 como resultado.

Agreguemos un comentario importante: los argumentos de estos operadores deben ser enteros. No debemos usar flotantes aquí.

La diferencia en el funcionamiento de los operadores lógicos y de bits es importante: los operadores lógicos no operan directamente con los bits de sus argumentos. Solo les interesa el valor entero final.

Los operadores a nivel de bits son más estrictos: tratan con cada bit por separado. Si asumimos que la variable entera ocupa 64 bits (lo que es común en los sistemas informáticos modernos), puede imaginar la operación a nivel de bits como una evaluación de 64 veces del operador lógico para cada par de bits de los argumentos. Su analogía es obviamente imperfecta, ya que en el mundo real todas estas 64 operaciones se realizan al mismo tiempo (simultáneamente).


## Diferencias entre operadores lógicos y operadores a nivel de bits

Ahora te mostraremos un ejemplo de la diferencia entre las operaciones lógicas y de bit. Supongamos que se han realizado las siguientes asignaciones:

```
valor1 = 15
valor2 = 22
```

Si asumimos que los enteros se almacenan con 32 bits, los valores binarios de las dos variables será la siguiente:

```
valor1: 00000000000000000000000000001111
valor2: 00000000000000000000000000010110
```

Vamos a usar un operador de lógico entre los dos valores:

```
valor1 and valor2
```

* Estamos realizando una una conjunción lógica.  
* Ambas variables `valor1` y `valor2` no son ceros, por lo que se considerará que representan a `True`. 
* Al consultar la tabla de verdad para el operador `and`, podemos ver que el resultado será `True`. 

Ahora estudiemos la operación a nivel de bits:

```
valor1 & valor2
```

El operador `&` operará con cada par de bits correspondientes por separado, produciendo los valores de los bits relevantes del resultado. Por lo tanto, el resultado será el siguiente:

```
valor1:          00000000000000000000000000001111
valor2:	         00000000000000000000000000010110
valor1 & valor2: 00000000000000000000000000000110
```

En Python:

```
print(bin(valor1))
print(bin(valor2))
print(bin(valor1 & valor2))
print(valor1 & valor2)
```

## Diferencias entre operadores lógicos y operadores a nivel de bits: Operador de negación

Veamos ahora los operadores de negación. Primero el lógico:

```
valor1 = 15
not valor1
```

* `valor1` es considerado `True` (número distintos de 0).
* El operador `not` nos devuelve el valor opuesto, por lo tanto `not valor1` se considera `False`.

La negación a nivel de bits es así:

```
valor1 = 15
~ valor1
```

Puede ser un poco sorprendente: el valor de `~valor1` es -16. Esto puede parecer extraño, pero no lo es en absoluto. Si deseas obtener más información, debes consultar cómo se representan los números binarios negativos usando el modo de resprentación complemento de dos.

```
valor1:	  00000000000000000000000000001111
~ valor1: 11111111111111111111111111110000
```

Cada uno de estos operadores de dos argumentos se puede utilizar en forma abreviada. Estos son los ejemplos de sus notaciones equivalentes:

```
x = x & y	x &= y
x = x | y	x |= y
x = x ^ y	x ^= y
```
