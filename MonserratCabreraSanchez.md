Monserrat Cabrera Sánchez

# Ejercicios con algoritmos

## Ejercicio 1

_Calcular la letra del DNI Español_

**Paso 1**: Definir el problema, a partir de un número de DNI hemos de calcular la letra.

- ¿Cómo se calcula la letra del DNI?

Número del DNI dividirlo entre 23 y el resto será el ```resultadoResto```.

El ```resultadoResto``` lo compararemos con la lista de códigos de la siguiente tabla de letras ```tablaLetrasDni```.

El código lo compararemos con la lista de códigos:

| resultadoRoesto | Letra |
| :-------------: | :---: |
|        0        |   T   |
|        1        |   R   |
|        2        |   W   |
|        3        |   A   |
|        4        |   G   |
|        5        |   M   |
|        6        |   Y   |
|        7        |   F   |
|        8        |   P   |
|        9        |   D   |
|       10        |   X   |
|       11        |   B   |
|       12        |   N   |
|       13        |   J   |
|       14        |   Z   |
|       15        |   S   |
|       16        |   Q   |
|       17        |   V   |
|       18        |   H   |
|       19        |   L   |
|       20        |   C   |
|       21        |   K   |
|       22        |   E   |

Ejemplo: El ``DNI`` con 11111111 tiene asociada la letra P, pues 8 es el resto de dividir 8 entre 23.

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ```DNI``` y ```tablaLetrasDNI```.

Proceso:

-  Validar que el ```DNI```  tenga 8 dígitos, y que sean todos numéricos enteros.
  - Si es errónea, asigne a la variable ```resultadoResto``` "DNI invalido"
- Dividimos ```DNI```  en 23 y el resto lo asignamos a ``resultadoResto``.
- Comparar el ```resultadoResto``` con los valores de la tabla ```tablaLetrasDNI``` y asignar a ``resultado`` el valor equivalente en la tabla.

Salida: 

- Escribir ``resultado``.

**Paso 3**: Escribir el pseudocódigo.

``` 
Algoritmo CalculoDNI
	# Entrada
	DNI <- leer()
	tablaLetrasDNI <- "TRWAGMYFPDXBNJZSQVHLCKE"
	# Proceso
	Si DNI es menor o igual que 99999999
		resultadoResto <- DNI mod 23 #mod es el resultado de dividir
		resultado <- tablaLetrasDNI[resultadoResto]
	Sino
		resultado <- "DNI Invalido"
	Fin si
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 2

_Nominas_

**Paso 1**: Definir el problema

El salario en España se calcula a partir del salario bruto anual, que incluye todas las percepciones económicas que recibe un trabajador durante un año, incluyendo salario base, pagas extras, complementos y otros conceptos retributivos.

A partir del salario bruto se deducen las cotizaciones a la Seguridad Social y el Impuesto sobre la Renta de las Personas Físicas (IRPF), que varían en función del nivel salarial y la situación personal del trabajador.

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``salarioBase``, ``pagasExtras``, ``complementos``, ``otrosConceptosRetributivos``, ``IRP``, ``SeguridadSocial``.

Proceso:

- Sumar ``salarioBase``,  ``pagasExtras``, ``complementos``, ``otrosConceptosRetributivos`` y/o asigno a ``salarioBruto``.
- Sumar ``IRP``, ``SeguridadSocial`` y lo asigno a ``deducciones.``
- ``salarioNeto`` asigna ``salarioBruto`` - ``deducciones.``

Salida:

Escribir(``salarioBruto``,``salarioNeto``)

**Paso 3**: Escribir el pseudocódigo

```
Algoritmo CalculoDNI
	# Entrada
	salarioBase <- Leer()
	pagasExtras <- Leer()
	complementos <- Leer()
	otrosconceptosRetributivos <- Leer()
	IRP <- Leer()
	SaguridadSocial <- Leer()
	# Proceso
	salarioBruto<-salarioBase+pagasExtras+complementos+otrosConcpetosRetributivos
	deducciones <- IRP+SeguridadSocial
	# Salida
	Escribir(salarioBruto, salarioNeto)
