# Unidad-2---Apuntes
<div align="justify">
   
<h1> Unidad 2 Graficación 2D.  </h1>
<img width="1024" height="559" alt="image" src="https://github.com/user-attachments/assets/f07e3e08-feb4-4345-8dd6-db1e1534e830" />
El diseño gráfico bidimensional, también conocido como diseño gráfico 2D, se enfoca en la generación y manipulación de imágenes digitales, modelos geométricos y texto sobre un plano bidimensional (altura y anchura). Incluye algoritmos de trazado de líneas, formas y transformaciones geométricas 2D como traslación, rotación y escalado.

La transformación bidimensional es un concepto fundamental en la geometría computacional y el diseño gráfico que se refiere a las operaciones matemáticas aplicadas a figuras en un plano bidimensional. Estas transformaciones modifican la posición, orientación, tamaño o forma de los objetos sin salir del plano. En el contexto de la gráfica por computadora y otros campos, las transformaciones bidimensionales se utilizan para manipular imágenes, figuras y coordenadas de manera eficiente. Estas transformaciones son fundamentales en áreas como la computación gráfica, el diseño asistido por computadora (CAD) y la geometría computacional. Existen varios tipos de transformaciones, como la traslación, rotación, escalamiento y reflexión, que permiten manipular objetos de manera precisa. Estas operaciones se representan comúnmente mediante matrices, lo que facilita su aplicación en diversos sistemas. En campos como la animación digital y los videojuegos, las transformaciones bidimensionales son esenciales para lograr movimiento, interacción y cambios visuales en objetos y personajes. Además, son cruciales en disciplinas como la cartografía, donde se utilizan para transformar y proyectar mapas con precisión.

<h2> 2.1. Transformación bidimensional. </h2>

Las transformaciones bidimensionales son operaciones geométricas fundamentales en computación gráfica que modifican la posición, tamaño, orientación o forma de objetos en un plano. Se aplican mediante matrices (usualmente coordenadas homogéneas $$3X3 $$) para manipular puntos $$P(x, y) $$ y convertirlos en nuevos puntos $$P'(x', y') $$, siendo esenciales en diseño, animación y modelado.

<h3> 2.1.1. Traslación. </h3>
Mueve un objeto a una nueva posición desplazando cada punto $$P(x, y) $$  un vector $$(T_x, T_y) $$ . Las ecuaciones son:

$$x' = x + Tx$$ $$y' = y + Ty$$

El objeto conserva su forma y tamaño. 

<p align="center">
<img width="320" height="187" alt="image" src="https://github.com/user-attachments/assets/54beb744-97c1-416d-a4f9-8a4495f9399d" />
</p>

<h3> 2.1.2. Escalamiento. </h3>

Altera el tamaño de un objeto multiplicando las coordenadas por factores de escala $$S(S_x, S_y) $$ respecto al origen.

$$x' = S_x \cdot x $$   $$y' = S_y \cdot y $$

Si $$S_x = S_y$$, el escalamiento es uniforme.

<p align="center">
<img width="248" height="203" alt="image" src="https://github.com/user-attachments/assets/a0d81abc-ac30-4359-a6ab-56e287c5c5dc" />
</p>

<h3> 2.1.3. Rotación. </h3>
Gira un objeto un ángulo $$θ $$ respecto al origen (normalmente en sentido antihorario). 

$$x′ = x \cdot cos(θ) -y \cdot sin(θ) $$ $$y′ = x \cdot sin(θ)+y \cdot cos(θ) $$

La rotación mantiene la forma y el tamaño del objeto.

<p align="center">
<img width="259" height="194" alt="image" src="https://github.com/user-attachments/assets/ad7a309a-753d-41db-b77a-68e16591e532" />
</p>

<h3> 2.1.4. Sesgado. </h3>
Deforma la forma de un objeto desplazando sus coordenadas en una dirección, haciendo que parezca inclinado. 

