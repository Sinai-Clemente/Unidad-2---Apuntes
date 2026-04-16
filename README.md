# Unidad-2---Apuntes
<div align="justify">
   
<h1> Unidad 2 Graficación 2D.  </h1>
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/f07e3e08-feb4-4345-8dd6-db1e1534e830" />
El diseño gráfico bidimensional, también conocido como diseño gráfico 2D, se enfoca en la generación y manipulación de imágenes digitales, modelos geométricos y texto sobre un plano bidimensional (altura y anchura). Incluye algoritmos de trazado de líneas, formas y transformaciones geométricas 2D como traslación, rotación y escalado.

La transformación bidimensional es un concepto fundamental en la geometría computacional y el diseño gráfico que se refiere a las operaciones matemáticas aplicadas a figuras en un plano bidimensional. Estas transformaciones modifican la posición, orientación, tamaño o forma de los objetos sin salir del plano. En el contexto de la gráfica por computadora y otros campos, las transformaciones bidimensionales se utilizan para manipular imágenes, figuras y coordenadas de manera eficiente. Estas transformaciones son fundamentales en áreas como la computación gráfica, el diseño asistido por computadora (CAD) y la geometría computacional. Existen varios tipos de transformaciones, como la traslación, rotación, escalamiento y reflexión, que permiten manipular objetos de manera precisa. Estas operaciones se representan comúnmente mediante matrices, lo que facilita su aplicación en diversos sistemas. En campos como la animación digital y los videojuegos, las transformaciones bidimensionales son esenciales para lograr movimiento, interacción y cambios visuales en objetos y personajes. Además, son cruciales en disciplinas como la cartografía, donde se utilizan para transformar y proyectar mapas con precisión.

<h2> 2.1. Transformación bidimensional. </h2>



###
<h2> 2.2.Representación matricial de las transformaciones bidimensionales. </h2>

La representación matricial de transformaciones bidimensionales (2D) utiliza matrices $$3X3 $$ y coordenadas homogéneas $$(x, y, 1)$$ para representar traslaciones, rotaciones y escalados como multiplicaciones de matrices. Este método permite combinar múltiples transformaciones en una sola matriz, facilitando la manipulación de objetos geométricos. La forma general es $$P'= M \cdot P $$, donde $$P $$ es el vector de posición, $$M $$ la matriz de transformación y $$P' $$ la nueva posición. 

En aplicaciones de diseño y de creación de imágenes realizamos transformaciones para ajustar los componentes de la imagen en sus posiciones apropiadas.
Es posible expresar cada una de las transformaciones básicas en la forma de matriz general:

$$P' = M_1 * P + M_2 $$

Con las posiciones de coordenadas $$P $$ y $$P’ $$ representadas como columnas de vector. La matriz $$M_1 $$ es una matriz de dos por dos, que contiene factores de multiplicación y $$M_2 $$ es una matriz de columnas de dos elementos que contiene términos de traslación. Para la traslación $$M_1 $$ es la matriz de identidad. Para la rotación o la escalación $$M_2 $$ contiene los términos de traslación asociados con el punto pivote o el punto fijo de escalación.
 
Se pueden combinar los términos de multiplicación y de adición para transformaciones geométricas bidimensionales en una sola representación de matriz al ampliar las representaciones de matriz de dos por dos a matrices de tres por tres. Esto permite expresar todas las ecuaciones de matriz como multiplicaciones de matriz, si también se amplían las representaciones de matriz para las posiciones de coordenadas. 

### Coordenadas homogéneas.

Para expresar cualquier transformación bidimensional como una multiplicación de matriz, se representa cada posición de coordenadas cartesianas $$(x, y) $$ con las tres coordenadas homogéneas  $$(x_h , y_h , h ) $$, donde:

$$x = xh/h $$     $$y = yh/h $$

Por tanto, una representación general de coordenadas homogéneas se puede expresar también como $$(h \cdot x, h \cdot y, h) $$. Para transformaciones geométricas bidimensionales, se selecciona el parámetro homogéneo $$h $$  como cualquier valor no cero. Así, existe un número finito de representaciones homogéneas equivalentes para cada punto de coordenadas $$(x, y) $$. Una opción conveniente consiste en solo establecer $$h=1 $$. Entonces, se representa cada posición bidimensional con las coordenadas homogéneas $$(x , y, 1) $$.

En matemáticas se utiliza el término coordenadas homogéneas  para referirse al efecto de esta representación de ecuaciones cartesianas. Cuando se convierte un punto cartesiano $$(x, y) $$ a una representación homogénea $$(x_h, y_h, h) $$ las ecuaciones que contiene $$x $$ y $$y $$, como $$f(x, y) = 0, $$ se convierten en ecuaciones homogéneas en los tres parámetros $$y $$. Esto solo significa que si se sustituye cada uno de los tres parámetros $$x_h, y_h, h $$ con cualquier valor $$v $$ veces ese parámetro, el valor $$v $$ se puede factorizar fuera de las ecuaciones.

