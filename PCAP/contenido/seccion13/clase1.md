# Trabajando con archivos

El acceso a archivos desde código en Python es una técnica esencial cuando se trata de procesar grandes volúmenes de datos. Mientras que en tareas simples, como la clasificación de 20 números, los datos pueden ingresarse manualmente, esto se vuelve más complicado cuando el volumen crece, como en el caso de 20,000 números. La solución eficiente es almacenar estos datos en archivos, los cuales el programa puede leer, procesar y luego guardar los resultados en otro archivo.

El uso de archivos es crucial para almacenar información entre ejecuciones de un programa, como en el caso de una base de datos simple. Además, muchos problemas complejos de programación requieren el uso de archivos para manejar datos persistentes, como imágenes, cálculos matemáticos o información financiera.

## Nombres de archivos

En Python, la gestión de nombres de archivos y rutas difiere según el sistema operativo debido a las convenciones que cada uno adopta para definir la ubicación de los archivos. 

* En los sistemas Linux, las rutas de archivos comienzan en el directorio raíz (`/`), mientras que en Windows inician con una letra de unidad (por ejemplo, `C:\`). 
    * En windows: `c:\directorio\archivo`
    * En Linux: `/directorio/archivo`
* Los nombres de archivo en Unix/Linux distinguen entre mayúsculas y minúsculas, mientras que en Windows no se hace distinción.
* Una complicación para los desarrolladores es el uso del carácter `\` en Windows como separador de directorios, que en Python tiene un papel especial en las cadenas, ya que se usa para introducir caracteres de escape como `\n` o `\t`. Esto puede causar errores si no se maneja adecuadamente.
* Para escribir código Python multiplataforma, se recomienda el uso del módulo `os.path` o `pathlib`, que proporcionan funciones para construir y manejar rutas de archivos independientemente del sistema operativo. Estos módulos permiten crear código más flexible y portable que se adapta automáticamente a las convenciones de rutas del sistema donde se ejecuta el programa.

En Python, al manejar nombres de archivos, es importante tener en cuenta las diferencias entre sistemas operativos como Unix/Linux y Windows.

En Linux, si tienes un archivo en el directorio `dir` con el nombre `file`, puedes asignarlo a una cadena de esta manera:
```
name = "/dir/file"
```
Sin embargo, en Windows si intentas esto:
```
name = "\dir\file"
```
Generará errores, ya que Python interpreta `\` como un carácter de escape (como `\n` para un salto de línea). Por lo tanto, para evitar esto, el nombre del archivo debe escribirse de esta manera:
```
name = "\\dir\\file"
```

Afortunadamente, Python es capaz de manejar `/` en las rutas de Windows. Por ejemplo, las siguientes asignaciones funcionarán en Windows:
```
name = "/dir/file"
name = "c:/dir/file"
```

## Streams o manejadores:

El acceso a archivos en Python se basa en el uso de manejadores o streams, que actúan como un intermediario entre el programa y el archivo físico. Podemos realizar varias operaciones sobre el stream:

* Debemos abrir el archivo (con `open()`).
* Realizar las operaciones necesarias (lectura, escritura, etc.).
* Al terminar, debemos cerrar el archivo (con `close()`). 

Es importante que cualquier error al abrir un archivo, como la inexistencia del mismo o la superación del límite de archivos abiertos por el sistema, sea manejado adecuadamente en el código para evitar fallos inesperados.

