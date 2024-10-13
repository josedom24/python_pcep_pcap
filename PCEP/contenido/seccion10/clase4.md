# Introducción a los métodos. Añadir elementos a las listas

## Funciones frente a métodos

* Un **método** es un tipo específico de **función**: funciona como una función pero actúa y se utiliza de forma distinta.
* Las funciones son independiente de los datos. 
* Los métodos están relacionados con determinados tipos de datos (que llamaremos **clases**) y cuando los usamos cambian el estado del dato con el que esta relacionado.
* Podemos crear variables (que llamaremos **objetos**) a partir de algunos tipos de datos (que llamaremos **clases**) que además de guardar información, pueden ejecutar determinadas funciones (que llamaremos **métodos**) que actuarán sobre los datos guardados.
* Profundizaremos en todos estos conceptos cuando estudiemos la **Programación Orientada a Objetos**.
* De los tipos de datos que hemos estudiado hasta ahora, las cadenas (String) y las listas (List) son clases por lo que pueden ejecutar métodos.
* En general, una invocación de función típica puede tener este aspecto:
    ```
    result = function(arg)
    ```
    La función toma un argumento, hace algo y devuelve un resultado.
* Una invocación de un método típico usualmente se ve así:
    ```
    result = data.method(arg)
    ```
    El nombre del método está precedido por el nombre de la variable (**objeto**) que posee el método, separado por punto.
* El método se comportará como una función: puede devolver algún resultado, pero puede hacer algo más: puede cambiar el estado interno de los datos a partir de los cuales se ha invocado.
* Las listas poseen un conjunto de métodos que pueden cambiar el estado de una lista, por ejemplo para añadir elementos a una lista utilizaremos un método.

## Agregando elementos a una lista: append() e insert()

Un nuevo elemento puede ser añadido al final de la lista existente ejecutando:

```
list.append(value)
```

Dicha operación se realiza mediante un método llamado `append()`. Toma el valor de su argumento y lo coloca al final de la lista que posee el método. La longitud de la lista aumenta en uno.

El método `insert()` es un poco más inteligente: puede agregar un nuevo elemento en cualquier lugar de la lista, no solo al final:

```
list.insert(location, value)
```

Toma dos argumentos:

* El primero muestra la ubicación requerida del elemento a insertar. Nota: todos los elementos existentes que ocupan ubicaciones a la derecha del nuevo elemento (incluido el que está en la posición indicada) se desplazan a la derecha, para hacer espacio para el nuevo elemento.
* El segundo es el elemento a insertar.

Veamos un ejemplo:

```
numeros = [111, 7, 2, 1]
print(len(numeros))
print(numeros)

numeros.append(4)
print(len(numeros))
print(numeros)

numeros.insert(0, 222)
print(len(numeros))
print(numeros)

numeros.insert(1, 333)
print(numeros)
```

* Se añade un elemento al final de la lista.
* Se añade un elemento al principio de la lista.
* Se añade un elemento en medio de la lista, por lo que los elementos posteriores se desplazan de posición.

## Agregando elementos a una lista vacía

Podemos declarar una lista vacía, sin ningún elemento. Para realiza dicha declaración podemos declarar una lista de la siguiente forma:

```
my_list = []
```

Posteriormente le podemos agregar nuevos elementos.

Veamos en ejemplo:

```
my_list = [] # Creando una lista vacía.

for i in range(5):
    my_list.append(i + 1)

print(my_list)
```

Comprueba que el siguiente código nos devuelve el mismo resultado:


```
my_list = []  # Creando una lista vacía.

for i in range(5):
    my_list.insert(0, i + 1)

print(my_list)
```