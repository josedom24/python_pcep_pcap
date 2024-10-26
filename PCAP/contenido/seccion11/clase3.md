# Creación de nuevas excepciones

Crear excepciones personalizadas en Python es una práctica útil cuando deseas manejar errores de una manera específica o cuando estás construyendo un módulo complejo. Las excepciones personalizadas permiten diferenciar tus errores de las excepciones estándar de Python y brindar información más relevante sobre el contexto del error.

Para crear tu propia excepción, debes definir una nueva clase que herede de una clase de excepción existente. Generalmente, si quieres que tu excepción esté relacionada con un tipo de error existente, la heredarás de esa excepción. Si deseas que tu jerarquía de excepciones sea independiente, puedes heredar de la clase `Exception`.

A continuación, se muestra un ejemplo donde se define una excepción personalizada `MyZeroDivisionError` que hereda de la excepción incorporada `ZeroDivisionError`. Luego, se presenta una función que lanza esta excepción en función de su entrada.

```
class MyZeroDivisionError(ZeroDivisionError):
    pass

def do_the_division(mine):
    if mine:
        raise MyZeroDivisionError("peores noticias")
    else:
        raise ZeroDivisionError("malas noticias")

# Manejo de excepciones con bloques except
for mode in [False, True]:
    try:
        do_the_division(mode)
    except ZeroDivisionError:
        print('División entre cero')

# Manejo de excepciones con bloques except diferenciados
for mode in [False, True]:
    try:
        do_the_division(mode)
    except MyZeroDivisionError:
        print('Mi división entre cero')
    except ZeroDivisionError:
        print('División entre cero original')
```

* **Definición de la Excepción**: Se define la clase `MyZeroDivisionError`, que hereda de `ZeroDivisionError`. La palabra clave `pass` se utiliza porque no se están añadiendo nuevos métodos o atributos.
* **Función `do_the_division()`**: Esta función toma un argumento booleano `mine`. Si es verdadero, lanza la excepción personalizada `MyZeroDivisionError` con un mensaje específico. Si es falso, lanza la excepción estándar `ZeroDivisionError`.
* **Manejo de Excepciones**:
   * En el primer bloque `try-except`, se intenta ejecutar `do_the_division()`. Si se produce cualquier `ZeroDivisionError`, se maneja con un bloque que imprime un mensaje genérico.
   * En el segundo bloque `try-except`, se distingue entre `MyZeroDivisionError` y `ZeroDivisionError`, permitiendo manejar cada excepción de forma específica. Esto muestra cómo el orden de los bloques `except` es importante; si el bloque más específico (`MyZeroDivisionError`) está después del más general (`ZeroDivisionError`), nunca se alcanzará.

## Creación de nuestra propia jerarquía de excepciones

Cuando se diseña un sistema complejo, como una simulación de un restaurante de pizza, puede ser útil definir una jerarquía de excepciones que refleje los problemas específicos del contexto. A continuación, se explica cómo crear excepciones personalizadas que proporcionen información adicional sobre los errores relacionados con la pizza.

* **Clase Base de Excepción: `PizzaError`**. Esta clase actuará como la excepción general para todos los problemas relacionados con la pizza.
* **Clase Derivada de Excepción: `TooMuchCheeseError`**.  Esta clase representa un caso específico de error que ocurre cuando se agrega demasiado queso a una pizza.

```
class PizzaError(Exception):
    def __init__(self, pizza, message):
        super().__init__(message)  # Llama al constructor de la clase base con el mensaje
        self.pizza = pizza  # Almacena información sobre la pizza

class TooMuchCheeseError(PizzaError):
    def __init__(self, pizza, cheese, message):
        super().__init__(pizza, message)  # Llama al constructor de PizzaError
        self.cheese = cheese  # Almacena información sobre el exceso de queso

# Ejemplo de uso
try:
    # Supongamos que una función chequea la cantidad de queso
    pizza_name = "Margarita"
    cheese_amount = 500  # en gramos
    if cheese_amount > 300:  # Suponiendo que 300g es el límite
        raise TooMuchCheeseError(pizza_name, cheese_amount, "Demasiado queso en la pizza.")
except TooMuchCheeseError as e:
    print(f"Error: {e} - Pizza: {e.pizza}, Queso: {e.cheese}g")
```


