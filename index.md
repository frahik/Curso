---
title       : Curso R - Básico
subtitle    : Un curso para programadores y NO programadores
author      : Francisco Javier Luna Vázquez
job         : Investigador 
framework   : io2012        
highlighter : highlight.js 
hitheme     : magula
widgets     : [mathjax, quiz, bootstrap]            
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
github      :
user        : frahik
repo        : Curso
license     : by-sa
---

## Hablemos de **R**

El objetivo de la diapositiva es proporcionar un punto de partida para las personas interesadas en aprender a usar **R**, esto con el fin de promover el conocimiento de manera sencilla, practica y entendible.

**R** se distribuye de manera gratuita y es un sistema para análisis estadísticos, tiene una vista doble, como programa y lenguaje de programación y es considerado como una implementación del dialecto del lenguaje S creado por los laboratorios AT&T Bell.

**R** está disponible en varias formas: el código fuente escrito principalmente en C, esencialmente para máquinas Unix y Linux, o como archivos binarios pre-compilados para Windows, Linux (Debian, RedHat,SuSe) y Macintosh, se distribuye bajo los términos de _GNU General Public Licence_ al igual que esta diapositiva.

-----

## Instalación de **R** 
Empezaremos por lo más básico, Podemos instalar **R** desde el siguiente link: https://www.r-project.org/ 

Pero como muchos somos algo despistados, estas son las maneras más populares para instalar **R** en distintos Sistemas Operativos:

|Sistema Operativo | Método   |
|------------------|----------|
|   Windows        | https://cran.itam.mx/bin/windows/base/R-3.3.2-win.exe  |
|Debian y derivados|`sudo apt-get install r-base`                           |
|Redhat y derivados| `sudo yum install R-core R-devel`                      |
|Arch y derivados  | `sudo pacman -S r`                                     |
|     Mac          | https://www.youtube.com/watch?v=ICGkG7Gg6j0            |

----

## IDE 
Una vez instalado, un entorno de desarrollo integrado será necesario para facilitar el desarrollo de códigos en **R**, por lo que se presentan tres de varias opciones para trabajar con **R**. 

|       IDE             |  Link     |
|:---------------------:|-----------|
|   Tinn-R              |https://sourceforge.net/projects/tinn-r/ |
|R-Studio [Recomendado] |https://www.rstudio.com/ |
| R commander (Rcmdr)   |http://www.rcommander.com/ |

----

## Primeros pasos 

En un principio y la manera más sencilla de ver **R** es que puede ser usado como una calculadora: 


```r
10+5 
```

```
## [1] 15
```

o


```r
10/5 
```

```
## [1] 2
```

Pero su potencial va más allá... 

Principalmente por que esta diapositiva fue diseñada en **R** y RMarkdown ;)

--- 

## Creación de objetos 

En **R** podemos crear y manipular objetos asignándole valores, cadenas de texto, funciones y un largo etc. 
Por ser el primer contacto con **R**, crearemos un objeto (izquierda del símbolo `=`), asignándole como valor la cadena de texto "Hola mundo" 

```r
saludo = "Hola mundo" 
```
Ahora para mostrar en consola lo que contiene la _variable_ u _objeto_ `saludo`, lo escribiremos tal cual y obtendremos una salida muy similar a la siguiente. 

```
## [1] "Hola mundo"
```

**NOTA:** 
> **R** es sensible a las MAYUSCULAS y minúsculas, por lo que `saludo` no es igual a `Saludo` o a `SALUDO`. 

-----

Otra manera de asignar valores a las variables es mediante el símbolo `<-` que se compone de un menor que y el signo de menos. 
 

```r
x <- 10+5 
```
 
Es recomendable incluir un espacio simple a cada lado del operador de asignación para incrementar la legibilidad. Pero <span class = 'red'>NO</span> coloques un espacio entre el `<` y el `-` que forman la flecha, recuerda que a pesar de estar compuesto por dos caracteres es un único símbolo. 
 
También podemos reasignar un valor a la variable que hemos creado y reutilizar la variable para realizar un calculo:   

```r
y <- x + 5 
y
```


```
## [1] 20
```

------

## Vectores 

Realmente hemos trabajado con vectores desde que empezamos con `10 + 5`, lo que nos devuelve **R** es un vector de índice 1, estas son otras formas de crear vectores. 


```r
X <- c(1,2,3) 
X 
```

```
## [1] 1 2 3
```

La manera anterior es a través del método concatenar `c( )`, que une los elementos separados por una coma, otra forma de crear un vector (numérico en éste caso) es usando `:` que nos hace una lista de uno en uno desde el primero valor hasta el último. 

```r
X <- 1:3 
X 
```

```
## [1] 1 2 3
```

-----

Por ultimo,  cuando ya tenemos una lista o simplemente queremos repetir algo $n$ veces, podemos usar la función `rep(x,times=n)`, que repetirá un número definido de veces lo indicado como parámetro x. 

```r
rep(1, times=3)  
```

```
## [1] 1 1 1
```

-----

### Accediendo a los valores del vector

Partiendo de que tenemos un vector con la edad de los integrantes de una familia se podría observar como si fuera una tabla:

|1  |2  |3  |4  |5  |
|---|---|---|---|---|
|45 |43 |13 |8  | 5 |