Sesgado en $$X $$: $$x′ = x + sh_x \cdot y,    y′ = y $$ 

Sesgado en $$Y $$: $$  x′ = x,      y′ = y + sh_y \cdot x $$

Esta transformación modifica los ángulos internos de la figura. 

<p align="center">
<img width="329" height="321" alt="image" src="https://github.com/user-attachments/assets/69e3126a-0053-4a59-b833-159105e8d8bb" />
</p>

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

Existe dos posibilidades de hacer transformaciones de sesgo, la primera en la dirección $$x $$ y la segunda en la dirección $$y $$. Para aplicar una transformación de sesgo en la dirección $$x $$ hacemos:

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

y en la dirección $$y $$ hacemos:

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

### Ejercicio de control con teclas de dirección.
Descripción del proyecto:

El objetivo de este ejercicio fue implementar el control de un objeto dentro de Blender utilizando las teclas de dirección del teclado, mediante el uso de scripting en Python.

Paso 1: Creación del dibujo

Primero, se procedió a realizar el dibujo dentro de Blender.
Para ello:

Se creó un objeto (puede ser una figura, modelo o dibujo simple).

Este objeto fue nombrado como "MiDibujo", ya que el código lo identifica mediante ese nombre.

Se ajustó su posición inicial dentro del espacio 2D.

Este paso es fundamental, ya que el script depende de la existencia del objeto para poder manipularlo.

<p align="center">
 <img width="468" height="597" alt="image" src="https://github.com/user-attachments/assets/f6122a9f-f107-42e4-8c81-1b5009039437" />
</p>


Paso 2: Implementación del código

Posteriormente, se añadió un script en Python dentro del editor de texto de Blender.

El código utiliza un operador modal, lo que permite capturar eventos del teclado en tiempo real.

Funcionamiento del código:

Se obtiene el objeto llamado "MiDibujo" desde la escena.

Se detectan las teclas presionadas por el usuario.

Dependiendo de la tecla, el objeto se mueve en diferentes direcciones:

Flecha izquierda: mueve el objeto en el eje X negativo.

Flecha derecha: mueve el objeto en el eje X positivo.

Flecha arriba: mueve el objeto hacia arriba en el eje Z.

Flecha abajo: mueve el objeto hacia abajo en el eje Z.

Cada movimiento se realiza en incrementos de 0.5 unidades.

La tecla ESC permite finalizar la ejecución del operador.

<p align="center">
<img width="1085" height="1015" alt="image" src="https://github.com/user-attachments/assets/3ad9bd22-18ac-4208-8eaf-0a431530893e" />
</p>

Código

```python
import bpy

class ModalMoveOperator(bpy.types.Operator):
    bl_idname = "object.modal_move_operator"
    bl_label = "Modal Move Operator"

    def modal(self, context, event):
        obj = bpy.data.objects.get("MiDibujo")
        
        if not obj:
            return {'CANCELLED'}

        if event.value == 'PRESS':
            # IZQUIERDA / DERECHA (Eje X)
            if event.type == 'LEFT_ARROW':
                obj.location.x -= 0.5
            elif event.type == 'RIGHT_ARROW':
                obj.location.x += 0.5
                
            # ARRIBA / ABAJO (Eje Z - Altura en vista frontal)
            elif event.type == 'UP_ARROW':
                obj.location.z += 0.5
            elif event.type == 'DOWN_ARROW':
                obj.location.z -= 0.5

            # SALIR
            elif event.type == 'ESC':
                return {'FINISHED'}

        return {'RUNNING_MODAL'}

    def invoke(self, context, event):
        context.window_manager.modal_handler_add(self)
        return {'RUNNING_MODAL'}

bpy.utils.register_class(ModalMoveOperator)
bpy.ops.object.modal_move_operator('INVOKE_DEFAULT')
```


