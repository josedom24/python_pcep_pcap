# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 6: Interacción con el usuario
## Clase: Resumen y cuestionario de la sección

### Resumen de sección

1. Los operadores de comparación (o también denominados operadores relacionales) se utilizan para comparar valores. La siguiente tabla ilustra cómo funcionan los operadores de comparación, asumiendo que `x=0`, `y=1` y `z=0`:

|Operador |	Descripción |Ejemplo|
|----------|----------|----------|
|== 	|Devuelve si los valores de los operandos son iguales, y False de lo contrario.| x == y  # False <br> x == z  # True|
|!= 	|Devuelve True si los valores de los operandos no son iguales, y False de lo contrario.|x != y  # True <br> x != z  # False|
|> 	    |Devuelve True si el valor del operando izquierdo es mayor que el valor del operando derecho, y False de lo contrario.|x > y  # False <br> y > z  # True|
|< 	    | Devuelve True si el valor del operando izquierdo es menor que el valor del operando derecho, y False de lo contrario.| x < y  # True <br> y < z  # False |
|≥ 	    | Devuelve True si el valor del operando izquierdo es mayor o igual al valor del operando derecho, y False de lo contrario.| x >= y  # False <br> x >= z  # True <br> y >= z  # True|
|≤ 	    | Devuelve True si el valor del operando izquierdo es menor o igual al valor del operando derecho, y False de lo contrario. | x <= y  # True <br> x <= z  # True <br> y <= z  # False |

2. Cuando deseas ejecutar algún código solo si se cumple una determinada condición, puedes usar una sentencia condicional:

    * Una única sentencia `if`, por ejemplo:

    ```
    x = 10

    if x == 10: # condición
        print("x es igual a 10")  # Ejecutado si la condición es Verdadera.
    ```

    * Una serie de sentencias `if`, por ejemplo:

    ```
    x = 10

    if x > 5: # primera condición
        print("x es mayor que 5")  # Ejecutado si la primera condición es Verdadera.

    if x < 10: # segunda condición
        print("x is less than 10")  # Ejecutado si la segunda condición es Verdadera.

    if x == 10: # tercera condición
        print("x is equal to 10")  # Ejecutado si la tercera condición es Verdadera.
    ```        

    Cada sentencia `if` se prueba por separado.

    * Una sentencia de `if-else`, por ejemplo:

    ```
    x = 10

    if x < 10:  # Condición
        print("x es menor que 10")  # Ejecutado si la condición es Verdadera.

    else:
        print("x es mayor o igual a 10")  # Ejecutado si la condición es Falsa.
    ```

    * Una serie de sentencias `if` seguidas de un else, por ejemplo:

    ```
    x = 10

    if x > 5:  # True
        print("x > 5")

    if x > 8:  # True
        print("x > 8")

    if x > 10:  # False
        print("x > 10")
    else:
        print("se ejecutará el else")
    ```

    Cada `if` se prueba por separado. El cuerpo de `else` se ejecuta si el último `if` es `False`.
    
    * La sentencia `if-elif-else`, por ejemplo:

    ```
    x = 10
    if x == 10:  # True
        print("x == 10")

    if x > 15:  # False
        print("x > 15")

    elif x > 10:  # False
        print("x > 10")

    elif x > 5:  # True
        print("x > 5")

    else:
        print("else no será ejecutado")
    ```

    Si la condición para `if` es `False`, el programa verifica las condiciones de los bloques `elif` posteriores: el primer `elif` que sea `True` es el que se ejecuta. Si todas las condiciones son `False`, se ejecutará el bloque `else`.
    
    * Sentencias condicionales anidadas, ejemplo:

    ```
    x = 10
    if x > 5:  # True
        if x == 6:  # False
            print("anidado: x == 6")
        elif x == 10:  # True
            print("anidado: x == 10")
        else:
            print("anidado: else")
    else:
        print("else")
    ```

 ### Cuestionario de sección

1. ¿Cuál es la salida del siguiente fragmento de código?

```
x = 5
y = 10
z = 8

print(x > y)
print(y > z)
```

2. ¿Cuál es la salida del siguiente fragmento de código?

```
x, y, z = 5, 10, 8

print(x > z)
print((y - 5) == x)
```

3. ¿Cuál es la salida del siguiente fragmento de código?

```
x, y, z = 5, 10, 8
x, y, z = z, y, x

print(x > z)
print((y - 5) == x)
```

4. ¿Cuál es la salida del siguiente fragmento de código?

```
x = 10

if x == 10:
    print(x == 10)
if x > 5:
    print(x > 5)
if x < 10:
    print(x < 10)
else:
    print("else")
```

5. ¿Cuál es la salida del siguiente fragmento de código?

```
x = "1"

if x == 1:
    print("uno")
elif x == "1":
    if int(x) > 1:
        print("dos")
    elif int(x) < 1:
        print("tres")
    else:
        print("cuatro")
if int(x) == 1:
    print("cinco")
else:
    print("seis")
```

6. ¿Cuál es la salida del siguiente fragmento de código?

```
x = 1
y = 1.0
z = "1"

if x == y:
    print("uno")
if y == int(z):
    print("dos")
elif x == y:
    print("tres")
else:
    print("cuatro")
```

### Solución cuestionario

1. Pregunta 1:

```
False
True
```

2. Pregunta 2:

```
False
True
```

3. Pregunta 3:

```
True
False
```

4. Pregunta 4:

```
True
True
else
```

5. Pregunta 5:

```
cuatro
cinco
```

6. Pregunta 6:

```
uno
dos
```