FinAlgoritmo
```



## Ejercicio 3

_Determinar la ruta para llegar a una ciudad por avión_

**Paso 1**: Definir el problema.

Se desea viajar de Lanzarote a Tampa Florida (EEUU), suponiendo que se desea el vuelo que menos tiempo tarde. Para ello se van a tomar los diferentes destinos que hay desde cada ciudad. 

![](C:\Users\monts\AppData\Roaming\Typora\typora-user-images\image-20230323185825430.png)

En el momento en el que se hizo el ejercicio se decidió el trayecto Lanzarote (ACE) - Tenerife Sur (TFS) - Nueva York Newark, NJ (EWR) - Tampa (TPA).

Entre los aeropuerto que se incluyen, se encuentran: Roma Fiumicino (FCO), Madrid (MAD), Gran Canaria (LPA), Londres City (LCY), París Charles de Gaulle (CDG), Zúrich (ZRH), Nassau International (NAS), Toronto Island (YTZ).

Para ello se toman varias listas de cadenas donde se incluyen diferentes destinos de cada aeropuerto.

``ACE`` = ["LPA", "TFS", "MAD", "LCY"]

``TFS`` = ["ACE", "CDG", "EWR",  "ZHR"]

``EWR`` = ["TPA", "TFS", "NAS", "YTZ"]

Resultado del algoritmo ``Viaje``(``ACE``,``TFS``,``EWR``) devuelve "ACE - TFS - EWR -TPA"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``ÀCE``, ``TFS``, ``EWR``.

Proceso: 

- Se cuenta el número de elementos de ``ACE`` y se asigna el valor a ``n`` (resulta que todas las variables presentan el mismo número de elementos).
- Asignar a ``i`` el valor 0.
- Repetir hasta que ``i`` sea mayor que ``n-1``:
  - Si ``ACE[i]`` es igual a  "TFS" entonces:
    - A ``resultado`` se le asigna el valor ``ACE[i]``.
    - A ``resultado`` se le añade el valor " - ".
    - Asignar a ``i`` el valor ``n``.
  - Sino asignar a ``i`` el valor ``i+1``.
- Asignar a ``i`` el valor 0.
- Repetir hasta que ``i`` sea mayor que ``n-1``:
  - Si ``TFS[i]`` es igual a  "EWR" entonces:
    - A ``resultado`` se le añade el valor ``TFS[i]``.
    - A ``resultado`` se le añade el valor " - ".
    - Asignar a ``i`` el valor ``n``.
  - Sino asignar a ``i`` el valor ``i+1``.
- Asignar a ``i`` el valor 0.
- Repetir hasta que ``i`` sea mayor que ``n-1``:
  - Si ``EWR[i]`` es igual a  "TPA" entonces:
    - A ``resultado`` se le añade el valor ``EWR[i]``.
    - Asignar a ``i`` el valor ``n``.
  - Sino asignar a ``i`` el valor ``i+1``.

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Viaje
	# Entrada
	ACE <- Leer()
	TFS <- Leer()
	EWR <- Leer()
	# Proceso
	Subalgoritmo ContarElementosLista(lista)
		contador <- 1 # contador de elementos de la lista
	 	i <- 0 # posición de la lista
	 	Mientras lista[i] sea diferente de finlista Haga
	 		Si Lista[i] es diferente de finlista Entonces
	 			contador <- contador+1 
	 		FinSi
	 	FinMientras
		Devolver i
	FinSubalgoritmo
	n <- ContarElementosLista(ACE) # En este caso todas las variables de entrada tienen la misma dimensión
	i <- 0
	Repetir 
		Si ACE[i] es igual a "TFS" Entonces
			resultado <- ACE[i]
			resultado <- resultado + " - "
			i <- n
		Sino
			i <- i+1
		FinSi
	Hasta que i sea mayor que n-1
	i <- 0
	Repetir 
		Si TFS[i] es igual a "EWR" Entonces
			resultado <- resultado + TFS[i]
			resultado <- resultado + " - "
			i <- n
		Sino
			i <- i+1
		FinSi
	Hasta que i sea mayor que n-1
	i <- 0
	Repetir 
		Si EWR[i] es igual a "TFS" Entonces
			resultado <- resultado + EWR[i]
			i <- n
		Sino
			i <- i+1
		FinSi
	Hasta que i sea mayor que n-1
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 4

_Calcula el área y perímetro de un círculo dado su radio_

**Paso 1**: Definir el problema, dado un radio calcular el área y el perímetro.

El círculo es una figura geométrica cerrada con todos sus puntos equidistantes de un punto central llamado centro. El círculo es una figura importante en matemáticas y física debido a sus propiedades geométricas y aplicaciones en la vida real.

El perímetro de un círculo es la longitud de la línea curva que rodea el círculo. La fórmula para calcularlo es:

perímetro = 2πr, 

donde r es el radio del círculo y π (pi) es una constante matemática aproximadamente igual a 3.14159. 

El área de un círculo se define como la cantidad de espacio dentro del círculo. La fórmula para calcularla es:

área = πr²,

donde r es el radio del círculo.

Ejemplo:

radio=1

El algoritmo ``AreaPerimetro``(radio) devuelve pi, 2pi

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``radio``

Proceso: 

- Multiplicar por un lado el ``radio`` por ``pi`` y por 2, asignar este valor a ``perimetro``.

-  Multiplicar  el ``radio`` por ``radio`` y por ``pi``, asignar este valor a ``perimetro``.

Salida:

Escribir(``area``,``perimetro``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo AreaPerimetro
	# Entrada
	radio<-Leer()
	# Proceso
	area<-radio multiplicar por pi por 2
	perimetro<-radio multiplicar por radio por pi
	# Salida
	Escribir(area, perimetro)
FinAlgoritmo
```



