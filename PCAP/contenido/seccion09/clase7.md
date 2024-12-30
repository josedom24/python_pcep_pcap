# Representación de los objetos

Veamos ahora un mecanismo útil relacionado con la forma en que los objetos pueden presentarse a sí mismos. Esta funcionalidad permite que los objetos tengan una representación más significativa y legible cuando se imprimen.

## La representación por defecto

Cuando intentamos imprimir un objeto en Python, por defecto se muestra una cadena que incluye el nombre de la clase, seguido por la dirección de memoria del objeto. Por ejemplo, al ejecutar el siguiente código:

```
class Estrella:
    def __init__(self, nombre, galaxia):
        self.nombre = nombre
        self.galaxia = galaxia

sol = Estrella("Sol", "Vía Láctea")
print(sol)
```

La salida será algo como:

```
<__main__.Estrella object at 0x7f1074cc7c50>
```

Aquí, `<__main__.Estrella>` indica que se trata de un objeto de la clase `Estrella`, y `0x7f1074cc7c50` es la dirección de memoria donde reside ese objeto. Aunque esta información es técnica y específica, no resulta útil para entender el significado o el estado del objeto.

## Mejorando la representación con `__str__`

Para ofrecer una representación más clara y útil de los objetos, Python proporciona el método `__str__()` que nos permite obtener una representación "informal" o legible por el usuario del objeto. Se llama cuando usamos la función `print()`. Este método devuelve una cadena con la representación del objeto.

Podemos implementar estos métodos en nuestra clase `Estrella` para que proporcione una salida más informativa:

```
class Estrella:
    def __init__(self, nombre, galaxia):
        self.nombre = nombre
        self.galaxia = galaxia

    def __str__(self):
        return self.nombre + ' en ' + self.galaxia

    
sol = Estrella("Sol", "Vía Láctea")
print(sol)          # Invoca __str__()
```

