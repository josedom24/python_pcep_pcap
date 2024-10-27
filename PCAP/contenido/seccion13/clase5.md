# Escritura en archivos de texto

El método `write()` en Python es una forma sencilla y efectiva de escribir datos en archivos de texto. Este método permite transferir cadenas al archivo abierto y es fundamental para la manipulación de datos en aplicaciones que requieren guardar información de forma persistente.

1. **Argumento**: `write()` toma un único argumento, que es la cadena que deseas escribir en el archivo.
2. **Modo de apertura**: Debes abrir el archivo en modo de escritura (`'w'`, `'wt'`, `'a'`, etc.). Abrir un archivo en modo de lectura (`'r'`) no permitirá la escritura.
3. **Sin caracteres de nueva línea automáticos**: `write()` no añade automáticamente un carácter de nueva línea al final, por lo que debes agregarlo manualmente si deseas que el contenido esté en varias líneas.

Veamos un ejemplo:

```
from os import strerror

try:
    # Abre el archivo en modo de escritura
    file = open('newtext.txt', 'wt')  # Crea un nuevo archivo o lo sobrescribe
    for i in range(10):
        s = "línea #" + str(i + 1) + "\n"  # Crea la cadena para cada línea
        for char in s:
            file.write(char)  # Escribe carácter por carácter
    file.close()  # Cierra el archivo
except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```

* Se importa para manejar errores de entrada/salida.
* Se inicia un bloque `try` para capturar excepciones.
* `open('newtext.txt', 'wt')` abre (o crea) el archivo `newtext.txt` en modo de escritura de texto.
* Se utiliza para iterar diez veces, creando una cadena para cada línea del archivo.
* Un bucle interno itera sobre cada carácter de la cadena y lo escribe en el archivo utilizando `file.write(char)`.
* Se cierra el archivo para asegurarse de que los datos se guardan correctamente.
* Se captura cualquier error de entrada/salida y se imprime un mensaje de error.

## Escritura de líneas enteras

La modificación del código para escribir líneas completas en un archivo de texto simplifica la operación de escritura, evitando el bucle interno que escribe carácter por carácter. En este caso, se utiliza el método `write()` para escribir cadenas completas en el archivo. Veamos el ejemplo:

```
from os import strerror

try:
    # Abre el archivo en modo de escritura
    file = open('newtext.txt', 'wt')  # Crea o sobrescribe el archivo
    for i in range(10):
        file.write("línea #" + str(i + 1) + "\n")  # Escribe la línea completa
    file.close()  # Cierra el archivo
except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```

## Enviando mensajes a `stderr`

Además de escribir en archivos de texto, puedes enviar mensajes de error a `stderr` para distinguirlos de la salida normal del programa. Esto es especialmente útil para la depuración y el manejo de errores.

```
import sys

# Enviar un mensaje de error a stderr
sys.stderr.write("Mensaje de Error\n")
```

