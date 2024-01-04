# *Ejercicio 1* Sea el PVI
$$
\begin{cases}
x'(t) &= t^{2} \sin (x) \\
x(0) &= x_{0} \\
\end{cases}
$$
## a) Determina si hay existencia y unicidad de solución e indica si se puede saber algo acerca del intervalo maximal de definición $I_{x_{0}}$.
Por ser $f(x,t) = t^{2} \sin (x)$ es una función continua en $t$ y Lipschitz globalmente en x, por lo que el teorema de Picard-Lindelöf nos da que existe un intervalo de definición en el cuál existe una única solución al problema de valor inicial.

Para estimar su intervalo de definición observamos (al ser un problema unidimensional) en qué puntos se anula $x'(t)$.

$$
\forall t \quad   x'(t) = 0 \implies \forall t \quad t^{2} \sin(x) = 0 \implies 
x \in \left\{k\pi | k \in \mathbb{Z} \}\right\} 
$$
Concluimos que existen trayectorias constantes para $x_{0} \in \left\{k\pi | k \in \mathbb{Z}\right\}$  y puesto a que tenemos unicidad de soluciones, estas no pueden cruzarse, lo que hace que para cada valor inicial quede contenido en su franja correspondiente.

## b) Define la sucesión de iteradas de Picard-Lindelöf asociada al PVI  y calcula las dos primeras iteraciones de la solución.
La sucesión de iteradas de Picard-Lindelöf se define como $$x_{k + 1}(t) = x_{0} + \int_{0}^{t} f(s, x_{k}(s)) \, ds$$
aplicado a nuestro problema nos da que
$$
\begin{align*}
x_{1}(t) &= x_{0} + \int_{0}^{t} s_{2} \sin (x_{0}) \, ds \\
&= x_{0} + \frac{t^{3}}{3} \sin (x_{0})
\end{align*}
$$
$$
\begin{align*}
x_{2}(t) &= 
x_{0} + \int_{0}^{t} s^{2} \sin \left( \frac{s^{3}}{3} \sin (x_{0}) \right) \, ds \\
&= x_{0} + \frac{1}{\sin (x_{0})} \int_{u_{0}}^{u_{t}} \sin(u) \, du 
\\
&= x_{0} + {\frac{\cos(x_{0})}{\sin x_{0}}} 
- \frac{\cos \left( x_{0} + \frac{t^{3}}{3} \sin (x_{0}) \right)}{\sin x_{0}}
\end{align*}
$$
donde hemos realizado el siguiente cambio de coordenadas para calcular la integral

