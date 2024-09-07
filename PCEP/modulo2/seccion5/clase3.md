# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 5: Comentarios
## Clase: Resumen y cuestionario de la sección

### Resumen de sección

1. Los comentarios pueden ser utilizados para colocar información adicional en el código. Son omitidos al momento de la ejecución. Dicha información es para los lectores que están manipulando el código. En Python, un comentario es un fragmento de texto que comienza con un `#`. El comentario se extiende hasta el final de la línea.
2. Si deseas colocar un comentario que abarque varias líneas, es necesario colocar un `#` al inicio de cada línea. Además, se puede utilizar un comentario para marcar un fragmento de código que no es necesario en el momento y no se desea ejecutar. (observa la última línea de código del siguiente fragmento), por ejemplo:

    ```
     # Este programa imprime
    # una introducción en la pantalla.
    print("¡Hola!")  #Invocando a la función print()
    # print("Soy Python.") 
    ```
3. Cuando sea posible, se deben auto comentar los nombres de las variables, por ejemplo, si se están utilizando dos variables para almacenar la altura y longitud de algo, los nombres `length` y `width` son una mejor elección que `myvar1` y `myvar2`.
4. Es importante utilizar los comentarios para que los programas sean más fáciles de entender, además de emplear variables legibles y significativas en el código. Sin embargo, es igualmente importante no utilizar nombres de variables que sean confusos, o dejar comentarios que contengan información incorrecta.
5. Los comentarios pueden ser muy útiles cuando tú estás leyendo tu propio código después de un tiempo (es común que los desarrolladores olviden lo que su propio código hace), y cuando otros están leyendo tu código (les puede ayudar a comprender que es lo que hacen tus programas y como es que lo hacen).

### Cuestionario de sección

1. ¿Cuál es el resultado del siguiente fragmento?

```
# print("Cadena #1")
print("Cadena #2") 
```

2. ¿Qué pasará cuando se ejecute el siguiente código?

```
 #Este es
un comentario
multilínea.#
 
print("¡Hola!") 
```

### Solución cuestionario

1. Pregunta 1:

`Cadena #2`

2. Pregunta 2:

`SyntaxError: invalid syntax`