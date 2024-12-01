# Módulos y namespaces

## Concepto de namespace

Un **namespace** (espacio de nombres) es un espacio en el que existen nombres únicos y no entran en conflicto entre sí. En términos sencillos, es como un sistema que asegura que los nombres dentro de un grupo o contexto no se repitan. Puedes pensar en un grupo social como un namespace donde cada miembro tiene un nombre único. Así, no se da el caso de que dos personas dentro de un grupo tengan el mismo nombre.

Para ilustrar cómo funciona un namespace, algunos ejemplos comunes serían:

* Apodos dentro de un grupo pequeño (por ejemplo, en una clase).
* Identificadores especiales, como el número de DNI, que permite a cada persona tener un número único.

## Importancia de los namespaces

* Dentro de un determinado namespace, cada nombre debe permanecer único.  
* Si importamos un módulo (un módulo es de hecho un archivo fuente de Python), se hacen conocidos todos los nombres definidos en el módulo, pero no se incluyen en el namespace del código.
* En un namespace, si dos entidades (como variables o funciones) tienen el mismo nombre, uno puede sobrescribir al otro. Sin embargo, cuando importas un módulo en Python, los nombres definidos dentro de ese módulo no se agregan automáticamente al namespace de tu código. Esto significa que puedes tener tus propias variables o funciones con el mismo nombre que las que están en el módulo, y no habrá conflicto.

## Ejemplo con el módulo math

Cuando importas el módulo `math`, las entidades como `pi` o `sin()` se definen dentro de ese módulo y no afectan directamente al namespace de tu código. Si tienes una variable o función llamada `pi` en tu código, no se sobrescribirá con la constante `pi` del módulo `math`. Para acceder a las entidades del módulo, debes usar el nombre del módulo seguido de un punto, como en `math.pi`. Esto es obligatorio y garantiza que el código pueda distinguir entre el namespace del módulo y cualquier otra variable o función que puedas haber definido en tu código.

Por ejemplo, si quieres imprimir el resultado de sin(½π), el código sería:

```
import math
print(math.sin(math.pi/2))
```

Si eliminas el uso del nombre del módulo (`math.`), el código fallará, ya que no sabrá de qué módulo provienen las entidades `pi` o `sin`.

## Coexistencia de dos namespace

En este ejemplo, se demuestra cómo pueden coexistir dos namespaces sin que se sobrescriban entre sí, incluso si ambos contienen entidades con el mismo nombre (como `pi` o `sin`).

En el código se ha definido una función `sin` y una variable `pi` en tu propio namespace, mientras que el módulo `math` también tiene una función `sin` y una constante `pi`.


```
import math

def sin(x):
    if 2 * x == pi:
        return 0.99999999
    else:
        return None

pi = 3.14

print(sin(pi/2))        # Usará tu propia definición de sin y pi.
print(math.sin(math.pi/2))  # Usará la función sin y pi del módulo math.
```

Esto demuestra que aunque ambos namespaces contienen entidades con los mismos nombres (`sin` y `pi`), no interfieren entre sí. El uso del nombre del módulo (`math.`) garantiza que se utilicen las entidades correctas del módulo, incluso si tu propio código también tiene entidades con los mismos nombres.