Ejecución 
Se logró controlar el movimiento del objeto en tiempo real usando el teclado, lo cual simula una interacción básica dentro del entorno 2D. 
<img width="1919" height="1013" alt="image" src="https://github.com/user-attachments/assets/7d552ef6-cdd9-4ccc-86a6-f6d7a07fb646" />


<h2> 2.3. Trazo de líneas curvas. </h2>
El trazo de líneas curvas es fundamental en el diseño asistido por computadora (CAD) y gráficos computacionales, permitiendo modelar formas suaves y complejas a partir de puntos de control. 

#### Línea
Una marca delgada hecha por un esferográfico o un lápiz etc.

En geometría una línea:

· es recta (sin curvas),  

· no tiene grosor,

· se extiende en ambas direcciones sin tener un final (infinitamente). 

Si tuviera fin se llamaría "segmento de línea"

#### Trazado de líneas

Diferentes tipos de líneas y situaciones en que se dibujan se resuelven con técnicas diferentes.

- Líneas cortas, o líneas que corren paralelas a otras que nos sirven de referencia.

- Líneas largas. Es el caso de líneas que unen dos puntos alejados, sin ninguna otra referencia. Las primeras líneas de cualquier croquis entran en esta categoría.

Líneas cortas o líneas paralelas a otras ya existentes se las puede dibujar de un solo trazo. Primero se deben mirar bien los puntos de inicio y terminación para luego ejecutar el trazo.

Para el trazado de líneas largas vamos a dar tres técnicas que se utilizarán según las circunstancias.

#### Líneas punto a punto
La técnica más rápida es, una vez determinados los puntos a unir se comienza moviendo el lápiz desde uno de ellos hacia el otro. Mientras se hace este movimiento se debe mantener la vista sobre el punto de destino. Esto último nos permitirá conservar la dirección.

#### Líneas compuestas
Una segunda técnica es proceder mediante trazos de cinco a siete centímetros; como si se estuviesen dibujando una sucesión de líneas más cortas. La interrupción del trazo permite verificar el rumbo del trazo y se corregir si es necesario. Los trazos sucesivos no se superponen a fin de posibilitar uniformidad de espesor. Se deja una pequeñísima luz entre ellos de forma tal que apenas resulte perceptible la interrupción y mantenga el espesor uniforme.

#### Líneas de construcción
Una tercera técnica, particularmente aplicable cuando se está planteando el dibujo, es utilizar líneas de tanteo. Resulta un poco más lenta que las anteriores, pero es de gran ayuda para obtener líneas rectas particularmente cuando son muy largas. Consiste en insinuar la línea en forma apenas visible con trazos muy suaves. Idealmente, solo el dibujante debería percibir esos trazos de tanteo. Se observa el resultado obtenido. Se introducen las correcciones necesarias hasta lograr definir el trayecto correcto. Entonces se comienza el trazado de la línea en forma similar al primer método, pero ahora con una guía visual. Si fuese necesario, porque se utilizaron demasiadas líneas de tanteo, se podrán borrar las que no sirven, antes del trazado definitivo.

<p align="center">
<img width="550" height="589" alt="image" src="https://github.com/user-attachments/assets/8b98b3f8-1ab4-4361-bf53-4463c8bdb67b" />
</p>

<h3> 2.3.1. Bézier. </h3>
Las herramientas de dibujo libre que incorporan la mayoría de programas vectoriales se basan en este concepto para el trazado de líneas curvas.
Este tipo de curvas fue desarrollado por Pierre Bézier por encargo de la empresa de automóviles Renault™ que buscaba una representación matemática para definir las transiciones suaves en la curvatura de las líneas de sus automóviles.

Curvas Bézier
Se generan a partir de funciones polinómicas de grado tres que permiten la representación de cualquier forma curvada y evitan la complicación innecesaria de cálculos matemáticos que se produciría usando polinomios de mayor grado.
Cualquier trazado de estas características está definido por una serie de puntos por los que pasa la curva y otros exteriores a ella que definen sus puntos de inflexión, es decir, aquellos en que cambia de curvatura, pasando de cóncava a convexa o viceversa.

