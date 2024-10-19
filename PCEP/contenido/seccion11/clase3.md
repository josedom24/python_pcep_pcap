# Operadores de pertenencia

## Los operadores in y not in

Python ofrece dos operadores muy poderosos, capaces de comprobar si un elemento pertenece a una lista.

Estos operadores son:

```
elem in my_list
elem not in my_list
```

* El primero de ellos (**in**) verifica si un elemento dado (el argumento izquierdo) está actualmente almacenado en algún lugar dentro de la lista (el argumento derecho), devuelve `True` en este caso.
* El segundo (**not in**) comprueba si un elemento dado (el argumento izquierdo) está ausente en una lista, devuelve `True` en este caso.

Veamos un ejemplo:

```
my_list = [0, 3, 12, 8, 2]

print(5 in my_list)
print(5 not in my_list)
print(12 in my_list)
```

En el siguiente ejemplo, pedimos al usuario que introduzca un número y nos informa si el número está dentro de la lista:

```
my_list = [0, 3, 12, 8, 2]
numero = int(input("Introduce un número:"))
if numero in my_list:
    print ("El número está dentro de la lista")
else:
    print ("El número no está dentro de la lista")
```

## Cuestionario

1. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    list_1 = ["A", "B", "C"]
    list_2 = list_1
    list_3 = list_2

    del list_1[0]
    del list_2[0]

    print(list_3)
    ```

2. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    list_1 = ["A", "B", "C"]
    list_2 = list_1
    list_3 = list_2

    del list_1[0]
    del list_2

    print(list_3)
    ```

3. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    list_1 = ["A", "B", "C"]
    list_2 = list_1
    list_3 = list_2

    del list_1[0]
    del list_2[:]

    print(list_3)
    ```

4. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    list_1 = ["A", "B", "C"]
    list_2 = list_1[:]
    list_3 = list_2[:]

    del list_1[0]
    del list_2[0]

    print(list_3)
    ```

5. Inserta `in` o `not in` en lugar de `???` para que el código genere el resultado esperado.

    ```
    my_list = [1, 2, "in", True, "ABC"]
    
    print(1 ??? my_list)  # salida True
    print("A" ??? my_list)  # salida True
    print(3 ??? my_list)  # salida True
    print(False ??? my_list)  # salida False
    ```

## Solución cuestionario

1. Pregunta 1:

    ```
    ['C']
    ```

2. Pregunta 2:

    ```
    ['B', 'C']
    ```

3. Pregunta 3:

    ```
    [ ]
    ```

4. Pregunta 4:

    ```
    ['A', 'B', 'C']
    ```


5. Pregunta 5:

    ```
    my_list = [1, 2, "in", True, "ABC"]

    print(1 in my_list)  # salida True
    print("A" not in my_list)  # salida True
    print(3 not in my_list)  # salida True
    print(False in my_list)  # salida False
    ```