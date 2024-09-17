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

### ¿Cómo tratamos los bits individuales?

Ahora te mostraremos para que puedes usar los operadores de bit a bit. Imagina que eres un desarrollador obligado a escribir una arte importante de un sistema operativo. Se te ha dicho que puedes usar una variable asignada de la siguiente forma:

```
flag_register = 0x1234
```

La variable almacena la información sobre varios aspectos de la configuración del sistema. Cada bit de la variable almacena un valor de **si/no**. También se te ha dicho que solo uno de estos bits es tuyo, el tercero (recuerda que los bits se numeran desde cero y el número de bits cero es el más bajo, mientras que el más alto es el número 31). Los bits restantes no pueden cambiar, porque están destinados a almacenar otros datos. Aquí está tu bit marcado con la letra x:

```
flag_register = 0000000000000000000000000000x000
```

Es posible que tengas que hacer frente a las siguientes tareas:

1. **Comprobar el estado de tu bit**: deseas averiguar el valor de tu bit; comparar la variable completa con cero no hará nada, porque los bits restantes pueden tener valores completamente impredecibles, pero puedes usar la siguiente propiedad de conjunción:

    ```
    x & 1 = x
    x & 0 = 0
    ```

    Si aplicas la operación `&` a la variable `flagRegister` junto con la siguiente secuencia de bits:

    ```
    00000000000000000000000000001000
    ```

    Hemos colocado un bit 1 en la posición de tu bit, como resultado, obtendrás una de las siguientes cadenas de bits:

    * `00000000000000000000000000001000` si tu bit se estableció en 1
    * `00000000000000000000000000000000` si tu bit es 0

    Dicha secuencia de ceros y unos, cuya tarea es tomar el valor o cambiar los bits seleccionados, se denomina **máscara de bits**.

    Construyamos una máscara de bits para detectar el estado de tus bits. Debería apuntar a el tercer bit. Ese bit tiene el peso de 2<pre>3</pre>=8. Se podría crear una máscara adecuada mediante la siguiente asignación:

    ```
    the_mask = 8
    ```

    Podemos tener el siguiente código para comprobar si tu bit es un 1 o un 0:

    ```
    if flag_register & the_mask:
        # Mi bit se estableció en 1.
    else:
        # Mi bit se restableció a 0.
    ```

2. **Reinicia tu bit**: asigna un cero al bit, mientras que todos los otros bits deben permanecer sin cambios; usemos la misma propiedad de la conjunción que antes, pero usemos una máscara ligeramente diferente, exactamente como se muestra a continuación:

    ```
    11111111111111111111111111110111
    ```

    Tenga en cuenta que la máscara se creó como resultado de la negación de todos los bits de la variable `the_mask`. Restablecer el bit es simple (una de las dos siguientes instrucciones):

    ```
    flag_register = flag_register & ~the_mask
    flag_register &= ~the_mask
    ```


3. **Establece tu bit**: asigna un 1 a tu bit, mientras que todos los bits restantes deben permanecer sin cambios; usa la siguiente propiedad de disyunción:

    ```
    x | 1 = 1
    x | 0 = x
    ```

    Ya estás listo para configurar su bit con una de las siguientes instrucciones:

    ```
    flag_register = flag_register | the_mask
    flag_register |= the_mask
    ```

4. **Niega tu bit**: reemplaza un 1 con un 0 y un 0 con un 1. Puedes utilizar una propiedad interesante del operador `xor`:

    ```
    x ^ 1 = ~x
    x ^ 0 = x
    ```

    Niega tu bit con las siguientes instrucciones:

    ```
    flag_register = flag_register ^ the_mask
    flag_register ^= the_mask
    ```

### Desplazamiento izquierdo binario y desplazamiento derecho binario

Python ofrece otra operación relacionada con los bits individuales: **shifting (desplazamiento)**. Esto se aplica solo a los valores de número entero, y no debe usar flotantes como argumentos para ello.

Ya aplicas esta operación muy a menudo y muy inconscientemente. ¿Cómo multiplicas cualquier número por diez? Echa un vistazo:

```
12345 × 10 = 123450
```

Como puede ver, multiplicar por diez es de hecho un desplazamiento de todos los dígitos a la izquierda y llenar el vacío resultante con cero.

¿División entre diez? Echa un vistazo:

```
12340 ÷ 10 = 1234
```

Dividir entre diez no es más que desplazar los dígitos a la derecha.

El ordenador realiza el mismo tipo de operación, pero con una diferencia: como dos es la base para los números binarios (no 10):

* **desplazar un valor un bit a la izquierda** corresponde a **multiplicarlo por dos**. 
* **desplazar un bit a la derecha** es como **dividir entre dos**.

Los operadores de cambio en Python son un par de dígrafos: `<<` y `>>`, sugiriendo claramente en qué dirección actuará el cambio.

```
value << bits
value >> bits
```

* El argumento izquierdo de estos operadores es un valor entero cuyos bits se desplazan. 
* Esto demuestra que esta operación ciertamente no es conmutativa-
* La prioridad de estos operadores es muy alta. 

Veamos un ejemplo:

```
var = 17
var_right = var >> 1
var_left = var << 2
print(var, var_left, var_right)
```

La invocación final de `print()` produce el siguiente resultado: `17 68 8`.
* `17 >> 1 → 17 // 2` (17 dividido entre 2 a la potencia de 1 = 8): desplazarse hacia la derecha en un bit equivale a la división entera entre dos.
* `17 << 2 → 17 * 4` (17 multiplicado por 2 a la potencia de 2 = 68): desplazarse hacia la izquierda dos bits es lo mismo que multiplicar números enteros por cuatro.


Veamos la tabla de prioridades actualizada , que contiene todos los operadores presentados hasta ahora:


1. `+`,`-` (unarios)
2. `**`
3. `*`,`/`,`//`,`%`
4. `+`,`-` (binarios)
5. `<<`, `>>`
6. `<`, `<=`, `>`, `>=` 	
7. `==`, `!=`
8. `&` 	
9. `|` 	
10. `=`, `+=`, `-=`, `*=`, `/=`, `%=`, `&=`, `^=`, `|=`, `>>=`, `<<=`