## Ejercicio 5

_Dada una lista de números enteros, determina cuál es el mayor y cuál es el menor_

**Paso 1**: Definir el problema se tiene una lista de números enteros y se debe determina cuál es el mayor y cuál es el menor.

Ejemplo:

listaEntero=[1,5,7,4,2]

El algoritmo ``MayorMenoLista``(listaEntero) devolverá 1, 7

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``listaEnteros``

Proceso:

- Se cuenta el número de elementos de ``listaEnteros`` y se asigna el valor a ``n``.
- Se crea ``listaOrdenada`` con ``n-1`` ceros.
- Se realiza un bucle para, este pretende ordenar todos los elementos de la lista. Para ``i`` empezando en 0 hasta que sea igual a ``n-1``. Se asigna a ``menorEntero`` el valor de ``listaOrdenada[i]``.
- Se realiza un bucle para anidado para recorre ``listaOrdenada``. Para ``j`` empezando en ``i`` hasta que sea igual a ``n-1``. Si ``menorEntero`` es mayor que ``listaEnteros[j]``,entonces se asigna el valor ``listaEnteros[j]`` a ``menorEntero``. 
- Tras finalizar el bucle anidado, el ``i``-menor elemento de la posición vendrá dado por ``menorEntero``, por lo que se asigna ``menorEntero`` a ``listaOrdenada[i]``.
- Asignar el primero valor de ``listaOrdenada`` a ``menorNumero``.
- Asignar el último valor de ``listaOrdenada`` a ``mayorNumero``.

