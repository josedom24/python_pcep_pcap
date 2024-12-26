# LABORATORIO: Un display LED

## Tiempo Estimado

30 minutos

## Nivel de Dificultad

Medio

## Objetivos

* Mejorar las habilidades del alumno al trabajar con cadenas.
* Usar cadenas para representar datos que no son texto.

## Escenario

Seguramente has visto un display de siete segmentos.

Es un dispositivo (a veces electrónico, a veces mecánico) diseñado para presentar un dígito decimal utilizando un subconjunto de siete segmentos. Si aún no sabes lo qué es, consulta la siguiente [enlace](https://en.wikipedia.org/wiki/Seven-segment_display) en Wikipedia.

Podemos representar cada dígito con un número de 7 bits. Cada bit indica si un segmento de un display digital de 7 segmentos debe encenderse (1) o no (0). La corresponencia entre los bits y los segmentos son:

```
  0
 ---
5|   |1
 ---
  6
4|   |2
 ---
  3
```



Tu tarea es escribir un programa que puede simular el funcionamiento de un display de siete segmentos, aunque vas a usar LEDs individuales en lugar de segmentos.

Cada dígito es construido con 13 LEDs (algunos iluminados, otros apagados, por supuesto), así es como lo imaginamos:

```
  # ### ### # # ### ### ### ### ### ### 
  #   #   # # # #   #     # # # # # # # 
  # ### ### ### ### ###   # ### ### # # 
  # #     #   #   # # #   # # #   # # # 
  # ### ###   # ### ###   # ### ### ###
```
Nota: el número 8 muestra todas las luces LED encendidas.

Tu código debe mostrar cualquier número entero no negativo ingresado por el usuario.

Consejo: puede ser muy útil usar una lista que contenga patrones de bits de los diez dígitos.

## Plantilla

```
digits = [ '1111110',  	# 0
	   '0110000',	# 1
	   '1101101',	# 2
	   '1111001',	# 3
	   '0110011',	# 4
	   '1011011',	# 5
	   '1011111',	# 6
	   '1110000',	# 7
	   '1111111',	# 8
	   '1111011',	# 9
	   ]


def print_number(numero):
    # Escribe la función aquí.


print_number(int(input("Ingresa el número que deseas mostrar: ")))
```


## Datos de prueba

Entrada de muestra: `123`

Salida de muestra:
```
  # ### ### 
  #   #   # 
  # ### ### 
  # #     # 
  # ### ### 
```
Entrada de muestra: `9081726354`

Salida de muestra:
```
### ### ###   # ### ### ### ### ### # # 
# # # # # #   #   #   # #     # #   # # 
### # # ###   #   # ### ### ### ### ### 
  # # # # #   #   # #   # #   #   #   # 
### ### ###   #   # ### ### ### ###   # 
```

