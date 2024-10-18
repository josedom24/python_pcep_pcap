# El módulo platform

El módulo `platform` en Python proporciona herramientas para obtener información sobre el entorno en el que se está ejecutando el programa, específicamente sobre el sistema operativo y el hardware. Esto es útil cuando se desea conocer la ubicación del programa dentro del entorno del ordenador, que consta de varias capas:

1. **Código (en ejecución)**: Es la capa más alta, donde el código de Python se ejecuta.
2. **Entorno de ejecución de Python**: Directamente debajo del código, el entorno de Python permite interactuar con el sistema operativo.
3. **Sistema operativo (SO)**: Ofrece servicios a Python para manejar archivos, procesos, y otros recursos.
4. **Hardware**: En la base de la pirámide, el hardware se encarga de los dispositivos físicos como el procesador, discos, interfaces de red y dispositivos de entrada (teclado, ratón).

El módulo `platform` permite obtener información sobre el sistema operativo, como el nombre y características del hardware. Esto puede ser útil para tareas como verificar la compatibilidad de un programa con el entorno de ejecución.

Veamos un ejemplo:

```
import platform

print("Sistema operativo:", platform.system())
print("Versión del sistema operativo:", platform.version())
print("Nombre del nodo de la red:", platform.node())
```

El módulo `platform` es útil para obtener esta información sin necesidad de interactuar directamente con el sistema operativo, permitiendo que el programa se adapte mejor al entorno en el que se ejecuta.

## Función `platform()`

La función `platform()` devuelve una cadena que describe el entorno de la plataforma actual. Existen dos parámetros que modifican la salida:

- `aliased`: Si se establece en `True` (o cualquier valor distinto de cero), se mostrarán nombres alternativos para las capas subyacentes.
- `terse`: Si se establece en `True`, se presentará una versión más corta de la descripción.

Ejemplo:

```
from platform import platform

print(platform())        # Muestra la plataforma completa.
print(platform(1))       # Usa nombres alternativos para las capas.
print(platform(0, 1))    # Usa nombres alternativos y muestra una forma más breve.
```

## La función machine

La función `machine()` nos devuelve  el nombre genérico del procesador que ejecuta el sistema operativo. Ejemplo:

```
from platform import machine
print(machine())
```

## La función processor

La función `processor()` devuelve una cadena con el nombre real del procesador (si lo fuese posible, en ocasiones devuelve una cadena vacía).

Ejemplo:
```
from platform import processor
print(processor())
```

## La función system

La función `system()` devuelve el nombre genérico del sistema operativo en una cadena.

Ejemplo:

```
from platform import system
print(system())
```

## La función version

La versión del sistema operativo se proporciona como una cadena por la función `version()`.

Ejemplo:

```
from platform import version
print(version())
```

## Las funciones python_implementation y python_version_tuple

Si necesitas saber que versión de Python está ejecutando tu código, puedes verificarlo utilizando una serie de funciones dedicadas, aquí hay dos de ellas:

* `python_implementation()`: devuelve una cadena que denota la implementación de Python (normalmente será "CPython").
* `python_version_tuple()`: devuelve una tupla de tres elementos la cual contiene:
    * La parte mayor de la versión de Python.
    * La parte menor.
    * El número del nivel de parche.

Ejemplo:
```
from platform import python_implementation, python_version_tuple
print(python_implementation())
for atr in python_version_tuple():
    print(atr)
```

## Índice de Módulos de Python

Los **módulos de Python** son una parte esencial del ecosistema de Python, proporcionando funciones y herramientas para ampliar las capacidades del lenguaje. Mientras que en esta clases solo se han cubierto los conceptos básicos, el universo de los módulos es vasto y extenso.

Python es solo una "galaxia" dentro de un universo de módulos que abarcan una amplia variedad de aplicaciones, desde genética hasta astrología. Además de los módulos estándar que vienen con Python, existen cientos de módulos adicionales creados y mantenidos por la comunidad, que no se distribuyen junto con Python, lo que amplía aún más las posibilidades de uso del lenguaje.

* **Documentación oficial de módulos de Python**: [Índice de módulos de Python](https://docs.python.org/3/py-modindex.html).

Aunque no es necesario aprender todos los módulos, es importante saber cómo encontrarlos y usarlos de manera efectiva para las necesidades específicas de cada proyecto.

## Cuestionario

1. ¿Cuál es el valor esperado de la variable result después de que se ejecuta el siguiente código?
```
import math
result = math.e == math.exp(1)
```

2. (Completa el enunciado) Establecer la semilla del generador con el mismo valor cada vez que se ejecuta tu programa garantiza que ...
3. ¿Cuál de las funciones del módulo platform utilizarías para determinar el nombre del CPU que corre dentro de tu computadora?
4. ¿Cuál es el resultado esperado del siguiente fragmento de código?
```
import platform
print(len(platform.python_version_tuple()))
```

## Solución cuestionario

1. Pregunta 1:

`True`

2. Pregunta 2:

 ... los valores pseudoaleatorios emitidos desde el módulo `random` serán exactamente los mismos.

3. Pregunta 3:

La función `processor()`

4. Pregunta 4:

`3`
