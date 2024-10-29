
1. ¿Cuál es el resultado esperado del siguiente código?
    ```
    def my_fun():
        for num in range(3):
            yield num

    for i in my_fun():
        print(i)
    ```
    * ```
      0
      1
      2
      ```
    * `SyntaxError`
    * `generator object my_fun at` alg\u00fan némero hexadecimal

2. ¿Cual es el resultado esperado del siguiente código?
    ```
    foo = [i + i for i in range(5)]
    print(foo)
    ```      
    
    * `[0, 2, 4, 6, 8]`
    * `[1, 3, 5, 7, 9]`
    * ```
      0
      2
      4
      6
      8
      ```

3. ¿Cual es el resultado esperado del siguiente código?
    ```
    x = lambda a, b: a ** b
    print(x(2, 10))
    ```
          
    * `1024`
    * `2222222222`
    * `SyntaxError`

4. Selecciona las sentencias verdaderas con respecto a la función `map()`. (Selecciona dos respuestas)
          
    * [ ] La función `map()` puede aceptar más de dos argumentos
    * [ ] El segundo argumento de la función `map()` puede ser una lista
    * [ ] El primer argumento de la función `map()` puede ser una lista
    * [ ] La función `map()` puede aceptar solamente dos argumentos

5. Selecciona las sentencias verdaderas respecto a la función `filter()`. (Selecciona dos respuestas)
          
    * [ ] La función filter `filter()` tiene la siguiente sintaxis: `filter(function, iterable)`
    * [ ] La función `filter()` devuelve un iterador
    * [ ] La función `filter()` no retorna un iterador
    * [ ] La función `filter()` tiene la siguiente sintaxis: `filter(iterable, function)`

6. ¿Cual es el resultado esperado del siguiente código?
    ```
    numbers = (1, 2, 5, 9, 15)

    def filter_numbers(num):
        nums = (1, 5, 17)
        if num in nums:
            return True
        else:
            return False


    filtered_numbers = filter(filter_numbers, numbers)
    for n in filtered_numbers:
        print(n)
    ```  
          
    * ```
      1
      5
    ```
    * `2, 9, 15`
    * `SyntaxError`

7. ¿Cuales de las siguientes sentencias son verdaderas? (Selecciona dos respuestas)
          
          
    * [ ] Una lista por compresión se convierte en un generador cuando se utiliza entre paréntesis (por ejemplo, `()`), no con corchetes (por ejemplo, `[]`)
    * [ ] La función `map()` crea una copia de su segundo argumento y le aplica el primer argumento
    * [ ] La sentencia `yield` debe ser empleada fuera de las funciones
    * [ ] La declaración de una función `lambda` es la misma que la de una función regular.

8. Los dos modos básicos de apertura de archivos, mutuamente excluyentes, se denominan:

    * Binario y de texto
    * Binario y ternario
    * De texto e imagen

9. Un método capaz de leer datos de un archivo y pasarlos a un arreglo de bytes se denomina:,

    * `readinto()`
    * `readout()`
    * `readin()`

10 .¿Qué sucede si se ejecuta el siguiente código, asumiendo que el directorio `d` ya existe?
    ```
    import os
    os.mkdir("/a/b/c/d")
    ```
    * Se genera una excepción `FileExistsError`
    * Se genera una excepción `DirectoryExistsError`
    * Python sobrescribirá el directorio existente

11. ¿Qué sucede si se ejecuta el siguiente código?
    ```
    import time
    time.sleep(30)
    print("¡Despierta!")
    ```
    * La cadena `¡Despierta!` se mostrará en la pantalla después de 30 segundos
    * La cadena `¡Despierta!` se mostrará treinta veces en la pantalla durante 30 segundos
    * La cadena `¡Despierta!` se mostrará en la pantalla durante 30 segundos

12. ¿Cual es el resultado esperado del siguiente código?
    ```
    import calendar
    
    cal = calendar.isleap(2019)
    print(cal)
    ```

    * `False`
    * `True`
    * `None`