Expresar coordenadas homogéneas nos permite representar todas las ecuaciones de transformación geométrica como multiplicaciones de matriz. Se representan las coordenadas con vectores de columna de tres elementos y las operaciones de transformación se expresan como matrices de $$3 $$ $$por $$ $$3 $$.


### Matriz de transformación.

Las transformaciones geométricas son funciones que nos permiten mapear un conjunto de vectores a otro, esto al ser multiplicados por una matriz de transformación asociada a la transformación deseada. Este tipo de transformaciones son fundamentales en GC, ya que nos permiten modelar objetos, cambiando su posición y/o forma.

Para transformar vectores 2D podemos utilizar matrices 

$$
 \begin{bmatrix} 
a & b \\ 
c & d  
\end{bmatrix} \begin{bmatrix} 
x \\
y
\end{bmatrix} 
$$
$$
 =\begin{bmatrix}
ax + by \\
cx + dy
\end{bmatrix} \begin{bmatrix} 
x \\
y
\end{bmatrix} = \begin{bmatrix}
x' \\
y'
\end{bmatrix}
$$

Este tipo de operación es una transformación lineal, donde se toma a un vector 2D y se obtiene a otro vector 2D como resultado. Con esta simple operación podemos tener una variedad de transformaciones muy útiles. 

Otra forma de pensarlo es como una transformación del sistema de coordenadas. Asumiendo que las matrices de transformación son invertibles,
vale la pena notar que dicha transformación es parecida a un cambio de base, donde se recibe a un vector en la base descrita por los vectores columna de la matriz, y se obtiene a un vector con sus coordenadas descritas en la base canónica.


#### 1. Traslación.

La transformación de traslación es la más sencilla de todas, ya que basta desplazar ciertas unidades en dirección del eje $$x $$  o $$y $$ para generar un movimiento sobre éstos, de modo que
$$x' = x + Tx$$ $$y' = y + Ty$$

$$
T(T_x, T_y) = \begin{bmatrix} 
1 & 0 & T_x \\ 
0 & 1 & T_y \\ 
0 & 0 & 1 
\end{bmatrix}
$$

<p align="center">
<img width="277" height="338" alt="image" src="https://github.com/user-attachments/assets/4f9debc9-ec7c-44b7-96bf-238a76a0eea3" /> <br>
  Figura 4.4. Traslación. Se traslada cada vértice del triángulo sumándole el vector $$|(Tx, Ty)$$  .
</p>


#### 2. Escalamiento

Una transformación de escalamiento como su nombre lo indica, permite cambiar el tamaño de un objeto. En particular, para escalar a un vector, necesitamos multiplicar a cada una de sus coordenadas por un factor de escalamiento, esto es

$$x' = S_x \cdot x $$   $$y' = S_y \cdot y $$

de modo que si  se agranda en dirección del eje , y sí $$|S_x| > 1 $$  se
encoge, análogamente con $$S_y $$.

<p align="center">
<img width="315" height="449" alt="image" src="https://github.com/user-attachments/assets/329dbb0c-ce94-4f10-ada7-3aca1ce36614" /><br>
Figura 4.1. Escalamiento. Se aplica la matriz $$S(S_x, S_y) $$ sobre cada vértice del triángulo.
</p>

Se dice que es un escalamiento uniforme cuando sus factores de escalamiento
son iguales $$S_x = S_y $$, en otro es un escalamiento no uniforme. 

Por consiguiente, la matriz de transformación es:

$$
S(S_x, S_y) = \begin{bmatrix} 
S_x & 0\\ 
0 &  S_y 
\end{bmatrix}
$$

Puesto que

$$
 \begin{bmatrix} 
S_x & 0\\ 
0 &  S_y  
\end{bmatrix} \begin{bmatrix} 
x \\
y
\end{bmatrix} =\begin{bmatrix}
S_x \cdot x \\
S_y \cdot y
\end{bmatrix} = \begin{bmatrix}
x' \\
y'
\end{bmatrix}
$$

Como mencionamos anteriormente, esta operación es parecida a un cambio de base, en este caso es como si tomáramos a un vector representado por una base escalada y lo describiéramos con la base canónica.

#### 3. Rotación. 

Supongamos que tenemos un vector $$v = (x, y) $$ y lo queremos rotar $$ϕ $$ grados con respecto al origen, en sentido contrario a las manecillas del reloj, obteniendo $$v' = (x', y') $$.
<p align="center">
<img width="319" height="419" alt="image" src="https://github.com/user-attachments/assets/77a1bd98-0365-40ea-85e9-dcf1dedc38f4" /> <br>
Figura 4.2. Rotación de un vector $$v $$.
</p>

Observemos que $$r = ∥v∥ $$ y además que entre $$v $$  y el eje $$x $$ se forma un ángulo $$θ $$.
Entonces, podemos parametrizar a $$v $$ como


$$x= r cos θ $$ $$y= r sin θ $$


Y como $$v' $$ es $$v $$ rotado $$ϕ $$ grados, su longitud sigue siendo $$r $$ y termina formando
un ángulo de $$θ + ϕ $$, entonces

$$x′ = r cos(θ + ϕ) $$ $$y′ = r sin(θ + ϕ) $$

