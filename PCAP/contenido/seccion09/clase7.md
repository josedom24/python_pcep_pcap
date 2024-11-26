# Representación de los objetos

Veamos ahora un mecanismo útil relacionado con la forma en que los objetos pueden presentarse a sí mismos. Esta funcionalidad permite que los objetos tengan una representación más significativa y legible cuando se imprimen.

## La representación por defecto

Cuando intentamos imprimir un objeto en Python, por defecto se muestra una cadena que incluye el nombre de la clase, seguido por la dirección de memoria del objeto. Por ejemplo, al ejecutar el siguiente código:

```
class Star:
    def __init__(self, name, galaxy):
        self.name = name
        self.galaxy = galaxy

sun = Star("Sol", "Vía Láctea")
print(sun)
```

La salida será algo como:

```
<__main__.Star object at 0x7f1074cc7c50>
```

Aquí, `<__main__.Star>` indica que se trata de un objeto de la clase `Star`, y `0x7f1074cc7c50` es la dirección de memoria donde reside ese objeto. Aunque esta información es técnica y específica, no resulta útil para entender el significado o el estado del objeto.

## Mejorando la Representación con `__str__`

Para ofrecer una representación más clara y útil de los objetos, Python proporciona el método `__str__()` que nos permite obtener una representación "informal" o legible por el usuario del objeto. Se llama cuando usamos la función `print()`. Este método devuelve una cadena con la representación del objeto.

Podemos implementar estos métodos en nuestra clase `Star` para que proporcione una salida más informativa:

```
class Star:
    def __init__(self, name, galaxy):
        self.name = name
        self.galaxy = galaxy

    def __str__(self):
        return self.name + ' en ' + self.galaxy

    
sun = Star("Sol", "Vía Láctea")
print(sun)          # Invoca __str__()
```

