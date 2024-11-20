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

