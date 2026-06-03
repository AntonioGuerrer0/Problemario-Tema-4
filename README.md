<h1 align="center">Problemario de Métodos Numéricos</h1>

<h3>Realizado por:</h3>

<ul>
    <li>Jose Antonio Guerrero Lazcano</li>
</ul>

<hr>

<h1 id="indice" align="center">ÍNDICE</h1>

<ul>

<li><a href="#competencia-asignatura">Competencia de la Asignatura</a></li>

<li>
<a href="#interpolacion"> TEMA 4: Interpolación</a>

<ul>
<li><a href="#interpolacion-lineal">Interpolación Lineal</a></li>
<li><a href="#interpolacion-cuadratica">Interpolación Cuadrática</a></li>
<li><a href="#lagrange">Interpolación Lagrange</a></li>
<li><a href="#newton">Interpolación de Newton</a></li>
</ul>

</li>
<h2 id="interpolacion-lineal" align="center">
1. Interpolación Lineal
</h2>

<h3>¿Qué es?</h3>

<p>
La interpolación lineal es un método numérico utilizado para estimar valores desconocidos dentro de un intervalo utilizando dos puntos conocidos. Este método supone que entre ambos puntos existe una línea recta.
</p>

<p>
Es una de las técnicas de interpolación más simples y utilizadas debido a su facilidad de implementación y rapidez de cálculo.
</p>

<p>
La interpolación lineal permite aproximar valores intermedios cuando no se dispone de todos los datos exactos de una función.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula de Interpolación Lineal</h4>

<pre>
f(x) = f(x0) + ((x - x0) / (x1 - x0)) * (f(x1) - f(x0))
</pre>

<h4>Donde:</h4>

<ul>
<li><b>x0 y x1:</b> puntos conocidos.</li>
<li><b>f(x0) y f(x1):</b> valores conocidos de la función.</li>
<li><b>x:</b> valor a interpolar.</li>
<li><b>f(x):</b> valor aproximado.</li>
</ul>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Es fácil de entender e implementar.</li>
<li>Requiere pocos cálculos matemáticos.</li>
<li>Es rápida para obtener aproximaciones.</li>
<li>Funciona bien con datos cercanos.</li>
<li>Es útil en aplicaciones simples de ingeniería.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede generar errores en funciones curvas.</li>
<li>Solo utiliza dos puntos para aproximar.</li>
<li>No es adecuada para datos complejos.</li>
<li>La precisión disminuye en intervalos grandes.</li>
<li>No representa correctamente comportamientos no lineales.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Procesamiento de datos y simulaciones numéricas.
</li>

<li>
<b>Ingeniería Civil:</b>
Estimación de valores estructurales y topográficos.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Análisis de movimiento y datos experimentales.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento digital de señales.
</li>

