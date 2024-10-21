# LABORATORIO: Tu propio split

## Tiempo Estimado

20 - 25 minutos

## Nivel de Dificultad

Medio

## Objetivos

* Mejorar las habilidades del alumno al trabajar con cadenas.
* Utilizar los métodos incorporados de Python para las cadenas.

## Escenario

Ya sabes como funciona el método `split()`. Ahora queremos que lo pruebes.

Tu tarea es escribir tu propia función, que se comporte casi como el método original `split()`, por ejemplo:

* Debe aceptar únicamente un argumento: una cadena.
* Debe devolver una lista de palabras creadas a partir de la cadena, dividida en los lugares donde la cadena contiene espacios en blanco.
* Si la cadena está vacía, la función debería devolver una lista vacía.
* Su nombre debe ser `mysplit()`.

Puedes usar esta plantilla:

```
def mysplit(strng):
    #
    # coloca tu código aquí
    #


print(mysplit("Ser o no ser, esa es la pregunta"))
print(mysplit("Ser o no ser,esa es la pregunta"))
print(mysplit("   "))
print(mysplit(" abc "))
print(mysplit(""))
```

## Salida esperada

```
['Ser', 'o', 'no', 'ser', 'esa', 'es,', 'la', 'pregunta']
['Ser', 'o', 'no', 'ser,esa', 'es', 'la', 'pregunta']
[]
['abc']
[]
```