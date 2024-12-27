# Programación orientada a objetos en Python

Para crear una clase en Python vamos a usar la palabra clave `class`. Veamos un ejemplo sencillo creando una clase que no hace nada:

```
class MiClase():
    pass
```

A partir de la definición de una clase podemos crear objetos que tendrán las características de la clase, para ello:

```
objeto1 = MiClase()
objeto2 = MiClase()
```

Realmente podemos pensar que cuando definimos una clase estamos creando un nuevo tipo de datos, y cuando creamos un ovjeto estamos creando una variable de ese nuevo tipo de datos:

```
type(objeto1)
<class '__main__.MiClase'>
```

## Atributos de objetos

Para definir atributos de objetos, basta con definir una variable dentro de los métodos, es una buena idea definir todos los atributos de nuestras instancias en el constructor, de modo que se creen con algún valor válido. 

## Método constructor `__init__`

Como hemos visto anteriormente los atributos de objetos no se crean hasta que no hemos ejecutado el método. Tenemos un método especial, llamado constructor `__init__`, que nos permite inicializar los atributos de objetos. Este método se llama cada vez que se crea una nueva instancia de la clase.

## Definiendo métodos. El parámetro self

El método constructor, al igual que todos los métodos de cualquier clase, recibe como primer parámetro a la instancia sobre la que está trabajando. Por convención a ese primer parámetro se lo suele llamar `self` (que podríamos traducir como yo mismo), pero puede llamarse de cualquier forma.

Para referirse a los atributos de objetos hay que hacerlo a partir del objeto `self`.

## Ejemplo

Aquí tienes un ejemplo de cómo crear una clase `Coche` con un constructor, un atributo y un método:

```
class Coche:
    def __init__(self, marca, modelo):
        self.marca = marca  # Atributo
        self.modelo = modelo  # Atributo

    def describir(self):
        # Método que imprime una descripción del coche
        return "Coche: " + self.marca+ " " +self.modelo

# Crear un objeto de la clase Coche
mi_coche = Coche("Toyota", "Corolla")

# Usar el método del objeto
print(mi_coche.describir())  # Salida: Coche: Toyota Corolla
```

* **Clase `Coche`**: Se define la clase que representa un coche.
* **Método `__init__`**: Este es el constructor. Inicializa los atributos `marca` y `modelo` cuando se crea un objeto de la clase `Coche`.
* **Método `describir`**: Este método devuelve una cadena que describe el coche.
* **Objeto `mi_coche`**: Se crea una instancia de la clase `Coche` con marca "Toyota" y modelo "Corolla".
* **Uso del Método**: Se llama al método `describir` del objeto `mi_coche` para imprimir la descripción.

## Herencia

La herencia permite que una clase (subclase) herede atributos y métodos de otra clase (superclase). Aquí tienes un ejemplo de herencia:

```
class CocheElectrico(Coche):  # CocheElectrico hereda de Coche
    def __init__(self, marca, modelo, autonomia):
        super().__init__(marca, modelo)  # Llamar al constructor de la superclase
        self.autonomia = autonomia  # Atributo adicional

    def describir(self):
        # Método que incluye la autonomía en la descripción
        return "Coche eléctrico: "+ self.marca + " " + self.modelo +", Autonomía: " + self.autonomia + " km"

# Crear un objeto de la clase CocheElectrico
mi_coche_electrico = CocheElectrico("Tesla", "Model S", 500)

# Usar el método del objeto
print(mi_coche_electrico.describir())  # Salida: Coche eléctrico: Tesla Model S, Autonomía: 500 km
```

* **Clase `CocheElectrico`**: Hereda de la clase `Coche`.
* **Uso de `super()`**: Dentro del constructor de `CocheElectrico`, se llama al constructor de `Coche` para inicializar los atributos `marca` y `modelo`.
* **Atributo `autonomia`**: Es un atributo adicional específico de la clase `CocheElectrico`.
* **Método `describir`**: Se sobrescribe para incluir información sobre la autonomía del coche eléctrico.

Para terminar indicar que en  Python cualquier elemento del lenguaje pertenece a una clase y todas las clases tienen el mismo rango y se utilizan del mismo modo.