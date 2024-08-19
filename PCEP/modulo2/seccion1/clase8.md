# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 1: El Programa "¡Hola, Mundo!"
## Clase: Resumen y cuestionario de la sección

### Resumen de sección

1. La función `print()` es una función integrada: imprime/envía un mensaje específico a la pantalla/ventana de consola.

2. Las funciones integradas, al contrario de las funciones definidas por el usuario, están siempre disponibles y no tienen que ser importadas. Python 3.7.1 viene con 69 funciones incorporadas. Puedes encontrar su lista completa en orden alfabético en [Python Standard Library](https://docs.python.org/3.7/library/functions.html).

3. Para llamar a una función (invocación de función), debe utilizarse el nombre de la función seguido de un paréntesis. Puedes pasar argumentos a una función colocándolos dentro de los paréntesis. Se deben separar los argumentos con una coma, por ejemplo, `print("¡Hola,", "Mundo!")`. Una función `print()` "vacía" imprime una línea vacía a la pantalla.

4. Las cadenas de Python están delimitadas por comillas, por ejemplo, "Soy una cadena" (comillas dobles), o 'Yo soy una cadena, también' (comillas simples).

5. Los programas de ordenador son colecciones de instrucciones. Una instrucción es un comando para realizar una tarea específica cuando se ejecuta, por ejemplo, para imprimir un determinado mensaje en la pantalla.

6. En las cadenas de Python la barra diagonal inversa (`\`) es un carácter especial que anuncia que el siguiente carácter tiene un significado diferente, por ejemplo, `\n` (el carácter de nueva línea) comienza una nueva línea de salida.

7. Los argumentos posicionales son aquellos cuyo significado viene dictado por su posición, por ejemplo, el segundo argumento se emite después del primero, el tercero se emite después del segundo, etc.

8. Los argumentos de palabra clave son aquellos cuyo significado no está dictado por su ubicación, sino por una palabra especial (palabra clave) que se utiliza para identificarlos.

9. Los parámetros `end` y `sep` se pueden usar para dar formato la salida de la función `print()`. El parámetro `sep` especifica el separador entre los argumentos emitidos. Por ejemplo, `print("H", "E", "L", "L", "O", sep="-")`, mientras que el parámetro `end` especifica que imprimir al final de la declaración de impresión.

### Cuestionario de sección

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


### Solución cuestionario

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
