# LABORATORIO: Leer enteros de forma segura

## Tiempo Estimado

15 - 25 minutos

## Nivel de Dificultad

Medio

## Objetivos

* Mejorar las habilidades del alumno al definir funciones.
* Utilizar excepciones para proporcionar un entorno de entrada más seguro.

## Escenario

Tu tarea es escribir una **función capaz de leer valores enteros y verificar si están dentro de un rango especificado**.

La función deberá:

* Aceptar tres argumentos: un mensaje, un límite inferior aceptable y un límite superior aceptable.
* Si el usuario ingresa una cadena que no es un valor entero, la función debe emitir el mensaje `Error: entrada incorrecta`, y solicitará al usuario que ingrese el valor nuevamente.
* Si el usuario ingresa un número que está fuera del rango especificado, la función debe emitir el mensaje `Error: el valor no está dentro del rango permitido (min..max)` y solicitará al usuario que ingrese el valor nuevamente.
* Si el valor de entrada es válido, será devuelto como resultado.

Puedes esta plantilla para realizar tu programa:

```
def read_int(prompt, min, max):
    #
    # Escribe tu código aquí.
    #


v = read_int("Ingresa un número entre -10 a 10: ", -10, 10)

print("El número es:", v)
```

## Datos de Prueba

Así es como la función debería reaccionar ante la entrada del usuario:

```
Ingresa un número entre -10 a 10: 100
Error: el valor no está dentro del rango permitido (-10..10)
Ingresa un número entre -10 a 10: asd
Error: entrada incorrecta
Ingresa un número entre -10 a 10: 1
El número es: 1
```