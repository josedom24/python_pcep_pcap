# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 1: El Programa "¡Hola, Mundo!"
## Clase: Invocación de funciones

### Argumentos de funciones

Como dijimos anteriormente las funciones pueden causar un efecto y realizar un cálculo devolviendo un resultado.

Para realizar estas dos tareas, una función puede recibir datos de entrada que llamamos **argumentos o parámetros**.

Dependiendo de las necesidades individuales, pueden aceptar cualquier cantidad de argumentos - tantos como sea necesario para realizar sus tareas. Nota: Cuando dijimos cualquier número, eso incluye el cero - algunas funciones de Python no necesitan ningún argumento.

Los argumentos se deben indicar dentro de los **paréntesis de la función**. Si vas a utilizar una función que no tiene ningún argumento, aún tiene que tener los paréntesis. Al colocar los paréntesis estamos indicando que el nombre utilizado es el nombre de una función.

En nuestro programa de ejemplo estamos trabajando con la función `print()`. Y cómo vemos tiene un argumento.

### Una cadena como el argumento de la función print()

El único argumento entregado a la función `print()` en este ejemplo es una **cadena de caracteres**: `"Hola, Mundo!"`.

Como puedes ver, **la cadena está delimitada por comillas**, de hecho, las comillas forman la cadena, recortan una parte del código y le asignan un significado diferente. Podemos imaginar que las comillas significan algo así: el texto entre nosotros no es un código. No está diseñado para ser ejecutado, y se debe tomar tal como está.

### Invocación de funciones

El nombre de la función (`print` en este caso) junto con los paréntesis y los argumento(s), forman la invocación de la función.

```
print("¡Hola, Mundo!") 
```

¿Qué sucede cuando Python encuentra una invocación de una función?

1. Python comprueba si el nombre especificado es **legal** (explora sus datos internos para encontrar una función existente del nombre; si esta búsqueda falla, Python aborta el código).
2. Python comprueba si los requisitos de la función para el número de argumentos **le permiten invocar** la función de esta manera (por ejemplo, si una función específica exige exactamente dos argumentos, cualquier invocación que entregue solo un argumento se considerará errónea y abortará la ejecución del código).
3. **Python deja el código por un momento** y salta dentro de la función que se desea invocar; por lo tanto, también toma los argumentos y los pasa a la función.
4. La función **ejecuta el código**, provoca el efecto deseado (si lo hubiera), evalúa el (los) resultado(s) deseado(s) y termina la tarea.
5. Python regresa al código (al lugar inmediatamente después de la invocación) y reanuda su ejecución.