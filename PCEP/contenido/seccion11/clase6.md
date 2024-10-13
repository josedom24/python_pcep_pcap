# Ordenación de una lista por el algoritmo burbuja

## Ordenamiento de una lista

Hemos aprendido a acceder y modificar los elementos de una lista. En este apartado vamos a aprender a ordenar las listas. Existen muchos algoritmos de ordenación, unos más simples y otros más complejos. En este apartado vamos a mostrar un algoritmo simple y fácil de entender para ordenar listas, sin embargo hay que indicar que no es muy eficiente para listas con muchos elementos.

Una lista se puede ordenar de dos maneras:

* **Ascendente**: si en cada par de elementos adyacentes, el primer elemento no es mayor que el segundo.
* **Descendente**: si en cada par de elementos adyacentes, el primer elemento no es menor que el segundo.

En las siguientes secciones, ordenaremos la lista en orden ascendente, de modo que los números se ordenen de menor a mayor.

## Ordenamiento de burbuja

Aquí está la lista:

```
[8, 10, 6, 2, 4]
```

El algoritmo será el siguiente:

1. Tomaremos el primer y el segundo elemento y los compararemos.
2. Si determinamos que están en el orden incorrecto (es decir, el primero es mayor que el segundo), los intercambiaremos.
3. Si su orden es válido, no haremos nada. 
4. A continuación tomamos el segundo y tercer elemento y volvemos a repetir los pasos.
5. Hay que repetir los pasos con cada par de elementos adyacentes.

En nuestro ejemplo:

1. El primer y segundo elemento están en el orden correcto, ya que 8 es menor que 10.
2. El segundo y tercer elemento están desordenados, los intercambiamos:
    ```
    [8, 6, 10, 2, 4]
    ```
3. El elemento tercero y cuarto también están en orden incorrectos, hay que intercambiarlos:
    ```
    [8, 6, 2, 10, 4]
    ```
4. El cuarto y quinto elemento también están desordenados, lo volvemos a intercambiar:
    ```
    [8, 6, 2, 4, 10]
    ```

En esta primera pasada, nos hemos asegurado que el elemento mayor, en nuestro caso 10, se ha posicionado de manera adecuada en el último lugar de la lista. Podemos imaginarnos que el número como una **burbuja** que ha ido desde fondo hasta la superficie en una copa de champán. El método de clasificación deriva su nombre de la misma observación: se denomina **ordenamiento de burbuja**.

Ya que el último elemento de la lista ya se ha determinado, ahora tenemos que ordenar los cuatro primeros elementos, repitiendo el proceso de comparación entre adyacentes con los cuatro primeros elementos.

Comenzamos el segundo ciclo:

1. El primer y segundo elemento están desordenados, lo intercambiamos:
    ```
    [6, 8, 2, 4, 10]
    ```
2. El segundo y tercer elemento también están desordenados, volvemos a intercambiar:
    ```
    [6, 2, 8, 4, 10]
    ```
3. Por último, el tercer y cuarto están desordenados y volvemos a intercambiar:
    ```
    [6, 2, 4, 8, 10]
    ```

El número 8 ha llegado a su lugar y volvemos a repetir el algoritmos con los tres primeros elementos:

1. El primer y segundo elemento están desordenados, lo intercambiamos.
    ```
    [2, 6, 4, 8, 10]
    ```
2. También intercambiamos el segundo y tercero, ya que están desordenados:
    ```
    [2, 4, 6, 8, 10]
    ```
La lista ya está ordenada, hemos terminado nuestro algoritmo. Si continuara sin estar ordenada, tendríamos que repetir el algoritmo para ordenar los dos primeros elementos.

Como puedes ver, la esencia de este algoritmo es simple: **comparamos los elementos adyacentes y, al intercambiar algunos de ellos, logramos nuestro objetivo**.

