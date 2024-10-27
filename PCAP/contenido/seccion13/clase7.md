# Ejemplo: como copiar archivos

Ahora que tienes un entendimiento más profundo sobre la manipulación de archivos en Python, aquí tienes un ejemplo de un programa que copia el contenido de un archivo a otro utilizando un búfer para hacer la transferencia de datos de manera eficiente.

Aquí está el código que implementa esta funcionalidad:

```
from os import strerror

# Solicita al usuario el nombre del archivo fuente
source_file_name = input("Ingresa el nombre del archivo fuente: ")

# Intenta abrir el archivo fuente
try:
    source_file = open(source_file_name, 'rb')
except IOError as e:
    print("No se puede abrir el archivo fuente:", strerror(e.errno))
    exit(e.errno)

# Solicita al usuario el nombre del archivo destino
destination_file_name = input("Ingresa el nombre del archivo destino: ")

# Intenta abrir el archivo destino
try:
    destination_file = open(destination_file_name, 'wb')
except IOError as e:
    print("No se puede crear el archivo de destino:", strerror(e.errno))
    source_file.close()
    exit(e.errno)

# Prepara un búfer de 64 kilobytes
buffer = bytearray(65536)
total = 0

# Copia los datos del archivo fuente al archivo destino
try:
    readin = source_file.readinto(buffer)
    while readin > 0:
        written = destination_file.write(buffer[:readin])
        total += written
        readin = source_file.readinto(buffer)
except IOError as e:
    print("Error durante la copia:", strerror(e.errno))
    exit(e.errno)

# Imprime el número total de bytes escritos
print(total, 'byte(s) escritos con éxito')

# Cierra los archivos
source_file.close()
destination_file.close()
```

* Se solicita el nombre del archivo fuente y destino. Se manejan errores en caso de que el archivo fuente no se pueda abrir o el archivo destino no se pueda crear.
* El archivo fuente se abre en modo lectura binaria (`'rb'`).
* El archivo destino se abre en modo escritura binaria (`'wb'`).
* Se crea un `bytearray` de 64 kilobytes para transferir datos de forma eficiente. Usar un búfer de 64 kilobytes es una buena práctica ya que permite que el programa realice menos operaciones de entrada/salida (E/S), lo que suele ser más eficiente. Puedes experimentar con diferentes tamaños de búfer para ver cómo afecta la velocidad de copia en tu entorno.
* Se lee del archivo fuente en el búfer y se escribe en el archivo destino.
* Un bucle `while` continúa hasta que se alcanza el final del archivo, leyendo y escribiendo datos en fragmentos.
* Se cierran ambos archivos después de completar la operación.
* Se mantiene un contador de los bytes escritos, que se imprime al final.

## Cuestionario

1. ¿Qué se espera del método `readlines()` cuando el stream está asociado con un archivo vacío?

2. ¿Qué se pretende hacer con el siguiente código?
    ```
    for line in open("file", "rt"):
        for char in line:
            if char.lower() not in "aeiouy ":
                print(char, end='')
    ```
3. Vas a procesar un mapa de bits almacenado en un archivo llamado `image.png` y quieres leer su contenido como un todo en una variable bytearray llamada image. Agrega una línea al siguiente código para lograr este objetivo.
    ```
    try:
        stream = open("image.png", "rb")
        # Inserta una línea aquí.
        stream.close()
    except IOError:
        print("fallido")
    else:
        print("exitoso")
    ```

## Solución cuestionario

1. Ejercicio 1

    Una lista vacía (una lista de longitud cero).

2. Ejercicio 2

    Copia el contenido del archivo `file` hacia la consola, ignorando las vocales.

3. Ejercicio 3

    `image = bytearray(stream.read())`