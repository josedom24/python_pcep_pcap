# Módulo 2: Tipos de datos, variables, operaciones básicas de entrada y salida, operadores básicos 
## Sección 2: Literales de Python 
## Clase: Cadenas

### Literales cadenas

Las cadenas se emplean cuando se requiere procesar texto (como nombres de cualquier tipo, direcciones, novelas, etc.), no números.

Para representar una cadena de caracteres se utilizan las comillas dobles o simples. Este es un ejemplo de una cadena: `"Yo soy una cadena."`.

Sin embargo, hay una cuestión. ¿Cómo se puede codificar una comilla dentro de una cadena que ya está delimitada por comillas?

Supongamos que se desea mostrar un muy sencillo mensaje:

```
Me gusta "Monty Python"
```

¿Cómo se puede hacer esto sin generar un error? Existen dos posibles soluciones.

1. La primera se basa en el concepto ya conocido del **carácter de escape**, el cual recordarás se utiliza empleando la diagonal invertida. La diagonal invertida puede también escapar de la comilla. 

    ```
    print("Me gusta \"Monty Python\"")
    ```

2. La segunda solución puede ser un poco sorprendente. Python puede utilizar una apóstrofe en lugar de una comilla. Cualquiera de estos dos caracteres puede delimitar una cadena, pero para ello se debe ser consistente: si se delimita una cadena con una comilla, se debe cerrar con una comilla, si se inicia una cadena con un apóstrofe, se debe terminar con un apóstrofe.

Este ejemplo funcionará también:

```
print('Me gusta "Monty Python"')
```

### Codificando Cadenas

Ahora, la siguiente pregunta es: ¿Cómo se puede insertar un apóstrofe (comilla simple) en una cadena la cual está limitada por dos apóstrofes?

Intenta imprimir una cadena que contenga el siguiente mensaje:

```
I'm Monty Python.
```

Dos posibles soluciones:

```
print('I\'m Monty Python.')
```

o

```
print("I'm Monty Python.")
```

Como se puede observar, la diagonal invertida es una herramienta muy poderosa, puede escapar no solo comillas, sino también apóstrofes.

Ya se ha mostrado, pero se desea hacer énfasis en este fenómeno una vez mas - una cadena puede estar vacía - puede no contener carácter alguno.

Una cadena vacía sigue siendo una cadena:

```
''
""
```