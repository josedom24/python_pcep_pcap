# Trabajando con archivos binarios

## ¿Qué es un `bytearray`?

Un `bytearray` es una clase en Python que permite almacenar datos en forma de una secuencia mutable de bytes. Es especialmente útil cuando se trabaja con datos binarios, como imágenes, archivos de audio o cualquier otro tipo de información que no esté en formato de texto. A diferencia de las cadenas de bytes (`bytes`), que son inmutables, los `bytearray` son mutables, lo que significa que puedes cambiar su contenido después de crearlos.

Sus características son:

1. **Mutable**: Puedes modificar un `bytearray` después de haberlo creado. Esto incluye cambiar, agregar o eliminar bytes.
2. **Almacenamiento de datos amorfos**: Un `bytearray` puede contener datos que no tienen una estructura predefinida, lo que es ideal para datos binarios.
3. **Indexación**: Puedes acceder a los elementos de un `bytearray` utilizando la indexación convencional, como lo harías con una lista.
4. **Función `len()`**: Puedes utilizar la función `len()` para obtener el número de bytes en un `bytearray`.
5. **Valores enteros**: Los elementos del `bytearray` deben ser enteros. Intentar establecer un elemento con un valor que no sea un entero provocará una excepción `TypeError`.
6. **Rango de valores**: Cada elemento del `bytearray` debe ser un valor entero dentro del rango de 0 a 255. Si intentas asignar un valor fuera de este rango, se generará una excepción `ValueError`.
7. **Impresión de elementos**: Puedes imprimir los elementos de un `bytearray` utilizando la función `hex()`, lo que permite visualizar los valores en formato hexadecimal.
8. **Inicialización**: Puedes crear un `bytearray` de varias maneras. Por ejemplo:
   - **Con un tamaño fijo**: `data = bytearray(10)` crea un `bytearray` con capacidad para 10 bytes, inicializados a cero.
   - **Con una cadena de bytes**: `data = bytearray(b"hello")` crea un `bytearray` a partir de una cadena de bytes.
   - **Con una lista de enteros**: `data = bytearray([65, 66, 67])` crea un `bytearray` que contiene los bytes correspondientes a los valores enteros (en este caso, A, B y C).

Aquí hay un ejemplo que ilustra algunas operaciones comunes con un `bytearray`:

```
# Crear un bytearray de 10 bytes
data = bytearray(10)
print(data)  # Salida: bytearray(b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00')

# Modificar un byte
data[0] = 65  # Cambiar el primer byte a 65 (corresponde a 'A')
print(data)  # Salida: bytearray(b'A\x00\x00\x00\x00\x00\x00\x00\x00\x00')

# Agregar nuevos bytes
data.append(66)  # Agregar 66 (corresponde a 'B')
print(data)  # Salida: bytearray(b'A\x00\x00\x00\x00\x00\x00\x00\x00\x00B')

# Convertir a bytes
bytes_data = bytes(data)
print(bytes_data)  # Salida: b'A\x00\x00\x00\x00\x00\x00\x00\x00\x00B'
```


Veamos otro ejemplo:

```
data = bytearray(10)

for i in range(len(data)):
    data[i] = 10 - i

for b in data:
    print(hex(b))
```

## Escritura en un archivo binario

Veamos cómo escribir un `bytearray` en un archivo binario y cómo leer ese contenido de nuevo en Python. Para escribir un `bytearray` en un archivo binario, debes seguir algunos pasos importantes:

* Se crea un `bytearray` con valores. Por ejemplo, puedes inicializarlo con valores a partir de 10, o puedes usar la función `ord('a')` para obtener valores ASCII.
* Abre el archivo en modo binario para escritura (`'wb'`), lo que indica que estás trabajando con datos binarios.
* Utiliza el método `write()` para enviar el `bytearray` al archivo. Este método devuelve la cantidad de bytes escritos correctamente.
* Cerramos el archivo después de la escritura.

Aquí tienes el código que realiza la escritura de un `bytearray` en un archivo binario:

```
from os import strerror

# Inicializa el bytearray
data = bytearray(10)

# Llena el bytearray con valores
for i in range(len(data)):
    data[i] = 10 + i  # Valores de 10 a 19

try:
    # Abre el archivo en modo binario para escritura
    binary_file = open('file.bin', 'wb')
    binary_file.write(data)  # Escribe el bytearray en el archivo
    binary_file.close()  # Cierra el archivo
except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))
```

