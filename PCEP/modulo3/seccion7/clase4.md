# Módulo 3: Valores booleanos, ejecución condicional, bucles, listas y su procesamiento, operadores lógicos y de bit a bit
## Sección 7: Listas multidimensionales
## Clase: Arreglos multidimensionales

## Arreglos tridimensionales

Para crear un arreglo de tres dimensiones en Python, los elementos de una lista serán listas, que a su vez tendrán como elementos otras listas. Si continuamos con la misma estructura tendríamos arreglos de diferentes dimensiones.

Veamos un ejemplo de un arreglo tridimensional: imagina un hotel que consta de tres edificios, de 15 pisos cada uno. Hay 20 habitaciones en cada piso. Para esto, necesitas un arreglo que pueda recopilar y procesar información sobre las habitaciones ocupadas/libres.

1. El tipo de elementos del arreglo sería un valor nooleano (`True`/`False`).
2. Necesitamos un arreglo de 3 dimensiones, para guardar la información de las 20 habitaciones de cada piso de cada edificio.

## Declaración de arreglos trimidencionales

Podríamos inicializar el arreglo durante su declaración, pero en este ejemplo habría que escribie mucha información,. Es más fácil usar compresión de listas:

```
habitaciones = [[[False for r in range(20)] for f in range(15)] for t in range(3)]
```

* El primer índice (0 a 2) selecciona uno de los edificios.
* El segundo (0 a 14) selecciona el piso
* El tercero (0 a 19) selecciona el número de habitación. 
* Todas las habitaciones están inicialmente desocupadas.

## Indexación de arreglos bidimensionales

Para acceder a un elemento de un arreglo de tres dimensiones habrá que indicar 3 índices. Por ejemplo para reservar una habitación en  el segundo edificio, en el décimo piso, habitación 14:

```
habitaciones[1][9][13] = True
```

Si queremos indicar como libre la segunda habitación en el quinto piso ubicado en el primer edificio:

```
habitaciones[0][4][1] = False
```

Otro ejemplo: verificar si hay siponibilidad en el pisoo 15 del tercer edificio:



Verifica si hay disponibilidad en el piso 15 del tercer edificio:

```
habitaciones = [[[False for r in range(20)] for f in range(15)] for t in range(3)]

# Indicamos como ocupadas algunas habitaciones del piso 15 del tercer edificio

habitaciones[2][14][0] = True
habitaciones[2][14][1] = True
habitaciones[2][14][2] = True

disponibilidad = 0

for num_habitacion in range(20):
    if not habitaciones[2][14][num_habitacion]:
        disponibilidad += 1
print("Hay disponibles",disponibilidad,"habitaciones en el piso 15 del edificio número 3.")

```

La variable `disponibilidad` contiene 0 si todas las habitaciones están ocupadas, o en dado caso el número de habitaciones disponibles.

## Recorrido de arreglos tridimensioonales

Para recorrer todos los elementos de un arreglo tridimensional, necesitamos tres bucles anidados. En el caso de ejemplod el hotel.

```
habitaciones = [[[False for r in range(20)] for f in range(15)] for t in range(3)]

# Indicamos como ocupadas algunas habitaciones del piso 15 del tercer edificio

habitaciones[2][14][0] = True
habitaciones[2][14][1] = True
habitaciones[2][14][2] = True

for edificio in habitaciones:
    for pisos in edificio:
        for habitacion in pisos:
            if habitacion:
                print("O ",end="")
            else:
                print("L ",end="")
        print()
    print("***********")
```

En este caso escribimos `L` si la habitación está libre y `O` si está ocupada. La información de cada piso se divide con unos asteriscos.
