---
title: "Fractal Julia"
author: "crsd"
date: "31 de Octubre de 2019"
output: 
      html_document:
        code_folding: hide
        css: air.css
        highlight: tango
        keep_md: yes
        theme: united
        toc: yes
        toc_float: yes
---

<style>
.list-group-item.active, .list-group-item.active:focus, .list-group-item.active:hover {
    background-color: #2F184F;
}
</style>




# Resumen

Continuando con el tema de [fractales](https://rpubs.com/desareca/Fractales) vistos, se explorarán algunas carácterísticas de los **Fractales de Julia**, al modificar el plano inicial complejo.

# Introducción

Los conjuntos de Julia, así llamados por el matemático Gaston Julia, son una familia
de conjuntos fractales que se obtienen al estudiar el comportamiento de los números
complejos al ser iterados por una [función holomorfa](https://es.wikipedia.org/wiki/Funci%C3%B3n_holomorfa). El conjunto de Julia de una función holomorfa $f(z)$ está construido por aquellos puntos que bajo la iteración de $f(z)$ tienen comportamiento "cáotico". El conjunto se denota $J(f)$, tal que:


$$J(f) := \{z \in \mathbb{C}, f^{n}(z) \to converge\}$$

$$f^{1}(z) = f(z)$$

$$f^{n}(z) = f(f^{n-1}(z))$$

De acuerdo a lo anterior, el **Conjunto de Julia** de la función $f$ está formado por los puntos del plano complejo para los cuales las iteraciones de la función en dichos puntos constituyen una sucesión no divergente.


# Plano Inicial Complejo.

El **Fractal de Julia** se carácteriza por aplicar una función compleja sobre el plano complejo de manera iterativa. Este plano representa un espacio de números complejos, 
donde el eje $x$ es la componente *Real* y el eje $y$ es la componente *Imaginaria*.

Al visualizar este plano se tiene un cono para el módulo $\|z\|$ y una forma helocoidal para la fase $\phi(z)$.



<!--html_preserve--><div id="rgl51663" style="width:700px;height:350px;" class="rglWebGL html-widget"></div>

## Análisis plano inicial complejo



#### Fractal con plano inicial lineal ($z_0=z$) {.tabset .tabset-fade}

Para los siguientes análisis se considerará un fractal típico $z^2 + c$, con $c=-0.4 + 0.6i$ y se verá como afecta al módulo $\|z\|$ y la fase $\phi(z)$ por separado al plano inicial del fractal.

En el caso del módulo se tiene que se generan varios circulos concentricos con una trama. la cantidad de circulos y la trama dependen del valor del módulo de $\|c\|$ y $\|z\|$. La fase $\phi(z)$ genera una zona de origen a zona de convergencia del fractal original. 

Como primera aproximación tenemos que el patrón queda definido con la amplitud y la posición en el plano por la fase. Como prueba de esto último, cuando aplicamos el **Conjugado** del plano por defecto, se invierten las zonas del patrón del fractal.

##### Fractal plano inicial $z_0=z$

<img src="Fractal_Julia_files/figure-html/F0-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=\|z\|$

<img src="Fractal_Julia_files/figure-html/F1-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=e^{i\phi(z)}$

<img src="Fractal_Julia_files/figure-html/F2-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=\bar{z}$

<img src="Fractal_Julia_files/figure-html/F3-1.png" style="display: block; margin: auto;" />

<br/>

#### Fractal con plano inicial modificado {.tabset .tabset-fade}

Ahora al considerar $z^2$ como plano inicial se tienen varios efectos, por un lado el módulo genera un patrón similar al generado por el plano $z$ pero curvado, modificando un poco el patrón, una intución de esto podría ser como un estiramiento desde el centro del patrón original. Por otro, la fase $\phi(z^2)$ aumenta las zonas al doble.

Esto se puede generalizar para $z^n$ que generan $n$ zonas donde se replica el patrón. En la figura siguiente se observa este efecto para $z^3$ y $z^4$ respectivamente.



<br/>

##### Fractal plano inicial $z_0=z^2$

<img src="Fractal_Julia_files/figure-html/Z2-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=\|z^2\|$

<img src="Fractal_Julia_files/figure-html/Z2M-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=e^{i\phi(z^2)}$

<img src="Fractal_Julia_files/figure-html/Z2F-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=z^3$

<img src="Fractal_Julia_files/figure-html/Z3-1.png" style="display: block; margin: auto;" />

##### Fractal plano inicial $z_0=z^4$

<img src="Fractal_Julia_files/figure-html/Z4-1.png" style="display: block; margin: auto;" />
<br/>
 

<div class=text-justify>
Un punto interesante es probar con otras funciones como plano complejo inicial, para ello se comienza probando varias funciones polinómicas.
</div>


## Funciones Polinómicas {.tabset}

Se considera una función polinómica de acuerdo a lo siguiente:

$$z_0(z)=\sum_{i=0}^{n}a_iz^i, a_i \in \mathbb{C}$$

Al incluir funciones polinómicas como plano incial se observa una réplica en distintos tamaños y ubicaciones del fractal original, por lo que se puede deducir que el patrón principal depende de la función $f(z)$ iterada y la constante compleja $c$. Por otro lado, el plano inicial $z_0(z)$ afecta en la ubicación, deformaciociones y cantidad de patrones originales repetidos.



### $$z_0(z)=\frac{i}{10}+z+z^2$$

<img src="Fractal_Julia_files/figure-html/Pol1-1.png" style="display: block; margin: auto;" />


### $$z_0(z)=z+iz^3$$

<img src="Fractal_Julia_files/figure-html/Pol2-1.png" style="display: block; margin: auto;" />

### $$z_0(z)=\frac{iz}{2}+z^2+z^4$$

<img src="Fractal_Julia_files/figure-html/Pol3-1.png" style="display: block; margin: auto;" />

### $$z_0(z)=z^2-z^3+z^4$$

<img src="Fractal_Julia_files/figure-html/Pol4-1.png" style="display: block; margin: auto;" />


## Otras funciones {.tabset}

Ahora se consideran otras funciones, con naturaleza diferente a las polinómicas para explorar el comportamiento de los fractales.

Nuevamente, utilizando otras funciones como $\frac{sin(3\pi z)}{3\pi z}$ o $\frac{log(iz)}{z}$ se generan réplicas, modificación de tamaños y posiciones del fractal original.

Un efecto muy interesante es el de utilizar $\|z\|$ que produce una deformación en el fractal, tal como se observa al utilizar las funciones $\frac{log(iz)}{\|z\|}$, $\frac{z^2}{\|z\|}$ o $\frac{e^z}{\|z^2\|}$




### $$\frac{sin(3\pi z)}{3\pi z}$$

<img src="Fractal_Julia_files/figure-html/Fx1-1.png" style="display: block; margin: auto;" />

### $$\frac{z^3 sin(3\pi z)}{3\pi}$$

<img src="Fractal_Julia_files/figure-html/Fx2-1.png" style="display: block; margin: auto;" />

### $$\frac{log(iz)}{z}$$

<img src="Fractal_Julia_files/figure-html/Fx3-1.png" style="display: block; margin: auto;" />

### $$\frac{log(iz)}{\|z\|}$$

<img src="Fractal_Julia_files/figure-html/Fx4-1.png" style="display: block; margin: auto;" />

### $$\frac{z^2}{\|z\|}$$

<img src="Fractal_Julia_files/figure-html/Fx5-1.png" style="display: block; margin: auto;" />

### $$\frac{e^z}{\|z^2\|}$$

<img src="Fractal_Julia_files/figure-html/Fx6-1.png" style="display: block; margin: auto;" />

## Movimieto del fractal en el plano

Cuando al plano inicial $z_0=z$ le sumamos un $c_0$ (o sea $z_0=z+c_0$), se genera un movimiento en el fractal original desde el centro, donde el fractal se desplaza una distancia equivalente al *módulo* $\|c_0\|$ en una dirección correspondiente al *ángulo de fase* $\phi(c_0)$ (en radianes) respecto de la vertical (en sentido antihorario). En el ejemplo siguiente se ve el movimiento en espiral del fractal modificando el valor de *fase* y *módulo* de $c_0$.

<br/>



<center>
![](Movimiento Z1.gif)
</center>

<br/>
<div class=text-justify>
Ahora se aplica el mismo concepto, pero al plano $z_0=z^2$. El módulo $\|c_0\|$ también define la distancia del origen y se agrega una deformación en el plano, haciendo que los fractales cercanos al centro tiendan a agrandarse.

Por otro lado, la fase $\phi(c_0)$ define la posición en el plano (al igual que para $z$) y la posición respecto al eje vertical del centro del fractal, girando con periodo $2\pi$ respecto a la vertical en sentido horario. Se observa además que se mantiene el efecto de $z^2$ centrado en el origen, generando 2 patrones del fractal original, tal como se muestra en la animación siguiente.

El efecto descrito para $z_0=z^2+c_0$ se puede generalizar para $z_0=z^n+c_0$.
</div>
<br/>



<center>
![](Movimiento Z2.gif)
</center>

<br/>

# Conclusiones

En los ejemplos anteriores se mostraron variadas propiedades muy interesantes como a partir de un fractal específico modificar la posición y tamaño, agregar copias y generar deformaciones de este. Con esto es posible generar patrones complejos de la geometría base del fractal como generar movimiento de este patrón. 

En general la creación de patrones fractales repetitivos se desarrolla utilizando fractales lineales. Al explorar modificaciones en los planos iniciales de los *fractales de Julia* se observa que es posible crear patrones repetitivos en base a fracatales no lineales.


---

# Código

**Funciones y librerias:**


```r
# Librerias
suppressWarnings(library(caTools))
suppressWarnings(library(EBImage))
suppressWarnings(library(RColorBrewer))
suppressWarnings(library(rgl))

# Funciones
rand_col <- function(n = 64, random = TRUE, seed = 123,
                     col1 = "#2F184F", col2 = "green", col3 = "blue"){
      # Funcionamiento:
      # ------------------------------------------------------------------------
      # Genera una paleta de n colores. Esta puede ser aleatoria o por defecto.
      # En ambos casos se consideran 3 colores con alpha 0.5, 1.0 y 0.35 
      # respectivamente.
      
      # Variables:
      # ------------------------------------------------------------------------
      # n:        Número de colores de la paleta.
      # random:   Entrega paleta de colores aleatoria.
      # seed:     Semilla para la paleta de colores aleatoria.
      # col1:     color 1 por defecto.
      # col2:     color 2 por defecto.
      # col3:     color 3 por defecto.
      
      # Resultado:
      #-------------------------------------------------------------------------
      # Paleta de n colores de acuerdo a los parámetros ingresados.

      if(!is.null(seed)){set.seed(seed)}
      hex = c("0","1","2","3","4","5","6","7",
              "8","9","A","B","C","D","E","F")
      addalpha <- function(colors, alpha=1.0) {
            r <- col2rgb(colors, alpha=T)
            r[4,] <- alpha*255
            r <- r/255.0
            return(rgb(r[1,], r[2,], r[3,], r[4,]))
      }
      if(random){
            col1 <- paste(c("#",sample(hex,6)),sep = "", collapse = "")
            col2 <- paste(c("#",sample(hex,6)),sep = "", collapse = "")
            col3 <- paste(c("#",sample(hex,6)),sep = "", collapse = "")
      }
      cr1 <- c(addalpha(col1, 0.5),
               col2,
               addalpha(col3, 0.35))
      cols <- colorRampPalette(cr1)(n)
}
algosJuliaT <- function(funcion, C = complex(real=-0.8, imag=0.156),
                       m = 100, n = 20, r = 1.5, gamma = 0.7, Zmod = NULL,
                       seed = 123, epc = NULL, epz = NULL,
                       stop = 0.93, end_frac = FALSE, verbose = FALSE){
      # Funcionamiento:
      # ------------------------------------------------------------------------
      # Genera un fractal de Julia a partir de una función y un parámetro constante
      # complejo "C". La variables de la función de entrada son "z" resultado de la 
      # función iterada, "c" constante compleja "C" y "k" iteración.
      # El resultado es un array de dimensiones (m, m, n).
      
      # Variables:
      # ------------------------------------------------------------------------
      # funcion:   función a utilizar en el fractal.
      # C:         constante compleja.
      # m:         resolución de la matriz (mxm).
      # n:         número de iteraciones.
      # r:         rango de la matriz Z en el plano complejo, desde -r a r para
      #            reales como imaginarios.
      # gamma:     ajusta la inclinación de la función exponencial.
      # Zmod:      Modificación al plano complejo inicial. El plano por defecto
      #            es un cono en magnitud y en fase es la relación entre el 
      #            eje y y el eje x.
      # seed:      Semilla para variables aleatorias.
      # epc:       Parámetro epsilon que sirve como el rango en que varía el valor
      #            de "C", por defecto NULL (o sea no varía).
      # epz:       Parámetro epsilon que sirve como el rango en que varía el valor
      #            de "z", por defecto NULL (o sea no varía).
      # stop:      detiene el algoritmo cuando la suma de los ceros es mayor 
      #            o igual al umbral, 93% por defecto.
      # verbose:   muestra el avance de las iteraciones.
      # end_frac:  Devuelve último cálculo (TRUE) o el array completo (FALSE), 
      #            por defecto FALSE.
      
      # Resultado:
      # ------------------------------------------------------------------------
      # Fractal resultante generado en un array de 1 o varios frames.
      # nota1:     la salida de la función utiliza una exponencial para 
      #            acotar el rango de salida entre 0 y 1.
      # nota2:     los argumentos de la función deben considerar z como la 
      #            variable iterativa, c como la constante, k como un argumento 
      #            dependiente de la iteración (opcional).
      if(is.null(funcion)){return("Ingresar función a calcular")}
      if(!is.null(funcion)){
            Z <- complex(real=rep(seq(-r,r, length.out=m), each=m),
                         imag=rep(seq(-r,r, length.out=m), m))
            Z <- matrix(Z,m,m)
            if(!is.null(Zmod)){Z <- Zmod*r}
            X <- array(0, c(m,m,0))
            if(verbose){
                  pb <- txtProgressBar(min = 0, max = n, style = 3, initial = 0)
            }
            nc = c(0,0)
            nz = c(0,0)
            set.seed(seed)
            for (k in 1:n) {
                  if(!is.null(epc)){nc <- runif(n=2, min = -epc, max = epc)}
                  if(!is.null(epz)){nz <- runif(n=2, min = -epz, max = epz)}
                  Z <- funcion(z=Re(Z)+nz[1]+1i*(Im(Z)+nz[2]),
                               c=Re(C)+nc[1]+1i*(Im(C)+nc[2]),
                               k=k)
                  Z[is.na(Mod(Z))] <- max(Re(Z[!is.na(Z)])) + 1i*max(Im(Z[!is.na(Z)]))
                  if(sum(exp(-gamma*abs(Z))==0)<=stop*m*m){
                        if(!end_frac){
                              X <- abind(X, exp(-gamma*abs(Z)), along = 3)
                              }
                        }
                  if(sum(exp(-gamma*abs(Z))==0)>stop*m*m){k <- n}
                  if(verbose){setTxtProgressBar(pb, k)}
            }
            if(verbose){close(pb)}
            if(end_frac){X <- abind(X, exp(-gamma*abs(Z)), along = 3)}
            return(X)     
      }
}
filtro <- function(img, w=NULL, size = 15, sigma = 10, inverse = TRUE){
      # Variables:
      # ------------------------------------------------------------------------
      # img:      Imágen a filtrar.
      # w:        Filtro a aplicar, por defecto aplica un filtro gaussiano pasa
      #           bajos.
      # size:     Tamaño de la ventana que se aplica al filtro gaussiano. Si se
      #           define el filtro "w" no se considera este parámetro.
      # sigma:    Decaimiento de la función guassiana. Si se define el filtro
      #           "w" no se considera este parámetro.
      # inverse:  Aplica el inverso del filtro "w". Para el filtro gaussiano
      #           aplica un filtro pasa alto.
      
      # Resultado:
      #-------------------------------------------------------------------------
      # Filtro generado a partir de los parámetros.
      
      if(is.null(w)){
            w = EBImage::makeBrush(size = size, shape = 'Gaussian', sigma = sigma)
      }
      if(inverse){w <- (mean(w)-w)/sd(w)}
      EBImage::filter2(img, w)
}
borde <- function(Im, gamma = 1, size = 5, sigma = 2, inverse = TRUE, 
                  verbose = TRUE){
      # Variables:
      # ------------------------------------------------------------------------
      # Im:       Fractal (array) al que se le extraen los bordes.
      # gamma:    Decaimiento de la función exponencial. Esto es un preprocesamiento
      #           para ajustar el fractal a valores entre 0 y 1, y para 
      #           intensificar los cambios en los valores del fractal.
      # size:     Tamaño de ventana de función filtro.
      # sigma:    Decaimiento de filtro gaussiano en función filtro.
      # inverse:  Aplica filtro inverso en función filtro.
      # verbose:  Muestra el avance del cálculo.
      
      # Resultado:
      #-------------------------------------------------------------------------
      # Array con los bordes del fractal o imagen de entrada.
      # nota:     Utiliza la función filtro.
      Im2 <- array(dim = c(dim(Im)[1],dim(Im)[2],0))
      if(verbose){pb <- txtProgressBar(min = 0, max = dim(Im)[3], style = 3, initial = 0)}
      for (k in 1:dim(Im)[3]) {
            img <- exp(-gamma*Mod(Im[,,k]))
            Imb = filtro(img, w=NULL, size = size,
                         sigma = sigma, inverse = inverse)
            Imb <- ifelse(Imb<0,0,Imb)
            Imb <- ifelse(Imb>1,1,Imb)
            Im2 <- abind(Im2, Imb, along = 3)
            if(verbose){setTxtProgressBar(pb, k)}
      }
      if(verbose){close(pb)}
      return(Im2)
}
fun_pol <- function(Z, a){
      # Funcionamiento:
      #-------------------------------------------------------------------------
      # Esta función toma el valor del plano inicial complejo Z y genera un 
      # polinomio de grado n (length(a)) con coeficientes a, se considera el 
      # término Z^0 como a[1] hasta el término Z^(n-1) como a[n].
      
      # Variables:
      #-------------------------------------------------------------------------
      # Z:        Plano complejo inicial para generar un polinomio de grado n-1.
      # a:        Coeficientes del polinomio complejo.
      
      # Resultado:
      #-------------------------------------------------------------------------
      # Genera una lista con el polinomio y el orden del polinomio.
      # pol:      Polinomio resultante.
      # n:        Grado del polinomio resultante.
      
      while (a[length(a)]==0) {a <- a[-length(a)]}
      n <- length(a)
      if(n>=1){
            pol <- 0
            for (l in 1:n) {pol <- pol + a[l]*Z^(l-1)}
            sum_a <- sum(a)
            sum_a <- ifelse(sum_a==0, sum_a+0.0001, sum_a)
            pol <- pol/sum_a
      }
      if(n==0){pol=NULL}
      return(list(n=n, pol=pol))
}
```

**Modulo y Fase del plano Complejo:**


```r
dim = 100
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)
mfrow3d(1, 2, sharedMouse = TRUE)
persp3d(c(1:dim),c(1:dim),Mod(Z), col = rand_col(n=3,random = FALSE)[],
        xlab = "Real", ylab = "Imaginario", zlab = "Modulo")
next3d()
persp3d(c(1:dim),c(1:dim),Arg(Z), col = rand_col(n=3,random = FALSE)[],
        xlab = "Real", ylab = "Imaginario", zlab = "Fase")
rglwidget(width = 700, height = 350)
```

**Cálculo y visualización de fractales con plano $z_0=z$:**

Cálculo fractales

```r
dim = 500
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)
Im <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = NULL,
                  r = 1.5, gamma = 0.8, stop = 0.93)

Im1 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Mod(Z),
                  r = 0.75, gamma = 0.8, stop = 0.93)

Im2 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z/Mod(Z),
                  r = 0.75, gamma = 0.8, stop = 0.93)
Im3 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Conj(Z),
                  r = 1.5, gamma = 0.8, stop = 0.93)
```
Fractal original ($z_0=z$)

```r
display(colormap(Im, rand_col(random = FALSE)), method = "raster")
```
Módulo ($z_0=\|z\|$)

```r
display(colormap(Im1, rand_col(random = FALSE)), method = "raster")
```
Fase ($z_0=e^{\phi(z)}$)

```r
display(colormap(Im2, rand_col(random = FALSE)), method = "raster")
```
Conjugado ($z_0=\bar{z}$)

```r
display(colormap(Im3, rand_col(random = FALSE)), method = "raster")
```

**Cálculo y visualización de fractales con plano modificado $z_0=z^2$:**

Cálculo fractales con planos modificados

```r
dim = 500
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)
Im <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z^2,
                  r = 1.5, gamma = 0.8, stop = 0.93)

Im1 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Mod(Z^2),
                  r = 0.75, gamma = 0.8, stop = 0.93)

Im2 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z^2/Mod(Z^2),
                  r = 0.75, gamma = 0.8, stop = 0.93)
Im3 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z^3,
                  r = 1.5, gamma = 0.8, stop = 0.93)
Im4 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z^4,
                  r = 1.5, gamma = 0.8, stop = 0.93)
```
$z_0=z^2$

```r
display(colormap(Im, rand_col(random = FALSE)), method = "raster")
```
$z_0=\|z^2\|$

```r
display(colormap(Im1, rand_col(random = FALSE)), method = "raster")
```
$z_0=e^{\phi(z^2)}$

```r
display(colormap(Im2, rand_col(random = FALSE)), method = "raster")
```
$z_0=z^3$

```r
display(colormap(Im3, rand_col(random = FALSE)), method = "raster")
```
$z_0=z^4$

```r
display(colormap(Im4, rand_col(random = FALSE)), method = "raster")
```

**Cálculo y visualización de fractales con plano modificado con funciones polinómicas:**

Cálculo fractales con planos modificados polinómicos

```r
dim = 500
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)

zpot <- fun_pol(Z, c(0.1,1,1,0,0))
Im <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = zpot$pol,
                  r = zpot$n, gamma = 0.8, stop = 0.93)

zpot <- fun_pol(Z, c(0,1,0,1i,0))
Im2 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = zpot$pol,
                  r = zpot$n, gamma = 0.8, stop = 0.93)

zpot <- fun_pol(Z, c(0,0.5i,1,0,1))
Im3 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = zpot$pol,
                  r = zpot$n, gamma = 0.8, stop = 0.93)

zpot <- fun_pol(Z, c(0,0,1,-1,1))
Im4 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = zpot$pol,
                  r = zpot$n, gamma = 0.8, stop = 0.93)
```
$z_0=\frac{i}{10}+z+z^2$

```r
display(colormap(Im, rand_col(random = FALSE)), method = "raster")
```
$z_0=z+iz^3$

```r
display(colormap(Im2, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{iz}{2}+z^2+z^4$

```r
display(colormap(Im3, rand_col(random = FALSE)), method = "raster")
```
$z_0=z^2-z^3+z^4$

```r
display(colormap(Im4, rand_col(random = FALSE)), method = "raster")
```

**Cálculo y visualización de fractales con plano modificado con otras funciones:**

Cálculo fractales con planos modificados

```r
dim = 500
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)

Im <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = (sin(Z*3*pi))/(3*pi*Z),
                  r = 1.5, gamma = 0.8, stop = 0.93)

