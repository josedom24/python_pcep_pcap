# El módulo calendar

El módulo `calendar` de la biblioteca estándar de Python proporciona funciones y herramientas útiles para trabajar con calendarios. A diferencia de los módulos `datetime` y `time`, que se centran más en la manipulación de fechas y horas, `calendar` se enfoca en la representación y visualización del calendario.

## Días de la semana

En el módulo `calendar`, los días de la semana se representan con valores enteros de la siguiente manera:

| Día de la semana | Valor entero | Constante         |
|------------------|--------------|-------------------|
| Lunes            | 0            | `calendar.MONDAY` |
| Martes           | 1            | `calendar.TUESDAY`|
| Miércoles        | 2            | `calendar.WEDNESDAY`|
| Jueves           | 3            | `calendar.THURSDAY`|
| Viernes          | 4            | `calendar.FRIDAY` |
| Sábado           | 5            | `calendar.SATURDAY`|
| Domingo          | 6            | `calendar.SUNDAY` |

Como se muestra en la tabla, el primer día de la semana, que es Lunes, se representa con el valor 0, mientras que el último día, Domingo, tiene el valor 6. Estas constantes son útiles para programar y gestionar días dentro del calendario.

## Meses del año

A diferencia de los días de la semana, los meses del año en el módulo `calendar` están indexados a partir de 1, donde:

* Enero es 1
* Febrero es 2
* ... 
* Diciembre es 12

Sin embargo, a diferencia de los días de la semana, el módulo `calendar` no proporciona constantes específicas para representar los meses.

## Visualización de calendarios

Para comenzar a trabajar con el módulo `calendar`, puedes utilizar la función `calendar`, que permite mostrar el calendario completo de un año específico. A continuación, te mostraremos cómo usar esta función para mostrar el calendario del año 2020.

```
import calendar
print(calendar.calendar(2020))
```

Si deseas ajustar el formato del calendario, puedes utilizar los siguientes parámetros opcionales:

- **`w`**: Establece el ancho de la columna de fecha (por defecto es 2).
- **`l`**: Define el número de líneas por semana (por defecto es 1).
- **`c`**: Especifica el número de espacios entre las columnas del mes (por defecto es 6).
- **`m`**: Define el número de columnas (por defecto es 3).

Estos parámetros te permiten personalizar cómo se muestra el calendario según tus necesidades.

Una alternativa a la función `calendar` es la función `prcal`. Esta función también permite mostrar el calendario de un año, pero no requiere el uso de `print` para mostrar el resultado. Su uso es igualmente sencillo:

```
import calendar
calendar.prcal(2020)
```

Al usar `prcal`, el calendario se imprimirá automáticamente en la consola, haciendo que sea una opción conveniente para visualizaciones rápidas.

## Calendario para un mes específico

El módulo `calendar` de Python ofrece una función útil llamada `month`, que permite mostrar el calendario de un mes específico dentro de un año determinado. Esto es especialmente práctico cuando solo necesitas visualizar un mes en lugar de un año completo.

```
import calendar
print(calendar.month(2020, 11))
```
Al igual que con la función `calendar`, puedes personalizar el formato de la función `month` utilizando los siguientes parámetros opcionales:

* **`w`**: Ancho de la columna de fecha (el valor predeterminado es 2).
* **`l`**: Número de líneas por semana (el valor predeterminado es 1).

Estos parámetros te permiten ajustar cómo se presenta el calendario en la salida.

Si prefieres no utilizar `print`, puedes optar por la función `prmonth`, que tiene la misma funcionalidad que `month` pero imprime el calendario directamente en la consola. Su uso es igual de sencillo:

```
import calendar
calendar.prmonth(2020, 11)
```

## Configurando el primer día de la semana

En el módulo `calendar` de Python, el primer día de la semana se establece de manera predeterminada como lunes. Sin embargo, puedes personalizar este comportamiento utilizando la función `setfirstweekday()`. Esta función permite definir cuál será el primer día de la semana al mostrar un calendario.


La función `setfirstweekday()` toma un parámetro que representa el día de la semana como un valor entero. 
Para cambiar el primer día de la semana a domingo, utilizarías la constante `calendar.SUNDAY`, que tiene un valor de 6.

```
import calendar

# Cambiar el primer día de la semana a domingo
calendar.setfirstweekday(calendar.SUNDAY)

# Imprimir el calendario de diciembre de 2020
calendar.prmonth(2020, 12)
```

## Determinando el día de la semana con `weekday()`

El módulo `calendar` de Python ofrece una función muy útil llamada `weekday()`, que te permite determinar el día de la semana correspondiente a una fecha específica. Esta función devuelve un valor entero que representa el día de la semana (el lunes corresponde a 0).

La función `weekday()` toma tres argumentos: el año, el mes y el día. A continuación, se muestra un ejemplo práctico en el que verificamos el día de la semana correspondiente al 24 de diciembre de 2020.

```
import calendar

# Verificar el día de la semana para el 24 de diciembre de 2020
print(calendar.weekday(2020, 12, 24))
```

El resultado es `3`,  esto significa que el 24 de diciembre de 2020 corresponde a un **jueves**, ya que el valor 3 está asignado a ese día.

## Obteniendo encabezados semanales con `weekheader()`

La función `weekheader()` del módulo `calendar` de Python te permite generar una cadena que contiene los nombres abreviados de los días de la semana, útil para mostrar encabezados en un calendario. Puedes especificar el ancho en caracteres para cada nombre de día, aunque si el ancho es mayor que 3, la función seguirá devolviendo las abreviaturas de tres caracteres.

El método toma un argumento que define el ancho de cada nombre de día. Si especificas un ancho menor o igual a 3, recibirás abreviaturas cortas como "Mo" para lunes, "Tu" para martes, etc.

Aquí hay un ejemplo donde especificamos un ancho de 2 caracteres:

```
import calendar

# Obtener encabezados semanales con un ancho de 2 caracteres
print(calendar.weekheader(2))
```

Recuerda que si has cambiado el primer día de la semana usando la función `setfirstweekday()`, esto afectará el orden de los días que se muestran en el resultado de `weekheader()`.

## Años bisiestos

El módulo `calendar` de Python proporciona funciones para determinar si un año es bisiesto y para contar cuántos años bisiestos hay en un rango específico. Aquí te muestro cómo funcionan las funciones `isleap` y `leapdays`.

* La función `isleap(year)` devuelve `True` si el año especificado es bisiesto y `False` si no lo es.
* La función `leapdays(y1, y2)` devuelve el número de años bisiestos en el intervalo que va desde `y1` hasta `y2`, excluyendo el año `y2`.

Veamos un ejemplo en el que comprobamos si el año 2020 es bisiesto y contamos cuántos años bisiestos hay entre 2010 y 2021:

```
import calendar

# Comprobar si 2020 es un año bisiesto
print(calendar.isleap(2020))

# Contar años bisiestos entre 2010 y 2021 (sin incluir 2021)
print(calendar.leapdays(2010, 2021))
```
