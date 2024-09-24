# LABORATORIO - Fundamentos de la sentencia if-else

## Tiempo Estimado

10 - 15 minutos

## Nivel de Dificultad

Fácil/Medio

## Objetivos

Familiarizar al estudiante con:

* Utilizar la sentencia if-else para ramificar la ruta de control.
* Construir un programa completo que resuelva problemas simples de la vida real.

## Escenario

Érase una vez una tierra de leche y miel, habitada por gente feliz y próspera. La gente pagaba impuestos, por supuesto, su felicidad tenía límites. El impuesto más importante, denominado *Impuesto Personal de Ingresos* (IPI, para abreviar) tenía que pagarse una vez al año y se evaluó utilizando la siguiente regla:

* Si el ingreso del ciudadano no era superior a 85.528 euros, el impuesto era igual al 18% del ingreso menos 556 euros y 2 céntimos (esta fue la llamada exención fiscal).
* Si el ingreso era superior a esta cantidad, el impuesto era igual a 14.839 euros y 2 céntimos, más el 32% del excedente sobre 85.528 euros.

Tu tarea es escribir una calculadora de impuestos.

* Debe aceptar un valor de punto flotante: el ingreso.
* A continuación, debe imprimir el impuesto calculado, redondeado a euros totales. Hay una función llamada `round()` que hará el redondeo por ti, la encontrarás en el código que puedes usar de plantilla:

```
income = float(input("Introduce el ingreso anual:"))

#
# Escribe tu código aquí.
#

tax = round(tax, 0)
print("El impuesto es:", tax, "euros")
```

Nota: Este país feliz nunca devuelve dinero a sus ciudadanos. Si el impuesto calculado es menor que cero, solo significa que no hay impuesto (el impuesto es igual a cero). Ten esto en cuenta durante tus cálculos.

Prueba tu código con los datos que hemos proporcionado. 

## Datos de Prueba

* Entrada de muestra: 10000
    * Resultado esperado: El impuesto es: 1244.0 euros
* Entrada de muestra: 100000
    * Resultado esperado: El impuesto es: 19470.0 euros
* Entrada de muestra: 1000
    * Resultado esperado: El impuesto es: 0.0 euros
* Entrada de muestra: -100
    * Resultado esperado: El impuesto es: 0.0 euros 

## Solución

```
income = float(input("Introduce el ingreso anual: "))

if income < 85528:
	tax = income * 0.18 - 556.02
else:
	tax = (income - 85528) * 0.32 + 14839.02

if tax < 0.0:
	tax = 0.0

tax = round(tax, 0)
print("El impuesto es:", tax, "euros")
```