Im1 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = (sin(Z*3*pi))*Z^4/(3*pi*Z),
                  r = 1.5, gamma = 0.8, stop = 0.93)

Im2 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = log(1i*Z)/Z,
                  r = 0.3, gamma = 0.8, stop = 0.93)

Im3 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = log(1i*Z)/Mod(Z),
                  r = 0.3, gamma = 0.8, stop = 0.93)

Im4 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = Z^2/Mod(Z),
                  r = 1.5, gamma = 0.8, stop = 0.93)

Im5 <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                  C = -0.4 + 0.6i, m = dim, n = 60, end_frac = TRUE,
                  verbose = FALSE, Zmod = exp(Z)/Mod(Z^2),
                  r = 0.1, gamma = 0.8, stop = 0.93)
```
$z_0=\frac{sin(3\pi z)}{3\pi z}$

```r
display(colormap(Im, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{z^3 sin(3\pi z)}{3\pi}$

```r
display(colormap(Im1, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{log(iz)}{z}$

```r
display(colormap(Im2, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{log(iz)}{\|z\|}$

```r
display(colormap(Im3, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{z^2}{\|z\|}$

```r
display(colormap(Im4, rand_col(random = FALSE)), method = "raster")
```
$z_0=\frac{e^z}{\|z^2\|}$

```r
display(colormap(Im5, rand_col(random = FALSE)), method = "raster")
```

**Movimiento fractal:**

$z_0=z+c_0$

```r
dim = 250
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)

Im <- array(0,c(dim,dim,0))
for (j in c(1:48)) {
      Imj <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                         C = -0.4+0.6i, m = dim, n = 60, end_frac = TRUE,
                         verbose = FALSE, Zmod = (Z^1)+1.2*j*exp(2i*pi*(45+15*j)/360)/48,
                         r = 1.5, gamma = 0.8, stop = 0.93)
      Im <- abind(Im, Imj[,,1], along = 3)
}
write.gif(Im, col = rand_col(n=255*2, random = FALSE)[],
          delay = 80/100, flip = TRUE, "Movimiento Z1.gif")
```
$z_0=z^2+c_0$

```r
dim = 250
Z <- complex(real=rep(seq(-1.,1., length.out=dim), each=dim),
             imag=rep(seq(-1.,1., length.out=dim), dim))
Z <- matrix(Z,dim,dim)

Im <- array(0,c(dim,dim,0))
for (j in c(1:48)) {
      Imj <- algosJuliaT(funcion = function(z,c,k){z^2+c},
                         C = -0.4+0.6i, m = dim, n = 60, end_frac = TRUE,
                         verbose = FALSE, Zmod = (Z^2)+1.2*j*exp(2i*pi*(45+15*j)/360)/48,
                         r = 1.5, gamma = 0.8, stop = 0.93)
      Im <- abind(Im, Imj[,,1], along = 3)
}
write.gif(Im, col = rand_col(n=255*2, random = FALSE)[],
          delay = 80/100, flip = TRUE, "Movimiento Z2.gif")
```


# Referencias

**Código y referencias bibliográficas en:**

https://github.com/desareca/Fractales


**fractales no lineales implementarlos en R:**

https://rpubs.com/desareca/Fractales


# Sesión


```
R version 3.6.0 (2019-04-26)
Platform: x86_64-w64-mingw32/x64 (64-bit)
Running under: Windows 10 x64 (build 18362)

Matrix products: default

locale:
[1] LC_COLLATE=Spanish_Chile.1252  LC_CTYPE=Spanish_Chile.1252   
[3] LC_MONETARY=Spanish_Chile.1252 LC_NUMERIC=C                  
[5] LC_TIME=Spanish_Chile.1252    

attached base packages:
[1] stats     graphics  grDevices utils     datasets  methods   base     

other attached packages:
[1] rgl_0.100.30       RColorBrewer_1.1-2 EBImage_4.26.0    
[4] caTools_1.17.1.2  

loaded via a namespace (and not attached):
 [1] Rcpp_1.0.2              compiler_3.6.0         
 [3] later_1.0.0             bitops_1.0-6           
 [5] tools_3.6.0             digest_0.6.21          
 [7] jsonlite_1.6            evaluate_0.14          
 [9] lattice_0.20-38         png_0.1-7              
[11] rlang_0.4.0             shiny_1.4.0            
[13] crosstalk_1.0.0         yaml_2.2.0             
[15] parallel_3.6.0          xfun_0.10              
[17] fastmap_1.0.1           stringr_1.4.0          
[19] knitr_1.25              fftwtools_0.9-8        
[21] htmlwidgets_1.5.1       locfit_1.5-9.1         
[23] manipulateWidget_0.10.0 grid_3.6.0             
[25] webshot_0.5.1           R6_2.4.0               
[27] jpeg_0.1-8              rmarkdown_1.16         
[29] magrittr_1.5            promises_1.1.0         
[31] htmltools_0.4.0         BiocGenerics_0.30.0    
[33] abind_1.4-5             mime_0.7               
[35] xtable_1.8-4            httpuv_1.5.2           
[37] tiff_0.1-5              miniUI_0.1.1.1         
[39] stringi_1.4.3           RCurl_1.95-4.12        
```
