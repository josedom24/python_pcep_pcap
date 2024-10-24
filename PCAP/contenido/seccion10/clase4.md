# Trabajando con propiedades y métodos heredados

Empecemos con el siguiente ejemplo:

```
class Super:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "Mi nombre es " + self.name + "."


class Sub(Super):
    def __init__(self, name):
        Super.__init__(self, name)


obj = Sub("Andy")

print(obj)
```

* Existe una clase llamada `Super`, que define su propio constructor utilizado para asignar la propiedad del objeto, llamada `name`.
* La clase también define el método `__str__()`, lo que permite que la clase pueda presentar su identidad en forma de texto.
* La clase se usa luego como base para crear una subclase llamada `Sub`. La clase `Sub` define su propio constructor, que invoca el de la superclase. Toma nota de como lo hemos hecho: `Super.__init__(self, name)`.
* Hemos nombrado explícitamente la superclase y hemos apuntado al método para invocar a `__init__()`, proporcionando todos los argumentos necesarios.
* Hemos instanciado un objeto de la clase `Sub` y lo hemos impreso. La salida es `Mi nombre es Andy`.
* Como no existe el método `__str__()` dentro de la clase `Sub`, la cadena a imprimir se producirá dentro de la clase `Super`. Esto significa que **el método `__str__()` ha sido heredado por la clase `Sub`**.

## La función `super()`

Partimos del mismo ejemplo, pero lo hemos modificado:

```
class Super:
    def __init__(self, name):
        self.name = name

    def __str__(self):
        return "Mi nombre es " + self.name + "."


class Sub(Super):
    def __init__(self, name):
        super().__init__(name)


obj = Sub("Andy")

print(obj)
```

En el ejemplo anterior, nombramos explícitamente la superclase. En este ejemplo, hacemos uso de la función `super()`, la cual **accede a la superclase sin necesidad de conocer su nombre**:

```
super().__init__(name)
```

La función `super()` crea un contexto en el que no tiene que (además, no debe) pasar el argumento propio al método que se invoca; es por eso que es posible activar el constructor de la superclase utilizando solo un argumento. Podemos usar este mecanismo para acceder a cualquier propiedad o método de la superclase.

## Las propiedades también se heredan

Las propiedades oo atributos también se heredan, tanso sin son de clases o si son de instancias.

### Variables de clases

```
# Probando propiedades: variables de clase.
class Super:
    supVar = 1


class Sub(Super):
    subVar = 2


obj = Sub()

print(obj.subVar)
print(obj.supVar)
```

En este caso cada clase define una variable de clase. Como puedes observar, la clase `Super` define una variable de clase llamada `supVar`, y la clase `Sub` define una variable llamada `subVar`. Ambas variables son visibles dentro del objeto de clase `Sub`.

### Variables de instancias

Las variables de instancias también se heredan:

```
# Probando propiedades: variables de instancia.
class Super:
    def __init__(self):
        self.supVar = 11


class Sub(Super):
    def __init__(self):
        super().__init__()
        self.subVar = 12


obj = Sub()

print(obj.subVar)
print(obj.supVar)
```

El constructor de la clase `Sub` crea una variable de instancia llamada `subVar`, mientras que el constructor de `Super` hace lo mismo con una variable de nombre `supVar`. Al igual que el ejemplo anterior, ambas variables son accesibles desde el objeto de clase `Sub`.

La existencia de la variable `supVar` obviamente está condicionada por la invocación del constructor de la clase `Super`. Omitirlo daría como resultado la ausencia de la variable en el objeto creado (pruébalo tu mismo).

## Conclusión

Cuando intentes acceder a una entidad (propiedad o método) de cualquier objeto, Python intentará (en este orden):

* Encontrarla dentro del objeto mismo.
* Encontrarla en todas las clases involucradas en la línea de herencia del objeto de abajo hacia arriba.
* Si ambos intentos fallan, una excepción (`AttributeError`) será generada.

La primera condición puede necesitar atención adicional. Como sabes, todos los objetos derivados de una clase en particular pueden tener diferentes conjuntos de atributos, y algunos de los atributos pueden agregarse al objeto mucho tiempo después de la creación del objeto.

Veamos un ejemplo:

```
class Level1:
    variable_1 = 100
    def __init__(self):
        self.var_1 = 101

    def fun_1(self):
        return 102


class Level2(Level1):
    variable_2 = 200
    def __init__(self):
        super().__init__()
        self.var_2 = 201
    
    def fun_2(self):
        return 202


class Level3(Level2):
    variable_3 = 300
    def __init__(self):
        super().__init__()
        self.var_3 = 301

    def fun_3(self):
        return 302


obj = Level3()

print(obj.variable_1, obj.var_1, obj.fun_1())
print(obj.variable_2, obj.var_2, obj.fun_2())
print(obj.variable_3, obj.var_3, obj.fun_3())
```
