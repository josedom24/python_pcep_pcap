# Listas y funciones

Podemos hacernos las siguientes preguntas:

* ¿Se puede enviar una lista a una función como un argumento?
* ¿Puede una lista ser el resultado de una función?

Veamos las respuestas en los siguientes apartados:

### Una lista como argumento de una función

Podemos mandar una lista como argumento de una función. La función la debemos codificar para que use el parámetro correspondiente como una lista.

Si pasamos una lista a una función, la función tiene que manejarla como una lista.

Veamos un ejemplo:

```
def list_sum(lst):
    s = 0
    
    for elem in lst:
        s += elem
    
    return s
```

La llamada a la función podría ser: 

```
print(list_sum([5, 4, 3]))
```

Internamente la función recorre la lista recibida, por lo tanto si no mnadmos una lista como argúmento:

```
print(list_sum(5))
```

Nos dará el siguiente error: `TypeError: 'int' object is not iterable`.

Esto se debe al hecho de que el bucle `for` no puede iterar un solo valor entero.

### DEvolución de una lista desde una función

Una función también puede devolver una lista. Veamos un ejemplo:

```
def strange_list_fun(n):
    strange_list = []
    
    for i in range(0, n):
        strange_list.insert(0, i)
    
    return strange_list

print(strange_list_fun(5))
```

La salida del programa será: `[4, 3, 2, 1, 0]`.