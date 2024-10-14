# Compresión de listas

## Declaración de listas

Para declarar o crear una lista tenemos varias alternativas:

1. En la declaración de la variable indicando los elementos que forman parte de la lista. Por ejemplo:

    ```
    my_list = [1, 2, 3, 4, 5]
    ```

2. Partir de la declaración de una lista vacía e ir añadiendo elementos a la lista. Veamos algunos ejemplos:

    ```
    my_list = [ ]
    my_list.append(1)
    my_list.append(2)
    my_list.append(3)
    my_list.append(4)
    my_list.append(5)
    ```

    También podemos automatizar esta acción usando un bucle `for`:

    ```
    my_list = [ ]
    for i in range(1,6):
        my_list.append(i)
    ```

    Podríamos usar una estructura condicional para añadir a la lista los elementos que nos interesa. Por ejemplo añadir a la lista sólo los números pares:

    ```
    my_list = [ ]
    for i in range(1,6):
        if i % 2 == 0:
            my_list.append(i)
    ```
3. Usando **compresión de listas**.

## Compresión de listas

La compresión de lista nos permite crear una lista y añadirle elementos. La lista se crea en tiempo de ejecución, y no se declara de forma estática.

La sintaxis de una compresión de lista es la siguiente:

```
[<expresión> for <elemento> in <lista> if <condicional>]
```

* Esto crea una nueva lista cuyos elementos se calcularan a partir de la expresión `expresión`.
* La nueva lista tendrá, de principio, tantos elementos como la lista `lsita` y la variable `elemento` se podrá usar en la expresión `expresión`.
* La parte de la estructura condicional es optativa, pero si aparece la condición se deberá cumplir para que se procese el elemento.

Veamos algunos ejemplos:

1. Creamos una lista con 5 cadenas:

    ```
    lista = ["Hola" for i in range(5)]
    ```
2. Creamos una lista con los 5 primeros números:

    ```
    lista = [i for i in range(1,6)]
    ```

3. Creamos una lista con los cuadrados de los cinco primeros números:

    ```
    lista = [i ** 2 for i in range(1,6)]
    ```
4. Creamos una lista con los números pares de los 10 primeros números:
    ```
    lista = [i for i in range(1,11) if i % 2 == 0]
    ```