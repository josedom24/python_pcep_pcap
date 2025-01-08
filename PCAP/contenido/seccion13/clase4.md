# Lectura de archivos de texto

Vamos a aprender a leer el contenido de un archivo de texto simple, imprimirlo en la consola y contar el número de caracteres que se han leído. A continuación, se detalla el proceso:

Asegúrate de tener un archivo llamado `text.txt` con el siguiente contenido:

```
Lo hermoso es mejor que lo feo.
Explícito es mejor que implícito.
Simple es mejor que complejo.
Complejo es mejor que complicado.
```

Aquí tienes un fragmento de código para abrir el archivo, leer su contenido y contar los caracteres:

```
# Abre el archivo text.txt en modo lectura con codificación UTF-8
stream = open("text.txt", "rt", encoding="utf-8")

# Lee el contenido del archivo
content = stream.read()

# Imprime el contenido del archivo
print(content)

# Cuenta y muestra el número total de caracteres leídos
character_count = len(content)
print("Número total de caracteres leídos:", character_count)

# Cierra el stream
stream.close()
```

* Se utiliza `open("text.txt", "rt", encoding="utf-8")` para abrir el archivo en modo lectura. El argumento `encoding="utf-8"` asegura que se lean correctamente los caracteres especiales si los hay.
* `stream.read()` lee todo el contenido del archivo y lo almacena en la variable `content`.
* `print(content)` muestra el contenido del archivo en la consola.
* `len(content)` cuenta el número total de caracteres en el contenido leído.
* `stream.close()` cierra el stream, liberando los recursos asociados.

## Leer archivos de texto carácter a carácter

Ahora vamos a leer un archivo de texto carácter por carácter utilizando Python. El método `read()` es versátil y puede adaptarse a diferentes necesidades. A continuación, se presenta un ejemplo de cómo usar este método para contar y mostrar cada carácter de un archivo.

Aquí tienes el código que abrirá el archivo, leerá cada carácter, lo imprimirá en la consola y contará el número total de caracteres leídos:

```
from os import strerror

try:
    counter = 0  # Inicializa el contador de caracteres
    stream = open('text.txt', "rt")  # Abre el archivo en modo lectura
    char = stream.read(1)  # Lee el primer carácter

    while char != '':  # Continúa hasta que no haya más caracteres
        print(char, end='')  # Imprime el carácter sin saltar a nueva línea
        counter += 1  # Incrementa el contador
        char = stream.read(1)  # Lee el siguiente carácter

    stream.close()  # Cierra el stream
    print("\n\nCaracteres en el archivo:", counter)  # Imprime el total de caracteres

except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```

* Importamos la función `strerror` del módulo `os` para manejar los errores de entrada/salida.
* Inicia un bloque `try` para manejar excepciones que puedan ocurrir durante la apertura y lectura del archivo.
* Se inicializa el contador de caracteres a 0 y se abre el archivo `text.txt` en modo lectura.
* `char = stream.read(1)` lee el primer carácter del archivo.
* Se utiliza un bucle `while` que continuará ejecutándose mientras `char` no sea una cadena vacía.
* Dentro del bucle, se imprime el carácter usando `print(char, end='')`, lo que evita un salto a la nueva línea después de cada impresión.
* Se incrementa el contador con `counter += 1`.
* Se lee el siguiente carácter con `char = stream.read(1)`.
* Después de que se han leído todos los caracteres, se cierra el stream.
* Si ocurre un error durante la operación de E/S, se captura la excepción y se imprime un mensaje que incluye la descripción del error.

Otra versión del mismo programa es la siguiente:

```
from os import strerror

try:
    counter = 0
    stream = open('text.txt', "rt")
    content = stream.read()
    for char in content:
        print(char, end='')
        counter += 1
    stream.close()
    print("\n\nCaracteres en el archivo:", counter)
except IOError as e:
    print("Se produjo un error de E/S:", strerr(e.errno))
```

