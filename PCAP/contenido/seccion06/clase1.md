# Ejemplo 1: El cifrado César

El primer problema que queremos mostrarte se llama Cifrado César, más detalles [aquí](https://en.wikipedia.org/wiki/Caesar_cipher).

Este cifrado fue (probablemente) inventado y utilizado por Cayo Julio César y sus tropas durante las Guerras Galas. La idea es bastante simple: cada letra del mensaje se reemplaza por su consecuente más cercano (A se convierte en B, B se convierte en C, y así sucesivamente). La única excepción es la Z, la cual se convierte en A.

Partimos de las siguientes condiciones:

* Solo acepta letras latinas (nota: los Romanos no usaban espacios en blanco ni dígitos).
* Todas las letras del mensaje están en mayúsculas (nota: los Romanos solo conocían las mayúsculas).

```
# Cifrado César.
texto = input("Ingresa tu mensaje: ")
cifrado = ''
for caracter in texto:
    if not caracter.isalpha():
        continue
    caracter = caracter.upper()
    code = ord(caracter) + 1
    if code > ord('Z'):
        code = ord('A')
    cifrado += chr(code)

print(cifrado)
```

Veamos el código:

* Pide al usuario que ingrese un mensaje (sin cifrar) de una línea.
* Prepara una cadena para el mensaje cifrado (esta vacía por ahora).
* Inicia la iteración a través del mensaje.
* Si el carácter actual no es alfabético...
* ...ignoralo.
* Convierte la letra a mayúsculas.
* Obtén el código de la letra e increméntalo en uno.
* Si el código resultante ha "dejado" el alfabeto latino (si es mayor que el código de la Z)...
* ... cámbialo al código de la A.
* Agrega el carácter recibido al final del mensaje cifrado.
* Imprime el cifrado.

El código, con este mensaje: `AVE CAESAR`
Da como salida: `BWFDBFTBS`

## Descifrando el mensaje

Ahora realizamos un programa para hacer la operación contraria: descifrar un mensaje:

```
# Cifrado César - descifrar un mensaje.
cifrado = input('Ingresa tu criptograma: ')
texto = ''
for caracter in cifrado:
    if not caracter.isalpha():
        continue
    caracter = caracter.upper()
    code = ord(caracter) - 1
    if code < ord('A'):
        code = ord('Z')
    texto += chr(code)

print(texto)
```
