# Reto 4
## David Montes

### A continuación se desarrollará la documentación de las soluciones del reto 4:
-----
Primer reto: Dado un número entero, determinar si ese número corresponde al código ASCII de una vocal minúscula.
---------
Para este reto, conviene usar la función "match-case", además es necesario evitar que se puedan introducir números negativos y letras; para lo cual se usa la función "is.digit".
```python
m=input("ingrese el código de ASCII del cual quiere saber si pertenece a una vocal minúscula: ")
if m.isdigit():
    n:int
    n=(int(m))
# codígos ASCII de las vocales minúsculas: a=97 e=101 i= 105 o= 111 u= 117
# es necesario delimitar la lista de números posibles a introducir
#es necesario evitar que se puedan introducir letras(se me ocurrio una idea interesante que no funciona) 
    if(n>255):
        print("introduzca un número valido para el código ASCII estándar.")
    else:
        if(97 <= n <= 117):
            match(n):
                case 97:
                    print("Usted eligio la a. El código ASCII elegido pertenece a una vocal minúscula." )
                case 101:
                    print("Usted eligio la e. El código ASCII elegido pertenece a una vocal minúscula.")
                case 105:
                    print("Usted eligio la i. El código ASCII elegido pertenece a una vocal minúscula.")
                case 111:
                    print("Usted eligio la o. El código ASCII elegido pertenece a una vocal minúscula.")
                case 117:
                    print("Usted eligio la u. El código ASCII elegido pertenece a una vocal minúscula.")
                case _:
                    print("El ASCII no pertenece al ASCII de ninguna vocal minúscula.")
        else:
            print("El número elegido no pertenece al ASCII de ninguna vocal minúscula.")
else:
    print("introduzca un código ASCII válido")
# creo que terminado, ahora sí
```

2.Dada una cadena de longitud 1, determine si el código ASCII de primera letra de la cadena es par o no.
----
Lo primero es definir a C(de cadena), como una cadena; dado que no se puede limitar al usuario para que escriba una cadena de la longitud deseada, es necesario delimitar la cantidad de carácteres que emplea el programa usando "[0]", luego se emplea un condicional con la función booleana "not", para evaluar si se ha introducido una cadena(si la cadena está vacía el programa arroja un error y pide que se reinicie el programa.), luego se determina a la variable "n", como un entero, y se utilizala función "ord", para obtener el código ASCII de "C"  y denominarlo como "n", luego con un condicional se evalua si "n" es par o no, utilizando la operación n%2; si erl resultado de la operación n%2 es igual a 0, significa que n es par, lo cual será impreso por el programa; sino, n es impar, lo cual tambien será impreso por el programa.
```python
C: str
#Según internet y el profesor puedo delimitar el número de carácteres usados de la cadena usando corchetes
C= str(input("Introduzca un carácter para saber su código ASCII, y si este es par o no:"))[0]
if( not C):
    print(" la cadena está vacía, intente de nuevo")
else:
    n:int
    n= ord(C)
    if(n%2):
        print("el código ASCII del primer carácter de su cadena es:",  ord(C), ",efectivamente es impar")
    else:
        print("el código ASCII del primer carácter de su cadena es:",  ord(C), ",efectivamente es par")
```

3.Dado un carácter, construya un programa en Python para determinar si el carácter es un dígito o no.
----
Este código empieza definiendo "n" como "string", se aplica el mismo método que en el anterior ejercicio para evitar la introducción de una cadena vacía, y el fallo del programa al introducir una cadena superior a un carácter, además se utiliza la función "ord", para obtener el código ASCII de "n"; dado que los dígitos del 0 al 9 se encuentran en orden dentro del código ASCII, solo es necesario verificar con un condicional si ```ord(n)``` está dentro del intervalo de códigos ASCII que son dígitos, entonces el programa imprime si el carácter introducido es un dígito o no.

```python
n: str
n= input("introduzca un carácter para saber si es un dígito o no:")[0]
if(not n):
    print("introduzca por lo menos un carácter")
else:
    if(ord(n)>47 and ord(n)<58):
        print("el carácter elegido es un dígito.")
    else:
        print("el carácter introducido no es un dígito. Por favor vuelva a intentarlo.")
``` 

