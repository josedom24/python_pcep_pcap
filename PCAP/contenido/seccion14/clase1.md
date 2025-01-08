# El módulo os

El módulo `os` en Python permite interactuar con el sistema operativo y proporciona funciones disponibles en sistemas Linux y Windows. Algunas de sus capacidades incluyen la creación de directorios (como el comando `mkdir`), realizar operaciones en archivos y directorios, obtener información sobre el sistema operativo, manejar procesos y operar en streams de E/S usando descriptores de archivos.

##  Obtener información del sistema operativo

El módulo `os` en Python permite obtener información sobre el sistema operativo actual utilizando la función `uname`, que devuelve un objeto con varios atributos:

* **systemname**: almacena el nombre del sistema operativo.
* **nodename**: almacena el nombre de la máquina en la red.
* **release**: almacena la versión del sistema operativo.
* **version**: almacena detalles sobre la versión del sistema operativo.
* **machine**: almacena el identificador de hardware (por ejemplo, `x86_64`).

```
import os
print(os.uname())
```

La función `uname` está disponible principalmente en sistemas Linux. En Windows, se puede utilizar la función del módulo `platform` para obtener información similar.

Además, el módulo `os` permite identificar rápidamente el sistema operativo mediante el atributo `name`, que puede devolver:

* **posix**: si se usa Linux.
* **nt**: si se usa Windows.
* **java**: si el código está escrito en Jython.

```
import os
print(os.name)
```

## Creando directorios

El módulo `os` proporciona la función `mkdir`, que permite crear un directorio, similar al comando `mkdir` en Linux y Windows. La función `mkdir` requiere una ruta que puede ser relativa o absoluta. A continuación, se presentan ejemplos de diferentes tipos de rutas:

* **Ruta relativa**: `my_first_directory` creará el directorio en el directorio de trabajo actual.
* **Ruta relativa explícita**: `./my_first_directory` apunta al directorio de trabajo actual y tiene el mismo efecto que la anterior.
* **Ruta relativa al directorio superior**: `../my_first_directory` creará el directorio en el directorio padre del actual.
* **Ruta absoluta**: `/python/my_first_directory` creará el directorio en la ruta absoluta que comienza desde el directorio raíz.

```
import os

os.mkdir("my_first_directory")
print(os.listdir())
```

La función `mkdir` genera un error `FileExistsError` si intentas crear un directorio que ya existe. Además, puede aceptar un argumento opcional `mode` para especificar los permisos del directorio, aunque en algunos sistemas este argumento puede ser ignorado. Para cambiar los permisos de un directorio, se recomienda utilizar la función `chmod`, que funciona como el comando `chmod` en Linux.

En el ejemplo, también se utiliza la función `listdir`, que devuelve una lista de los nombres de archivos y directorios en la ruta especificada. Si no se proporciona un argumento, `listdir` utilizará el directorio de trabajo actual. Esta función omite las entradas `.` y `..`, que son comunes en los resultados de comandos de consola.

## Creación recursiva de directorios

La función `mkdir` es útil para crear un solo directorio, pero si necesitas crear un directorio dentro de otro ya creado, puedes usar la función `makedirs`. Esta función permite la creación recursiva de directorios, lo que significa que se crearán todos los directorios en la ruta especificada sin necesidad de crear cada uno manualmente.

```
import os

os.makedirs("my_first_directory/my_second_directory")
os.chdir("my_first_directory")
print(os.listdir())
```

En este ejemplo, se crean dos directorios: `my_first_directory` y `my_second_directory`, donde el segundo se encuentra dentro del primero. Al usar `makedirs`, no es necesario cambiar manualmente al directorio `my_first_directory` para crear `my_second_directory`. 

Para cambiar el directorio de trabajo actual, se utiliza la función `chdir`, que toma como argumento cualquier ruta relativa o absoluta.

## Averiguar el directorio donde estamos

El módulo `os` proporciona una función llamada `getcwd` que te permite conocer el directorio de trabajo actual. Esta función es útil cuando navegas en estructuras de directorios grandes y necesitas saber en qué directorio te encuentras.

```
import os

os.makedirs("my_first_directory/my_second_directory")
os.chdir("my_first_directory")
print(os.getcwd())
os.chdir("my_second_directory")
print(os.getcwd())
```

En este ejemplo, primero se crean los directorios `my_first_directory` y `my_second_directory`. Luego, se cambia el directorio de trabajo actual a `my_first_directory` y se imprime la ruta del directorio actual. Después, al cambiar al directorio `my_second_directory`, se vuelve a imprimir la ruta del directorio actual.

## Eliminar directorios

El módulo `os` ofrece funciones para eliminar directorios, permitiendo borrar tanto un solo directorio como directorios que contienen subdirectorios.

Para eliminar un solo directorio, se utiliza la función `rmdir`, que requiere la ruta del directorio como argumento. A continuación, se muestra un ejemplo:

```
import os

os.mkdir("my_first_directory")
print(os.listdir())  
os.rmdir("my_first_directory")  
print(os.listdir())  
```

En este caso, el primer `print` muestra el directorio creado, y el segundo `print` debería devolver una lista vacía, confirmando que el directorio ha sido eliminado.

Para eliminar un directorio que contiene subdirectorios, se utiliza la función `removedirs`, que también requiere una ruta completa. Aquí hay un ejemplo:

```
import os

os.makedirs("my_first_directory/my_second_directory")  
os.removedirs("my_first_directory/my_second_directory") 
print(os.listdir())  
```

Al utilizar `rmdir` o `removedirs`, el directorio debe existir y estar vacío, de lo contrario, se generará una excepción.

## Ejecución de comandos


La función `system()` del módulo `os` permite ejecutar comandos del sistema operativo desde Python. Esta función acepta un comando en forma de cadena y se puede utilizar tanto en Windows como en sistemas Linux.

* En **Windows**, `system()` devuelve el valor devuelto por el shell tras ejecutar el comando.
* En **Linux**, devuelve el estado de salida del proceso ejecutado.

```
import os

returned_value = os.system("mkdir my_first_directory")
print(returned_value)  # Imprime el valor devuelto por el comando
```
Al ejecutar el código anterior, se espera un resultado de `0`, que indica que el comando se ejecutó con éxito en sistemas Linux. Este resultado significa que el directorio `my_first_directory` se ha creado correctamente.

Este enfoque proporciona una forma directa de interactuar con el sistema operativo mediante comandos, aunque es importante considerar que la ejecución de comandos de esta manera puede ser menos segura que utilizar funciones específicas de Python para operaciones de archivos y directorios.

## Cuestionario

1. ¿Cuál es el resultado del siguiente fragmento si se ejecuta en Linux?
    ```
    import os
    print(os.name)
    ```

2. ¿Cuál es el resultado del siguiente fragmento de código?

    ```
    import os

    os.mkdir("hello")
    print(os.listdir())
    ```

## Solución cuestionario

1. Ejercicio 1

    `posix`

2. Ejercicio 2

    `['hello']`