# Diccionarios

El diccionario es otro tipo de estructura de datos de Python. No es una secuencia (pero puede adaptarse fácilmente a un procesamiento secuencial) y además es mutable.

En un diccionario los datos (**valor**) guardados se referencias con una **clave**(key). La palabra que se obtiene del diccionario es denominada valor.

Esto significa que un diccionario es un conjunto de **pares de claves y valores**. 

* **Cada clave debe de ser única**. No es posible tener una clave duplicada.
* Una **clave puede ser un tipo de dato de cualquier tipo**: puede ser un número (entero o flotante), o incluso una cadena.
* Un **diccionario no es una lista**. Una lista contiene un conjunto de valores numerados, mientras que un diccionario almacena pares de valores.
* La función `len()` aplica también para los diccionarios, regresa la **cantidad de pares (clave-valor)** en el diccionario.
* Los valores también pueden ser cualquier tipo de datos.

## ¿Cómo crear un diccionario?

Si deseas asignar algunos pares iniciales a un diccionario, utiliza la siguiente sintaxis:
```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}
phone_numbers = {'jefe': 5551234567, 'Suzy': 22657854310}
empty_dictionary = {}

print(dictionary)
print(phone_numbers)
print(empty_dictionary)
```
* Como vemos tanto los valores como las claves son de distintos tipos de datos.
* La lista de todos los pares es encerrada con **llaves**, mientras que los pares son separados por **comas**, y las claves y valores por **dos puntos**.
* Los diccionarios vacíos son construidos por un par vacío de llaves.
* El diccionario entero se puede imprimir con una invocación a la función `print()`. 
* Al imprimir el diccionario puede que el orden de los pares sa distinto al de su asignación. Hay que recordar que los diccionarios no son listas, no guardan el orden de sus datos, el orden no tiene significado.

## ¿Cómo utilizar un diccionario?

Si deseas obtener cualquiera de los valores, debes de proporcionar una clave válida:
```
print(dictionary['gato'])
print(phone_numbers['Suzy'])
```

* El obtener el valor de un diccionario es semejante a la indexación, gracias a los corchetes alrededor del valor de la clave.
* Si una clave es una cadena, se tiene que especificar como una cadena.
* Las claves son sensibles a las mayúsculas y minúsculas: 'Suzy' sería diferente a 'suzy'.

No se puede utilizar una clave que no exista. Hacer algo como lo siguiente provocará un error de ejecución.:
```
print(phone_numbers['presidente'])
```

Podemos usar el operador `in` o `not iin` para comprobar si existe una clave en el diccionario:

```
dictionary = {"gato" : "cat", "perro" : "dog", "caballo" : "horse"}
words = ['gato', 'león', 'caballo']

for word in words:
    if word in dictionary:
        print(word, "->", dictionary[word])
    else:
        print(word, "no está en el diccionario")
```


Cuando escribes una expresión grande o larga, puede ser una buena idea mantenerla alineada verticalmente. Así es como puede hacer que el código sea más legible y más amigable para el programador, por ejemplo:
```
# Ejemplo 1:
dictionary = {
              "gato": "cat",
              "perro": "dog",
              "caballo": "horse"
              }

# Ejemplo 2:
phone_numbers = {'jefe': 5551234567,
                 'Suzy': 22657854310
                 }
```

Este tipo de formato se llama sangría francesa.

