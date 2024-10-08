# Más argumentos de la función print()

## Usando múltiples argumentos

Hasta ahora hemos probado el comportamiento de la función `print()` sin argumentos y con un argumento. Vamos a comprobar que podemos enviar más argumentos a  la función `print()`.

Veamos el siguiente ejemplo:

```
print("La Araña Witsi Witsi" , "subió" , "a su telaraña.")
```

Hay una invocación de la función `print()`, pero contiene tres argumentos. Todos ellos son cadenas.

Los argumentos están **separados por comas**. Los hemos rodeado de espacios para hacerlos más visibles, pero no es realmente necesario, y no lo haremos más. Los distintos argumentos que mandamos a una función hay que separarlos por comas.

Al ejecutar el código aparecerá el siguiente texto:

```
La Araña Witsi Witsi subió a su telaraña.
```

Es decir, las cadenas de caracteres que indicamos en cada argumentos se escriben en pantalla separadas por un espacio.

## Argumentos posicionales

Escribe el siguiente programa:

```
print("Mi nombre es", "Python.")
print("Monty Python.")
```

La forma en que estamos pasando los argumentos a la función `print()` es la más común en Python, y se llama la **forma posicional**. Este nombre proviene del hecho de que el significado del argumento está dictado por su posición (por ejemplo, el segundo argumento se mostrará después del primero, no al revés).

Ejecuta el código y comprueba si el resultado coincide con tus predicciones.

## Argumentos por palabra clave

Python ofrece otro mecanismo para el paso de argumentos: **argumentos por palabras clave**. El nombre proviene del hecho de que el significado de estos argumentos se toma no de su ubicación (posición) sino de la palabra especial (palabra clave) utilizada para identificarlos.

La función `print()` tiene dos argumentos por palabra clave que puedes usar para tus propósitos. 

### Argumento end

El primero se llama `end`. Para ver cómo funciona escribe este código:

```
print("Mi nombre es", "Python.", end=" ")
print("Monty Python.")
```

Para usarlo, es necesario conocer algunas reglas:

* **Un argumento por palabra clave consta de tres elementos**: una palabra clave se identifica el argumento (`end` aquí); un signo de igual (=); y un valor asignado a ese argumento;
* Cualquier argumento por palabra clave **debe colocarse después del último argumento posicional** (esto es muy importante).

En nuestro ejemplo, hemos utilizado el argumento por palabra clave `end`, y lo hemos configurado como cadena que contiene un espacio. Al ejecutar el programa se muestra el siguiente texto:

```
Mi nombre es Python. Monty Python.
```

Como puedes ver, el argumento por palabra clave `end` determina los caracteres que la función `print()` envía a la salida una vez que llega al final de sus argumentos posicionales. El comportamiento predeterminado refleja la situación en la que el argumento por palabra clave `end` se usa implícitamente de la siguiente manera: `end="\n"`.

### Argumento sep

Dijimos anteriormente que la función `print()` separa sus argumentos de salida con espacios. Este comportamiento también se puede cambiar. El argumento por palabra clave que puede hacer esto se denomina `sep` (como en separador).

Veamos el siguiente código:

```
print("Mi", "nombre", "es", "Monty", "Python.", sep="-")
```

La ejecución producirá el siguiente texto:

```
Mi-nombre-es-Monty-Python.
```

La función `print()` ahora usa un guión, en lugar de un espacio, para separar los argumentos de salida. El valor del argumento `sep` también puede ser una cadena vacía. 

Ambos argumentos por palabra clave **pueden mezclarse en una invocación**, Veamos un ejemplo:

```
print("Mi", "nombre", "es", sep="_", end="*")
print("Monty", "Python.", sep="*", end="*\n")
```

El ejemplo no tiene mucho sentido, pero presenta de forma visible las interacciones entre `end` y `sep`. 

## Cuestionario

1. ¿Cuál es la salida del siguiente programa?

    ```
    print("Mi\nnombre\nes\nBond.", end=" ")
    print("James Bond.") 
    ```

2. ¿Cuál es la salida del siguiente programa?

    ```
    print(sep="&", "fish", "chips") 
    ```

3. ¿Cuál de las siguientes `print()` invocaciones de función generarán un SyntaxError?

    ```
    print('Greg\'s book.')
    print("'Greg's book.'")
    print('"Greg\'s book."')
    print("Greg\'s book.")
    print('"Greg's book."')
    ```


## Solución cuestionario

1. Pregunta 1:

    ```
    Mi
    nombre
    es
    Bond. James Bond.
    ```
2. Pregunta 2:

    ```
      File "main.py", line 1
        print(sep="&", "fish", "chips")
                      ^
    SyntaxError: positional argument follows keyword argument
    ```

    Recuerda: Los argumentos de palabras clave deben pasarse después de cualquier argumento posicional requerido.

3. Pregunta 3:

    La línea 5 generará un `SyntaxError`, porque el símbolo `'` en la cadena `Greg's book.` requiere un carácter de escape.
