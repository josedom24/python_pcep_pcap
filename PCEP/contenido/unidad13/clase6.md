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

Internamente la función recorre la lista recibida, por lo tanto si no mandamos una lista como argumento:

```
print(list_sum(5))
```

Nos dará el siguiente error: `TypeError: 'int' object is not iterable`.

Esto se debe al hecho de que el bucle `for` no puede iterar un solo valor entero.

### Devolución de una lista desde una función

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

## Cuestionario

1. ¿Cuál es la salida del siguiente fragmento de código?
```
def hi():
    return
    print("¡Hola!")

hi()
```

2. ¿Cuál es la salida del siguiente fragmento de código?
```
def is_int(data):
    if type(data) == int:
        return True
    elif type(data) == float:
        return False

print(is_int(5))
print(is_int(5.0))
print(is_int("5"))
```

3. ¿Cuál es la salida del siguiente fragmento de código?
```
def even_num_lst(ran):
    lst = []
    for num in range(ran):
        if num % 2 == 0:
            lst.append(num)
    return lst

print(even_num_lst(11))
```

4. ¿Cuál es la salida del siguiente fragmento de código?
```
def list_updater(lst):
    upd_list = []
    for elem in lst:
        elem **= 2
        upd_list.append(elem)
    return upd_list

foo = [1, 2, 3, 4, 5]
print(list_updater(foo))
```

## Solución cuestionario

1. Pregunta 1

La función devolverá un valor `None` implícito 

2. Pregunta 2

```
True
False
None
```

3. Pregunta 3

`[0, 2, 4, 6, 8, 10]`

4. Pregunta 4

`[1, 4, 9, 16, 25]`

