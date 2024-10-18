# Importación de todas las entidades de un módulo

El tercer método de importación en Python utiliza la siguiente sintaxis:

```
from <modulo> import *
```

En este caso, el nombre de una entidad o la lista de entidades es sustituido por un asterisco (*) lo que permite importar todas las entidades del módulo. 

* Se elimina la necesidad de enumerar cada entidad por separado, pero...
* podemos generar conflictos con nombres ya existentes en el código. Por este motivo, se recomienda usar esta técnica solo de forma temporal y evitarla en código regular.

## Importando un módulo: la palabra clave reservada as

Si no se está conforme con el nombre del módulo, se puede utilizar la palabra clave reservada `as` para asignarle un **alias** o nombre alternativo. Este proceso, conocido como **aliasing o renombrado**, permite que el módulo se identifique con un nombre distinto, lo que puede facilitar su uso o evitar conflictos de nombres.

La sintaxis para renombrar un módulo es:

```
import <modulo> as <alias>
```

Aquí, <modulo> es el nombre original del módulo, mientras que <alias> es el nombre alternativo que se desea usar.

Vemos un ejemplo: si necesitas cambiar la palabra `math`, puedes indicar un alias de la siguiente manera:

```
import math as m
print(m.sin(m.pi/2))
```

Hay que tener en cuenta que si asignamos un alias, no podemos usar el nombre original del módulo.

## Alias de entidades de módulos

También podemos asignarle un alias a una entidad del módulo que hemos importado, para ello:

```
from <modulo> import <entidad> as <alias>
```

Como anteriormente, el nombre original (sin alias) se vuelve inaccesible.

Podemos importar varias entidades y asignarle un alias, para ello empleamos la coma para la separación, de esta manera:

```
from <modulo> import <entidad1> as <alias1>, <entidad2> as <alias2>, ...
```

El ejemplo:

```
from math import pi as PI, sin as sen
print(sen(PI/2))
```

## Cuestionario

1. Quieres invocar la función `make_money()` contenida en el módulo llamado `mint`. Tu código comienza con la siguiente línea: `import mint`. ¿Cuál es la forma adecuada de invocar a la función?

2. Quieres invocar la función `make_money()` contenida en el módulo llamado `mint`. Tu código comienza con la siguiente línea: `from mint import make_money`. ¿Cuál es la forma adecuada de invocar a la función?

3. Has escrito una función llamada `make_money` por tu cuenta. Necesitas importar una función con el mismo nombre del módulo `mint` y no deseas cambiar el nombre de ninguno de tus nombres previamente definidos. ¿Qué variante de la sentencia `import` puede ayudarte con el problema?

4. ¿Qué forma de invocación de la función `make_money` es válida si tu código comienza con la siguiente línea? `from mint import *`

## Solución cuestionario

1. Pregunta 1:

`mint.make_money()`

2. Pregunta 2:

`make_money()`

3. Pregunta 3:

`from mint import make_money as make_more_money`

4. Pregunta 4:

`make_money()`