Salida: Escribir(``menorNumero``, ``mayorNumero``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo MayorMenoLista
	# Entrada
	listaEnteros <- Leer()
	# Proceso
	n <- ContarElementosLista(listaEnteros)
	listaOrdenada[n-1] # Se define una lista con n elementos
	Para i=0 Hasta n-1 con paso 1 Hacer
		menorEntero <- listaOrdenada[i]
		Para j=i Hasta n-1 con paso 1 Hacer
			Si menorEntero es mayor que listaEnteros[j] Entonces
				menorEntero <- listaEnteros[j]			
			FinSi
		FinPara
		listaOrdenada[i] <- menorEntero
	FinPara
	menorNumero <- listaOrdenada[0]
	mayorNumero <- listaOrdenada[n-1]
	# Salida
	Escribir(menorNumero, mayorNumero)
FinAlgoritmo
```



## Ejercicio 6

_Crea un algoritmo que convierta grados Celsius a Fahrenheit_

**Paso 1**: Definir el problema, se debe crear un algoritmo que convierta grados Celsius a Fahrenheit.

La fórmula para convertir una temperatura en grados Celsius (°C) a grados Fahrenheit (°F) es la siguiente:

°F = (°C x 1.8) + 32

Esto significa que se debe multiplicar la temperatura en grados Celsius por 1.8 y luego sumar 32 para obtener la temperatura equivalente en grados Fahrenheit.

Es importante tener en cuenta que la escala Celsius se utiliza comúnmente en muchos países, mientras que la escala Fahrenheit se utiliza principalmente en los Estados Unidos y algunos otros países. En algunas situaciones, como en la ciencia y la medicina, se utilizan otras escalas de temperatura, como la escala Kelvin.

Ejemplo:

gradosCelsius=10

El algoritmo ``CelsiusFahrenheit``(gradosCelsius) devolverá 50

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``gradosCelsius``

Proceso: 

- Se multiplicar ``gradosCelsius`` por 1.8 y al resultado se le suma 32. Asignando el valor final a ``gradosFahrenheit``.

Salida:

Escribir(``gradosFahrenheit``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo CelsiusFahrenheit
	# Entrada
	gradosCelsius <- Leer()
	# Proceso
	gradosFahrenheit <- gradosCelsius multiplicado por 1.8+32
	# Salida
	Escribir(gradosCelsius)
FinAlgoritmo
```



## Ejercicio 7

_Par o impar_

**Paso 1**: Definir el problema, dado un número entero, crea un algoritmo que determine si es par o impar.

Un número par es aquel que al dividirse entre 2 su resto es 0 y por el contrario, si el resto es 1, entonces se trata de un número impar.

Ejemplo:

numero=12

El algoritmo ``ParImpar``(numero) devolverá "es par"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``numero``

Proceso: 

- Si el resto de dividir ``numero`` entre 2 es 0, entonces se asigna a ``resultado`` "es par".
- En caso contrario, se asigna a ``resultado`` "es impar".

Salida:

Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo ParImpar
	# Entrada
	numero <- Leer()
	# Proceso
	Si numero mod 2 es igual a 0 Entonces
    	resultado <- "es par"
    Sino
    	resultado <- "es impar"
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 8

_Bisiesto_

**Paso 1**: Definir el problema, crea un algoritmo que determine si un año es bisiesto o no.

Un año bisiesto es aquel que tiene 366 días en lugar de los 365 días habituales de un año común. Esto se debe a que en un año bisiesto se agrega un día extra, el 29 de febrero, para compensar el desfase que existe entre el calendario gregoriano (que se utiliza actualmente) y el año solar (el tiempo que tarda la Tierra en dar una vuelta alrededor del Sol).

Para determinar si un año es bisiesto o no, se debe seguir la siguiente regla: un año es bisiesto si es divisible entre 4 pero no es divisible entre 100, o si es divisible entre 400.

Ejemplo:

año=4040

El algoritmo ``Bisiesto``(año) devolverá "es bisiesto"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``año``

Proceso:

- Si al dividir ``año`` entre 4  su resto es 0 y al dividir ``año`` entre 100 su resto es diferente a 0, entonces asignar a ``resultado`` "es bisiesto".
- En caso contrario, asignar a ``resultado`` "no es bisiesto"

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Bisiesto
	# Entrada
	año <- Leer()
	# Proceso
	Si año mod 4 es igual a 0 y año mod 100 es diferente a 0 Entonces 
		resultado <- "es bisiesto"
	Sino
		resultado <- "no es bisiesto"
	FinSi
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 9

_Palíndromo_

**Paso 1**: Definir el problema, crea un algoritmo que determine si una cadena de texto es un palíndromo o no.

Un palíndromo es una palabra, frase o número que se lee igual de izquierda a derecha que de derecha a izquierda.

Ejemplo:

cadena=ojo

El algoritmo ``Palindromo``(cadena) devolverá "es palindromo"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``cadena``

Proceso:

- Se lee en sentido inverso ``cadena`` y se asigna el resultado a ``cadenaInversa`` para ello:
  - Se cuenta el número de elementos de la ``cadena``, se resta 1 y se asigna el valor a ``n``.
  - Se crea la variable ``cadenaInversa``, que se inicializa vacía.
  - Es necesario realizar un bucle mientras para concatenar la ``cadenaInversa``. Mientras ``n`` sea mayor que 0, se concatena ``cadenaInversa`` con el elemento ``n`` de la ``cadena``.
- Se compara ``cadena`` con ``cadenaInversa``:
  - Si son iguales asignar a ``resultado`` "es palindromo".
  - Sino son iguales, asignar a ``resultado`` "no es palindromo".

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Palindromo
	# Entrada
	cadena <- Leer()
	# Proceso
	n <- ContarElementosLista(cadena)-1
	cadenaInversa <- ""
	Mientras n sea mayor o igual que 0 hacer
		cadenaInversa <- cadenaInversa + cadena[n]
		n <- n-1
	FinMientras
	Si cadena es igual a cadenaInversa Entonces
		resultado <- "es palindromo"
	Sino
		resultado <- "no es palindromo"
	FinSi
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 10

_Lista ordenada alfabéticamente_

**Paso 1**: Definir el problema,  dada una lista de nombres, crea un algoritmo que ordene la lista alfabéticamente.

ASCII (American Standard Code for Information Interchange) es un conjunto de caracteres que se utiliza para representar los caracteres en una computadora. Es un estándar de codificación de caracteres de siete bits, que asigna un número único a cada caracter y símbolo comúnmente utilizado en el idioma inglés, incluyendo letras, números, signos de puntuación y caracteres especiales.

Cada caracter ASCII se representa con un número decimal que va desde 0 a 127, que es el rango de los siete bits que se utilizan para codificarlos. Por ejemplo, el número ASCII para la letra "A" mayúscula es 65, y el número ASCII para la letra "a" minúscula es 97.

En la actualidad, ASCII ha sido sustituido por otros estándares de codificación de caracteres más avanzados, como Unicode, que incluye muchos más caracteres, incluyendo aquellos utilizados en otros idiomas además del inglés. Sin embargo, el conjunto de caracteres ASCII sigue siendo importante y se utiliza como base para muchos otros estándares de codificación de caracteres.

Ejemplo:

lista=["Atardecer",  "Amanecer",  "Anochecer"]

El algoritmo ``ListaORdenada``(lista) devolverá ["Amanecer", "Anochecer", "Atardecer"]

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``lista``

Proceso:

- Se ordena alfabéticamente la lista:

  - Se cuenta el número de elementos de la ``lista`` y se agina a ``n``.
  - Se crea una variable ``listaOrdenada``, que es donde se van a ordenar los nombres alfabéticamente.
  - Se van a ordenar las palabras de ``lista`` en orden alfabético, por lo que es necesario hacer un bucle para. Para i=0 Hasta n-2 con paso 1, se asigna a ``menorPalabra`` el elemento ``listaOrdenada[i]``. 
  - Se requiere un bucle para anidado, que empiece en la variable de posición del bucle anterior. Este tiene por finalidad almacenar la ``menorPalabra`` que hay desde la posición ``i`` en adelante y  su localización en ``posicion``.
  - Tras acabar el bucle anidado, se sustituirán los valores. De forma que, se almacenará el elemento ``i`` en   ``temporal`` y ``listaOrdenada[posicion]`` se intercambiará el elemento menor que se encuentra en ``menorPalabra`` por ``temporal``.

Salida: Escribir(``listaOrdenada``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo ListaOrdenada
	# Entrada
	lista <- Leer()
	# Proceso
	n <- ContarElementosLista(lista)
	listaOrdenada <- lista
	Para i=0 Hasta n-2 con paso 1 Hacer
		menorPalabra <- listaOrdenada[i]
		Para j=i Hasta n-1 con paso 1 Hacer
			Si menorPalabra es mayor que listaOrdenada[j] Entonces
				menorPalabra <- listaOrdenada[j]
				posicion <- j
			FinSi
		FinPara
		temporal <- listaOrdenada[i]
		listaOrdenada[i] <- menorPalabra
		listaOrdenada[posicion] <- temporal
	FinPara
	# Salida
	Escribir(listaOrdenada)
FinAlgoritmo
```



## Ejercicio 11

_Factorial_

**Paso 1**: Definir el problema, crea un algoritmo que calcule el factorial de un número entero.

El factorial de un número entero positivo k, representado como k!, se define como el producto de todos los números enteros positivos desde 1 hasta k. Matemáticamente, se expresa como:

k! = 1 x 2 x 3 x ... x k

Ejemplo:

entero = 4

El algoritmo ``Factorial``(4) devolverá 24

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``entero``.

Proceso:

- Asignar a ``i`` el valor ``entero``.

- Se debe realizar un bucle mientras (también vale un bucle para con paso -1), para multiplicar la variable ``factorial`` por el número ``i`` menores que ``entero``, hasta el 1. 

- Salida: Escribir(``factorial``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Factorial
	# Entrada
	entero <- Leer()
	# Proceso
	i <- entero
	Mientras i sea mayor que 1 Hacer
		factorial <- factorial multiplicado por i
		i <- i-1
	FinMientras
	# Salida
	Escribir(factorial)
FinAlgoritmo
```



## Ejercicio 12

_Primo_

**Paso 1**: Definir el problema, dado un número entero, crea un algoritmo que determine si es primo o no.

Un número primo es un número entero mayor que 1 que solo es divisible por 1 y por sí mismo.

Ejemplo

número=13

El algoritmo ``NumeroPrimo``(13) devolverá "es primo"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``posiblePrimo``

Proceso:

- Crear una variable ``primo`` inicializada a ``True``.
- Asignar a ``numero`` el valor ``posiblePrimo-1``.
- Se debe realizar un bucle mientras, para comprobar si ``posiblePrimo`` módulo ``numero`` es igual a 0 y ``numero`` debe tomar cualquier valor mayor que 2. En caso de que el módulo sea 0, se asigna a ``primo`` el valor ``False`` y se sale del bucle mientras, asignando a ``numero`` el valor 1.
- Según el valor de ``primo``, la variable ``resultado`` será "es primo" o "no es primo."

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo NumeroPrimo
	# Entrada
	posiblePrimo <- Leer()
	# Proceso
	primo <- True
	numero <- posiblePrimo-1
	Mientras numero sea mayor o igual que 2 Hacer
		Si posiblePrimo mod numero es igual a 0 Entonces
			primo <- False
			numero <- 1 # break
		FinSi
		numero<-numero-1
	FinMientras
	Si primo es igual a True Entonces
		resultado <- "es primo"
	Sino 
		resultado <- "no es primo"
	Fin Si
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 13

_Calcular área y volumen de un cubo, según su lado_

**Paso 1**: Definir el problema, crea un algoritmo que calcule el área y volumen de un cubo dado su lado.

El área y el volumen de un cubo se pueden calcular de la siguiente manera:

- Área de un cubo: es la suma de las áreas de las seis caras del cubo. Todas las caras de un cubo son cuadrados con el mismo lado, por lo que el área de cada cara se puede calcular como el lado al cuadrado. Entonces, el área total del cubo se calcula multiplicando el área de una cara por seis.

Área = 6 x (lado)^2

- Volumen de un cubo: se calcula elevando al cubo la longitud de uno de los lados del cubo.

Volumen = (lado)^3

Ejemplo:

lado=4

El algoritmo ``AreaVolumenCubo``(lado) devolverá 96, 64

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``lado``

Proceso:

- Elevar``lado`` al cubo , asignar este valor a ``volumen``.
- Multiplicar  el ``lado`` por  si mismo y por 6 que es el número de caras de un cubo, asignar este valor a ``area``.

Salida:

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo AreaVolumenCubo
	# Entrada
	lado <- Leer()
	# Proceso
	volumen <- lado multiplicado por lado por lado
	area <- lado multiplicado por lado por 6
	# Salida
	Escribir(area, volumen)
FinAlgoritmo
```



## Ejercicio 14

_Suma de los elementos pares de una lista_

**Paso 1**: Definir el problema, dada una lista de números enteros, crea un algoritmo que calcule la suma de todos los números  pares de la lista.

Ejemplo:

lista=[1,2,3,4]

El algoritmo ``SumaPar``(lista) devolverá 6 

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``lista``

Proceso: 

- Se cuenta el número de elementos en ``lista`` y se asigna a la variable ``n``.
- Se asigna a una variable ``suma`` el valor 0.
- Se debe hacer un bucle para, con la finalidad de recorrer la ``lista`` buscando los elementos pares y sumar los mismos a la variable ``suma``.

Salida: Escribir(``suma``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo SumaPar
	# Entrada
	lista <- Leer()
	# Proceso
	suma <- 0
	n <- ContarElementosLista(lista)
	Para i=0 Hasta n-1 con paso 1 Hacer
		Si lista[i] mod 2 es igual a 0 Entonces
    		suma <- suma + lista[i]
    	FinSi
	FinPara
	# Salida
	Escribir(suma)
FinAlgoritmo
```



## Ejercicio 15

_Tipo de número_

**Paso 1**: Definir el problema, crea un algoritmo que determine si un número es positivo, negativo o cero.

Un número positivo es todo aquel que sea mayor que 0 y negativo es todo el que esté por debajo de 0.

Ejemplo:

numero=``pi`` 

El algoritmo ``TipoNumero``(``pi``) devolverá "es positivo"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``numero``

Proceso: 

Según el ``numero`` hacer:

- Si ``numero`` es mayor que 0:
  - Se asigna "es positivo" a ``resultado``.
- O si el ``numero`` es igual a 0:
  - Se asigna "es cero" a ``resultado``.
- Sino el ``numero`` es menor que 0:
  - Se asigna "es negativo" a ``resultado``.

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo TipoNumero
	# Entrada
	numero <- Leer()
	# Proceso
	Si numero es mayor que 0 Entonces
		resultado <- "es positivo"
	Sino numero es menor que 0 Entonces
		resultado <- "es negativo"
	Sino
		resultado <- "es cero"
	FinSi
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 16

_Media de una lista_

**Paso 1**: Definir el problema, dada una lista de números enteros, crea un algoritmo que calcule la media de la lista.

La media es un valor numérico que representa el centro de un conjunto de datos. 

Se obtiene sumando todos los valores de un conjunto de datos y dividiendo la suma por la cantidad de elementos en el conjunto.

La fórmula para calcular la media es:

Media = (sumatorio de los valores) / (cantidad de valores)

Ejemplo:

lista=[1,2,3,4]

El algoritmo ``MediaLista``(lista) devolverá 2.5 (que es 10/4)

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``lista``

Proceso:

- Se cuenta el número de elementos en ``lista`` y se asigna a la variable ``n``.
- Se debe hacer un bucle para, este pretende recorrer todos los elementos de ``lista``, para incorporar su valor a ``suma``.
- Dividir ``suma`` entre ``n`` y asignar el resultado a la variable ``media``.

Salida:

Escribir(``suma``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo MediaLista
# Entrada
	lista <- Leer()
	# Proceso
	suma <- 0
	n <- ContarElementosLista(lista)
	Para i=0 Hasta n-1 con paso 1 Hacer
		suma <- suma + lista[i]
	FinPara
	media <- dividir suma entre n
	# Salida
	Escribir(media)
FinAlgoritmo
```



## Ejercicio 17

_Adivinanza_

**Paso 1**: Definir el problema, crea un algoritmo que genere un número aleatorio entre 1 y 100, y le pida al usuario adivinarlo. El  algoritmo deberá indicar si el número introducido es mayor o menor que el número aleatorio, hasta  que el usuario adivine el número correcto.

En matemáticas, un número aleatorio viene dado, por:

![{\displaystyle X_{i}=\left[a^{i}X_{0}+{\frac {c(a^{i}-1)}{a-1}}\right]{\bmod {m}}}](https://wikimedia.org/api/rest_v1/media/math/render/svg/2879f44f847e3206375c4239d86618e3b01d66a0)



donde _m_ es el módulo,  _a_ es el multiplicador, _c_ es el incremento y _X_0_ es la semilla o el valor inicial, que es un número entero no negativo.

Ejemplo:

el algoritmo ``Adivinanza``() devolverá en algún punto "¡Enhorabuena ha acertado el número aleatorio!"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: 

Proceso:

- Se genera un número aleatorio entre 1 y 100, asignado su valor a la variable ``numeroAleatorio``.
- Asignar a la variable ``numero`` el valor 0.
- Se debe hacer un bucle mientras, que pretende repetir la instrucción por pantalla de "Intente adivinar el número generado aleatoriamente entre 1 y 100" y almacene este número en la variable ``numero``, hasta que el usuario adivine el ``numeroAleatorio``. Indicándole pistas de si "Su número introducido es mayor que el número aleatorio" o si "Su número introducido es menor que el número aleatorio".

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Adivinanza
	# Entrada
	# Proceso
	numeroAleatorio <- GenerarNumeroAleatorio(1,100) # En su mayoría los lenguajes tienen una palabra reservada para crear un número aleatorio entero
	numero <- 0
	Mientras numeroAleatorio sea diferente a numero Hacer
		Escribir("Intente adivinar el número generado aleatoriamente entre 1 y 100")
		numero <- Leer()
		Si numero es mayor que numeroAleatorio Entonces
			Escribir("Su número introducido es mayor que el número aleatorio")
		Sino numero es menor que numeroAleatorio Entonces
			Escribir("Su número introducido es menor que el número aleatorio")
		Sino
			resultado <- "¡Enhorabuena ha acertado el número aleatorio!"
		FinSi
	FinMientras
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 18

_Anagrama_

**Paso 1**: Definir el problema, crea un algoritmo que determine si una cadena de texto es un anagrama de otra cadena de texto.

Un anagrama es una palabra o frase formada por la reorganización de las letras de otra palabra o frase, conservando las mismas letras pero en un orden diferente. 

Ejemplo:

cadena = "mar"

anagrama = "ram"

El algoritmo ``Anagrama``(cadena, anagrama) devolverá "es anagrama"

cadena = "hola"

anagrama = "olas"

El algoritmo ``Anagrama``(cadena, anagrama) devolverá "no es anagrama"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``cadena``, ``anagrama``

Proceso:

- Se cuenta el número de elementos de ``cadena`` y el número de elementos de ``anagrama``, asignándose estos valores a ``n`` y ``m`` , respectivamente.
- Si ``n`` y ``m`` son iguales:
  - Se necesita un bucle mientras para recorre todas las letras de ``cadena``. 
  - Se requiere de un bucle para anidado, pues se necesita recorrer ``anagrama`` buscando las letras de ``cadena`` y reorganizando las letras en ``anagrama``. De este modo, se podrá comprobar si dos cadenas son coincidentes y se asignará a ``resultado`` el valor "es anagrama" o "no es anagrama".

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Anagrama
	# Entrada
	cadena <- Leer()
	anagrama <- Leer() 
	# Proceso
	n<-ContarElementosLista(cadena)
	m<-ContarElementosLista(anagrama)
	Si n es igual a m
		i <- 0
		resultado <- "es anagrama"
		Mientras i sea menor o igual que n-1
			noEstaLetra <- True
			Para j=i Hasta n-1 con paso 1 Hacer
				Si cadena[i] es igual a anagrama[j] Entonces
					posicion <- j
					noEstaLetra <- False
				FinSi
			FinPara
			Si noEstaLetra es igual a True Entonces
				resultado <- "no es anagrama"
				i <- n
			Sino
				temporal <- anagrama[i]
				anagrama[i] <- cadena[i]
				anagrama[posicion] <- temporal
				i <- i+1
			FinSi
		FinMientras
	Sino 
		resultado <- "no es anagrama"
	FinSi
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



## Ejercicio 19

_Duplicados en lista_

**Paso 1**: Definir el problema,  dada una lista de números enteros, crea un algoritmo que elimine los números duplicados de la  lista.

El problema a afrontar es que si hay una lista de enteros, en el caso de que un número se repita dos veces, este no aparezca nuevamente al final del algoritmo. 

Ejemplo:

lista = [1, 2, 3, 4, 3, 2, 1]

El algoritmo ``listaSinDuplicados``(lista) devolverá [1,2,3,4]

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``lista``

Proceso:

- Se cuenta el número de elementos en ``lista`` y se asigna a la variable ``n``.
- Se crea una variable ``listaNoDuplicados`` de ``n`` ceros y se asigna el valor ``lista[0]`` a ``listaNoDuplicados[0]``.
- Se asigna a la variable ``m``  el valor 1, que es la longitud de números no duplicados.

- Se va a realizar un bucle para que recorrerá los elementos de la ``lista``, que permita ir rellenando ``listaNoDuplicados``. Se recurre a una variable ``noEstaEnLista`` que toma valores ``True`` o ``False`` si el número ``i`` no está o si está, respectivamente, en la ``listaNoDuplicados``.
- Se realiza un bucle para anidado, porque es necesario recorrer ``listaNoDuplicados`` ,para saber si el número ``i`` está en ``listaNoDuplicados``. Si se encuentra el número ``i``  de ``lista`` en ``listaNoDuplicados``, se modifica el valor de ``noEstaEnLista`` a ``False`` y se sale del bucle.
- Al acabarse el bucle anidado, se tiene que si ``noEstaEnLista`` es ``True`` se añade el elemento ``lista[i]`` en la última posición de la ``listaNoDuplicados[m]``. De modo que, en ese momento se tiene un elemento más, es decir, a ``m`` se le asigna el valor ``m+1``.

Salida: 

Resultado(``listaFinal``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo ListaSinDuplicados
	# Entrada
	lista <- Leer()
	# Proceso
	n <- ContarElementosLista(lista)
	listaNoDuplicados[n] # Se define una lista con n ceros
	listaNoDuplicados[0] <- lista[0] # El primer elemento de la lista nunca será un duplicado
	m <- 1
	Para i=0 Hasta n-1 con paso 1 Hacer
		noEstaEnLista <- True
		j <- 0
		Repetir 
			Si lista[i] es igual a listaNoDuplicados[j]
				j <- m
				noEstaEnLista <- False
			Sino
				j <- j+1
			FinSi
		Hasta que j sea mayor o igual que m
		Si noEstaEnLista es igual a True
			listaNoDuplicados[m] <- lista[i]
			m <- m+1
		FinSi
		FinPara
	FinPara
	# Salida
	Para i=0 Hasta m-1 con paso 1 Hacer
		Escribir(listaNoDuplicados[i])
	FinPara
```



## Ejercicio 20

_Capicúa_

**Paso 1**: Definir el problema, crea un algoritmo que determine si un número es capicúa o no.

Un número capicúa es un número que se lee igual de izquierda a derecha, que de derecha a izquierda. En otras palabras, si se invierte el orden de los dígitos se obtiene el mismo número.

Ejemplo: 

numero = 123454321

el algoritmo ``Capicua``(numero) devolverá "es capicua"

numero = 12345432

el algoritmo ``Capicua``(numero) devolverá "no es capicua"

**Paso 2**: Poner la entrada, el proceso y la salida.

Entrada: ``numero``

Proceso:

- Se cambia la variable ``numero`` a cadena.
- Se cuenta el número de elementos que hay en ``numero`` y se asigna el valor a ``n``.
- Se necesita un bucle mientras, para recorrer en sentido inverso ``numero`` y concatenar sus elementos sucesivamente en ``numeroInverso``.
- Se compara ``numero`` con `numeroInverso`:
  - Si son iguales asignar a ``resultado`` "es capicua".
  - Sino son iguales, asignar a ``resultado`` "no es capicua".

Salida: Escribir(``resultado``)

**Paso 3**: Escribir el pseudocódigo.

```
Algoritmo Capicua
	# Entrada
	numero <- Leer()
	# Proceso
	numero <- CambiarFormatoString(numero)
	n <- ContarElementosLista(numero)-1
	numeroInverso <- ""
	Mientras n sea mayor o igual que 0 Hacer
		numeroInverso <- numeroInverso + numero[n]
		n <- n-1
	FinMientras
	Si numero es igual a numeroInverso Entonces
		resultado <- "es capicua"
	Sino
		resultado <- "no es capicua"
	FinSi
	# Salida
	Escribir(resultado)
FinAlgoritmo
```



















