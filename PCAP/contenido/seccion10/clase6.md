# Polimorfismo

Al construir una jerarquía de clases, no se trata solo de organizar clases sin propósito. Es esencial analizar el problema cuidadosamente para determinar qué clases deben estar en la parte superior y cuáles en la inferior. Un punto clave para recordar es cómo se gestionan los métodos cuando son redefinidos en las subclases, lo que afecta directamente al comportamiento de la jerarquía.

En el siguiente ejemplo, tenemos dos clases: `Uno` y `Dos`, donde `Dos` hereda de `Uno`. Ambas clases definen el método `opera()`. El método `operacion()` invoca `opera()` dentro de la clase `Uno`, pero dependiendo de si se invoca en un objeto de `Uno` o de `Dos`, el resultado cambia.

```
class Uno:
    def opera(self):
        print("Escribo 1")

    def operacion(self):
        self.opera()

class Dos(Uno):
    def opera(self):
        print("Escribo 2")

objeto1 = Uno()
objeto2 = Dos()

objeto1.operacion()  # Salida: Escribo 1
objeto2.operacion()  # Salida: Escribo 2
```

* La primera invocación de `operacion()` en un objeto de la clase `Uno` llama al método `opera()` definido en `Uno`.
* La segunda invocación de `operacion()` en un objeto de la clase `Dos` llama al método `opera()` redefinido en `Dos`. Esto sucede a pesar de que `opera()` se invoca dentro de la clase `Uno`, lo que demuestra el funcionamiento del **polimorfismo**.

## Polimorfismo y métodos virtuales

Esta situación, donde una subclase puede modificar el comportamiento de su superclase, se denomina **polimorfismo**. El término proviene del griego, donde "polys" significa "muchos" y "morphe" significa "forma". En este contexto, significa que una misma clase puede adoptar diferentes formas dependiendo de cómo sus subclases redefinen ciertos métodos.

Cuando un método de una subclase cambia el comportamiento de su superclase, este método se llama **método virtual**. Esto resalta que ninguna clase tiene su comportamiento completamente fijo, ya que siempre puede ser modificado por una subclase.

