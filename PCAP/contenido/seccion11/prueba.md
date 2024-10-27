# Prueba intermedia

1. Una estructura de datos descrita como LIFO es en realidad:

    * Un montón
    * Una pila
    * Una lista
    * Un arból

2. Si el constructor de la clase se declara de la siguiente manera, ¿cuál de las asignaciones es válida?

    ```
    class Class:
        def __init__(self):
            pass
    ```

    * `object = Class`
    * `object = Class(self)`
    * `object = Class()`
    * `object = Class(object)`

3. Si hay una superclase llamada A y una subclase llamada B, ¿cuál de las invocaciones presentadas debería poner en lugar del comentario?
    ```
    class A:
        def __init__(self):
            self.a = 1
    
    
    class B(A):
        def __init__(self):
            # Colocar la línea seleccionada aquí.
            self.b = 2
    ```

    * `A.__init__()`
    * `A.__init__(self)`
    * `A.__init__(1)`
    * `__init__()`

4. ¿Cuál será el efecto de ejecutar el siguiente código?

    ```
    class A:
        def __init__(self,v):
            self.__a = v + 1
    
    
    a = A(0)
    print(a.__a)
    ```

    * El código generará una excepción `AttributeError`
    * 1
    * 0
    * 2

5. ¿Cuál será la salida del siguiente código?

    ```
    class A:
        def __init__(self,v = 1):
            self.v = v
    
        def set(self,v):
            self.v = v
            return v
    
    
    a = A()
    print(a.set(a.v + 1))
    ```

    * 2
    * 1
    * 0
    * 3

6. ¿Cuál será la salida del siguiente código?

    ```
    class A:
        X = 0
        def __init__(self,v = 0):
            self.Y = v
            A.X += v
    
    
    a = A()
    b = A(1)
    c = A(2)
    print(c.X)
    ```

    * 3
    * 2
    * 0
    * 1

7. ¿Cuál será la salida del siguiente código?

    ```
    class A:
        A = 1
    
    
    print(hasattr(A,'A'))
    ```

    * False
    * True
    * 0
    * 1

8. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
         def __init__(self):
            pass
    
    
    a = A(1)
    print(hasattr(a,'A'))
    ```

    * 1
    * False
    * True
    * Generará una excepción

9. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
        def __str__(self):
            return 'a'
    
    
    class B(A):
        def __str__(self):
            return 'b'
    
    
    class C(B):
        pass
    
    
    o = C()
    print(o)
    ```

    * Imprimirá b
    * Generará una excepción
    * Imprimirá c
    * Imprimirá a

10. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
        pass
    
    
    class B(A):
        pass
    
    
    class C(B):
        pass
    
    
    print(issubclass(C,A))
    ```

    * Generará una excepción
    * Imprimirá True
    * Imprimirá 1
    * Imprimirá False

11. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
        def a(self):
            print('a')
    
    
    class B:
        def a(self):
            print('b')
    
    
    class C(B,A):
        def c(self):
            self.a()
    
    
    o = C()
    o.c()
    ```

    * Imprimirá c
    * Imprimirá a
    * Imprimirá b
    * Generará una excepción

12. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
        def __str__(self):
            return 'a'
    
    
    class B:
        def __str__(self):
            return 'b'
    
    
    class C(A, B):
        pass
    
    
    o = C()
    print(o)
    ```

    * Imprimirá a
    * Imprimirá c
    * Generará una excepción
    * Imprimirá b

13. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class A:
        v = 2
    
    
    class B(A):
        v = 1
    
    
    class C(B):
        pass
    
    
    o = C()
    print(o.v)
    ```

    * Imprimirá 1
    * Imprimirá una línea vacía
    * Imprimirá 2
    * Generará una excepción

14. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    def f(x):
        try:
            x = x / x
        except:
            print("a",end='')
        else:
            print("b",end='')
        finally:
            print("c",end='')
    
    
    f(1)
    f(0)
    ```

    * Generará una excepción no controlada
    * Imprimirá `acac`
    * Imprimirá `bcbc`
    * Imprimirá `bcac`

15. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    try:
        raise Exception(1,2,3)
    except Exception as e:
        print(len(e.args))
    ``` 

    * Imprimirá 2
    * Imprimirá 3
    * Imprimirá 1
    * Generará una excepción no controlada

16. ¿Cuál será el resultado de ejecutar el siguiente código?

    ```
    class Ex(Exception)
        def __init__(self, msg):
            Exception.__init__(self, msg + msg)
            self.args = (msg,)
    
    
    try:
        raise Ex('ex')
    except Ex as e:
        print(e)
    except Exception as e:
        print(e)
    ```

    * Imprimirá `ex`
    * Imprimirá una línea vacía
    * Generará una excepción no controlada
    * Imprimirá `exex`