Sustiuímos por sus identidades trigonométricas, quedando

$$x′ = r[cosθ cosϕ − sinθ sinϕ]$$ $$y′ = r[sinθ cosϕ + rcosθ sinϕ] $$

$$⇒ x′ = rcosθ cosϕ − rsinθ sinϕ]$$ $$y′ = rsinθ cosϕ + cosθ sinϕ $$

$$⇒ x′ = xcosϕ − ysinϕ $$ $$y′ = ycosϕ + xsinϕ $$

<p align="center">
<img width="514" height="375" alt="image" src="https://github.com/user-attachments/assets/90400c53-9e1a-4600-9287-647bd3670578" /><br>
Figura 4.3. Rotación. Se aplica la matriz $$R(ϕ) $$ sobre cada vértice del triángulo.
</p>

Finalmente la matriz de transformación es

$$
R(ϕ) = \begin{bmatrix} 
cos ϕ & − sin ϕ \\ 
sin ϕ & cos ϕ  
\end{bmatrix} 
$$

Puesto que

$$
 \begin{bmatrix} 
cos ϕ & − sin ϕ\\ 
sin ϕ &  cos ϕ  
\end{bmatrix}  =\begin{bmatrix}
x cos ϕ − y sin ϕ  \\
x sin ϕy + cos ϕ
\end{bmatrix} = \begin{bmatrix}
x' \\
y'
\end{bmatrix}
$$

Análogamente, en sentido de las manecillas del reloj estaría dada por

$$
 \begin{bmatrix} 
cos ϕ & sin ϕ\\ 
-sin ϕ &  cos ϕ  
\end{bmatrix} 
$$

Y de manera similar al escalamiento podemos pensar a los vectores recibidos en
una base rotada y finalmente descritos con la base canónica.


####  4. Sesgado. 

El sesgado (shear o cizallamiento) es una transformación geométrica no rígida que deforma objetos, desplazando sus puntos en una dirección específica (horizontal, vertical o ambas). Modifica la geometría al deslizar capas del objeto, siendo fundamental para cambiar la forma sin alterar el tamaño de la misma manera que el escalado.

Existe dos posibilidades de hacer transformaciones de sesgo, la primera en la dirección $$x $$ y la segunda en la dirección $$y $$. Para aplicar una transformación de sesgo en la dirección $$x $$ hacemos

$$
 P = \begin{bmatrix} 
x' \\
y' \\
1
\end{bmatrix} = \begin{bmatrix} 
1 & a & 0 \\ 
0 & 1 & 0 \\ 
0 & 0 & 1 
\end{bmatrix} \begin{bmatrix}
x \\
y \\
1
\end{bmatrix}
$$

y en la dirección $$y $$ hacemos

$$
 P = \begin{bmatrix} 
x' \\
y' \\
1
\end{bmatrix} = \begin{bmatrix} 
1 & 0 & 0 \\ 
b & 1 & 0 \\ 
0 & 0 & 1 
\end{bmatrix} \begin{bmatrix}
x \\
y \\
1
\end{bmatrix}
$$

<p align="center">
  <img width="458" height="175" alt="image" src="https://github.com/user-attachments/assets/df825ba4-dbdd-4cb1-9ca1-34973f03ff4e" />
</p>

La ventaja principal de la composición de trasformaciones, es que varias transformaciones (por ejemplo, rotar y luego trasladar) se pueden combinar multiplicando sus respectivas matrices $$(M_f = M_R \cdot .... \cdot M_2 \cdot M_1) $$ para obtener una única matriz que aplica todos los cambios.

<p align="center">
<img width="270" height="186" alt="image" src="https://github.com/user-attachments/assets/36907003-045a-4969-ba76-b6f7bffd770a" />
<img width="276" height="182" alt="image" src="https://github.com/user-attachments/assets/1ce0869f-d25f-4448-8844-13d7a8388c6d" />
</p>


<h2> 2.3. Trazo de líneas curvas. </h2>

<h3> 2.3.1. Bézier. </h3>

<h3> 2.3.2. B-spline. </h3>

<h2> 2.4. Fractales </h2>

<h2> 2.5. Uso y creación de fuentes de texto. </h2>




```python

```


</div>

Referencias
Gosende, J., & Gosende, J. (2025, 20 mayo). ¿Qué es el Diseño Bidimensional o Diseño 2D? ¿Cómo se aplica? Javier Gosende. https://www.javiergosende.com/diseno-bidimensional-2d#:~:text=El%20dise%C3%B1o%20gr%C3%A1fico%20bidimensional%2C%20tambi%C3%A9n,espacio%20plano%2C%20sin%20profundidad%20tridimensional.

https://www.studocu.com/es-mx/document/instituto-de-terapia-ocupacional/sistemas-programables/2-qwertyuiiiiopzxcvbnm/109578771

Eduardo Adam Navas López, Navas Lopez Eduardo Adam. (2011). Una Humilde Introducción a la Graficación Por Computador. . España: Editorial Academica Espanola.

https://graficacion2d21.blogspot.com/2020/10/21-transformacion-bidimensional.html?m=1

# Referencias
