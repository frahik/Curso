---
title       : Curso R - Básico
subtitle    : Aprendiendo lo básico de R
author      : Francisco Javier Luna Vázquez
job         : Estudiante
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
github      :
user        : frahik
repo        : Curso
---

## Instalación de R 
¡Saludos! 
Empezaremos por lo más básico, Podemos instalar R desde el siguiente link: https://www.r-project.org/ 

#### [Windows] 
> https://cran.itam.mx/bin/windows/base/R-3.3.2-win.exe 

#### [Linux ]
##### Debian y derivados (Ubuntu, Elementary)
> `sudo apt-get install r-base`

##### RPM (Redhat, CentOS y derivados)
> `sudo yum install R-core R-devel`

##### Arch (Antergos, Cinnamon y derivados)
> `sudo pacman -S r`

#### [Mac - VideoTutorial] 
> https://www.youtube.com/watch?v=ICGkG7Gg6j0 

----

## IDE 
Una vez instalo R, un entorno de desarrollo integrado será necesario para facilitar el desarrollo de códigos en R, por lo que se presentan dos de varias opciones para trabajar con R. 

#### Tinn-R 
> https://sourceforge.net/projects/tinn-r/ 

#### R-Studio [Recomendado] 
> https://www.rstudio.com/ 

----
## Primeros pasos 
R puede ser usado como una calculadora: 

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
 
Principalmente por que esta diapositiva fue diseñada en R y RMarkdown ;) 

-----

### Creación de objetos 

En R podemos crear y manipular objetos asignándole valores, cadenas de texto, funciones y un largo etc. 
Por ser el primer contacto con R, crearemos un objeto (izquierda del símbolo `=`), asignándole como valor la cadena de texto "Hola mundo" 

```r
saludo = "Hola mundo" 
```
Ahora para mostrar en consola lo que contiene la variable u objeto `saludo`, lo escribiremos tal cual y obtendremos una salida muy similar a la siguiente. 

```
## [1] "Hola mundo"
```

**NOTA:** 
> R es sensible a las MAYUSCULAS y minúsculas, por lo que `saludo` no es igual a `Saludo` o a `SALUDO`. 

-----

Otra manera de asignar valores a las variables es mediante el símbolo `<-` que se compone de un menor que y el signo de menos. 
 

```r
x <- 10+5 
```
 
Es recomendable incluir un espacio simple a cada lado del operador de asignación para incrementar la legibilidad. Pero NO coloques un espacio entre el `<` y el `-` que forman la flecha, recuerda que a pesar de estar compuesto por dos caracteres es un único símbolo. 
 
También podemos reasignar un valor a la variable que hemos creado y reutilizar la variable para realizar un calculo: 

```r
x <- 10+20 
x 
```

```
## [1] 30
```

```r
y <- x + 5 
y 
```

```
## [1] 35
```

------

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

## Vectores 

Realmente hemos trabajado con vectores desde que empezamos con `10 + 5`, lo que nos devuelve R es un vector de índice 1, estas son otras formas de crear vectores. 


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

Por ultimo,  cuando ya tenemos una lista o simplemente queremos repetir algo n veces, podemos usar la función `rep(x,times=n)`, que repetirá un número definido de veces lo indicado como parámetro x. 

```r
rep(1, times=3)  
```

```
## [1] 1 1 1
```

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

Otra forma, única para el lenguaje de R es la siguiente. 

```r
set.seed(1) 
ifelse(10%%2==0,"Par","Impar")  
```

```
## [1] "Par"
```

-----
