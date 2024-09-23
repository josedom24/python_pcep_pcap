# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 6: Interacción con el usuario
## Clase: Resumen y cuestionario de la sección

## Resumen de sección

1. La función `print()` envía datos a la consola, mientras que la función `input()` obtiene datos de la consola.
2. La función `input()` viene con un parámetro inicial: un mensaje de tipo cadena para el usuario. Permite escribir un mensaje antes de la entrada del usuario, por ejemplo:

    ```
    name = input("Ingresa tu nombre: ")
    print("Hola, " + name + ". ¡Un gusto conocerte!")
    ```

3. Cuando la función `input()` es llamada o invocada, el flujo del programa se detiene, el símbolo del cursor se mantiene parpadeando (le está indicando al usuario que tome acción ya que la consola está en modo de entrada) hasta que el usuario haya ingresado un dato y/o haya presionado la tecla Enter.

    Consejo: La característica mencionada anteriormente de la función input() puede ser utilizada para pedirle al usuario que termine o finalice el programa. Observa el siguiente código:

    ```
    name = input("Ingresa tu nombre: ")
    print("Hola, " + name + ". ¡Un gusto conocerte!")
    
    print("\nPresiona la tecla Enter para finalizar el programa.")
    input()
    print("FIN.")
    ```
4. El resultado de la función `input()` es una cadena. Podemos convertir las cadenas a números usando las funciones `int()` o `float()`.

5. La función `int()` toma un argumento (por ejemplo, una cadena: *int(string)*) e intenta convertirlo a un valor entero; si llegase a fallar, el programa entero fallará también (existe una manera de solucionar esto, se explicará mas adelante).

6. La función `float()` toma un argumento (por ejemplo, una cadena: *float(string)*) e intenta convertirlo a flotante (el resto es lo mismo).

7. Se pueden unir cadenas unas con otras a través del operador de concatenación (`+`). Observa el siguiente código:

    ```
    num_1 = input("Ingresa el primer número: ") # Ingresa 12
    num_2 = input("Ingresa el segundo número: ") # Ingresa 21

    print(num_1 + num_2) el programa retorna 1221
    ```

8. También se pueden multiplicar (`*` - replicación) cadenas, por ejemplo:

    ```
    my_input = input("Ingresa algo: ") # Ejemplo: hola
    print(my_input * 3) # Salida esperada: holaholahola
    ```

 ## Cuestionario de sección

1. ¿Cuál es la salida del siguiente código?

```
x = int(input("Ingresa un número: ")) # El usuario ingresa un 2 
print(x * "5")
```

2. ¿Cuál es la salida esperada del siguiente código?

```
x = input("Ingresa un número: ") # El usuario ingresa un 2 
print(type(x))
```

## Solución cuestionario

1. Pregunta 1:

`55`

2. Pregunta 2:

`<class 'str'>`
