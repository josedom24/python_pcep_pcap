# Ejemplo de recorrido de listas

## Intercambio de variables

El problema que vamos a resolver es el siguiente: ¿Cómo se pueden intercambiar los valores de dos variables?

Echa un vistazo al fragmento:

```
variable_1 = 1
variable_2 = 2

variable_2 = variable_1
variable_1 = variable_2
```

Esto es incorrecto, porque perderemos el valor almacenado en `variable_2`. Necesitamos una tercera variable que sirva como almacenamiento auxiliar. El código sería de esta manera:

```
variable_1 = 1
variable_2 = 2

auxiliar = variable_1
variable_1 = variable_2
variable_2 = auxiliar
```

Pero Python nos permite una solución que funciona también y es muy clara:

```
variable_1 = 1
variable_2 = 2

variable_1, variable_2 = variable_2, variable_1
```

## Intercambio de los elementos de una lista

Vamos a utilizar lo visto en el punto anterior para resolver el siguiente problema: queremos invertir el orden de una lista. Es decir, por ejemplo en una lista de 5 elementos, que remos intercambiar el primer elemento por el último y el segundo por el cuarto.

Usando lo aprendido en el aparatado anterior, el código sería:

```
my_list = [10, 1, 8, 3, 5]

my_list[0], my_list[4] = my_list[4], my_list[0]
my_list[1], my_list[3] = my_list[3], my_list[1]

print(my_list)
```

Pero, y si tuviéramos una lista con muchos elementos?. ¿Sería esta solución válida?. Podríamos utilizar el bucle `for` para recorrer la lista e ir haciendo los intercambios, el código quedaría:

```
my_list = [10, 1, 8, 3, 5]
length = len(my_list)

for i in range(length // 2):
    my_list[i], my_list[length - i - 1] = my_list[length - i - 1], my_list[i]

print(my_list)
```

* Hemos asignado la variable `length` a la longitud de la lista actual (esto hace que nuestro código sea un poco más claro y más corto).
* Hemos preparado el bucle for para que se ejecute su cuerpo `length // 2` veces (esto funciona bien para listas con longitudes pares e impares, porque cuando la lista contiene un número impar de elementos, el del medio permanece intacto).
* Hemos intercambiado el elemento `i` (desde el principio de la lista) por el que tiene un índice igual a `length-i-1` (desde el final de la lista); en nuestro ejemplo:
    * En la primera iteración: `i = 0` y `length-i-1 = 4`.
    * En la segunda iteración: `i = 1` y `length-i-1 = 3`. 

    

