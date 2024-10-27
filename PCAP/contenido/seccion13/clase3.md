# Abriendo y cerrando los archivos

## Abrir archivos  con `open()`

La sintaxis básica para abrir un archivo es:

```
stream = open(file, mode='r', encoding=None)
```

* **`file`**: Especifica el nombre del archivo que se va a abrir.
* **`mode`**: Indica el modo de apertura del archivo, es decir, si será para lectura, escritura, etc. Si no se especifica, el valor predeterminado es lectura en modo texto (`'r'`).
* **`encoding`**: Define la codificación de caracteres (por ejemplo, `UTF-8`). Es útil para archivos de texto. Si no se define, la codificación predeterminada depende del sistema.

## Modos básicos de apertura:

1. **`r` (lectura)**:
   * Abre el archivo en modo lectura.
   * El archivo **debe existir**; de lo contrario, se generará una excepción `FileNotFoundError`.

2. **`w` (escritura)**:
   * Abre el archivo en modo escritura.
   * Si el archivo no existe, se **crea**. Si existe, se **trunca** (su contenido se borra).
   * Si no puede crear o truncar el archivo (por permisos, por ejemplo), generará una excepción.

3. **`a` (adjuntar)**:
   * Abre el archivo en modo adjuntar.
   * Si el archivo no existe, se **crea**. Si ya existe, el **cabezal de escritura** se coloca al final del archivo, sin borrar el contenido anterior.

4. **`r+` (lectura y actualización)**:
   * Abre el archivo para **lectura y escritura**.
   * El archivo **debe existir** y permitir escritura. Permite realizar ambas operaciones en el stream.

5. **`w+` (escritura y actualización)**:
   * Abre el archivo para **lectura y escritura**, pero el archivo se **trunca** si ya existe.
   * Si el archivo no existe, se **crea**.

6. **`x` (creación exclusiva)**:
   * Abre un archivo para **creación exclusiva**. Si el archivo ya existe, la función `open()` generará una excepción.

## Modos de apertura en texto vs binario:

* **Modo texto** (predeterminado):
  * Usado cuando se procesan archivos de texto (es decir, caracteres).
  * Ejemplo: `rt` (lectura en texto), `wt` (escritura en texto).

* **Modo binario**:
  * Usado cuando se procesan datos en formato binario (por ejemplo, imágenes, archivos ejecutables).
  * Para abrir en modo binario, se agrega una **`b`** al final del modo.
  * Ejemplo: `rb` (lectura en binario), `wb` (escritura en binario).

| Modo Texto | Modo Binario | Descripción                    |
|------------|--------------|--------------------------------|
| `rt`       | `rb`         | Lectura                        |
| `wt`       | `wb`         | Escritura                      |
| `at`       | `ab`         | Adjuntar                       |
| `r+t`      | `r+b`        | Lectura y actualización        |
| `w+t`      | `w+b`        | Escritura y actualización      |

Tenemos que tener en cuenta:

* Si abres un archivo con **`a` (adjuntar)**, el cabezal de escritura se coloca al final del archivo.
* Si no especificas si el archivo es binario o texto, se **asume modo texto**.
* Al abrir en **modo binario**, no hay traducción de caracteres de nueva línea.

Estos modos te permiten elegir la forma adecuada de manejar los archivos en función de tus necesidades de lectura y escritura, ya sea en texto o binario.

## Ejemplo

Cuando se desea abrir un archivo para leerlo, el proceso en Python puede gestionarse mediante un bloque `try-except` para capturar posibles errores. Aquí está el ejemplo explicado:

```
try:
    stream = open("~/Descargas/file.txt", "rt")
    # El procesamiento va aquí.
    stream.close()
except Exception as exc:
    print("No se puede abrir el archivo:", exc)
```

Nota: Si trabajamos en Windows el nombre del fichero podría ser: `C:\\Users\\User\\Desktop\\file.txt`.

* El bloque `try-except` se utiliza para manejar errores de ejecución. Si la apertura del archivo falla, el programa no se detiene bruscamente; en su lugar, captura la excepción y la maneja con un mensaje explicativo.
* La función `open()`* intenta abrir el archivo ubicado en `~/Descargas/file.txt`. El archivo se abre en **modo lectura y texto** con `"rt"`. Si la apertura es exitosa, devuelve un objeto de archivo y lo asigna a la variable `stream`.
* Usamos `stream.close()` para cerrar el archivo después de su uso, liberando recursos.

## Streams pre-abiertos

Cuando un programa comienza en Python, existen tres streams ya abiertos, que no necesitan una llamada a `open()`. Para usarlos, es necesario importar el módulo `sys`:

