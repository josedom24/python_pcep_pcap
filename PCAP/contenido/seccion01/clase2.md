# Importación de módulos

Para utilizar un módulo en Python, es necesario **importarlo**. La importación de módulos se realiza mediante la instrucción `import`, que es una palabra clave reservada en Python.

Por ejemplo, si deseas utilizar dos entidades del módulo math (por ejemplo, la constante `π` y la función `sin()`), primero debes importar el módulo de la siguiente manera:

```
import math
```

En esta instrucción:

* `import` es la palabra reservada para importar un módulo.
* `math` es el nombre del módulo que se quiere importar.

Una vez importado, puedes acceder a las entidades del módulo usando la sintaxis `math.entidad`, como:

```
print(math.pi)  # Imprime el valor de π
print(math.sin(30))  # Calcula el seno de 30 grados
```

Si queremos importar varios módulos tenemos dos opciones: repitiendo la instrucción import o listando varios módulos separados por comas:

```
import math
import sys
```

o

```
import math, sys
```

Consideraciones:

* La instrucción `import` puede colocarse en cualquier parte del código, pero debe hacerse antes de usar cualquiera de las entidades del módulo.
* Se pueden importar múltiples módulos a la vez, y la lista de módulos puede ser arbitrariamente larga.

## Concepto de Namespace

Un **namespace** (espacio de nombres) es un espacio en el que existen nombres únicos y no entran en conflicto entre sí. En términos sencillos, es como un sistema que asegura que los nombres dentro de un grupo o contexto no se repitan. Puedes pensar en un grupo social como un namespace donde cada miembro tiene un nombre único. Así, no se da el caso de que dos personas dentro de un grupo tengan el mismo nombre.

Para ilustrar cómo funciona un namespace, algunos ejemplos comunes serían:

* Apodos dentro de un grupo pequeño (por ejemplo, en una clase).
* Identificadores especiales, como el número de DNI, que permite a cada persona tener un número único.

## Importancia de los namespaces

* Dentro de un determinado namespace, cada nombre debe permanecer único.  
* Si importamos un módulo (un módulo es de hecho un archivo fuente de Python), se hacen conocidos todos los nombres definidos en el módulo, pero no se incluyen en el namespace del código.
* En un namespace, si dos entidades (como variables o funciones) tienen el mismo nombre, uno puede sobrescribir al otro. Sin embargo, cuando importas un módulo en Python, los nombres definidos dentro de ese módulo no se agregan automáticamente al namespace de tu código. Esto significa que puedes tener tus propias variables o funciones con el mismo nombre que las que están en el módulo, y no habrá conflicto.

## Ejemplo con el módulo math

Cuando importas el módulo `math`, las entidades como `pi` o `sin()` se definen dentro de ese módulo y no afectan directamente al namespace de tu código. Si tienes una variable o función llamada `pi` en tu código, no se sobrescribirá con la constante `pi` del módulo `math`. Para acceder a las entidades del módulo, debes usar el nombre del módulo seguido de un punto, como en `math.pi`. Ejemplo:

```
import math

# Aquí accedemos a la constante pi del módulo math
print(math.pi)
```
De esta manera, el módulo y sus nombres permanecen en su propio espacio, y tú puedes mantener nombres en tu código sin que se sobrescriban.