## Lectura de un archivo binario

Para leer el contenido de un archivo binario y almacenarlo en un `bytearray`, se utiliza el método `readinto()`, que llena un `bytearray` existente con los datos leídos. Aquí están los pasos:

* Abre el archivo en modo binario para lectura (`'rb'`).
* Usa el método `readinto()` para leer los bytes directamente en un `bytearray` ya creado. Este método devuelve el número de bytes leídos con éxito.
* Puedes imprimir el contenido del `bytearray` para verificar que los datos leídos son correctos.

Aquí tienes el código que lee el `bytearray` de un archivo binario:

```
from os import strerror

data = bytearray(10)  # Crea un bytearray con espacio para 10 bytes

try:
    # Abre el archivo en modo binario para lectura
    binary_file = open('file.bin', 'rb')
    num_bytes_read = binary_file.readinto(data)  # Llena el bytearray con datos
    binary_file.close()  # Cierra el archivo

    # Imprime los valores leídos en formato hexadecimal
    for b in data:
        print(hex(b), end=' ')
except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))
```

## Lectura de ficheros binarios con `read()`

Tenemos una forma alternativa para leer archivos binarios: El método `read()` ofrece una forma sencilla de leer el contenido completo de un archivo binario en Python. A diferencia de `readinto()`, que requiere un `bytearray` existente para llenar, `read()` crea un nuevo objeto de tipo `bytes`, que es inmutable.

A continuación, se presenta el código que escribe un `bytearray` en un archivo binario y luego lo lee usando `read()`:

```
from os import strerror

# Inicializa el bytearray
data = bytearray(10)

# Llena el bytearray con valores
for i in range(len(data)):
    data[i] = 10 + i  # Valores de 10 a 19

try:
    # Abre el archivo en modo binario para escritura
    binary_file = open('file.bin', 'wb')
    binary_file.write(data)  # Escribe el bytearray en el archivo
    binary_file.close()  # Cierra el archivo
except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))

# Ingresa aquí el código que lee los bytes del stream.
try:
    # Abre el archivo en modo binario para lectura
    binary_file = open('file.bin', 'rb')
    
    # Lee todo el contenido del archivo en un objeto de bytes
    data = binary_file.read()
    binary_file.close()  # Cierra el archivo

    # Convierte el objeto de bytes a bytearray para manipulación
    byte_data = bytearray(data)

    # Imprime los valores leídos en formato hexadecimal
    for b in byte_data:
        print(hex(b), end=' ')
except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))
```

El método `read()` también permite especificar el número máximo de bytes a leer al invocarlo con un argumento. Esto es útil cuando deseas controlar la cantidad de datos que se leen del archivo en una sola operación.

* **Número de Bytes**: Al pasar un argumento, `read(n)` intentará leer hasta `n` bytes del archivo.
* **Longitud del Objeto Devuelto**: La longitud del objeto devuelto por `read(n)` puede ser menor que `n` si se alcanza el final del archivo antes de haber leído todos los bytes solicitados.

A continuación, se muestra un ejemplo que escribe un `bytearray` en un archivo binario y luego lee los primeros 5 bytes usando el método `read()`:

```
from os import strerror

# Inicializa el bytearray
data = bytearray(10)

# Llena el bytearray con valores
for i in range(len(data)):
    data[i] = 10 + i  # Valores de 10 a 19

try:
    # Abre el archivo en modo binario para escritura
    binary_file = open('file.bin', 'wb')
    binary_file.write(data)  # Escribe el bytearray en el archivo
    binary_file.close()  # Cierra el archivo
except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))

# Ingresa aquí el código que lee los bytes del stream.
try:
    # Abre el archivo en modo binario para lectura
    binary_file = open('file.bin', 'rb')
    
    # Lee los primeros 5 bytes del archivo
    data = bytearray(binary_file.read(5))  # Leer 5 bytes
    binary_file.close()  # Cierra el archivo

    # Imprime los valores leídos en formato hexadecimal
    for b in data:
        print(hex(b), end=' ')

except IOError as e:
    print("Se produjo un error de E/S:", strerror(e.errno))
```
