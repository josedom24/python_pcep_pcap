#  LABORATORIO - Cuántos días

## Tiempo Estimado

15 - 20 minutos

## Nivel de Dificultad

Medio

## Objetivos

Familiarizar al estudiante con:

* Proyectar y escribir funciones con parámetros.
* Utilizar la instrucción `return`.
* Utilizar las funciones propias del estudiante.

## Escenario

Tu tarea es escribir y probar una función que toma dos argumentos (un año y un mes) y devuelve el número de días del mes/año dado (mientras que solo febrero es sensible al valor `año`, tendrá 28 o 29 según el tipo de año).

Haz que la función devuelva None si los argumentos no tienen sentido.

Puedes usar la siguiente plantilla:

```
def año_bisiesto(año):
#
# Tu código del laboratorio anterior
#

def dias_del_mes(año, mes):
#
# Escribe tu código aquí.
#

test_years = [1900, 2000, 2016, 1987]
test_months = [2, 2, 1, 11]
test_results = [28, 29, 31, 30]
for i in range(len(test_years)):
	yr = test_years[i]
	mo = test_months[i]
	print(yr, mo, "->", end="")
	result = dias_del_mes(yr, mo)
	if result == test_results[i]:
		print("OK")
	else:
		print("Fallido")
```

Debes usar la función escrita en el laboratorio anterior. Te recomendamos que utilices una lista con los días de los meses. Puedes crearla dentro de la función; este truco acortará significativamente el código.

Hemos preparado un código de prueba, lo puedes ampliar para probar más fechas.

