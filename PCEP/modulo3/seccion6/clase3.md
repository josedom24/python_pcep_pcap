# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 6: Operaciones con listas
## Clase: Operadores de pertenencia

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