Manejadores de la curva
En un trazado Bézier existen "manejadores" en cada uno de sus nodos de manera que se puede alterar la curvatura a voluntad para adaptar el trazo a cualquier forma imaginable, controlando la suavidad de las zonas de transición.

<p align="center">
<img width="509" height="313" alt="image" src="https://github.com/user-attachments/assets/ef025536-65f6-458e-b81f-ccc49d08e06f" />
</p>

En general, es posible ajustar una curva de Bézier para cualquier numero de puntos de control. El numero de puntos de control que se debe aproximar y su posición relativa determina el grado de polinomio de Bézier. La idea de definir geométricamente las formas no es demasiado compleja: un punto del plano puede definirse por coordenadas. Por ejemplo, un conjunto A tiene unas coordenadas(x1, y1) y a un punto B le corresponde (x2, y2).para trazar una recta entre ambos basta con conocer su posición. Si en lugar de unir dos puntos con una recta se unen con una curva, surgen los elementos esenciales de una curva Bézier: los puntos se denominan puntos de anclaje o nodos. La forma de la curva se define por unos puntos invisibles en el dibujo, denominados puntos de control, manejadores o manecillas

<h3> 2.3.2. B-spline. </h3>
En el subcampo matemático de análisis numérico, una B-spline o Basis spline (o traducido una línea polinómica suave básica), es una función spline que tiene el mínimo soporte con respecto a un determinado grado, suavidad y partición del dominio. Un teorema fundamental establece que cada función spline de un determinado grado, suavidad y partición del dominio, se puede representar como una combinación lineal de B-splines del mismo grado y suavidad, y sobre la misma partición.​ El término B-spline fue acuñado por Isaac Jacob Schoenberg y es la abreviatura de spline básica. Las B-splines pueden ser evaluadas de una manera numéricamente estable por el algoritmo de Boor. De un modo simplificado, se han creado variantes potencialmente más rápidas que el algoritmo de Boor, pero adolecen comparativamente de una menor estabilidad.
En el subcampo de la informática de diseño asistido por computadora y de gráficos por computadora, el término B-spline se refiere con frecuencia a una curva parametrizada por otras funciones spline, que se expresan como combinaciones lineales de B-splines (en el sentido matemático anterior). Una B-spline es simplemente una generalización de una curva de Bézier, que puede evitar el fenómeno Runge sin necesidad de aumentar el grado de la B-spline

<p align="center">
<img width="509" height="313" alt="image" src="https://github.com/user-attachments/assets/3bbbc829-a24e-4b28-9e47-966e224410d3" / >
</p>

### Ejercicio dibujo de la Animación frame x frame
En el siguiente enlace se explica detalladamente el proceso para diseñar un dibujo con animación frame by frame en Blender, una técnica que consiste en crear movimiento a partir de la secuencia de imágenes individuales o fotogramas.

https://github.com/Sinai-Clemente/U2-PROYECTO-INTEGRADOR/blob/main/README.md#u2-proyecto-integrador

Resultado<br>
Como resultado final, se obtuvo una animación 2D fluida de una mascota, lograda mediante el uso de dibujo cuadro por cuadro, organización por capas y aplicación de efectos visuales.<br>
<p align="center">
 <img width="1408" height="768" alt="image" src="https://github.com/user-attachments/assets/9db72aa4-cf49-4dc5-9a7c-e111e341753c" />
</p>

<h2> 2.4. Fractales </h2>
Los fractale son objetos geométricos caracterizados por la autosimilitud (repetición de patrones a diferentes escalas) y una estructura recursiva infinita. Propuesto por Benoît Mandelbrot, permiten representar formas complejas y naturales (montañas, nubes) que la geometría euclidiana tradicional no puede describir, utilizando algoritmos recursivos. Los ejemplos más populares son el conjunto “Mandelbrot” o el triángulo “Sierpinski”.

