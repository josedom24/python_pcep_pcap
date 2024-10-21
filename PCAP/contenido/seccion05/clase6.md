# Métodos de las cadenas de caracteres (2ª parte)

## Métodos de validación

### `startswith()` y `endswith()`

* El método `startswith()` comprueba si la cadena dada **empieza** con el argumento especificado y devuelve `True` o `False`, dependiendo del resultado.
* El método `endswith()` comprueba si la cadena dada **termina** con el argumento especificado y devuelve `True` o `False`, dependiendo del resultado.

```
# Demostración del método startswith():
print("omega".startswith("meg"))
print("omega".startswith("om"))

# Demostración del método endswith():
t = "zeta"
print(t.endswith("a"))
print(t.endswith("A"))
print(t.endswith("et"))
print(t.endswith("eta"))
```

### `isalnum()`, `isalpha()`, `isdigit()`, `islower()`, `isupper()`, `isspace()`

Estos métodos nos permiten comprobar que tipo de caracteres forman la cadena:

* `isalnum()`: comprueba si la cadena contiene **solo dígitos o caracteres alfabéticos (letras)** y devuelve `True` o `False` de acuerdo al resultado.
    ```
    # Demostración del método the isalnum():
    print('lambda30'.isalnum())
    print('lambda'.isalnum())
    print('30'.isalnum())
    print('@'.isalnum())
    print('lambda_30'.isalnum())
    print(''.isalnum())
    ```
* `isalpha()`: comprueba si la cadena contiene solo **caracteres alfabéticos (letras)** y devuelve `True` o `False` de acuerdo al resultado.
* `isdigit()`: comprueba si la cadena contiene solo **caracteres númericos** y devuelve `True` o `False` de acuerdo al resultado.
    ```
    # Ejemplo 1: Demostración del método isapha():
    print("Moooo".isalpha())
    print('Mu40'.isalpha())

    # Ejemplo 2: Demostración del método isdigit():
    print('2018'.isdigit())
    print("Year2019".isdigit())
    ```
* `islower()`: comprueba si la cadena contiene solo caracteres alfabéticos (letras) en **mínúsculas** y devuelve `True` o `False` de acuerdo al resultado.
* `isupper()`: comprueba si la cadena contiene solo caracteres alfabéticos (letras) en **mayúscula** y devuelve `True` o `False` de acuerdo al resultado.
* `isspace()`: comprueba si la cadena contiene solo **espacios en blanco** y devuelve `True` o `False` de acuerdo al resultado.
    ```
    # Ejemplo 1: Demostración del método islower():
    print("Moooo".islower())
    print('moooo'.islower())

    # Ejemplo 2: Demostración del método isspace(:
    print(' \n '.isspace())
    print(" ".isspace())
    print("mooo mooo mooo".isspace())

    # Ejemplo 3: Demostración del método isupper():
    print("Moooo".isupper())
    print('moooo'.isupper())
    print('MOOOO'.isupper())
    ```

## Métodos de sustitución

### `replace()`

El método `replace()` con dos parámetros devuelve una copia de la cadena original en la que todas las apariciones del primer argumento han sido reemplazadas por el segundo argumento.

```
# Demostración del método replace():
print("www.netacad.com".replace("netacad.com", "pythoninstitute.org"))
print("This is it!".replace("is", "are"))
print("Apple juice".replace("juice", ""))
```
Si el segundo argumento es una cadena vacía, reemplazar significa realmente eliminar el primer argumento de la cadena. 

La variante del método `replace()` con tres parámetros emplea un tercer argumento (un número) para limitar el número de reemplazos.

```
print("This is it!".replace("is", "are", 1))
print("This is it!".replace("is", "are", 2))
```

### `strip()`, `lstrip()` y `rstrip()`

El método sin parámetros `lstrip()` devuelve una cadena recién creada formada a partir de la original eliminando todos los espacios en blanco iniciales.

```
# Demostración del método the lstrip():
print("[" + " tau ".lstrip() + "]")
```

El método con un parámetro `lstrip()` hace lo mismo que su versión sin parámetros, pero elimina todos los caracteres incluidos en el argumento (una cadena), no solo espacios en blanco:

```
print("www.cisco.com".lstrip("w."))
```

`rstrip()` hacen lo mismo que el método `lstrip`, pero afecta el lado opuesto de la cadena.

```
# Demostración del método rstrip():
print("[" + " upsilon ".rstrip() + "]")
print("cisco.com".rstrip(".com"))
```

Por último, el método `strip()` combina los efectos causados por `rstrip()` y `lstrip(): crea una nueva cadena que carece de todos los espacios en blanco (o la subacadena indicada como argumento) iniciales y finales.

```
# Demostración del método strip():
print("[" + "   aleph   ".strip() + "]")
print("*****aleph**".strip("*"))
```

## Métodos de unión y división

### `join()`

* El método realiza una unión y espera un argumento del tipo lista.
* Se debe asegurar que todos los elementos de la lista sean cadenas: de lo contrario, el método generará una excepción `TypeError`.
* Todos los elementos de la lista serán unidos en una sola cadena pero...
* ... la cadena desde la que se ha invocado el método será utilizada como separador, puesta entre las cadenas.
* La cadena recién creada se devuelve como resultado.

```
# Demonstrating the join() method:
print(",".join(["Python", "es", "bonito"]))
print(" ".join(["Python", "es", "bonito"]))
```

### `split()`

El método `split()` divide la cadena y crea una lista de todas las subcadenas detectadas.

El método asume que las subcadenas están delimitadas por espacios en blanco, los espacios no participan en la operación y no se copian en la lista resultante.

```
print("Python es bonito".split())
```

Si indicamos una cadena como argumento, se asume que esa cadena es el delimitador:

```
fecha="19/10/2024"
lista_fecha=fecha.split("/")
print(lista_fecha)
```