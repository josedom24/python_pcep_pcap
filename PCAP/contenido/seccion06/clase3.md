# Ejemplo 3: El validador IBAN

Este programa implementa (en una forma ligeramente simplificada) un algoritmo utilizado por los bancos Europeos para especificar los números de cuenta. El estándar llamado **IBAN (Número de cuenta bancaria internacional)** proporciona un método simple y bastante confiable para validar los números de cuenta contra errores tipográficos simples que pueden ocurrir al introducir el número. Puedes encontrar más detalles [aquí](https://en.wikipedia.org/wiki/International_Bank_Account_Number).

Un número de cuenta compatible con IBAN consta de:

* Un código de país de dos letras tomado del estándar ISO 3166-1 (por ejemplo, FR para Francia, GB para Gran Bretaña DE para Alemania, y así sucesivamente).
* Dos dígitos de verificación utilizados para realizar las verificaciones de validez: pruebas rápidas y simples, pero no totalmente confiables, que muestran si un número es inválido (distorsionado por un error tipográfico) o válido.
* El número de cuenta real (hasta 30 caracteres alfanuméricos; la longitud de esa parte depende del país).

El estándar dice que la validación requiere los siguientes pasos (según Wikipedia):

1. Verificar que la longitud total del IBAN sea correcta según el país (este programa no lo hará, pero puedes modificar el código para cumplir con este requisito si lo deseas; nota: pero debes enseñar al código a conocer todas las longitudes utilizadas en Europa).
2. Mueve los cuatro caracteres iniciales al final de la cadena (es decir, el código del país y los dígitos de verificación).
3. Reemplaza cada letra en la cadena con dos dígitos, expandiendo así la cadena, donde A = 10, B = 11 ... Z = 35.
4. Interpreta la cadena como un entero decimal y calcula el resto de la división del número entre 97. Si el resto es 1, pasa la prueba de verificación de dígitos y el IBAN puede ser válido.

```
# Validador IBAN.

iban = input("Ingresa un IBAN, por favor: ")
iban = iban.replace(' ','')

if not iban.isalnum():
    print("Has introducido caracteres no válidos.")
elif len(iban) < 15:
    print("El IBAN ingresado es demasiado corto.")
elif len(iban) > 31:
    print("El IBAN ingresado es demasiado largo.")
else:
    iban = (iban[4:] + iban[0:4]).upper()
    iban2 = ''
    for caracter in iban:
        if caracter.isdigit():
            iban2 += caracter
        else:
            iban2 += str(10 + ord(caracter) - ord('A'))
    iban = int(iban2)
    if iban % 97 == 1:
        print("El IBAN ingresado es válido.")
    else:
        print("El IBAN ingresado no es válido.")
```


* Pide al usuario que ingrese el IBAN (el número puede contener espacios, ya que mejoran significativamente la legibilidad del número...
* ... pero elimina los espacios de inmediato).
* El IBAN ingresado debe constar solo de dígitos y letras, de lo contrario...
* ... muestra un mensaje.
* El IBAN no debe tener menos de 15 caracteres (esta es la variante más corta, utilizada en Noruega).
* Si es más corto, se informa al usuario.
* Además, el IBAN no puede tener más de 31 caracteres (esta es la variante más larga, utilizada en Malta).
* Si es más largo, se le informa al usuario.
* Se comienza con el procesamiento.
* Se mueven los cuatro caracteres iniciales al final del número y se convierten todas las letras a mayúsculas (paso 02 del algoritmo).
* Esta es la variable utilizada para completar el número, creada al reemplazar las letras con dígitos (de acuerdo con el paso 03 del algoritmo).
* Iterar a través del IBAN.
* Si el carácter es un dígito...
* ... se copia.
* De lo contrario...
* ... conviértelo en dos dígitos (observa cómo se hace aquí).
* La forma convertida del IBAN está lista: ahora se convierte en un número entero.
* ¿el residuo de la división de iban2 entre 97 es igual a 1?
* Si es así, entonces el número es correcto.
* De lo contrario...
* ... el número no es válido.

Agreguemos algunos datos de prueba (todos estos números son válidos; puedes invalidarlos cambiando cualquier carácter).

* Inglés: GB72 HBZU 7006 7212 1253 00
* Francés: FR76 30003 03620 00020216907 50
* Alemán: DE02100100100152517108

Si eres residente de la UE, puedes usar tu propio número de cuenta para hacer pruebas.
