# Manejo de archivos

El concepto de **streams** en Python se refiere a la forma en que los programas interactúan con archivos para realizar operaciones de lectura y escritura. Cuando se abre un archivo, se debe especificar un **modo de apertura** que define qué tipo de operaciones se pueden realizar en ese archivo. Existen tres modos básicos:

1. **Modo Lectura** (`'r'`): Permite leer desde el archivo, pero no escribir. Intentar escribir en este modo genera una excepción `UnsupportedOperation`.
2. **Modo Escritura** (`'w'`): Permite escribir en el archivo, pero no leer. Si intentas leer en este modo, también se generará una excepción.
3. **Modo Actualizar** (`'r+'`, `'w+'`): Permite tanto leer como escribir en el archivo.

## Movimiento del "cabezal" en los streams
Al igual que una grabadora, los streams tienen un "cabezal" virtual que se mueve a medida que lees o escribes en el archivo. Cada vez que lees datos, el cabezal se desplaza en función de la cantidad de bytes leídos, y cuando escribes, se mueve de manera similar.

Este concepto de **posición actual del archivo** es clave para entender cómo manipular datos en un stream, ya que la ubicación del cabezal determina desde dónde leerás o dónde escribirás a continuación.

## Objetos para trabajar con streams

En Python, los archivos se manejan a través de objetos que representan diferentes tipos de streams. Estos objetos pertenecen a clases específicas, que determinan cómo se procesará el archivo. El tipo de objeto creado depende del contenido del archivo y de las operaciones que deseas realizar. El archivo se abre con la función `open()`, que devuelve el objeto adecuado según el tipo de archivo y el modo de apertura especificado.

### Clases principales para el manejo de archivos:
1. **IOBase**: Clase base para todo tipo de objetos de I/O.
2. **RawIOBase**: Utilizada para el manejo de archivos en modo binario sin buffers.
3. **BufferedIOBase**: Utilizada para archivos en modo binario con buffers.
4. **TextIOBase**: Utilizada para archivos de texto.

Para la mayoría de los casos prácticos, trabajarás con objetos de las clases **BufferedIOBase** y **TextIOBase**, ya que son los más adecuados para manejar archivos binarios y de texto, respectivamente.

## Apertura y cierre de archivos

Cuando abres un archivo con `open()`, se crea automáticamente un objeto de una de estas clases. Puedes realizar operaciones de lectura o escritura según el modo de apertura que hayas especificado. Una vez que terminas de trabajar con el archivo, es importante cerrarlo usando el método `close()` para liberar los recursos.

Estos objetos son fundamentales para gestionar correctamente la lectura y escritura en archivos de manera segura y eficiente.

## Tipos de stremas

Al manejar archivos en Python, es importante entender la diferencia entre **streams de texto** y **streams binarios**:

1. **Streams de texto**: Están organizados en líneas y contienen caracteres tipográficos (letras, dígitos, símbolos). Se procesan línea por línea o carácter por carácter. Por ejemplo, un archivo de texto es lo que verías al abrir un archivo `.txt` en un editor de texto.

2. **Streams binarios**: Son secuencias de bytes sin una estructura en líneas. Se usan para manejar datos como imágenes, audios, videos, o archivos ejecutables. Los datos se leen y escriben por bloques de bytes, en lugar de líneas o caracteres. El tamaño de los bloques puede variar según lo necesites.

## Diferencias entre Linux y Windows

En cuanto al manejo de líneas, los sistemas Linux y Windows tienen diferentes formas de marcar el final de una línea:
* En Linux, se usa el carácter **LF** (Line Feed, código ASCII 10) que se representa como `\n`.
* En Windows, se usa una combinación de **CR** (Carriage Return, código ASCII 13) y **LF** (código ASCII 10), lo que se representa como `\r\n`.

Si un programa se escribe para procesar archivos de texto en Windows y espera encontrar `\r\n` al final de cada línea, fallará en sistemas Linux, donde solo se usa `\n`. Esta diferencia puede hacer que un programa no sea portable, es decir, que no funcione correctamente en diferentes sistemas operativos.

Para evitar problemas de **falta de portabilidad**, es fundamental que los programas escritos en Python sean capaces de manejar correctamente las diferentes convenciones de fin de línea, lo cual puede lograrse abriendo archivos en modo texto, ya que Python se encarga automáticamente de estas diferencias al leer o escribir archivos de texto en distintos sistemas.

Si trabajamos con archivos de texto:
* En sistemas Linux, al leer o escribir líneas no hay cambios especiales.
* En Windows, al leer un archivo, cada par `\r\n` se convierte automáticamente en `\n`. Al escribir, `\n` se traduce a `\r\n`. Esto asegura que el mismo código funcione en ambos sistemas operativos sin problemas de portabilidad.
* Es un proceso **transparente** para el programador.

Con archivos binarios noo ocurre ninguna conversión de caracteres. Los bytes se toman y se escriben tal cual, sin modificaciones.
  

