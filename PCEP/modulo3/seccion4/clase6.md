# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 4: Listas
## Clase: Ejemplo de recorrido de listas

### Intercambio de variables

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

auxiliary = variable_1
variable_1 = variable_2
variable_2 = auxiliary
```

Pero Python nos permite una solución que funciona también y es muy clara:

```
variable_1 = 1
variable_2 = 2

variable_1, variable_2 = variable_2, variable_1
```

### Intercambio de los elementos de una lista

Vamos a utilizar lo visto en el punto anterior para resolver el siguiente problema: queremos invertir el orden de una lista. Es decir, por ejemplo en una lista de 5 elementos, que remos intercambiar el primer elemento por el último y el segundo por el cuarto.

