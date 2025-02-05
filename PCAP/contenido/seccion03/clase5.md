# Nuestro primer paquete (2ª parte)

## Paso 5

La estructura del paquete finalmente toma forma con la presencia del archivo `__init__.py`. Este archivo no solo debe estar en la carpeta raíz del paquete, sino que también puede colocarse en cualquier subcarpeta (subpaquete) si se necesita inicialización o un tratamiento especial para ciertos módulos.

```
ciencia
├── animales
│   ├── mamiferos
│   │   ├── perro.py
│   │   └── gato.py
│   └── aves.py
├── plantas
│   ├── arboles.py
│   └── flores.py
├── __init__.py
└── clima.py
```

Esto permite que subpaquetes específicos se comporten de manera independiente, si así lo requieren. Ahora, con la estructura del paquete completa, la siguiente pregunta es: **¿dónde colocar esta estructura para que Python la reconozca?** La respuesta es simple: **en cualquier lugar**, siempre y cuando le indiques a Python dónde está ubicada, utilizando los métodos ya conocidos para modificar la ruta de acceso.

## Paso 6

Imagina que has configurado tu entorno de trabajo correctamente y que el árbol de módulos y subpaquetes está listo, con los archivos `__init__.py` en su lugar y la ruta de acceso ajustada para que Python pueda localizar el paquete.

```
dir
├── modulos
│   └── module.py
├── paquetes
│   └── ciencia
│       ├── animales
│       │   ├── mamiferos
│       │   │   ├── perro.py
│       │   │   └── gato.py
│       │   └── aves.py
│       ├── plantas
│       │   ├── arboles.py
│       │   └── flores.py
│       ├── __init__.py
│       └── clima.py
└── programas
    ├── programa1.py
    ├── programa2.py
    └── ...
```

El próximo paso será continuar con tus pruebas utilizando el archivo `programa3.py`.

## Paso 7

Para acceder a la función `Predecir()` del módulo `clima` dentro del paquete `ciencia`, es necesario utilizar **nombres de paquetes calificados**, lo que significa que se debe especificar la ruta completa del módulo desde la raíz del paquete. Esta práctica asegura que Python pueda ubicar el módulo correcto dentro de la jerarquía de carpetas y subcarpetas.

Por ejemplo, el archivo `programa3.py` se modifica de la siguiente manera:

```
from sys import path
path.append('../paquetes')

import ciencia.clima
import ciencia.animales.aves

print(ciencia.clima.Predecir())
print(ciencia.animales.aves.Volar())

from ciencia.clima import Predecir
print(Predecir())
```

En este caso:

* La variable `path` se ajusta para que Python pueda localizar el paquete `ciencia`.
* Se utiliza un **import calificado**, que apunta a la ruta completa del módulo desde el paquete raíz.
* También existe una **variante válida** para acceder a la función `Predecir()` sin tener que hacer referencia a todo el nombre del paquete cada vez. Aquí se importa **directamente la función** `Predecir()` desde el módulo `clima`, evitando la necesidad de usar el nombre calificado del paquete en el cuerpo del código, aunque sigue siendo necesario para la importación.

## Paso 8

Ahora que tienes acceso a los módulos `perro` y `gato` dentro del subpaquete `mamiferos`, puedes usarlos en tu código utilizando importaciones calificados. A continuación te mostramos cómo hacerlo, en el fichero `programa4.py`:

```
from sys import path

path.append('../paquetes')

import ciencia.animales.mamiferos.perro
from ciencia.animales.mamiferos.gato import Maullar

print(ciencia.animales.mamiferos.perro.Ladrar())
print(Maullar())
```

También puedes usar **alias** para simplificar el código y hacer las importaciones más legibles, lo vemos en el fichero `programa5.py`:

```
from sys import path

path.append('../paquetes')

import ciencia.plantas.arboles as arboles
import ciencia.plantas.flores as flores

print(arboles.Crecer())
print(flores.Florecer())
```

## Paso 9

En este paso, imaginamos que todo el subdirectorio desde la carpeta `ciencia` ha sido comprimido en un archivo comprimido llamado `cienciapack.zip`, el cual se coloca en la carpeta `paquetes`. Ahora puedes usar este archivo zip como un paquete en tu código, lo vemos en el `programa6.py`:

```
from sys import path

path.append('../paquetes/cienciapack.zip')

import ciencia.plantas.arboles as arboles
import ciencia.plantas.flores as flores
from ciencia.animales.mamiferos.perro import Ladrar
from ciencia.animales.mamiferos.gato import Maullar
from ciencia.clima import Predecir

print(arboles.Crecer())
print(flores.Florecer())
print(Ladrar())
print(Maullar())
print(Predecir())
```

Este método te permite gestionar y acceder a tus módulos como si fueran parte de un paquete comprimido, lo que resulta útil para distribuir y organizar código.

## Cuestionario

1. Deseas evitar que el usuario de tu módulo ejecute tu código como un script ordinario. ¿Cómo lograrías tal efecto?

2. Algunos paquetes adicionales y necesarios se almacenan dentro del directorio `~/Python/Project/Modules`. Escribe un código asegurándote de que Python recorra el directorio para encontrar todos los módulos solicitados.

3. El directorio mencionado en el ejercicio anterior contiene un subárbol con la siguiente estructura:

    ```
    abc
     |__ def
          |__ mymodule.py
    ```

    Asumiendo que `~/Python/Project/Modules` se ha adjuntado con éxito a la lista `sys.path`, escribe una directiva de importación que te permita usar todas las entidades de `mymodule`.

## Solución cuestionario

1. Pregunta 1

    ```
    import sys

    if __name__ == "__main__":
        print "¡No hagas eso!"
        sys.exit()
    ```

2. Pregunta 2
    ```
    import sys

    # ¡Toma en cuenta las diagonales invertidas dobles!
    sys.path.append("~/Python/Project/Modules")
    ```

3. Pregunta 3
    
    `import abc.def.mymodule`
