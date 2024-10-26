# Herencia múltiple

## Cómo Python encuentra propiedades y métodos: continuación

En Python, la **herencia múltiple** ocurre cuando una clase deriva de más de una superclase, permitiéndole heredar atributos y métodos de todas ellas. Esta característica es esencial para estructurar clases con múltiples comportamientos o propiedades comunes, y se presenta en la sintaxis como una lista de superclases separadas por comas entre paréntesis después del nombre de la clase.

Veamos el siguiente ejemplo:

```
class SuperA:
    var_a = 10
    def fun_a(self):
        return 11

class SuperB:
    var_b = 20
    def fun_b(self):
        return 21

class Sub(SuperA, SuperB):
    pass

obj = Sub()

print(obj.var_a, obj.fun_a())  # Salida: 10 11
print(obj.var_b, obj.fun_b())  # Salida: 20 21
```

En este caso, la clase `Sub` tiene dos superclases: `SuperA` y `SuperB`. Esto significa que la clase `Sub` hereda todos los atributos (`var_a`, `var_b`) y métodos (`fun_a()`, `fun_b()`) de las superclases. Cuando se crea un objeto de la clase `Sub`, podemos acceder a las propiedades y métodos de ambas clases sin problema alguno.

La salida de este código es:

```
10 11
20 21
```

## Anulación de métodos y atributos (Overriding)

En Python, cuando varias clases dentro de una jerarquía de herencia definen métodos o atributos con el mismo nombre, el lenguaje sigue una estrategia conocida como **anulación** o **overriding**. Esto significa que la clase más derivada, o la más reciente en la cadena de herencia, reemplaza el comportamiento definido previamente en clases superiores con el mismo nombre. Veamos este fenómeno en detalle utilizando el siguiente código:

```
class Level1:
    var = 100
    def fun(self):
        return 101

class Level2(Level1):
    var = 200
    def fun(self):
        return 201

class Level3(Level2):
    pass

obj = Level3()

print(obj.var, obj.fun())  # Salida: 200 201
```

En este ejemplo, tanto `Level1` como `Level2` definen un atributo de clase llamado `var` y un método `fun()`. La clase `Level3` hereda de `Level2`, pero no redefine estos elementos. Sin embargo, debido a que Python sigue un orden jerárquico de herencia, los atributos y métodos de `Level2` **anulan** los definidos en `Level1`.

Por lo tanto, cuando se crea una instancia de `Level3` y se accede a sus propiedades, Python busca en el **Method Resolution Order (MRO)** y encuentra que los valores de `var` y `fun()` definidos en `Level2` están más cerca en la jerarquía. Como resultado, el código produce:

```
200 201
```

Este comportamiento de anulación permite modificar o refinar el comportamiento heredado de clases superiores. Es útil cuando una clase derivada necesita cambiar el comportamiento de su clase padre sin alterar el código de la clase original. La **herencia múltiple** también puede complicar este escenario, especialmente cuando dos superclases definen la misma entidad. En ese caso, el MRO **MRO** (Method Resolution Order, que es el orden en el que Python busca atributos y métodos en las clases padres) sigue reglas estrictas para decidir cuál de las entidades se prioriza, basándose en el orden de herencia en la definición de la clase derivada.

## Overriding en herencia múltiple

## Cómo Python encuentra propiedades y métodos: continuando con la herencia múltiple

En Python en la **herencia múltiple** se plantea una pregunta interesante: cuando una clase tiene múltiples superclases, ¿cómo determina Python de dónde provienen los atributos y métodos si tienen el mismo nombre en varias clases? Vamos a analizarlo utilizando un ejemplo concreto de herencia múltiple:

```
class Left:
    var = "L"
    var_left = "LL"
    def fun(self):
        return "Left"

class Right:
    var = "R"
    var_right = "RR"
    def fun(self):
        return "Right"

class Sub(Left, Right):
    pass

obj = Sub()

print(obj.var, obj.var_left, obj.var_right, obj.fun())  # Salida: L LL RR Left
```

En este ejemplo, la clase `Sub` hereda de dos superclases: `Left` y `Right`. Ambas clases definen un atributo `var` y un método `fun()`, lo que podría generar confusión acerca de cuál de estas definiciones se utilizará cuando se cree un objeto de la clase `Sub`.

* `var_right` proviene claramente de la clase `Right`, y `var_left` proviene de `Left`.
* Sin embargo, la variable `var` y el método `fun()` existen tanto en `Left` como en `Right`, pero Python toma las versiones de **`Left`**. Esto se debe a que, cuando busca un atributo o método en un objeto, Python sigue el **Method Resolution Order (MRO)**, que es el orden en el que Python explora las clases de una jerarquía de herencia.

Python busca componentes de un objeto de la siguiente manera:

1. **Dentro del objeto mismo**: Si no se encuentra el atributo o método en el objeto, continúa con el siguiente paso.
2. **En las superclases**, de abajo hacia arriba en la jerarquía.
3. **Si hay más de una clase en una ruta de herencia**, Python escanea de **izquierda a derecha** según el orden de herencia.

En este caso, `Left` se encuentra a la izquierda de `Right` en la definición de la clase `Sub`, por lo que se priorizan los atributos y métodos de `Left`.

Si modificamos el orden de herencia:

```
class Sub(Right, Left):
    pass

obj = Sub()

print(obj.var, obj.var_left, obj.var_right, obj.fun())  # Salida: R LL RR Right
```

Al cambiar el orden de herencia, ahora Python prioriza los atributos y métodos de la clase **`Right`**. Por lo tanto, la salida será:

```
R LL RR Right
```