<p align="center">
<img width="425" height="330" alt="image" src="https://github.com/user-attachments/assets/772167bf-d2a5-43f4-b7ea-7eb61fe9bc30" />
</p>

Los fractales se grafican mediante métodos geométricos (reglas de producción) o iterando fórmulas sobre coordenadas, con un alto consumo de recursos computacionales debido a la recursión. A diferencia de las figuras euclidianas (punto 0, línea 1, plano 2), los fractales tienen dimensiones fraccionarias que miden su rugosidad o capacidad de ocupar el espacio.

### Tipos de Fractales
Los fractales se clasifican principalmente por su método de generación: 

#### Fractales Lineales (Geométricos):

Se crean reemplazando partes de una figura con copias de sí misma a escala.

Ejemplos: Copo de nieve de Koch (perímetro infinito con área finita), Triángulo de Sierpinski y el Conjunto de Cantor.

<p align="center">
<img width="203" height="379" alt="image" src="https://github.com/user-attachments/assets/dd149210-768d-43ae-a372-b4d7d7295126" />
</p>



#### Fractales No Lineales (Algoritmos de escape):

Basados en funciones complejas que determinan si un punto "escapa" al infinito tras varias iteraciones.

Ejemplos: El Conjunto de Mandelbrot (el más famoso en computación gráfica) y los Conjuntos de Julia.

<p align="center">
<img width="234" height="216" alt="image" src="https://github.com/user-attachments/assets/cdde5629-2be6-4fb8-9e73-6076d26ddb01" />
</p>



#### Fractales Aleatorios:

Utilizan procesos estocásticos (al azar) para simular fenómenos naturales.

Aplicaciones: Generación de terrenos, nubes, texturas realistas y simulación de sistemas biológicos.

<p align="center">
<img width="600" height="300" alt="image" src="https://github.com/user-attachments/assets/a6a8b497-bddf-4084-9e11-bdd1bb3e6740" />
</p>

<h2> 2.5. Uso y creación de fuentes de texto. </h2>
El uso y creación de fuentes de texto implica definir y manipular caracteres alfanuméricos como formas geométricas (vectores o mapa de bits) para su visualización. Incluye la selección de tipografías, manejo de estilos (Serif, Sans-serif), escalamiento y técnicas de renderizado para legibilidad. Las fuentes digitales (TTF, OTF) se integran mediante APIs gráficas para representar información clara. 

También llamada tipografía, es una definición de los distintos caracteres que se pueden usar en un documento; de este modo, las distintas fuentes presentarán las letras con un dibujo o tipo de letra diferente y en un sistema infofrmatico cada símbolo individual se le llama caracter o procesador de textos de un tipo y tamaño determinados.

### TIPOGRAFÍA DIGITAL
Los archivos de tipografía son independientes de las aplicaciones que los usan, que normalmente se instalan en un determinado directorio del sistema operativo para que estén disponibles en todos los programas que los necesiten.

Los más comunes son:

-TTF (TrueType Font)

-PostScript Type 1

-OTF (OpenType Font)

<p align="center">
<img width="600" height="251" alt="image" src="https://github.com/user-attachments/assets/c271a656-0242-4629-8c70-6c60f97e08c7" />
</p>

#### PostScript Type 1
Es un lenguaje de descripción de páginas (en inglés: Page Description Language, PDL), utilizado en muchas impresoras y, de manera usual, como formato de transporte de archivos gráficos en talleres de impresión profesional.

#### OTF (Open Type Font)
Es un formato de tipos de letra escalables para computadora; su arquitectura esta basada en la de su antecesor (True Type), cuya estructura básica conserva y la cual complementa con tablas de datos que permiten incorporar a un tipo o familia tipográfica funciones tipográficas y lingüísticas avanzadas.

#### TTF (Tru Type Font)
Es un formato estándar de tipos de letra escalables desarrollado inicialmente por Apple Computer a finales de la década de los ochenta para competir comercialmente con el formato "Type 1" de Adobe Systems, el cual estaba basado en el lenguaje de descripción de página conocido como PostScript.


