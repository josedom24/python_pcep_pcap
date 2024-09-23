# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 4: Variable 
## Clase: Resumen y cuestionario de la sección

## Resumen de sección

1. Una **variable** es una ubicación nombrada reservada para almacenar valores en la memoria. Una variable es creada o inicializada automáticamente cuando se le asigna un valor por primera vez. 

2. Cada variable debe de tener un nombre único, un **identificador**. Un nombre válido debe ser aquel que no contiene espacios, debe comenzar con un guion bajo (`_`), o una letra, y no puede ser una palabra reservada de Python. El primer carácter puede estar seguido de guiones bajos, letras, y dígitos. Las variables en Python son sensibles a mayúsculas y minúsculas.

3. Python es un lenguaje **de tipo dinámico**, lo que significa que no se necesita declarar variables en él. Para asignar valores a las variables, se utiliza simplemente el **operador de asignación**, es decir el signo de igual (`=`) por ejemplo, `var = 1`.

4. También es posible utilizar **operadores de asignación compuesta** (operadores abreviados) para modificar los valores asignados a las variables, por ejemplo, `var += 1`, o `var /= 5 * 2`.

5. Se les puede asignar valores nuevos a variables ya existentes utilizando el operador de asignación o un operador abreviado, por ejemplo:
    
    ```
    var = 2
    print(var)

    var = 3
    print(var)

    var += 1
    print(var)
    ```
6. Se puede unir texto con variables empleado el operador `+`, y utilizar la función `print()` para mostrar o imprimir los resultados, por ejemplo:

    ```
    var = "007"
    print("Agente " + var)
    ```

## Cuestionario de sección

1. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    var = 2
    var = 3
    print(var)
    ```

2. ¿Cuáles de los siguientes nombres de variables son ilegales en Python?

    ```
    my_var
    m
    101
    averylongvariablename
    m101
    m 101
    Del
    del
    ```

3. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    a = '1'
    b = "1"
    print(a + b)
    ```

4. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    a = 6
    b = 3
    a /= 2 * b
    print(a)
    ```

## Solución cuestionario

1. Pregunta 1:

    ```
    3
    ```

2. Pregunta 2:

    ```
    my_var
    m
    101 # incorrecto (comienza con un dígito)
    averylongvariablename
    m101
    m 101 # incorrecto (contiene un espacio)
    Del
    del # incorrecto (es una palabra clave reservada)
    ```

3. Pregunta 3:

    ```
    11
    ```

4. Pregunta 4:

    ```
    1.0
    ```

    Explicación:

    ```
    2 * b = 6   
    a = 6 → 6 / 6 = 1.0 
    ```