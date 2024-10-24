# LABORATORIO: Días de la semana

## Tiempo Estimado

30 - 60 minutos

## Nivel de Dificultad

Fácil/Medio

## Objetivos

* Mejorar las habilidades del estudiante para definir clases desde cero.
* Definir y usar variables de instancia.
* Definir y usar métodos.

## Escenario

Tu tarea es implementar una clase llamada `Weeker` que almacena y manipula los días de la semana.

El constructor de la clase acepta un argumento: una cadena. La cadena representa el nombre del día de la semana y los únicos valores aceptables deben provenir del siguiente conjunto:

`Lun Mar Mie Jue Vie Sab Dom`

Invocar al constructor con un argumento desde fuera de este conjunto debería generar la excepción `WeekDayError` (defínela tu mismo). La clase debe proporcionar las siguientes facilidades:

* Los objetos de la clase deben ser "imprimibles", es decir, deben poder convertirse implícitamente en cadenas de la misma forma que los argumentos del constructor. 
* La clase debe estar equipada con métodos de un parámetro llamados `add_days(n)` y `subtract_days(n)`, siendo `n` un número entero que actualiza el día de la semana almacenado dentro del objeto mediante el número de días indicado, hacia adelante o hacia atrás.
* Todas las propiedades del objeto deben ser privadas.

Puedes usar la siguiente plantilla:

```
class WeekDayError(Exception):
    pass
	

class Weeker:
    #
    # Escribir código aquí.
    #

    def __init__(self, day):
        #
        # Escribir código aquí.
        #

    def __str__(self):
        #
        # Escribir código aquí.
        #

    def add_days(self, n):
        #
        # Escribir código aquí.
        #

    def subtract_days(self, n):
        #
        # Escribir código aquí.
        #


try:
    weekday = Weeker('Lun')
    print(weekday)
    weekday.add_days(15)
    print(weekday)
    weekday.subtract_days(23)
    print(weekday)
    weekday = Weeker('Lun')
except WeekDayError:
    print("Lo siento, no puedo atender tu solicitud.")
```

## Salida Esperada
```
Lun
Mar
Dom
Lo siento, no puedo atender tu solicitud.
```