### Uso de Fuentes de Texto en Graficación 2D
Representación: Los caracteres se definen como formas cerradas (vectores) o mapas de bits (píxeles), lo que permite escalarlos sin perder calidad, especialmente con fuentes TrueType (TTF).

Clasificación: Se utilizan fuentes con remates (Serif), sin remates (Sans-serif), monoespaciadas y caligráficas, cada una con aplicaciones específicas en el diseño técnico o artístico.

Técnicas de Renderizado: Se ajustan atributos como interletrado, interlineado y suavizado (antialiasing) para mejorar la legibilidad en pantallas.

API Gráficas: Herramientas como la explicada en este informe sobre graficación 2D permiten la ubicación precisa de texto en coordenadas 2D.


### Creación y Manipulación de Fuentes
Diseño Digital: Los caracteres se crean mediante curvas (habitualmente Bézier), ajustando el trazo, la personalidad y el espaciado (kerning).

Formatos: Las fuentes se guardan en formatos estándar como OpenType (OTF) y TTF, que son independientes de la aplicación y se instalan en el sistema operativo.

Personalización: Se pueden diseñar fuentes técnicas, como las abordadas en este ejemplo de AutoCAD, para rótulos y documentación en dibujo técnico.

### Aspectos Técnicos
Psicología Tipográfica: Se selecciona la fuente según el tono deseado, donde las Sans-serif suelen ser preferidas para visualización de datos por su limpieza, según se detalla en este video de elementos de diseño.

Integración: En entornos como este manual de graficación, el uso de fuentes es fundamental para asegurar la accesibilidad y correcta visualización en diferentes plataformas.

<p align="center">
<img width="509" height="313" alt="image" src="https://github.com/user-attachments/assets/3b0af943-8576-4fd0-98a5-c68ef07edc55" />
</p>

</div>

# Referencias

Gosende, J., & Gosende, J. (2025, 20 mayo). ¿Qué es el Diseño Bidimensional o Diseño 2D? ¿Cómo se aplica? Javier Gosende. https://www.javiergosende.com/diseno-bidimensional-2d#:~:text=El%20dise%C3%B1o%20gr%C3%A1fico%20bidimensional%2C%20tambi%C3%A9n,espacio%20plano%2C%20sin%20profundidad%20tridimensional.

Jean H.,  & Jean H., (2024, 15 Octubre). Gráficación 2D: Transformación Bidimensional - Unidad 2 IS. https://www.studocu.com/es-mx/document/instituto-de-terapia-ocupacional/sistemas-programables/2-qwertyuiiiiopzxcvbnm/109578771

Eduardo Adam Navas López, Navas Lopez Eduardo Adam. (2011). Una Humilde Introducción a la Graficación Por Computador. . España: Editorial Academica Espanola. https://imusic.dk/artist/Eduardo+Adam+Navas+L%C3%B3pez

Christian Javier Mendoza Ramos, Mendoza Ramos Christian Javier, (2020, octubre 18). Graficacion 2d. https://graficacion2d21.blogspot.com/?m=1

Fractales. (s. f.). https://fernandez-torres-jose.blogspot.com/2012/08/fractales.html?m=1

Álvaro Rodríguez - Finanzas VLR. (2024, 3 enero). Elementos básicos de diseño gráfico: Tipografía, tipo de fuente, fuente personalizada -PowerPoint [Vídeo]. YouTube. https://www.youtube.com/watch?v=bn0h-RUuwYg

Notas para el curso de graficación por computadora. (s. f.). https://prometeo.matem.unam.mx/recursos/VariosNiveles/iCartesiLibri/recursos/Notas_Graficacion_por_Computadora/index.html?page=8

Introducción a la graficación por computadora . (s. f.). https://proyectodescartes.org/iCartesiLibri/PDF/GraficacionComputadora.pdf

  


