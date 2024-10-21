## Comparación de cadenas

Las cadenas se comparan carácter a carácter, en el momento en que dos caracteres no son iguales se compara alfabéticamente (es decir, se convierte a código unicode y se comparan).

Ejemplos

```
"a">"A"
True


"informatica">"informacion"
True


"abcde">"abcdef"
False
```
