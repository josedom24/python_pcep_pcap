# Nuestro primer módulo (1ª parte)

En los siguientes dos apartados vamos a estudiar los pasos para crear nuestro primer módulo. Para ello vamos a seguir los siguientes pasos:

## Paso 1: Creación del archivo `module.py`

El primer paso es crear un archivo vacío llamado `module.py`, que será el módulo que usaremos. Aunque esté vacío al principio, será llenado con código más adelante. Se recomienda crear un nuevo directorio vacío para trabajar con estos ficheros.

## Paso 2: Creación del archivo `main.py`

El segundo archivo es `main.py`, que contiene la línea `import module`. Ambos archivos deben estar en la misma carpeta. 

Al ejecutar `main.py`, no deberías ver nada, lo que indica que Python ha importado correctamente el módulo vacío. Después de esto, notarás una nueva subcarpeta llamada `__pycache__` que contiene un archivo compilado del módulo (`module.cpython-xy.pyc`).

El archivo `.pyc` es una versión semi-compilada del módulo que Python genera automáticamente para optimizar futuras importaciones. Este proceso es transparente para el usuario, y Python solo recompila el archivo si detecta cambios en el módulo fuente.

## Paso 3: Actualización de `module.py`

Se añade contenido al archivo `module.py`:

```
print("Me gusta ser un módulo.")
```

Este archivo puede ejecutarse como cualquier otro script. Al hacerlo, la consola mostrará: `Me gusta ser un módulo.`

Hasta este punto, no hay diferencias entre un módulo y un script ordinario.

## Paso 4: Importación en `main.py`

El archivo `main.py` sigue conteniendo solo la línea `import module`. Al ejecutarlo, deberías ver la misma salida en la consola: `Me gusta ser un módulo.`

Esto ocurre porque, cuando un módulo es importado, su contenido se ejecuta automáticamente. Sin embargo, esta inicialización solo sucede la primera vez que se importa, evitando repeticiones innecesarias. Python recuerda qué módulos ya han sido importados.

## Paso 5: Uso de la variable `__name__`

Python asigna a cada archivo una variable especial llamada `__name__`. Al modificar `module.py` de la siguiente manera:

```
print("Me gusta ser un módulo.")
print(__name__)
```

Si ejecutas `module.py` directamente, verás:

```
Me gusta ser un módulo.
__main__
```

Si ejecutas `main.py` con el módulo importado, la salida será:

```
Me gusta ser un módulo.
module
```

Podemos decir:

* Que cuando se ejecuta un archivo directamente, la variable `__name__` se establece en `__main__`. 
* Cuando el archivo es importado como un módulo, `__name__` toma el nombre del archivo (excluyendo la extensión `py`).

