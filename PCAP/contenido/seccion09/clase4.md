# Métodos de instancia

En Python, un **método** es una función que está definida dentro de una clase y que está asociada a un objeto de esa clase. A continuación, resumimos los aspectos clave sobre los métodos:

1. Cuando definimos un método tendrá  al menos un parámetro, y este parámetro se suele denominar `self`. Aunque el método se puede invocar sin argumentos, el parámetro `self` siempre debe estar presente en su definición. El nombre `self` es una convención para referirse al objeto mismo al cual pertenece el método.
2. El parámetro `self` identifica el objeto al que se le está aplicando el método. Cuando llamamos a un método, Python pasa automáticamente el objeto como argumento al parámetro `self`, por lo que no es necesario que lo especifiquemos al invocar el método.

    Ejemplo:

    ```
    class Clase:
        def metodo(self):
            print("método")

    obj = Clase()
    obj.metodo()  # Se invoca el método sin pasar self
    ```

3. Si deseas que un método acepte otros parámetros además de `self`, estos se colocan después de `self` en la definición. Al invocar el método, se deben pasar estos argumentos, pero **sin** especificar `self` (Python se encarga de pasarlo por ti).

    Ejemplo:

    ```
    class Clase:
        def metodo(self, par):
            print("método:", par)

    obj = Clase()
    obj.metodo(1)
    obj.metodo(2)
    obj.metodo(3)
    ```

## Más sobre el parámetro self


En Python, el parámetro `self` dentro de los métodos de una clase tiene un papel crucial, ya que permite acceder tanto a las **variables de clase** como a las **variables de instancia**, así como invocar otros métodos dentro de la misma clase.

### Acceso a variables de clase e instancia usando `self`

El parámetro `self` permite acceder a las variables de clase (que son compartidas por todas las instancias de la clase) y a las variables de instancia (que son únicas para cada objeto). A continuación, un ejemplo que muestra cómo se utiliza `self` para acceder a ambas:

```
class Clase:
    varia = 2  # Variable de clase

    def metodo(self):
        print(self.varia, self.var)  # Acceso a variable de clase e instancia

obj = Clase()
obj.var = 3  # Variable de instancia asignada a este objeto
obj.metodo()  # Invocamos el método que accede a ambas variables
```

* `self.varia` accede a la **variable de clase** `varia`, que es igual a `2`.
* `self.var` accede a la **variable de instancia** `var`, que fue asignada como `3` al objeto `obj`.

### Invocación de otros métodos dentro de una clase usando `self`

El parámetro `self` también permite invocar otros métodos de la misma clase. Esto es útil para organizar el comportamiento de los objetos en múltiples métodos que pueden interactuar entre sí.

Ejemplo:

```
class Clase:
    def otro_metodo(self):
        print("otro")  # Otro método dentro de la clase

    def metodo(self):
        print("método")
        self.otro_metodo()  # Invoca el método 'otro_metodo' usando self

obj = Clase()
obj.metodo()
```

En este ejemplo, cuando se invoca `obj.metodo()`, este método a su vez llama al método `otro_metodo()` usando `self.otro_metodo()`. Esto demuestra cómo `self` permite que los métodos dentro de una clase se comuniquen entre sí.

## El método constructor

En Python, cuando defines un método especial llamado `__init__`, no se trata de un método regular, sino de un **constructor**. Este método se invoca automáticamente cuando se crea una nueva instancia de la clase. A continuación, se resumen los aspectos más importantes de los constructores en Python.

El constructor `__init__` tiene como objetivo **inicializar** el objeto cuando se crea. Este método es donde se puede configurar el estado interno del objeto y crear las variables de instancia necesarias para su funcionamiento.

* **El parámetro `self`**: Al igual que en cualquier método de clase, el constructor debe tener el parámetro `self`, que hace referencia al objeto que se está creando. Este parámetro se configura automáticamente cuando se instancia un objeto.
* **Otros parámetros**: El constructor puede aceptar parámetros adicionales que permiten personalizar la creación del objeto. Estos parámetros deben pasarse al invocar la clase para crear una instancia.
* **No retorna un valor**: El constructor no puede retornar un valor explícito (con `return`). Su único propósito es inicializar el objeto.

Veamos un ejemplo, donde el constructor `__init__` toma un parámetro adicional llamado `value` y lo utiliza para inicializar una variable de instancia `var`:

```
class Clase:
    def __init__(self, value):
        self.var = value  # Inicializa la variable de instancia

objeto_1 = Clase("objeto")  # Crea un objeto con el valor "objeto"
print(objeto_1.var)  # Imprime el valor de la variable de instancia
```

* Cuando se crea un objeto con la sintaxis `objeto_1 = Clase("objeto")`, Python automáticamente llama al método `__init__` para inicializar el objeto `objeto_1`. En este caso, el valor `"objeto"` es pasado como argumento al constructor, que lo asigna a la variable de instancia `self.var`.
* No es posible invocar directamente el método `__init__` desde un objeto. Este método se llama solo al momento de la creación del objeto. Sin embargo, puedes invocar el constructor de una superclase cuando estás trabajando con herencia (este tema será tratado en detalle más adelante).

## Métodos con valores por defecto

Como __init__ es un método, y un método es una función, puedes hacer los mismos trucos con constructores y métodos que con las funciones ordinarias. 
Por ejemplo podemos tener parámetros con valores por defecto:

```
class Clase:
    def __init__(self, value = None):
        self.var = value


objeto_1 = Clase("objeto")
objeto_2 = Clase()

print(objeto_1.var)
print(objeto_2.var)
```

## Métodos ocultos

Podemos tener métodos ocultos un método, para ello su nombre debe comenzar con `__`. El ejemplo muestra este efecto:

```
class Clase:
    def visible(self):
        print("visible")
    
    def __oculto(self):
        print("oculto")


obj = Clase()
obj.visible()

try:
    obj.__oculto()
except:
    print("fallido")

obj._Clase__oculto()
```