dónde, si queremos saber la edad del primer integrante, podemos observar que su edad es 45, y el promedio de todas las edades (es decir $\sum_{i=1}^{5} x_i$) es de 22.8 años.

Todos éstos calculos se pueden hacer de manera rápida y en algunos casos son intuitivos, pero con grandes cantidades de datos, estas tareas se vuelven más complejas, pero continuemos con el mismo ejemplo en  **R**.

------

Partiendo de la edad de los cinco integrantes, crearemos un vector con las edades de cada uno

```r
edad_familia <- c(45,43,13,8,5)
```

para consultar la edad de un integrante $x$ basta con poner la posición a la que queremos acceder, en éste caso, la primer posición:

```r
edad_familia[1]
```

```
## [1] 45
```

Mientras que para calcular el promedio basta con usar la función `mean( )`

```r
mean(edad_familia)
```

```
## [1] 22.8
```

-----

## Matrices
Para crear una matriz en **R** se utiliza la función


```r
matrix(data = NA, nrow = 1, ncol = 1, byrow = FALSE, dimnames = NULL)
```

donde `matrix()` corresponde al nombre de la función y todo lo que está dentro de los paréntesis son los argumentos de dicha función.

| Argumentos | Signficado |
|------------|------------|
|   `data`   |Es un vector de datos opcional |
|   `nrow`   |Número deseado de filas        |
|   `ncol`   |Número deseado de columnas     |
|   `byrow`  |Valor lógico. Si es falso (valor por defecto), la matriz se llena por orden columna, de otra manera se llenará primero por filas. |
| `dimnames` |Utilizado para darles nombres a las filas y a las columnas, respectivamente. |

-----

### apply

La función `apply` permite realizar un cálculo por fila ó por columna, dará un vector de longitud p con el resultado de la operacion realizad, ya sea por filas o por columnas. 


Veamos que el uso es:

```r
apply(X, MARGIN, FUN)
```
donde `apply()` corresponde al nombre de la función y todo lo que está dentro de los paréntesis son los argumentos de dicha función.

| Argumentos | Signficado |
|------------|------------|
|   `X`      |Es el vector o matriz original|
|   `MARGIN` |Indica donde se aplicara la función (1 indica fila, 2 indica columna)      |
|   `FUN`    |Es la funcion a aplicar (Suma, promedio, entre muchas otras)     |

-----

Para ver un ejemplo, crearemos una matriz con 9 valores y sacaremos el promedio por columna.


```r
x <- matrix(data = 1:9, nrow=3, ncol=3, byrow = TRUE)
x
```

```
##      [,1] [,2] [,3]
## [1,]    1    2    3
## [2,]    4    5    6
## [3,]    7    8    9
```

```r
apply(x,2,mean)
```

```
## [1] 4 5 6
```

El argumento 2 en `apply(x,2,mean)` indica que el cálculo del promedio debe realizarse en la segunda dimensión, es decir, en las columnas. 

-----

## Escribir y leer archivos de texto, CSV en **R**.

### Archivo de texto


-----

### CSV (Comma-separated values)


-----


## Graficas

Hasta éste momento hemos expresado todos los resultados en salidas de consola, lo cual, para muchos puede ser un poco tedioso, sin decir aburrido, por lo que, expresar los resultados en graficas sencillas, permiten comprender rapidamente el tema del que se habla, vaya, que _«Una imagen vale más que mil palabras»_



-----

## Condiciones (if-else) 
Habrá momentos en los que ocuparemos tener en cuenta que queremos hacer si no sucede un evento, por ejemplo, saber si un número es par o no. 
 
Para ello usaremos las condiciones, existen dos maneras: 

```r
if(10%%2==0){ 
  print("Es par") 
}else{ 
  print("Es impar") 
} 
```

```
## [1] "Es par"
```

-----

Otra forma, única para el lenguaje de **R** es la siguiente. 

```r
set.seed(1) 
ifelse(10%%2==0,"Par","Impar")  
```

```
## [1] "Par"
```

-----

## Ciclos, Repeticiones o Loops 
 
Habrá momentos en las que ocuparemos realizar un número determinado de veces una misma rutina, para esto existe el ciclo for: 
 

```r
for(i in 1:5){ 
  print(i) 
} 
```

```
## [1] 1
## [1] 2
## [1] 3
## [1] 4
## [1] 5
```

----

Y en ocasiones no sabremos hasta que momento queremos detener el ciclo, por lo que podemos usar: 
 

```r
i = 1 
while(i < 50){ 
  i = i * 2 
  print(i) 
} 
```

```
## [1] 2
## [1] 4
## [1] 8
## [1] 16
## [1] 32
## [1] 64
```

---

## Paquetes
Los paquetes en **R**, son como _«Extensiones»_ y nos sirven para evitar reinventar la rueda, existen muchos paquetes disponibles en el CRAN de **R** y para instalarlos basta un comando en la propia terminal de **R**:

`install.packages("NombreDelPaquete")`

Con ello podremos expandir el potencial de **R** y a la vez facilitarnos el trabajo de _«hacerlo por nosotros mismos»_.

-----

## Ejemplos para trabajar en **R**

Supongamos que


-----

Puedes continuar el curso con la siguiente diapositiva:

https://frahik.github.io/CursoRIntermedio

-----