```
import sys
```

1. **`sys.stdin` (entrada estándar)**:
   - Asociado con el teclado.
   - Está pre-abierto para lectura, y la función `input()` obtiene datos de este stream por defecto.

2. **`sys.stdout` (salida estándar)**:
   - Asociado con la pantalla.
   - Pre-abierto para escritura, y es el destino principal para la salida de datos del programa. La función `print()` envía sus datos a este stream.

3. **`sys.stderr` (salida de error estándar)**:
   - Asociado también con la pantalla.
   - Pre-abierto para escritura, pero se usa para enviar mensajes de error.
   - Es útil para mantener separados los mensajes de error de la salida normal, lo que permite dirigir cada tipo de mensaje a destinos diferentes.

Este esquema de manejo de streams pre-abiertos es parte fundamental de la entrada y salida en programas Python.

## Comprobando errores al abrir un archivo

### Diagnosticando problemas con los streams

Cuando se trabaja con streams en Python, es crucial manejar los errores que puedan surgir durante la apertura o el procesamiento de archivos. Si deseas un manejo más específico para distintos tipos de errores, puedes usar el módulo `errno`, que proporciona constantes que representan códigos de error comunes. Aquí tienes un ejemplo:

```
import errno

try:
    s = open("c:/users/user/Desktop/file.txt", "rt")
    # El procesamiento va aquí.
    s.close()
except Exception as exc:
    if exc.errno == errno.EACCES:
        print("Permiso denegado.")
    elif exc.errno == errno.EBADF:
        print("Número de archivo incorrecto.")
    elif exc.errno == errno.EEXIST:
        print("El archivo ya existe.")
    elif exc.errno == errno.EFBIG:
        print("El archivo es demasiado grande.")
    elif exc.errno == errno.EISDIR:
        print("Se ha tratado un directorio como archivo.")
    elif exc.errno == errno.EMFILE:
        print("Demasiados archivos abiertos.")
    elif exc.errno == errno.ENOENT:
        print("El archivo o directorio no existe.")
    elif exc.errno == errno.ENOSPC:
        print("No queda espacio en el dispositivo.")
    else:
        print("Error desconocido:", exc.errno)
```

* Al inicio, importamos el módulo `errno` para utilizar sus constantes de error.
* Capturamos la excepción `exc` si ocurre un error.  Comprobamos el código de error (`exc.errno`) y, dependiendo del error específico, se imprime un mensaje adecuado.

Puedes simplificar el manejo de errores utilizando la función `strerror()` del módulo `os`. Esta función toma un número de error y devuelve una cadena que describe el error.

Aquí te mostramos cómo puedes hacerlo:

```
from os import strerror

try:
    s = open("c:/users/user/Desktop/file.txt", "rt")
    # El procesamiento va aquí.
    s.close()
except Exception as exc:
    print("El archivo no pudo ser abierto:", strerror(exc.errno))
```

* Al inicio, importamos la función `strerror` del módulo `os`, que nos ayudará a traducir códigos de error a mensajes comprensibles.
* Si ocurre un error al intentar abrir el archivo, se captura la excepción `exc`. Usamos `strerror(exc.errno)` para obtener una descripción del error, que se imprime en la consola.

## Cerrando streams

La gestión adecuada de streams en Python incluye el cierre correcto de estos al finalizar su uso. Esto se hace mediante el método `close()` del objeto de stream. Para ello:

```
stream.close()
```
Esta función no devuelve nada, pero puede generar una excepción `IOError` si ocurre un error durante el cierre.

Es importante cerrar el stream:

* **Liberación de recursos**: Cerrar un stream asegura que los recursos del sistema se liberen adecuadamente.
* **Transferencia de datos**: Si el stream se abrió para escritura, los datos pueden no haberse transferido al dispositivo físico. Cerrar el stream forzará a que los buffers se descarguen, lo cual podría fallar, provocando un error.

## Cuestionario

1. ¿Cómo se codifica el valor del argumento modo de la función `open()` si se va a crear un nuevo archivo de texto?

2. ¿Cuál es el significado del valor representado por `errno.EACESS`?

3. ¿Cuál es la salida esperada del siguiente código, asumiendo que el archivo llamado file no existe?
    ```
    import errno

    try:
        stream = open("file", "rb")
        print("existe")
        stream.close()
    except IOError as error:
        if error.errno == errno.ENOENT:
            print("ausente")
        else:
            print("desconocido")
    ```

## Solución cuestionario

1. Ejercicio 1

    `wt` o `w`

2. Ejercicio 2

    **Permiso denegado**: no se permite acceder al contenido del archivo.

3. Ejercicio 3

    `ausente`