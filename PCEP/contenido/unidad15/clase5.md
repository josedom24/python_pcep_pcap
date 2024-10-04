# Ejemplo con tuplas y diccionarios

Veamos un ejemplo donde vemos como  las tuplas y los diccionarios pueden trabajar juntos.

Imaginemos el siguiente problema:

* Necesitas un programa para calcular los promedios de tus alumnos.
* El programa pide el nombre del alumno seguido de su calificación.
* Los nombres son ingresados en cualquier orden.
* El ingresar un nombre vacío finaliza el ingreso de los datos 
* Una lista con todos los nombre y el promedio de cada alumno debe ser mostrada al final.

Veamos el programa:

```
school_class = {}

while True:
    name = input("Ingresa el nombre del estudiante: ")
    if name == '':
        break
    
    score = int(input("Ingresa la calificación del estudiante (0-10): "))
    if score not in range(0, 11):
	    break
    
    if name in school_class:
        school_class[name] += (score,)
    else:
        school_class[name] = (score,)
        
for name in sorted(school_class.keys()):
    adding = 0
    counter = 0
    for score in school_class[name]:
        adding += score
        counter += 1
    print(name, ":", adding / counter)
```


Este es un ejemplo de salida del programa:

```
Ingresa el nombre del estudiante: Bob
Ingresa la calificación del estudiante (0-10): 7
Ingresa el nombre del estudiante: Andy
Ingresa la calificación del estudiante (0-10): 3
Ingresa el nombre del estudiante: Bob
Ingresa la calificación del estudiante (0-10): 2
Ingresa el nombre del estudiante: Andy
Ingresa la calificación del estudiante (0-10): 10
Ingresa el nombre del estudiante: Andy
Ingresa la calificación del estudiante (0-10): 3
Ingresa el nombre del estudiante: Bob
Ingresa la calificación del estudiante (0-10): 9
Ingresa el nombre del estudiante:
Andy : 5.333333333333333
Bob : 6.0
```