<li>
<b>Ingeniería Industrial:</b>
Análisis estadístico y optimización de procesos.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir x0 = 2
    Definir y0 = 4

    Definir x1 = 6
    Definir y1 = 10

    Definir x = 4

    resultado =
    y0 + ((x - x0) / (x1 - x0))
    * (y1 - y0)

    Mostrar "Valor interpolado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class InterpolacionLineal {

    public static double interpolar(
            double x0,
            double y0,
            double x1,
            double y1,
            double x) {

        return y0 + ((x - x0) / (x1 - x0)) * (y1 - y0);
    }

    public static void main(String[] args) {

        double x0 = 2;
        double y0 = 4;

        double x1 = 6;
        double y1 = 10;

        double x = 4;

        double resultado = interpolar(x0, y0, x1, y1, x);

        System.out.println("Valor interpolado: " + resultado);
    }
}
```
<h3>Compilación del codigo</h3>

<img width="335" height="89" alt="Captura de pantalla 2026-05-27 194913" src="https://github.com/user-attachments/assets/cf868956-971e-49aa-a1ec-97a19355e0f0" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="interpolacion-cuadratica" align="center">
2. Interpolación Cuadrática
</h2>

<h3>¿Qué es?</h3>

<p>
La interpolación cuadrática es un método numérico utilizado para aproximar valores desconocidos mediante una función polinómica de segundo grado. A diferencia de la interpolación lineal, este método utiliza tres puntos conocidos para construir una parábola que pase por dichos puntos.
</p>

<p>
La interpolación cuadrática proporciona una mejor aproximación cuando los datos presentan curvaturas o cambios no lineales.
</p>

<p>
Es ampliamente utilizada en análisis numérico y simulaciones matemáticas debido a su mayor precisión respecto a métodos lineales.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Polinomio cuadrático general</h4>

<pre>
P(x) = ax² + bx + c
</pre>

<h4>Forma de interpolación cuadrática</h4>

<pre>
P(x) = y0L0(x) + y1L1(x) + y2L2(x)
</pre>

<h4>Donde:</h4>

<ul>
<li><b>x0, x1, x2:</b> puntos conocidos.</li>
<li><b>y0, y1, y2:</b> valores conocidos de la función.</li>
<li><b>P(x):</b> valor interpolado.</li>
<li><b>L(x):</b> polinomios de interpolación.</li>
</ul>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Mayor precisión que la interpolación lineal.</li>
<li>Representa mejor funciones curvas.</li>
<li>Permite aproximaciones más suaves.</li>
<li>Es útil para análisis matemáticos complejos.</li>
<li>Reduce errores en ciertos cálculos numéricos.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Requiere más cálculos matemáticos.</li>
<li>Necesita al menos tres puntos conocidos.</li>
<li>Puede presentar oscilaciones en algunos casos.</li>
<li>Es más compleja de implementar.</li>
<li>No siempre mejora la precisión en grandes intervalos.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Simulación matemática y procesamiento numérico.
</li>

<li>
<b>Ingeniería Civil:</b>
Modelado de estructuras y análisis topográfico.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Análisis de trayectorias y movimiento.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento y análisis de señales.
</li>

<li>
<b>Ingeniería Industrial:</b>
Optimización de datos y análisis estadístico.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir x0 = 1
    Definir y0 = 1

    Definir x1 = 2
    Definir y1 = 4

    Definir x2 = 3
    Definir y2 = 9

    Definir x = 2.5

    L0 = ((x - x1) * (x - x2)) /
         ((x0 - x1) * (x0 - x2))

    L1 = ((x - x0) * (x - x2)) /
         ((x1 - x0) * (x1 - x2))

    L2 = ((x - x0) * (x - x1)) /
         ((x2 - x0) * (x2 - x1))

    resultado =
    (y0 * L0) + (y1 * L1) + (y2 * L2)

    Mostrar "Valor interpolado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class InterpolacionCuadratica {

    public static double interpolar(
            double x0, double y0,
            double x1, double y1,
            double x2, double y2,
            double x) {

        double L0 = ((x - x1) * (x - x2)) /
                    ((x0 - x1) * (x0 - x2));

        double L1 = ((x - x0) * (x - x2)) /
                    ((x1 - x0) * (x1 - x2));

        double L2 = ((x - x0) * (x - x1)) /
                    ((x2 - x0) * (x2 - x1));

        return (y0 * L0) + (y1 * L1) + (y2 * L2);
    }

    public static void main(String[] args) {

        double x0 = 1;
        double y0 = 1;

        double x1 = 2;
        double y1 = 4;

        double x2 = 3;
        double y2 = 9;

        double x = 2.5;

        double resultado = interpolar(
                x0, y0,
                x1, y1,
                x2, y2,
                x);

        System.out.println("Valor interpolado: " + resultado);
    }
}
```
<h3>Compilación del codigo</h3>

<img width="331" height="90" alt="Captura de pantalla 2026-05-27 195122" src="https://github.com/user-attachments/assets/ba9d58ad-7198-409d-b9ec-39d4a9cb498b" />

<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="lagrange" align="center">
3. Interpolación Lagrange
</h2>

<h3>¿Qué es?</h3>

<p>
La interpolación de Lagrange es un método numérico utilizado para encontrar un polinomio que pase exactamente por un conjunto de puntos conocidos. Este método construye un polinomio de interpolación utilizando combinaciones de polinomios base llamados polinomios de Lagrange.
</p>

<p>
La interpolación de Lagrange es muy utilizada cuando se necesita aproximar funciones a partir de datos discretos sin resolver sistemas de ecuaciones.
</p>

