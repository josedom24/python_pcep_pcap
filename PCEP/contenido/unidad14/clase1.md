# Ejemplo 1: Cálculo del IMC

Definamos una función que calcula el **Índice de Masa Corporal (IMC)**.
El IMC es igual al peso en kilogramos dividido por la altura en metros al cuadrado:

![imc](img/imc.png)

Como puedes observar, la formula necesita dos valores:

* peso (originalmente en kilogramos).
* altura (originalmente en metros).

La nueva función tendrá dos parámetros. Su nombre será `imc`:

```
def imc(weight, height):
    return weight / height ** 2


print(imc(52.5, 1.65))
```

El resultado del ejemplo anterior es el siguiente: `19.283746556473833`.

La función hace lo que deseamos, pero es un poco sencilla - asume que los valores de ambos parámetros son significativos. Se debe comprobar que son confiables.

Vamos a comprobar ambos y regresar None si cualquiera de los dos es incorrecto.

def bmi(weight, height):
    if height < 1.0 or height > 2.5 or \
    weight < 20 or weight > 200:
        return None

    return weight / height ** 2


print(bmi(352.5, 1.65))

Observa el código en el editor. Hay dos cosas a las cuales hay que prestar atención.

Primero, se asegura que los datos que sean ingresados sean correctos, de lo contrario la salida será:
None

salida

Segundo, observa como el símbolo de diagonal invertida (\) es empleado. Si se termina una línea de código con el, Python entenderá que la línea continua en la siguiente.

Esto puede ser útil cuando se tienen largas líneas de código y se desea que sean más legibles.

Sin embargo, hay algo que omitimos: las medias en sistema inglés. La función no es útil para personas que utilicen libras, pies y pulgadas.

¿Qué podemos hacer por ellos?

Escribimos dos funciones sencillas para convertir unidades del sistema inglés al sistema métrico. Comencemos con las pulgadas.

Es bien conocido que 1 lb = 0.45359237 kg. Esto lo emplearemos en nuestra nueva función.

Esta función se llamará lb_to_kg:
def lb_to_kg(lb):
    return lb * 0.45359237


print(lb_to_kg(1))


El resultado de la prueba es el siguiente:
0.45359237

salida

Haremos lo mismo ahora con los pies y pulgadas: 1 ft = 0.3048 m, y 1 in = 2.54 cm = 0.0254 m.

La función se llamará ft_and_inch_to_m:
def ft_and_inch_to_m(ft, inch):
    return ft * 0.3048 + inch * 0.0254


print(ft_and_inch_to_m(1, 1))


El resultado de una prueba rápida es:
0.3302

salida

Resulta como esperado.

Nota: queríamos nombrar el segundo parámetro solo in, no inch, pero no pudimos. ¿Sabes por qué?

in es una palabra clave reservada de Python â no se puede usar como nombre.

Vamos a convertir seis pies a metros:
print(ft_and_inch_to_m(6, 0))


Esta es la salida:
1.8288000000000002

salida

Es muy posible que en ocasiones se desee utilizar solo pies sin pulgadas. ¿Python nos ayudará? Por supuesto que si.

Se ha modificado el código un poco:
def ft_and_inch_to_m(ft, inch = 0.0):
    return ft * 0.3048 + inch * 0.0254


print(ft_and_inch_to_m(6))


Ahora el parámetro inch tiene como valor predeterminado el 0.0.

El código produce la siguiente salida, esto es lo que se esperaba:
1.8288000000000002

salida

Finalmente, el código es capaz de responder a la pregunta: ¿Cuál es el IMC de una persona que tiene 5'7" de altura y un peso de 176 lbs?

Este es el código que hemos construido:
def ft_and_inch_to_m(ft, inch = 0.0):
    return ft * 0.3048 + inch * 0.0254


def lb_to_kg(lb):
    return lb * 0.45359237


def bmi(weight, height):
    if height < 1.0 or height > 2.5 or weight < 20 or weight > 200:
        return None
    
    return weight / height ** 2


print(bmi(weight = lb_to_kg(176), height = ft_and_inch_to_m(5, 7)))


La respuesta es:
27.565214082533313

salida

Ejecuta el código y pruébalo.

    Sandbox

Code
def bmi(weight, height):
if height < 1.0 or height > 2.5 or \
weight < 20 or weight > 200:
return None

return weight / height ** 2


print(bmi(352.5, 1.65))

    Console