$$
\begin{align*}
u &= x_{0} + s^{3} \sin (x_{0}) \\
du &= s^{2} \sin (x_{0}) ds \\
u_{0} &= x_{0} \\
u_{t} &= x_{0} + \frac{t^{3}}{3} \sin (x_{0}) \\
\end{align*}
$$
## c) Si $x_{0} > 0$ demuestra que la solución del PVI satisface $\forall t\in I_{x_{0}} \quad x(t) > 0$.
Por el [[#Determina si hay existencia y unicidad de solución e indica si se puede saber algo acerca del intervalo maximal de definición $I_{x_{0}}$. | apartado 1]] para todos los $x_{0}$ tal que $I_{x_{0}} \subset \mathbb{R}^+$ esto está trivialmente demostrado.

## d) Si $x_0 > 0$ utiliza la desigualdad de Grönwall para asegurar que la solución del PVI satisface $\forall {t \in I_{x_{0}}} \cap [0, \infty) \quad x(t) \le x_{0} e^{ \frac{t^{3}}{3} }$ ¿Qué se puede concluir sobre $I_{x_{0}}$.
Usando que $\forall {x>0} \quad {\sin (x) < x}$ tenemos que $x'(t) \le t^{2} x(t)$ donde aplicando la desigualdad obtenemos $x(t) \le x_{0} e^{ \int_{0}^{t} s^{2} \, ds } \le x_{0} e^{ \frac{t^{3}}{3} }$.

No sé que nueva información puedo concluir de esto.

# *Ejercicio 2* Responde razonadamente a los siguientes apartados:

## a) Considera el sistema $x' = f(t,x)$ con $f\in C^1(\mathbb{R} \times \mathbb{R}^n; \mathbb{R}^n)$ y sea $\bar{x}(t) \in \mathbb{R}^n$ una solución en $[0, \infty)$. ¿Qué significa que $\bar{x}(t)$ sea asintóticamente estable?
Significa que $\exists x_{f} \in \mathbb{R}^n \quad \bar{x}(t)  \ \underset{t \to \infty} \longrightarrow x_{f}$

## b) Las funciones $x_{1}(t) =0$ y $x_{2}(t) = t^{3}$ son soluciones de PVI $\begin{cases} x' = 3x^{2/3}\\x(0) = 0\end{cases}$ ¿Cuál (o cuáles) de las hipótesis del teorema de Picard-Lindelöf están fallando?

$f(t,x) = 3x^{2/3}$ no es Lipschitz en 0 ya que la derivada no está acotada.

## c) Sea $x' = f(x)$ un sistema autónomo con $f\in(\mathbb{R}^{2};\mathbb{R}^{2})$ y $\Omega \subset \mathbb{R}^{2}$ un abierto simplemente conexo. ¿Por qué si $div f < 0$ en $\Omega$, entonces no puede existir ninguna órbita homoclínica en $\Omega$?

Por el criterio de Bendixon, sabemos que si la divergencia tiene signo constante en una región, no existen órbitas cerradas en esta.
Una órbita homoclínica es una caso particular de órbita cerrada por lo tanto esto no es posible.

## d) ¿Qué utilidad puede tener saber cómo es el diagrama de fases del sistema linealizado en un punto de equilibrio hiperbólico de un problema autónomo?
El teorema de Hartman-Grobman nos dice que estos equilibrios son topológicamente equivalentes a los de su sistema linealizado.

# *Ejercicio 3* Consideremos el sistema $\begin{cases}x' = x(4 - x^{2} - y)\\ y'= y(-3 + x)\end{cases}$ con datos iniciales $(x(0),y(0)) = (x_{0}, y_{0}) \in C_{1}$ donde $C_{1} = \{ (x,y) \in \mathbb{R}^{2} : x>0,\, y>0 \}$ es el primer  cuadrante del plano.

## a) Estudia los puntos de equilibrio en $\overline{C_{1}}$ y analiza su estabilidad.
En primer lugar trazaremos las nullclinas y observaremos las trayectorias en las mismas.

$$
x' = 0 \implies x(4 - x^{2} - y) = 0 \implies x=0 \, \lor\, y = 4 - x^{2}
$$
$$
\begin{align*}
x' = 0 \,\land\, x = 0 &\implies y' = - 3y \leq 0 \text{ en } \overline{C_{1}}\\
x' = 0 \,\land\, y = 4 - x^{2} &\implies y' = (4-x^{2})(-3 + x) \leq 0 \text{ en } \overline{C_{1}} \\
y' = 0 \,\land\, y = 0 &\implies x' = x(4- x^{2}) \leq 0 \text{ en } \overline{C_{1}} \\
y' = 0 \,\land\, x = 3 &\implies x' = -9 -3y < 0 \text{ en } \overline{C_{1}} \\
\end{align*}
$$
Lo que nos dá el siguiente diagrama junto con los puntos de equilibrio $(x,y)\in \{ (0,0), (2,0) \}$
![[ej3-diag.png]]
Estudiamos la linealización del sistema 
$$
J_{(x,y)} = \begin{bmatrix}
4 - 3x^{2} - y && x \\ \\
y && -3
\end{bmatrix}
$$
en los puntos de equilibrio
$$
J_{(0,0)} = \begin{bmatrix}
4  && 0 \\ \\
0 && -3
\end{bmatrix}
$$
Es un punto de silla, es decir, hiperbólico y se mantiene por Hartman-Grubman en el sistema original.

$$
J_{(2,0)} = \begin{bmatrix}
-8  && 2 \\ \\
0 && -3
\end{bmatrix}
$$
Que es un foco estable, una vez mas, hiperbólico.

## b) Prueba que la región $R = \{ (x,y) \in C_{1} : y < 4 - x^{2} \}$ es positivamente invariante.

Nos disponemos a cercar la región por las curvas $x = 0$, $y=0$ e $y = 4-x^{2}$ para concluir que el campo no puede escapar de ellas.

En el anterior apartado observamos que $x = 0$, $y= 0$ y el punto $(2,0)$ son trayectorias del sistema y por unicidad y existencia estas no podrán cruzarse ni alcanzarse en tiempo finito.
Del mismo modo, ya realizado en el apartado anterior, vimos que para $y = 4 -x^2$ las trayectorias siempre apuntan hacia el interior de nuestra región.

Podemos concluir entonces que la región es positivamente invariante.

## c) Demuestra que si $(x(t),y(t))$ es la solución con dato inicial $(x_{0}, y_{0}) \in R$, entonces las dos funciones $x(t)$ e $y(t)$ son monótonas. Analiza rigurosamente el comportamiento asintótico de las soluciones con estos datos iniciales.

Puesto que tenemos la nullclinas ya calculadas y son funciones continuas, sabemos que en la región $x'$ es positiva e $y'$ es negativa, es decir, ambas son monótonas y tienden al punto de equilibrio en $(2,0)$.

# *Ejercicio 4* Sea $\mu \in C^1(\mathbb{R}^{2};\mathbb{R})$ que satisface $\mu(0,0) = 0, \, \mu > 0$ en $\mathbb{R}^2 \setminus \{ (0,0) \}$ y $\lim_{ |(x,y)| \to +\infty } \mu(x,y) = +\infty$. Consideremos la ecuación $x'' + (\mu(x,x') - 1)x' + x = 0$.

## a) Prueba que existen $0 < r_{0} < R_{0}$ tales que $\{ (x,y) : x^{2} + y^{2} \le r_{0}^{2} \}\subset \{ (x,y) : (x,y) : \mu(x,y) < 1 \} \subset \{ (x,y) : \mu(x,y) \le 1 \} \subset \{ (x,y) : x^{2} + y^{2} < R_{0}^2 \}$. Concluye que el anillo $A_{r_{0},R_{0}} = \{ (x,y) : r_{0}^2 \le x^{2} + y^{2} \le R_{0}^{2}\}$ es positivamente invariante. ¿Tiene el sistema alguna órbita periódica?
Por continuidad sabemos que $\exists x,y \quad \mu(x,y) = 1$, definimos $r_{0}$ como el valor mínimo de $x^{2} + y^{2}$ para los $x$ e $y$ que cumplen $\mu(x,y) = 1$. 
Del mismo modo podemos definir $R_{0}$ como el valor máximo de $x^{2} + y^{2}$ para los $x$ e $y$ que cumplen $\mu(x,y) = 1$. 

$$
\begin{cases}
x' &= y \\
y' &= - x - (\mu(x,y) - 1)y
\end{cases}
=
\begin{cases}
x' &= y \\
y' &= -x + y -y \mu(x,y)\\
\end{cases}
$$
Observemos entonces la función de Lyapunov $V(x,y)= x^{2} + y^{2} \geq 0$  en la región  $\{ (x,y) : x^{2} + y^{2} \le R_{0}^{2} \}$ tiene como derivada

$$
\begin{align*}
\frac{dV(x,y)}{dt}
&=
\frac{\partial V(x,y)}{\partial x} \frac{dx}{dt} + \frac{\partial V(x,y)}{\partial y} \frac{dy}{dt}\\
&= 2x x' + 2y y'\\
&= 2xy + 2y( -x + y - y \mu (x,y))\\
&= 2xy - 2yx + 2y^{2} - 2y^{2} \mu (x,y)\\
&= 2y^{2} (1 - \mu (x,y))
\end{align*}
$$
valor que será negativo para cualquier curva $x^{2} + y^{2} = R$ con $R > R_{0}$.

Lo que nos dice que el anillo es positivamente invariante.

Podemos realizar un análisis similar con $r_{0}$ para concluir que la región sería negativamente invariante.

Podemos aplicar el teorema de Poincaré-Bendixon ya que estas dos curvas forman un 
ánulo positivamente invariante sin puntos fijos en su interior (ya que $(0,0)$ es el único punto de equilibrio) que nos dice que existe una órbita periódica en su interior.

## b) Supongamos que no hay órbitas periódicas fuera de $B_{R_{0}}$. Demuestra que para todo dato inicial $(x_{0},y_{0}) \in \mathbb{R}^{2}$ existe un tiempo $\tau \geq 0$ tal que la solución que parte de ese dato inicial verifica $\forall t \ge \tau \quad x^{2}(t) +y^{2}(t) <R_{0}^2$.

De la ecuación $x^{2} + y^{2} = r^{2}$ obtengo que $x x' + y y' = r r'$ lo que sustituyendo el problema actual nos da $r r' = y^{2}(1 - \mu(\theta,r))$ que sabiendo que $y = r \sin (\theta)$ simplifica a $r' = r(1 - \mu(\theta, r)) \sin^{2}(\theta)$ que podemos observar es negativo en todo $r > R_{0}$ salvo cuando $y = 0$, pero estos puntos no son equilibrios y por hipótesis no hay órbitas periódicas, así que podemos concluir que el comportamiento asintótico es que el radio decrece hasta al menos cruzar la frontera de la región que en el apartado anterior definimos como positivamente invariante. Q.E.D.
