# Importación de entidades de un módulo

En Python también podemos importar una entidad o varias de un módulo. Con este método se especifica exactamente qué entidades de un módulo se desean importar al namespace del código. Este método usa la sintaxis:
```
from <moodulo> import <entidad>
```
La instrucción consta de los siguientes elementos:

* La palabra clave `from`: indica que se va a importar de un módulo.
* El nombre del módulo: el módulo del que se van a importar las entidades.
* La palabra clave `import`: señala que se va a importar algo desde el módulo.
* El nombre o lista de nombres de las entidades: las entidades específicas del módulo que serán importadas.

Con este método conseguimos dos cosas:

* **Importación selectiva**: solo se importan las entidades listadas, no todo el módulo.
* **Acceso directo**: las entidades importadas se pueden usar directamente en el código sin necesidad de anteponer el nombre del módulo.

## Ejemplo de importación selectiva

```
from math import sin, pi

print(sin(pi/2))
```

En este ejemplo, solo se importan `sin` y `pi` del módulo `math`. Esto produce el mismo resultado que el ejemplo anterior, donde se utilizó `math.sin` y `math.pi`. La principal diferencia es que ahora no es necesario usar el prefijo `math.`.

Hay que tener en cuenta, que si intentamos entidades no importadas de esta manera (como `math.e`), Python generará un error, ya que solo las entidades específicamente listadas son accesibles.

Este método hace que el código sea más simple visualmente, pero tiene implicaciones más profundas en cómo se gestionan los nombres y el namespace.

## Gestión de nombres y namespace

Veamos cómo las importaciones selectivas de entidades desde un módulo pueden reemplazar definiciones previas dentro del mismo namespace. A continuación, se explica paso a paso el funcionamiento del código:

```
pi = 3.14

def sin(x):
    if 2 * x == pi:
        return 0.99999999
    else:
        return None

print(sin(pi / 2))

from math import sin, pi

print(sin(pi / 2))
```

En resumen:
* Las primeras líneas definen funciones y variables locales.
* La importación desde el módulo `math` reemplaza las definiciones previas de `pi` y `sin`, y el resultado de `sin(pi / 2)` cambia a 1.0 en lugar de 0.99999999.

Esto muestra cómo las importaciones selectivas pueden reemplazar las definiciones locales en el namespace, afectando el comportamiento del código.