<p>
Permite obtener una función polinómica capaz de estimar valores intermedios con buena precisión.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Fórmula general de Lagrange</h4>

<pre>
P(x) = Σ [ yi * Li(x) ]
</pre>

<h4>Polinomio base de Lagrange</h4>

<pre>
Li(x) = Π [(x - xj) / (xi - xj)]
</pre>

<h4>Donde:</h4>

<ul>
<li><b>P(x):</b> polinomio interpolador.</li>
<li><b>Li(x):</b> polinomio base.</li>
<li><b>xi, yi:</b> puntos conocidos.</li>
<li><b>x:</b> valor a interpolar.</li>
</ul>

<hr>

<h3>Ventajas</h3>

<ul>
<li>No requiere resolver sistemas de ecuaciones.</li>
<li>Permite interpolar múltiples puntos.</li>
<li>Ofrece buena precisión en funciones suaves.</li>
<li>Es útil en análisis numérico.</li>
<li>Puede implementarse fácilmente en programación.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>El polinomio puede volverse muy grande.</li>
<li>Puede presentar oscilaciones con muchos puntos.</li>
<li>Consume más tiempo de cálculo.</li>
<li>Es menos eficiente para grandes conjuntos de datos.</li>
<li>Los errores aumentan en intervalos amplios.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Procesamiento numérico y simulaciones matemáticas.
</li>

<li>
<b>Ingeniería Civil:</b>
Análisis estructural y representación de datos.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Modelado de trayectorias y sistemas físicos.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento digital de señales.
</li>

<li>
<b>Ingeniería Industrial:</b>
Análisis estadístico y optimización matemática.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir x = {1, 2, 3}
    Definir y = {1, 4, 9}

    Definir valorX = 2.5

    resultado = 0

    Para i = 0 hasta longitud de x - 1

        termino = y[i]

        Para j = 0 hasta longitud de x - 1

            Si i ≠ j Entonces

                termino =
                termino * (valorX - x[j]) /
                (x[i] - x[j])

            Fin Si

        Fin Para

        resultado = resultado + termino

    Fin Para

    Mostrar "Valor interpolado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3>

```java
public class InterpolacionLagrange {

    public static double lagrange(
            double[] x,
            double[] y,
            double valorX) {

        double resultado = 0;

        for(int i = 0; i < x.length; i++) {

            double termino = y[i];

            for(int j = 0; j < x.length; j++) {

                if(i != j) {

                    termino *= (valorX - x[j]) /
                               (x[i] - x[j]);
                }
            }

            resultado += termino;
        }

        return resultado;
    }

    public static void main(String[] args) {

        double[] x = {1, 2, 3};
        double[] y = {1, 4, 9};

        double valorX = 2.5;

        double resultado = lagrange(x, y, valorX);

        System.out.println("Valor interpolado: " + resultado);
    }
}
```
<h3>Compilación del codigo</h3>
<img width="346" height="117" alt="Captura de pantalla 2026-05-27 195615" src="https://github.com/user-attachments/assets/59783608-6326-41f0-8db4-78243e946b18" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>

<h2 id="newton" align="center">
4. Interpolación de Newton
</h2>

<h3>¿Qué es?</h3>

<p>
La interpolación de Newton es un método numérico utilizado para construir un polinomio que pase por un conjunto de puntos conocidos. Este método utiliza diferencias divididas para generar el polinomio interpolador de manera eficiente.
</p>

<p>
A diferencia de otros métodos de interpolación, la interpolación de Newton facilita agregar nuevos puntos sin necesidad de recalcular completamente el polinomio.
</p>

<p>
Es ampliamente utilizada en análisis numérico debido a su eficiencia y facilidad de implementación computacional.
</p>

<hr>

<h3>Fórmulas</h3>

<h4>Polinomio de Newton</h4>

<pre>
P(x) = f(x0)
+ (x - x0)f[x0,x1]
+ (x - x0)(x - x1)f[x0,x1,x2]
+ ...
</pre>

<h4>Diferencia dividida</h4>

<pre>
f[xi,xj] = (f(xj) - f(xi)) / (xj - xi)
</pre>

<h4>Donde:</h4>

