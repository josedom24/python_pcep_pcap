# LABORATORIO: Triángulo

## Tiempo Estimado

30 - 60 minutos

## Nivel de Dificultad

Fácil/Medio

## Objetivos

* Mejorar las habilidades del estudiante para definir clases desde cero.
* Emplear composición.

## Escenario

Llamamos **composición** a la situación en la que una clase contiene (como atributos) una o más instancias de otra clase, a las que delegará parte de sus funcionalidades.

Vamos a definir una clase para representar un triangulo. Nuestro triangulo estará formado por tres puntos, estos puntos se guardarán en un objeto de clase `Point` que desarrollamos en el taller anterior,

La nueva clase se llamará `Triangle` y esto es lo que queremos:

* El constructor acepta tres argumentos, todos ellos son objetos de la clase `Point`.
* Los puntos se almacenan dentro del objeto como una lista privada
* La clase proporciona un método sin parámetros llamado `perimeter()`, que calcula el perímetro del triángulo descrito por los tres puntos; el perímetro es la suma de todas las longitudes de los lados.

Puedes usar la siguiente plantilla:

```
import math


class Point:
    #
    # El código copiado del laboratorio anterior.
    #


class Triangle:
    def __init__(self, vertice1, vertice2, vertice3):
        #
        # Escribir el código aquí.
        #

    def perimeter(self):
        #
        # Escribir el código aquí.
        #


triangle = Triangle(Point(0, 0), Point(1, 0), Point(0, 1))
print(triangle.perimeter())
```

## Salida esperada

`3.414213562373095`