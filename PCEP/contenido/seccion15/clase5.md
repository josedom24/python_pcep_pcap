# Ejemplo con tuplas y diccionarios

Veamos un ejemplo donde vemos como las tuplas y los diccionarios pueden trabajar juntos.

Imaginemos el siguiente problema:

* Necesitas un programa para calcular la media de notas de tus alumnos.
* El programa pide el nombre del alumno seguido de su calificación.
* Los nombres son ingresados en cualquier orden.
* El ingresar un nombre vacío finaliza el ingreso de los datos 
* Una lista con todos los nombre y el promedio de cada alumno debe ser mostrada al final.

Veamos el programa:

```
alumnos = {}

nombre = input("Ingresa el nombre del estudiante: ")
while nombre != "":

    nota = int(input("Ingresa la calificación del estudiante (0-10): "))
    if nota not in range(0, 11):
	    break
    
    if nombre in alumnos:
        alumnos[nombre] += (nota,)
    else:
        alumnos[nombre] = (nota,)
    nombre = input("Ingresa el nombre del estudiante: ")
        
for nombre in sorted(alumnos.keys()):
    total = 0
    contador = 0
    for nota in alumnos[nombre]:
        total += nota
        contador += 1
    print(nombre, ":", total / contador)
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

## Cuestionario

1. ¿Qué ocurrirá cuando se intente ejecutar el siguiente código?

    ```
    my_tup = (1, 2, 3)
    print(my_tup[2])
    ```

2. ¿Cuál es la salida del siguiente fragmento de código?

    ```
    tup = 1, 2, 3
    a, b, c = tup

    print(a * b * c)
    ```

3. Completa el código para emplear correctamente el método `count()` para encontrar la cantidad de 2 duplicados en la tupla 
siguiente.

    ```
    tup = 1, 2, 3, 2, 4, 5, 6, 2, 7, 2, 8, 9
    duplicates = # Escribe tu código aquí.

    print(duplicates)    # salida: 4
    ```

4. Escribe un programa que "una" los dos diccionarios (`d1` y `d2`) para crear uno nuevo (`d3`).

    ```
    d1 = {'Adam Smith': 'A', 'Judy Paxton': 'B+'}
    d2 = {'Mary Louis': 'A', 'Patrick White': 'C'}
    d3 = {}

    for item in (d1, d2):
        # Escribe tu código aquí.

    print(d3)
    ```

5. Escribe un programa que convierta la lista `my_list` en una tupla.

    ```
    my_list = ["car", "Ford", "flower", "Tulip"]

    t =  # Escribe tu código aquí.
    print(t)
    ```

6. Escribe un programa que convierta la tupla `colors` en un diccionario.

    ```
    colors = (("green", "#008000"), ("blue", "#0000FF"))

    # Escribe tu código aquí.

    print(colors_dictionary)
    ```

7. ¿Que ocurrirá cuando se ejecute el siguiente código?

    ```
    my_dictionary = {"A": 1, "B": 2}
    copy_my_dictionary = my_dictionary.copy()
    my_dictionary.clear()

    print(copy_my_dictionary)
    ```

8. ¿Cuál es la salida del siguiente programa?

    ```
    colors = {
        "blanco": (255, 255, 255),
        "gris": (128, 128, 128),
        "rojo": (255, 0, 0),
        "verde": (0, 128, 0)
        }
    
    for col, rgb in colors.items():
        print(col, ":", rgb)
    ```

## Solución cuestionario

1. Pregunta 1

    El programa imprimirá `3` en pantalla. 

2. Pregunta 2

    El programa imprimirá `6` en pantalla. Los elementos de la tupla `tup` han sido "desempaquetados" en las variables `a`, `b`, y `c`.

3. Pregunta 3

    ```
    tup = 1, 2, 3, 2, 4, 5, 6, 2, 7, 2, 8, 9
    duplicates = tup.count(2)

    print(duplicates)    # salida: 4
    ```

4. Pregunta 4

    ```
    d1 = {'Adam Smith': 'A', 'Judy Paxton': 'B+'}
    d2 = {'Mary Louis': 'A', 'Patrick White': 'C'}
    d3 = {}

    for item in (d1, d2):
        d3.update(item)

    print(d3)
    ```

5. Pregunta 5

    ```
    my_list = ["car", "Ford", "flower", "Tulip"]

    t = tuple(my_list)
    print(t)
    ```

6. Pregunta 6

    ```
    colors = (("green", "#008000"), ("blue", "#0000FF"))

    colors_dictionary = dict(colors)
    print(colors_dictionary)
    ```

7. Pregunta 7

    El programa mostrará `{'A': 1, 'B': 2}` en pantalla. 

8. Pregunta 8

    ```
    blanco : (255, 255, 255)
    gris : (128, 128, 128)
    rojo : (255, 0, 0)
    verde : (0, 128, 0)
    ```