<ul>
<li><b>P(x):</b> polinomio interpolador.</li>
<li><b>f[xi,xj]:</b> diferencia dividida.</li>
<li><b>x0, x1, x2:</b> puntos conocidos.</li>
<li><b>x:</b> valor a interpolar.</li>
</ul>

<hr>

<h3>Ventajas</h3>

<ul>
<li>Permite agregar nuevos puntos fácilmente.</li>
<li>Es eficiente computacionalmente.</li>
<li>Reduce cálculos repetitivos.</li>
<li>Ofrece buena precisión en aproximaciones.</li>
<li>Es muy utilizada en programación numérica.</li>
</ul>

<hr>

<h3>Desventajas</h3>

<ul>
<li>Puede presentar errores en muchos puntos.</li>
<li>El polinomio puede crecer demasiado.</li>
<li>Es sensible a errores de redondeo.</li>
<li>Puede generar oscilaciones.</li>
<li>Es más compleja que la interpolación lineal.</li>
</ul>

<hr>

<h3>¿En qué ramas de la ingeniería se utiliza?</h3>

<ul>

<li>
<b>Ingeniería en Sistemas Computacionales:</b>
Simulación numérica y desarrollo de software científico.
</li>

<li>
<b>Ingeniería Civil:</b>
Análisis de datos estructurales y topográficos.
</li>

<li>
<b>Ingeniería Mecánica:</b>
Modelado de sistemas físicos y trayectorias.
</li>

<li>
<b>Ingeniería Electrónica:</b>
Procesamiento digital de señales.
</li>

<li>
<b>Ingeniería Industrial:</b>
Análisis matemático y optimización de procesos.
</li>

</ul>

<hr>
<h3>Pseudocódigo</h3>

<pre>
Inicio

    Definir x = {1, 2, 3}
    Definir y = {1, 4, 9}

    Definir valorX = 2.5

    n = longitud de x

    Definir matriz diferencias[n][n]

    Para i = 0 hasta n - 1

        diferencias[i][0] = y[i]

    Fin Para

    Para j = 1 hasta n - 1

        Para i = 0 hasta n - j - 1

            diferencias[i][j] =
            (diferencias[i + 1][j - 1] -
             diferencias[i][j - 1]) /
            (x[i + j] - x[i])

        Fin Para

    Fin Para

    resultado = diferencias[0][0]

    Para i = 1 hasta n - 1

        termino = diferencias[0][i]

        Para j = 0 hasta i - 1

            termino =
            termino * (valorX - x[j])

        Fin Para

        resultado = resultado + termino

    Fin Para

    Mostrar "Valor interpolado: "
    + resultado

Fin
</pre>
<h3>Ejemplo en Java</h3><img width="332" height="87" alt="Captura de pantalla 2026-05-27 200125" src="https://github.com/user-attachments/assets/6fa83102-7d20-4cdb-baf5-dc4df945add0" />


```java
public class InterpolacionNewton {

    public static double calcularNewton(
            double[] x,
            double[] y,
            double valorX) {

        int n = x.length;

        double[][] diferencias = new double[n][n];

        for(int i = 0; i < n; i++) {
            diferencias[i][0] = y[i];
        }

        for(int j = 1; j < n; j++) {

            for(int i = 0; i < n - j; i++) {

                diferencias[i][j] =
                    (diferencias[i + 1][j - 1] -
                     diferencias[i][j - 1]) /
                    (x[i + j] - x[i]);
            }
        }

        double resultado = diferencias[0][0];

        for(int i = 1; i < n; i++) {

            double termino = diferencias[0][i];

            for(int j = 0; j < i; j++) {
                termino *= (valorX - x[j]);
            }

            resultado += termino;
        }

        return resultado;
    }

    public static void main(String[] args) {

        double[] x = {1, 2, 3};
        double[] y = {1, 4, 9};

        double valorX = 2.5;

        double resultado =
            calcularNewton(x, y, valorX);

        System.out.println(
            "Valor interpolado: " + resultado);
    }
}
```
<h3>Compilación de codigo</h3>
<img width="332" height="87" alt="Captura de pantalla 2026-05-27 200125" src="https://github.com/user-attachments/assets/3d585d28-75a8-4bf8-9146-4da1529e702b" />


<p align="right">
<a href="#indice">⬆ Volver al índice</a>
</p>
<hr>