* Hemos definido la clase `PizzaError`** a partir de `Exception`. El constructor recibe dos parámetros: `pizza` (nombre de la pizza) y `message` (descripción del error). Se llama al constructor de la superclase (`Exception`) con el mensaje de error y se almacena la información sobre la pizza en el atributo `self.pizza`.
* Hemos definido la clase `TooMuchCheeseError`** a partir de `PizzaError`. El constructor recibe tres parámetros: `pizza`, `cheese` (cantidad de queso en gramos), y `message`. Se llama al constructor de `PizzaError` y se almacena la cantidad de queso en el atributo `self.cheese`.
* Se simula una verificación de la cantidad de queso. Si la cantidad excede el límite permitido (300 gramos), se lanza la excepción `TooMuchCheeseError`.
* En el bloque `except`, se captura la excepción y se imprime un mensaje que incluye detalles sobre la pizza y la cantidad de queso.

## Ejemplo final

En este ejercicio, combinamos las excepciones `PizzaError` y `TooMuchCheeseError` dentro de una función `make_pizza()`, que lanza estas excepciones en caso de errores específicos al hacer una pizza. También se mejoró el manejo de excepciones al establecer valores predeterminados en los constructores, permitiendo su uso sin tener que especificar todos los argumentos cada vez.

Aquí tienes el código que ilustra esta implementación:

```
class PizzaError(Exception):
    def __init__(self, pizza='desconocida', message=''):
        super().__init__(message)  # Llama al constructor de la clase base
        self.pizza = pizza  # Almacena información sobre la pizza

class TooMuchCheeseError(PizzaError):
    def __init__(self, pizza='desconocida', cheese='>100', message=''):
        super().__init__(pizza, message)  # Llama al constructor de PizzaError
        self.cheese = cheese  # Almacena información sobre el exceso de queso

def make_pizza(pizza, cheese):
    if pizza not in ['margherita', 'capricciosa', 'calzone']:
        raise PizzaError(pizza, "no hay tal pizza en el menú")  # Lanza PizzaError si la pizza no está en el menú
    if cheese > 100:
        raise TooMuchCheeseError(pizza, cheese, "demasiado queso")  # Lanza TooMuchCheeseError si hay demasiado queso
    print("¡Pizza lista!")  # Indica que la pizza se ha preparado correctamente

# Prueba de la función con diferentes entradas
for (pz, ch) in [('calzone', 0), ('margherita', 110), ('mafia', 20)]:
    try:
        make_pizza(pz, ch)  # Intenta hacer la pizza
    except TooMuchCheeseError as tmce:
        print(tmce, ':', tmce.cheese)  # Maneja el error de exceso de queso
    except PizzaError as pe:
        print(pe, ':', pe.pizza)  # Maneja el error de pizza no válida
```

* Hemos redefinido las clases donde creamos las nuevas excepciones:
   * **`PizzaError`**: Constructor permite asignar un nombre de pizza y un mensaje de error. Los valores predeterminados son `'desconocida'` para `pizza` y `''` para `message`.
   * **`TooMuchCheeseError`**: Derivada de `PizzaError`, tiene su propio constructor que también establece un valor predeterminado para `cheese` (que representa la cantidad de queso) y un mensaje de error.
* La función `make_pizza()`:
   * Verifica si la pizza solicitada está en el menú.
   * Si no está, lanza un `PizzaError`.
   * Si la cantidad de queso excede los 100 gramos, lanza un `TooMuchCheeseError`.
   * Si todo está correcto, imprime un mensaje indicando que la pizza está lista.
* Realizamos un bucle para probar el programa:
   * Itera sobre una lista de tuplas que contienen diferentes combinaciones de pizzas y cantidades de queso.
   * Usa bloques `try` y `except` para manejar cada tipo de excepción.
   * Si ocurre un `TooMuchCheeseError`, se imprime un mensaje con la cantidad de queso. Si ocurre un `PizzaError`, se imprime un mensaje con el nombre de la pizza.

## Cuestionario

1. ¿Cuál es el resultado esperado del siguiente código?
    ```
    import math

    try:
        print(math.sqrt(9))
    except ValueError:
        print("inf")
    else:
        print("ok")
    ```
2. ¿Cuál es el resultado esperado del siguiente código?
    ```
    import math

    try:
        print(math.sqrt(-9))
    except ValueError:
        print("inf")
    else:
        print("ok")
    finally:
        print("fin")
    ```
3. ¿Cuál es el resultado esperado del siguiente código?
    ```
    import math

    class NewValueError(ValueError):
        def __init__(self, name, color, state):
            self.data = (name, color, state)

    try:
        raise NewValueError("Advertencia enemiga", "Alerta roja", "Alta disponibilidad")
    except NewValueError as nve:
        for arg in nve.args:
            print(arg, end='! ')
    ```

## Solución cuestionario

1. Ejercicio 1

    ```
    3.0
    ok
    ```
2. Ejercicio 2

    ```
    inf
    fin
    ```
3. Ejercicio 3

    ```
    Advertencia enemiga! Alerta roja! Alta disponibilidad! 
    ```

