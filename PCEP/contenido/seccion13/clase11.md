# LABORATORIO - Conversión del consumo de combustible

## Tiempo Estimado

10 - 15 minutos

## Nivel de Dificultad

Fácil

## Objetivos

* Mejorar las habilidades del estudiante para definir y emplear funciones.

## Escenario

El consumo de combustible de un automóvil se puede expresar de muchas maneras diferentes. Por ejemplo, en Europa, se muestra como la cantidad de combustible consumido por cada 100 kilómetros.

En los EE. UU., se muestra como la cantidad de millas recorridas por un automóvil con un galón de combustible.

Tu tarea es escribir un par de funciones que conviertan l/100km a mpg (millas por galón), y viceversa.

Las funciones:

* Se llaman `litros_100km_a_millas_galon` y `millas_galon_a_litros_100km` respectivamente.
* Tiene un parámetro con el valor a convertir.

Aquí hay información para ayudarte:

* 1 milla = 1609.344 metros.
* 1 galón = 3.785411784 litros. 

Puedes usar esta plantilla:

```
def litros_100km_a_millas_galon(liters):
#
# Escribe tu código aquí.
#

def millas_galon_a_litros_100km(miles):
#
# Escribe tu código aquí.
#

print(litros_100km_a_millas_galon(3.9))
print(litros_100km_a_millas_galon(7.5))
print(litros_100km_a_millas_galon(10.))
print(millas_galon_a_litros_100km(60.3))
print(millas_galon_a_litros_100km(31.4))
print(millas_galon_a_litros_100km(23.5))
```

Ejecuta tu código y verifica si tu salida es la misma que la nuestra.

## Salida esperada:

```
60.31143162393162
31.36194444444444
23.52145833333333
3.9007393587617467
7.490910297239916
10.009131205673757
```

