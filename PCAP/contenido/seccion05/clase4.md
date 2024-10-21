# Las cadenas son inmutables

En Python, las **cadenas de texto** son inmutables. Esta es una característica clave que tiene implicaciones importantes en la forma en que las cadenas se manipulan en comparación con otros tipos de datos como las listas.

## ¿Qué significa la inmutabilidad?

La **inmutabilidad** significa que, una vez creada, una cadena no puede ser modificada. Cualquier operación que parezca modificar una cadena en realidad genera una nueva. Esto contrasta con las **listas**, que son mutables y pueden ser alteradas en el lugar, es decir, puedes agregar, eliminar o modificar elementos de una lista sin crear una nueva.

## Diferencias clave entre cadenas y listas

1. **No puedes eliminar elementos individuales de una cadena**. A diferencia de las listas, no es posible usar la instrucción `del` para eliminar un carácter específico de una cadena. Por ejemplo, el siguiente código generará un error:

    ```
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    del alphabet[0]  # Error: las cadenas son inmutables
    ```

   Lo único que puedes hacer con `del` y una cadena es eliminar la cadena completa, no partes de ella.

2. **No puedes modificar o agregar elementos a una cadena**. A diferencia de las listas, que tienen métodos como `append()` o `insert()`, las cadenas no cuentan con estos métodos porque no se pueden modificar. Cualquier intento de usarlos resultará en un error:

    ```
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    alphabet.append("A")  # Error: las cadenas no tienen el método append()
    
    alphabet.insert(0, "A")  # Error: las cadenas no tienen el método insert()
    ```

3. Cómo hemos comentado si **podemos crear nuevas cadenas a partir de otras**.

    ```
    alphabet = "bcdefghijklmnopqrstuvwxy"

    alphabet = "a" + alphabet
    alphabet = alphabet + "z"

    print(alphabet)
    ```

4. Por lo tanto, los métodos que vamos a estudiar **no cambian la cadenas, devuelven nuevas cadenas modificadas**.

    ```
    cadena = "python"
    cadena2 = cadena.upprt()
    cadena = cadena.upprt()
    ```
    