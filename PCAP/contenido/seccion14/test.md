
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

