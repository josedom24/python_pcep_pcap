# La palabra reservada global

Vamos a contestar la siguiente pregunta: ¿Una función es capaz de modificar una variable que fue definida fuera de ella? Esto sería muy incomodo.

Como hemos visto hasta ahora la respuesta es **no**, sin embargo, existe un método especial en Python el cual puede extender el alcance de una variable incluyendo el cuerpo de las funciones para poder no solo leer los valores de las variables sino también modificarlos.

Esto se consigue utilizando la palabra clave reservada llamada `global`:

```
global name
global name1, name2, ...
```

Si declaramos variables dentro de la función con `global`, obliga a Python a abstenerse de crear una nueva variable dentro de la función; se empleará la que se puede acceder desde el exterior.

En otras palabras, este nombre se convierte en global (tiene un alcance global, y no importa si se esta leyendo o asignando un valor).

Veamos un ejemplo:

```
def my_function():
    global var
    var = 2
    print("¿Conozco a aquella variable?", var)


var = 1
my_function()
print(var)
```

La salida sería:
```
¿Conozco a aquella variable? 2
2
```

## Modificación de los argumentos de una función

Si modificamos dentro de una función el valor de los parámetros, ¿los argumentos recibidos en la llamada de la función cambian?. La respuesta es que depende del tipo de dato, más concretamente de la mutabilidad del tipo de datos:

* Si el dato es inmutable, es decir no se puede modificar, por ejemplo los escales, el cambio de parámetro no modifica el argumento.
* Si es dato es mutable, por ejemplo las listas, el cambio del parámetro modifica el argumento.

## Ejemplo con escalares

Vemos un ejemplo utilizando un escalar:

```
def my_function(n):
    print("Yo recibí", n)
    n += 1
    print("Ahora tengo", n)


var = 1
my_function(var)
print(var)
```

La salida del código es:

```
Yo recibí 1
Ahora tengo 2
1
```

La conclusión es obvia: al cambiar el valor del parámetro `n` este no se propaga fuera de la función al argumento `var`. Esto también significa que una función recibe el valor del argumento, no el argumento en sí. 

## Ejemplo con listas

Veamos un ejemplo:

```
def my_function(my_list_1):
    print("Print #1:", my_list_1)
    print("Print #2:", my_list_2)
    my_list_1 = [0, 1]
    print("Print #3:", my_list_1)
    print("Print #4:", my_list_2)


my_list_2 = [2, 3]
my_function(my_list_2)
print("Print #5:", my_list_2)
```

La salida del código es:
```
Print #1: [2, 3]
Print #2: [2, 3]
Print #3: [0, 1]
Print #4: [2, 3]
Print #5: [2, 3]
```

Parece ser que se sigue aplicando la misma regla.

Finalmente, la diferencia se puede observar en el siguiente ejemplo:

```
def my_function(my_list_1):
    print("Print #1:", my_list_1)
    print("Print #2:", my_list_2)
    del my_list_1[0]  # Presta atención a esta línea.
    print("Print #3:", my_list_1)
    print("Print #4:", my_list_2)


my_list_2 = [2, 3]
my_function(my_list_2)
print("Print #5:", my_list_2)
```

La salida será el siguiente:

```
Print #1: [2, 3]
Print #2: [2, 3]
Print #3: [3]
Print #4: [3]
Print #5: [3]
```

* En el primer ejemplo, la instrucción de asignación (`my_list_1 = [0, 1]`) crea una nueva lista, por lo tanto no estamos modificando el valor del argumento. Se crea una nueva variable con el mismo nombre.
* En el segundo ejemplo, al modificar la lista dentro de la función, estamos cambiando también el argumento.

## Cuestionario

1. ¿Qué ocurrirá cuando se intente ejecutar el siguiente código?
    ```
    def message():
        alt = 1
        print("¡Hola, mundo!")
    print(alt)
    ```
2. ¿Cuál es la salida del siguiente fragmento de código?
    ```
    a = 1
    def fun():
        a = 2
        print(a)
    fun()
    print(a)
    ```

3. ¿Cuál es la salida del siguiente fragmento de código?
    ```
    a = 1
    def fun():
        global a
        a = 2
        print(a)
    fun()
    a = 3
    print(a)
    ```

4. ¿Cuál es la salida del siguiente fragmento de código?
    ```
    a = 1
    def fun():
        global a
        a = 2
        print(a)
    a = 3
    fun()
    print(a)
    ```

## Solución cuestionario

1. Pregunta 1

    Se arrojará una excepción `NameError (NameError: name 'alt' is not defined)`.

2. Pregunta 2

    ```
    2
    1
    ```

3. Pregunta 3

    ```
    2
    3
    ```

4. Pregunta 4

    ```
    2
    2
    ```