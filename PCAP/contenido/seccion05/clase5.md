# Métodos de las cadenas de caracteres

Cuando creamos una cadena de caracteres estamos creando un objeto de la clase str, que tiene definido un conjunto de métodos:

```
cadena.capitalize    cadena.isalnum       cadena.join          cadena.rsplit
cadena.casefold      cadena.isalpha       cadena.ljust         cadena.rstrip
cadena.center        cadena.isdecimal     cadena.lower         cadena.split
cadena.count         cadena.isdigit       cadena.lstrip        cadena.splitlines
cadena.encode        cadena.isidentifier  cadena.maketrans     cadena.startswith
cadena.endswith      cadena.islower       cadena.partition     cadena.strip
cadena.expandtabs    cadena.isnumeric     cadena.replace       cadena.swapcase
cadena.find          cadena.isprintable   cadena.rfind         cadena.title
cadena.format        cadena.isspace       cadena.rindex        cadena.translate
cadena.format_map    cadena.istitle       cadena.rjust         cadena.upper
cadena.index         cadena.isupper       cadena.rpartition    cadena.zfill
```

## Métodos de formato

### `capitalize()`
### `lower()`
### `upper()`
### `swapcase()`
### `title()`
### `center()`

## Métodos de búsqueda

### `count()`

El método `count()` cuenta todas las apariciones del elemento dentro de la secuencia. La ausencia de tal elemento no causa ningún problema. Ejemplo:

```
# Demostración de la función list():
print("abcabc".count("b"))
print('abcabc'.count("d"))
```

### `find()`

Busca una subcadena en una cadena desde el principio, para encontrar el primer elemento del valor especificado en su argumento.

* Si la encuentra, devuelve el índice de la primera aparición del argumento.
* Si no la encuentra devuelve `-1`

No se debe de emplear `find()` si deseas verificar si un solo carácter aparece dentro de una cadena, el operador `in` será significativamente más rápido.
Si deseas realizar la búsqueda, no desde el principio de la cadena, sino desde cualquier posición, puedes usar una variante de dos parámetros del método `find()`. El segundo argumento especifica el índice en el que se iniciará la búsqueda.

```
# Demonstrando el método find():
print("aAbByYzZaA".find("a"))
print("aAbByYzZaA".find("Z"))
print("aAbByYzZaA".find("D"))
print("aAbByYzZaA".find("a",1))
print("aAbByYzZaA".find("y",5))
```

Se puede emplear el método find() para buscar todas las ocurrencias de la subcadena, como aquí:

```
texto = """Una variante del lorem ipsum ordinario
se utiliza en la composición tipográfica desde los años sesenta 
o antes, cuando se popularizó por los anuncios 
de las hojas de transferencia Letraset. Se introdujo en 
en la era de la información a mediados de los ochenta por Aldus Corporation, 
que lo empleó en plantillas gráficas y de tratamiento de textos
para su programa de autoedición PageMaker (de Wikipedia)"""

encontrado = texto.find('de')
while encontrado != -1:
    print(encontrado)
    encontrado = texto.find('de', encontrado + 1)
```

Existe otra variante del módulo con tres parámetros. El tercer argumento apunta al primer índice que no se tendrá en cuenta durante la búsqueda (en realidad es el límite superior de la búsqueda).

Observa el ejemplo a continuación:
```
print('kappa'.find('a', 1, 4))
print('kappa'.find('a', 2, 4))
```

### `rfind()`

Este método funciona igual que `find()` pero comienzan sus búsquedas desde el final de la cadena, no el principio (de ahí el prefijo `r`, de reversa).

```
txt = "Hello, welcome to my world."
print(txt.rfind("e"))
print(txt.rfind("e", 5, 10))
```

### `index()` y `rindex()`: 

Funcionan exactamente igual que `find()` y `rfind()`, pero si no se encuentra la subcadena se devuelve una excepción `ValueError`.

```
# Demonstrando el método index() y rindex():
print("aAbByYzZaA".index("a"))
print("aAbByYzZaA".rindex("a"))
print("aAbByYzZaA".index("D"))
```

## Métodos de validación

### `startswith()`
### `endswith()`
### `isalnum()`
### `isalpha()`
### `isdigit()`
### `islower()`
### `isupper()`
### `isspace()`

## Métodos de sustitución

### `replace()`
### `strip()`
### `lstrip()`
### `rstrip()`

## Métodos de unión y división

### `join()`
### `split()`