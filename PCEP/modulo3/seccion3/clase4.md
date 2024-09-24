# Resumen y cuestionario

## ¿Cómo tratamos los bits individuales?

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

## Desplazamiento izquierdo binario y desplazamiento derecho binario

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

