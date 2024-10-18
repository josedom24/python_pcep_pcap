# La función dir()

La función `dir()` en Python revela los nombres de todas las entidades disponibles dentro de un módulo previamente importado. Aunque no tiene relación con el comando `dir` de terminales, funciona de manera similar al listar los nombres de las funciones, variables y otros elementos dentro de un módulo.

Podemos usar directamente la función:

```
import math
dir(math)
```

Podemos observar que la función devuelve una lista con las entidades, por lo tanto si queremos imprimir cada uno de los nombres podemos ejecutar el siguiente código:

```
import math

for name in dir(math):
    print(name, end="\t")
```

Esos nombres incluyen funciones matemáticas familiares, como `sin`, `cos` y `pi`, además de otros elementos con doble guion bajo (__), que tienen significados especiales.

