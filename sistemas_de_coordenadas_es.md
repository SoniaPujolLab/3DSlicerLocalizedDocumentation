# Sistemas de coordenadas

## Introducción

Uno de los problemas al trabajar con imágenes médicas y aplicaciones son las diferencias entre los sistemas de coordenadas. Hay tres sistemas de coordenadas que se usan comúnmente en las aplicaciones de imagen: se puede distinguir entre el sistema de coordenadas del **mundo**, el **anatómico** y el **de la imagen**.

La siguiente figura ilustra los tres espacios y sus ejes correspondientes:

[![coordinate_systems](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems.png)

Cada sistema de coordenadas cumple un propósito y representa sus datos de una manera particular.

Imagen anatómica basada en una [imagen compartida por la organización My MS](https://my-ms.org/mri_planes.htm).

Tenga en cuenta que Chand John, de Stanford, creó una [presentación detallada sobre la forma en que se manejan las coordenadas en Slicer](https://www.na-mic.org/w/img_auth.php/3/3f/Coordinate_Systems_Demystified.ppt).

### Sistema de coordenadas del mundo

El sistema de coordenadas del mundo es normalmente un sistema de coordenadas cartesiano en el que se posiciona un modelo (por ejemplo, un escáner de RM o un paciente). Cada modelo tiene su propio sistema de coordenadas, pero solo hay un sistema de coordenadas del mundo para definir la posición y la orientación de cada modelo.

### Sistema de coordenadas anatómico

El sistema de coordenadas de modelo más importante para las técnicas de imagen médica es el espacio anatómico (también llamado sistema de coordenadas del paciente). Este espacio consta de tres planos para describir la posición anatómica estándar de un ser humano:

- el *plano axial* es paralelo al suelo y separa la cabeza (Superior) de los pies (Inferior).

- el *plano coronal* es perpendicular al suelo y separa el frente (Anterior) de la parte posterior (Posterior).

- el *plano sagital* es perpendicular al suelo y separa la izquierda (Left) de la derecha (Right).

De estos planos se deduce que todos los ejes tienen su notación en una dirección positiva (por ejemplo, el eje Superior negativo está representado por el eje Inferior).

El sistema de coordenadas anatómico es un espacio tridimensional continuo en el que se ha muestreado una imagen. En neuroimagen, es común definir este espacio con respecto al ser humano cuyo cerebro se está escaneando. Por lo tanto, la base 3D se define a lo largo de los ejes anatómicos anterior-posterior, inferior-superior e izquierda-derecha.

Sin embargo, distintas aplicaciones médicas usan distintas definiciones de esta base 3D. Las más comunes son las siguientes bases:

- LPS (Left, Posterior, Superior; izquierda, posterior, superior) se usa en las imágenes DICOM

\[\begin{split}
LPS = \begin{Bmatrix}
\text{de la derecha hacia la izquierda} \\
\text{de anterior hacia posterior} \\
\text{de inferior hacia superior}
\end{Bmatrix}
\end{split}\]

- RAS (Right, Anterior, Superior; derecha, anterior, superior) es similar a LPS con los dos primeros ejes invertidos

\[\begin{split}
RAS = \begin{Bmatrix}
\text{de la izquierda hacia la derecha} \\
\text{de posterior hacia anterior} \\
\text{de inferior hacia superior}
\end{Bmatrix}
\end{split}\]

Por lo tanto, la única diferencia entre las dos convenciones es que el signo de las dos primeras coordenadas está invertido.

Ambas bases son igual de útiles y lógicas. Solo es necesario saber a qué base está referenciada una imagen.

### Sistema de coordenadas de la imagen

El sistema de coordenadas de la imagen describe cómo se adquirió una imagen con respecto a la anatomía. Los escáneres médicos crean matrices regulares y rectangulares de puntos y celdas que comienzan en la esquina superior izquierda. El eje \(i\) aumenta hacia la derecha, el eje \(j\) hacia abajo y el eje \(k\) hacia atrás.

Además del valor de intensidad de cada vóxel \((i j k)\), también se almacenan el origen y el espaciado de las coordenadas anatómicas.

- El origen representa la posición del primer vóxel (0, 0, 0) en el sistema de coordenadas anatómico, por ejemplo (100, 50, -25) mm.

- El espaciado especifica la distancia entre vóxeles a lo largo de cada eje, por ejemplo (1.5, 0.5, 0.5) mm.

El siguiente ejemplo 2D muestra el significado del origen y el espaciado:

[![image_coordinates](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_image_coordinates.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_image_coordinates.png)

Usando el origen y el espaciado, puede calcularse la posición correspondiente de cada vóxel (en coordenadas de imagen) en coordenadas anatómicas.

## Transformación de la imagen

La transformación de un vector del espacio de imagen \((i j k)'\) a un vector del espacio anatómico \(\vec{x}\) es una transformación afín, que consiste en una transformación lineal \(\mathbf{A}\) seguida de una traslación \(\vec{t}\).

\[
\vec{x} = A \begin{pmatrix} i & j & k \end{pmatrix}' + \vec{t}
\]

La matriz de transformación \(\mathbf{A}\) es una matriz de \(3 \times 3\) y contiene toda la información sobre las direcciones del espacio y el escalado de los ejes.

\(\vec{t}\) es un vector de \(3 \times 1\) y contiene información sobre la posición geométrica del primer vóxel.

\[\begin{split}
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & A_{13} \\ A_{21} & A_{22} & A_{23} \\ A_{31} & A_{32} & A_{33} \end{pmatrix}
\begin{pmatrix} i \\ j \\ k \end{pmatrix} + \begin{pmatrix} t_1 \\ t_2 \\ t_3 \end{pmatrix}
\end{split}\]

La última ecuación muestra que la transformación lineal se realiza mediante una multiplicación de matrices y la traslación mediante una suma de vectores. Para representar ambas, la transformación y la traslación, mediante una multiplicación de matrices, debe usarse una matriz aumentada. Esta técnica requiere que la matriz \(\mathbf{A}\) se aumente con una fila adicional de ceros en la parte inferior, una columna adicional —el vector de traslación— a la derecha, y un \(1\) en la esquina inferior derecha. Además, todos los vectores deben escribirse como coordenadas homogéneas, lo que significa que se les agrega un \(1\) al final.

\[\begin{split}
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \\ 1 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & A_{13} & t_1 \\ A_{21} & A_{22} & A_{23} & t_2 \\
 A_{31} & A_{32} & A_{33} & t_3 \\ 0 & 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} i \\ j \\ k \\ 1 \end{pmatrix}
\end{split}\]

Dependiendo del espacio anatómico usado (LPS o RAS), la matriz de \(4 \times 4\) se llama matriz **IJKtoLPS** o **IJKtoRAS**, porque representa la transformación de IJK a LPS o RAS.

## Ejemplo 2D o cálculo de una matriz *IJtoLS*

La siguiente figura muestra el espacio anatómico con una base L(P)S a la izquierda y las coordenadas de imagen correspondientes a la derecha.

[![IJtoLS](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoLS.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoLS.png)

El origen (las coordenadas del primer píxel en el espacio anatómico) es (50, 300) mm y el espaciado (la distancia entre dos píxeles) es (50, 50) mm.

Como este es un ejemplo 2D, \(\mathbf{A}\) es una matriz de \(2 \times 2\) y \(\vec{t}\) un vector de \(2 \times 1\). Por lo tanto, la ecuación de la transformación afín es:

\[\begin{split}
\begin{pmatrix} L \\ S \\ 1 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & t_1 \\ A_{21} & A_{22} & t_2 \\ 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} i \\ j \\ 1 \end{pmatrix}
\end{split}\]

Al multiplicar la matriz **IJtoLS** y el vector del lado derecho, se obtendrá el siguiente producto:

![matrix_multiplication](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_matrix_multiplication.png)

La última ecuación y el producto de matrices muestran que deben determinarse un total de 6 variables desconocidas \((A_{11}, A_{12}, A_{21}, A_{22}, t_1, t_2)\). El conocimiento del origen y el espaciado, sin embargo, permite las siguientes relaciones entre el espacio de imagen y el espacio anatómico:

\[\begin{split}
\begin{pmatrix} L \\ S \end{pmatrix} \equiv \begin{pmatrix} i \\ j \end{pmatrix} \qquad
\begin{pmatrix} 50 \\ 300 \end{pmatrix} \equiv \begin{pmatrix} 0 \\ 0 \end{pmatrix} \qquad
\begin{pmatrix} 100 \\ 300 \end{pmatrix} \equiv \begin{pmatrix} 1 \\ 0 \end{pmatrix} \qquad
\begin{pmatrix} 50 \\ 250 \end{pmatrix} \equiv \begin{pmatrix} 0 \\ 1 \end{pmatrix} \qquad \dots
\end{split}\]

Así, pueden derivarse al menos seis ecuaciones:

\[\begin{split}
\begin{align*}
50 &= A_{11} \cdot 0 + A_{12} \cdot 0 + t_1 \cdot 1 \\
300 &= A_{21} \cdot 0 + A_{22} \cdot 0 + t_2 \cdot 1 \\
100 &= A_{11} \cdot 1 + A_{12} \cdot 0 + t_1 \cdot 1 \\
300 &= A_{21} \cdot 1 + A_{22} \cdot 0 + t_2 \cdot 1 \\
50 &= A_{11} \cdot 0 + A_{12} \cdot 1 + t_1 \cdot 1 \\
250 &= A_{21} \cdot 0 + A_{22} \cdot 1 + t_2 \cdot 1
\end{align*}
\end{split}\]

Como se mencionó anteriormente, la traslación \(\vec{t}\) contiene la información sobre la posición geométrica del primer píxel y, por lo tanto, es equivalente al origen. Este resultado también se confirma con las primeras ecuaciones.

La solución de las demás ecuaciones conduce a la siguiente matriz **IJtoLS**:

\[\begin{split}
IJtoLS = \begin{pmatrix} 50 & 0 & 50 \\ 0 & -50 & 300 \\ 0 & 0 & 1 \end{pmatrix}
\end{split}\]

En el caso de que se usara una base R(A)S, simplemente se invierten los ejes izquierdo y anterior del espacio anatómico, y el sistema de coordenadas de la imagen aparece de la misma manera que en el caso L(P)S.

[![IJtoRS](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoRS.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoRS.png)

Para este ejemplo 2D, la matriz **IJtoRS** sería:

\[\begin{split}
IJtoRS = \begin{pmatrix} -50 & 0 & 250 \\ 0 & -50 & 300 \\ 0 & 0 & 1 \end{pmatrix}
\end{split}\]

Esta matriz se parece mucho a la matriz **IJtoLS**, con 2 diferencias:

- La traslación \(\vec{t}\) ha cambiado debido a un origen diferente.

- El eje derecho está invertido, por lo que la primera columna de la matriz **IJtoRS** simplemente tiene el signo invertido.

## Convención de sistema de coordenadas en Slicer

DICOM y la mayoría del software de imagen médica usan el **sistema de coordenadas LPS** para almacenar todos los datos. La elección del origen es arbitraria porque solo tienen significado las diferencias relativas, por lo que no existe un estándar universal, pero a menudo se establece en algún centro geométrico del sistema de imagen, o se elige cerca del centro de un objeto de interés.

Tanto LPS como RAS eran de uso amplio a principios de la década de 2000, cuando comenzó el desarrollo de Slicer, y los desarrolladores de Slicer optaron por usar el sistema de coordenadas RAS. Históricamente, los escaneos realizados con equipos de GE usaban RAS, mientras que Siemens y otros usaban LPS. Dado que varios investigadores de GE fueron de los primeros colaboradores de Slicer, se adoptó RAS para la representación interna.

Slicer todavía **usa el sistema de coordenadas RAS para almacenar internamente los valores de coordenadas** de todos los tipos de datos, pero, por compatibilidad con otro software, **asume que todos los datos de los archivos están almacenados en el sistema de coordenadas LPS** (a menos que en el archivo se indique explícitamente que el sistema de coordenadas es RAS). Para lograrlo, siempre que Slicer lee o escribe un archivo, puede necesitar invertir el signo de los dos primeros ejes de coordenadas para convertir los datos al sistema de coordenadas RAS.

### Relaciones con otro software/convenciones

#### ITK

[ITK](https://itk.org/) usa la convención LPS.

#### Usar MATLAB para mapear coordenadas RAS de Slicer (por ejemplo, marcadores fiduciales) al espacio de vóxeles de una imagen NIfTI

Para extraer la matriz de transformación "voxel a mundo" del encabezado de un archivo NIfTI (entrada: `qto_xyz:1-4`) en MATLAB:

```
d = inv(M) * [ R A S 1 ]'

```

donde `M` es la matriz y `R A S` son coordenadas en Slicer, entonces `d` da un vector de coordenadas de vóxel.

(Solución cortesía de András Jakab, Universidad de Debrecen)

## Referencias

- <https://people.cs.uchicago.edu/~glk/unlinked/nrrd-iomf.pdf>

- <http://www.grahamwideman.com/gw/brain/orientation/orientterms.htm>

- <https://nifti.nimh.nih.gov/nifti-1/documentation/faq>

- <https://teem.sourceforge.net/nrrd/format.html>

- [DICOM 2013 PS3.3 Image Position and Image Orientation](https://dicom.nema.org/dicom/2013/output/chtml/part03/sect_C.7.html#sect_C.7.6.2.1.1)
