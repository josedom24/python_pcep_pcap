# LABORATORIO: Histograma de frecuencia de caracteres ordenados

## Tiempo Estimado

15 - 30 minutos

## Nivel de Dificultad

Medio

## Objetivos

* Mejorar las habilidades del estudiante para operar con archivos en modo (lectura/escritura).
* Emplear lambdas para cambiar el ordenamiento.

## Escenario

El código anterior necesita ser mejorado. Está bien, pero tiene que ser mejor.

Tu tarea es hacer algunas enmiendas, que generen los siguientes resultados:

* El histograma de salida se ordenará en función de la frecuencia de los caracteres (el contador más grande debe presentarse primero).
* El histograma debe enviarse a un archivo con el mismo nombre que el de entrada, pero con la extensión '.hist' (debe concatenarse con el nombre original).

Ayuda: Emplea una lambda para cambiar el ordenamiento.

## Salida esperada

Suponiendo que el archivo de prueba contiene solo una línea con:

`cBabAa`

El resultado esperado debería verse de la siguiente manera:
```
a -> 3
b -> 2
c -> 1
```

