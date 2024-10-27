# Test intermedio: comprueba lo que has aprendido

1. Una subclase suele ser:
    * Más especializada que su superclase
    * Más general que su superclase
    * Una copia de su superclase
                
2. Un objeto se caracteriza por los siguientes tres aspectos:
   
    * nombre, propiedades, métodos
    * nombre, dueño, posesión
    * propiedades, fincas, tierras
                
3. Un nombre alternativo para una estructura de datos llamada pila es:
   
    * LIFO
    * FIFO
    * FOLO
                
4. Una variable que existe como un ser separado en objetos separados se llama:
   
    * Una variable de instancia
    * Una variable separada
    * Una variable orientada a objetos
                
5. Una función capaz de comprobar si un objeto está equipado con una propiedad determinada se llama:
   
    * `hasattr()`
    * `hasvar()`
    * `hasprop()`
                
6. ¿Hay alguna forma de comprobar si una clase es una subclase de otra clase?
   
    * Sí, hay una función capaz de hacer eso
    * No
    * Puede ser posible, pero solo bajo condiciones especiales
                
7. La función llamada `super()` puede ser utilizada para:
   
    * Acceder a los atributos o métodos de una superclase
    * Hacer una clase super
    * Hacer una clase mejor
                
8. Una excepción definida por el usuario:
   
    * Puede derivarse de la clase `Exception`
    * No debe derivarse de la clase `Exception`
    * Debe derivarse de la clase `Exception`
                
9. Selecciona las sentencias verdaderas. (Selecciona dos< respuestas)

    * [ ] El bloque `finally` de la sentencia `try` es siempre ejecutado.
    * [ ] La propiedad `args` es una tupla diseñada para recopilar todos los argumentos pasados al constructor de la clase.
    * [ ] El bloque `finally` de la sentencia `try` puede ser ejecutado si se cumplen condiciones especiales.
    * [ ] No se pueden definir nuevas excepciones como subclases derivadas de excepciones predefinidas.
                
10. ¿Cuál es la salida del siguiente código?

    ```
    import math
    try:
        print(math.pow(2))
    except TypeError:
        print(\"A\")
    else:
        print(\"B\")
    ```
  
    * `A`
    * `B`
    * El programa provocará una excepción `ValueError`
                   