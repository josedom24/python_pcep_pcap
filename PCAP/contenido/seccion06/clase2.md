# Ejemplo 2: El Cifrado César: descifrando un mensaje

En esta ocasión realizamos un programa para hacer la operación contraria: descifrar un mensaje:

```
# Cifrado César - descifrar un mensaje.
cipher = input('Ingresa tu criptograma: ')
text = ''
for char in cipher:
    if not char.isalpha():
        continue
    char = char.upper()
    code = ord(char) - 1
    if code < ord('A'):
        code = ord('Z')
    text += chr(code)

print(text)
```
