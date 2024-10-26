# Polimorfismo

Al construir una jerarquía de clases, no se trata solo de organizar clases sin propósito. Es esencial analizar el problema cuidadosamente para determinar qué clases deben estar en la parte superior y cuáles en la inferior. Un punto clave para recordar es cómo se gestionan los métodos cuando son redefinidos en las subclases, lo que afecta directamente al comportamiento de la jerarquía.

En el siguiente ejemplo, tenemos dos clases: `One` y `Two`, donde `Two` hereda de `One`. Ambas clases definen el método `do_it()`. El método `doanything()` invoca `do_it()` dentro de la clase `One`, pero dependiendo de si se invoca en un objeto de `One` o de `Two`, el resultado cambia.

```
class One:
    def do_it(self):
        print("do_it de One")

    def doanything(self):
        self.do_it()

class Two(One):
    def do_it(self):
        print("do_it de Two")

one = One()
two = Two()

one.doanything()  # Salida: do_it de One
two.doanything()  # Salida: do_it de Two
```

* La primera invocación de `doanything()` en un objeto de la clase `One` llama al método `do_it()` definido en `One`.
* La segunda invocación de `doanything()` en un objeto de la clase `Two` llama al método `do_it()` redefinido en `Two`. Esto sucede a pesar de que `do_it()` se invoca dentro de la clase `One`, lo que demuestra el funcionamiento del **polimorfismo**.

## Polimorfismo y métodos virtuales

Esta situación, donde una subclase puede modificar el comportamiento de su superclase, se denomina **polimorfismo**. El término proviene del griego, donde "polys" significa "muchos" y "morphe" significa "forma". En este contexto, significa que una misma clase puede adoptar diferentes formas dependiendo de cómo sus subclases redefinen ciertos métodos.

Cuando un método de una subclase cambia el comportamiento de su superclase, este método se llama **método virtual**. Esto resalta que ninguna clase tiene su comportamiento completamente fijo, ya que siempre puede ser modificado por una subclase.