En este caso se lee todo el archivo y se copia en memoria con lel método `stream.read()` (cuidado con los ficheros grandes!!!). Y a continuación se procesa el texto, iterando con un bucle `for` su contenido, y se actualiza el valor del contador en cada vuelta del bucle.

## Leer archivos de texto línea por línea

En esta sección, aprenderemos a utilizar el método `readline()` para manejar archivos de texto, facilitando la lectura línea por línea. Esto no solo permite trabajar con líneas completas, sino que también simplifica el conteo de líneas en el archivo.

Aquí tienes el código que abrirá el archivo `text.txt`, leerá cada línea, imprimirá su contenido y contará tanto los caracteres como las líneas leídas:

```
from os import strerror

try:
    character_counter = 0  # Inicializa el contador de caracteres
    line_counter = 0  # Inicializa el contador de líneas
    stream = open('text.txt', 'rt')  # Abre el archivo en modo lectura
    line = stream.readline()  # Lee la primera línea

    while line != '':  # Continúa hasta que no haya más líneas
        line_counter += 1  # Incrementa el contador de líneas
        for char in line:  # Itera sobre cada carácter en la línea
            print(char, end='')  # Imprime el carácter sin saltar a nueva línea
            character_counter += 1  # Incrementa el contador de caracteres
        line = stream.readline()  # Lee la siguiente línea

    stream.close()  # Cierra el stream
    print("\n\nCaracteres en el archivo:", character_counter)  # Imprime el total de caracteres
    print("Líneas en el archivo:", line_counter)  # Imprime el total de líneas

except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```

También podemos usar el método `readlines()` que nos permite leer todo el contenido de un archivo de texto en forma de líneas. Este método devuelve una lista de cadenas, donde cada cadena representa una línea del archivo.

Aquí tienes un ejemplo de código que utiliza `readlines()` para leer el archivo `text.txt`, imprimir su contenido carácter por carácter y contar tanto los caracteres como las líneas:

```
from os import strerror

try:
    character_counter = 0  # Inicializa el contador de caracteres
    line_counter = 0  # Inicializa el contador de líneas
    stream = open('text.txt', 'rt')  # Abre el archivo en modo lectura
    lines = stream.readlines(20)  # Lee líneas del archivo, hasta 20 bytes a la vez

    while len(lines) != 0:  # Continúa hasta que no haya más líneas
        for line in lines:  # Itera sobre las líneas leídas
            line_counter += 1  # Incrementa el contador de líneas
            for char in line:  # Itera sobre cada carácter en la línea
                print(char, end='')  # Imprime el carácter sin saltar a nueva línea
                character_counter += 1  # Incrementa el contador de caracteres
        lines = stream.readlines(10)  # Lee más líneas, hasta 10 bytes a la vez

    stream.close()  # Cierra el stream
    print("\n\nCaracteres en el archivo:", character_counter)  # Imprime el total de caracteres
    print("Líneas en el archivo:", line_counter)  # Imprime el total de líneas

except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```

## Iterando sobre un stream

En este último ejemplo, aprovechamos la capacidad del objeto devuelto por `open()` en modo de texto para ser iterable. Esto simplifica aún más el código, permitiendo leer el archivo línea por línea sin necesidad de gestionar manualmente el cierre del archivo.

Aquí tienes el código que ilustra este enfoque:

```
from os import strerror

try:
    character_counter = 0  # Inicializa el contador de caracteres
    line_counter = 0  # Inicializa el contador de líneas

    # Itera directamente sobre el objeto de archivo
    for line in open('text.txt', 'rt'):
        line_counter += 1  # Incrementa el contador de líneas
        for char in line:  # Itera sobre cada carácter en la línea
            print(char, end='')  # Imprime el carácter sin saltar a nueva línea
            character_counter += 1  # Incrementa el contador de caracteres

    # Cierre automático del archivo cuando se alcanza el final
    print("\n\nCaracteres en el archivo:", character_counter)  # Imprime el total de caracteres
    print("Líneas en el archivo:", line_counter)  # Imprime el total de líneas

except IOError as e:  # Manejo de excepciones
    print("Se produjo un error de E/S:", strerror(e.errno))
```