4.Dado un número real x, construya un programa que permita determinar si el número es positivo, negativo o cero.
Para cada caso se debe imprimir el texto que se especifica a continuación:
Positivo: "El número x es positivo"
Negativo: "El número x es negativo"
Cero (0): "El número x es el neutro para la suma"
----
Aquí se emplea un método similar al del primer punto para evitar la introducción de letras, pero con una alteración para permitir el ingreso de los carácteres como el "-" y el "." propios de los números reales. Luego usando dos condicionales se evalua si el número "n" es mayor o igual a cero, si es mayor, se juzga como positivo y se imprime, si es igual, se considera igual a 0 y se imprime; si no cumple con los anteriores casos, se juzga como negativo y se imprime.
```python
m= input("introduzca un número real")
if (('-' in m) or ('.' in m))or m.isdigit():
        n:float
        n=(float(m))
        if( n>0):
            print("El número", n ,"es positivo")
        else:
            if(n==0):
                print("El número", n ,"es igual a cero(0)")
            else:
                print("El número", n ,"es negativo")
else:
    print("introduzca un carácter válido")
```
5.Dado el centro y el radio de un círculo, determinar si un punto de R2 pertenece o no al interior del círculo.
---
Para hacer el cuento breve, este programa aprovecha la formula general del círculo "(x-a)^2+(y-b)^2=r^2", para verificar si el punto está dentro del círculo, usando un condicional y comprobando que los valores de las coordenadas ingresadas permitan que se cumpla la ecuación(con una variante para que también aplique a puntos del interior del círculo y no exclusivamente de la circunferencia). Usando métodos anteriormente explicados, se evita que el usuario introduzca una cadena vacia o letras.
```python
na= input("introduzca la coordenada x del centro del círculo:")
nb= input("introduzca la coordenada y del centro del círculo:")
nc= input("introduzca el radio del círculo:")
nd= input("introduzca la coordenada x del punto R2:")
ne= input("introduzca la coordenada y del punto R2:")
if(((((not na)or (not nb)) or( not nc)) or (not nd)) or (not ne)):
    print("introduzca por lo menos un número real")
else:
    if (('-' in na) or 
        ('.' in na)) or na.isdigit():
        a: float
        a=(float(na))   
        if (('-' in nb) or 
            ('.' in nb))or nb.isdigit():
            b: float
            b=(float(nb))
            if (('-' in nc) or 
                '.' in nc)or nc.isdigit():  
                c: float
                c=(float(nc))
                if (('-' in nd) or 
                '.' in nd)or nd.isdigit():
                        d: float
                        d=(float(nd))
                        if(('-' in ne) or 
                        '.' in ne)or ne.isdigit():
                            e: float
                            e=(float(ne))
                            f= a-d
                            f2= f*f
                            g= b-e
                            g2= e*e
                            h= c*c
                            if(f2 + g2 <= h):
                                print( "el punto R2 elegido está dentro del círculo")
                            else:
                                print("el punto R2 elegido está fuera del círculo")
                        else:
                            print("por favor introduzca solo números reales(coordenada y de R2)")
                else:
                    print("por favor introduzca solo números reales(coordenada x del punto R2)")     
            else:
                print("por favor introduzca solo números reales(radio del círculo)")
        else:
            print("por favor introduzca solo números reales(coordenada y del centro del círculo)")
    else:
        print("por favor introduzca solo números reales(coordenada x del centro del círculo)")
```

6.Dadas tres longitudes positivas, determinar si con esas longitudes se puede construir un triángulo.
---
Este programa se basa en verificar que las tres longitudes ingresadas cumplan con todas las condiciones de la desigualdad triangular, a través de un condidiconal y la concatenación de funciones / puertas lógicas AND. También se emplean los métodos anteriores para evitar la introducción de letras y se evita que el usuario pueda introducir longitudes negativas.

```python
na= input("introduzca la longitud del lado A:")
nb= input("introduzca la longitud del lado B:")
nc= input("introduzca la longitud del lado C")
if (('.' in na)) or na.isdigit():
    a: float
    a=(float(na))   
    if (('.' in nb))or nb.isdigit():
        b: float
        b=(float(nb))
        if (('.' in nc))or nc.isdigit():  
            c: float
            c=(float(nc))
            if(((a+b>c) and (b+c>a) and (a+c>b))):
                print("Esto, en efecto es un triangulo")
            else:
                print("Este conjunto de líneas tiene de triángulo lo que Bad Bunny de rey del pop")
        else:
            print("introduzca solo números reales positivos(lado C)")
    else:
        print("introduzca solo números reales positivos(lado B)")
else:
    print("introduzca solo números reales positivos(lado A)")
#happy happy happy
```