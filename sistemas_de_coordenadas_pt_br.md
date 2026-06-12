# Sistemas de coordenadas

## Introdução

Um dos problemas ao lidar com imagens médicas e aplicativos são as diferenças entre os sistemas de coordenadas. Há três sistemas de coordenadas comumente usados em aplicativos de imagem: pode-se distinguir entre o sistema de coordenadas do **mundo**, o **anatômico** e o **da imagem**.

A figura a seguir ilustra os três espaços e seus eixos correspondentes:

[![coordinate_systems](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems.png)

Cada sistema de coordenadas cumpre um propósito e representa seus dados de uma maneira específica.

Imagem anatômica baseada em uma [imagem compartilhada pela organização My MS](https://my-ms.org/mri_planes.htm).

Observe que Chand John, de Stanford, criou uma [apresentação detalhada sobre a forma como as coordenadas são tratadas no Slicer](https://www.na-mic.org/w/img_auth.php/3/3f/Coordinate_Systems_Demystified.ppt).

### Sistema de coordenadas do mundo

O sistema de coordenadas do mundo é normalmente um sistema de coordenadas cartesiano no qual um modelo (por exemplo, um aparelho de RM ou um paciente) é posicionado. Cada modelo tem seu próprio sistema de coordenadas, mas há apenas um sistema de coordenadas do mundo para definir a posição e a orientação de cada modelo.

### Sistema de coordenadas anatômico

O sistema de coordenadas de modelo mais importante para as técnicas de imagem médica é o espaço anatômico (também chamado de sistema de coordenadas do paciente). Esse espaço consiste em três planos para descrever a posição anatômica padrão de um ser humano:

- o *plano axial* é paralelo ao chão e separa a cabeça (Superior) dos pés (Inferior).

- o *plano coronal* é perpendicular ao chão e separa a frente (Anterior) das costas (Posterior).

- o *plano sagital* é perpendicular ao chão e separa a esquerda (Left) da direita (Right).

Desses planos, conclui-se que todos os eixos têm sua notação em uma direção positiva (por exemplo, o eixo Superior negativo é representado pelo eixo Inferior).

O sistema de coordenadas anatômico é um espaço tridimensional contínuo no qual uma imagem foi amostrada. Em neuroimagem, é comum definir esse espaço em relação ao ser humano cujo cérebro está sendo escaneado. Assim, a base 3D é definida ao longo dos eixos anatômicos anterior-posterior, inferior-superior e esquerda-direita.

No entanto, diferentes aplicativos médicos usam diferentes definições dessa base 3D. As mais comuns são as seguintes bases:

- LPS (Left, Posterior, Superior; esquerda, posterior, superior) é usada nas imagens DICOM

\[\begin{split}
LPS = \begin{Bmatrix}
\text{da direita para a esquerda} \\
\text{de anterior para posterior} \\
\text{de inferior para superior}
\end{Bmatrix}
\end{split}\]

- RAS (Right, Anterior, Superior; direita, anterior, superior) é semelhante à LPS com os dois primeiros eixos invertidos

\[\begin{split}
RAS = \begin{Bmatrix}
\text{da esquerda para a direita} \\
\text{de posterior para anterior} \\
\text{de inferior para superior}
\end{Bmatrix}
\end{split}\]

Assim, a única diferença entre as duas convenções é que o sinal das duas primeiras coordenadas é invertido.

Ambas as bases são igualmente úteis e lógicas. É necessário apenas saber a qual base uma imagem está referenciada.

### Sistema de coordenadas da imagem

O sistema de coordenadas da imagem descreve como uma imagem foi adquirida em relação à anatomia. Os scanners médicos criam matrizes regulares e retangulares de pontos e células que começam no canto superior esquerdo. O eixo \(i\) aumenta para a direita, o eixo \(j\) para baixo e o eixo \(k\) para trás.

Além do valor de intensidade de cada voxel \((i j k)\), o origem e o espaçamento das coordenadas anatômicas também são armazenados.

- A origem representa a posição do primeiro voxel (0, 0, 0) no sistema de coordenadas anatômico, por exemplo (100, 50, -25) mm.

- O espaçamento especifica a distância entre voxels ao longo de cada eixo, por exemplo (1.5, 0.5, 0.5) mm.

O exemplo 2D a seguir mostra o significado da origem e do espaçamento:

[![image_coordinates](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_image_coordinates.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_image_coordinates.png)

Usando a origem e o espaçamento, pode-se calcular a posição correspondente de cada voxel (em coordenadas de imagem) em coordenadas anatômicas.

## Transformação da imagem

A transformação de um vetor do espaço de imagem \((i j k)'\) para um vetor do espaço anatômico \(\vec{x}\) é uma transformação afim, que consiste em uma transformação linear \(\mathbf{A}\) seguida de uma translação \(\vec{t}\).

\[
\vec{x} = A \begin{pmatrix} i & j & k \end{pmatrix}' + \vec{t}
\]

A matriz de transformação \(\mathbf{A}\) é uma matriz \(3 \times 3\) e contém todas as informações sobre as direções do espaço e o escalonamento dos eixos.

\(\vec{t}\) é um vetor \(3 \times 1\) e contém informações sobre a posição geométrica do primeiro voxel.

\[\begin{split}
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & A_{13} \\ A_{21} & A_{22} & A_{23} \\ A_{31} & A_{32} & A_{33} \end{pmatrix}
\begin{pmatrix} i \\ j \\ k \end{pmatrix} + \begin{pmatrix} t_1 \\ t_2 \\ t_3 \end{pmatrix}
\end{split}\]

A última equação mostra que a transformação linear é realizada por uma multiplicação de matrizes e a translação por uma adição de vetores. Para representar ambas, a transformação e a translação, por uma multiplicação de matrizes, uma matriz aumentada deve ser usada. Essa técnica exige que a matriz \(\mathbf{A}\) seja aumentada com uma linha adicional de zeros na parte inferior, uma coluna adicional — o vetor de translação — à direita, e um \(1\) no canto inferior direito. Além disso, todos os vetores precisam ser escritos como coordenadas homogêneas, o que significa que um \(1\) é acrescentado ao final.

\[\begin{split}
\begin{pmatrix} x_1 \\ x_2 \\ x_3 \\ 1 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & A_{13} & t_1 \\ A_{21} & A_{22} & A_{23} & t_2 \\
 A_{31} & A_{32} & A_{33} & t_3 \\ 0 & 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} i \\ j \\ k \\ 1 \end{pmatrix}
\end{split}\]

Dependendo do espaço anatômico usado (LPS ou RAS), a matriz \(4 \times 4\) é chamada de matriz **IJKtoLPS** ou **IJKtoRAS**, porque representa a transformação de IJK para LPS ou RAS.

## Exemplo 2D ou cálculo de uma matriz *IJtoLS*

A figura a seguir mostra o espaço anatômico com uma base L(P)S à esquerda e as coordenadas de imagem correspondentes à direita.

[![IJtoLS](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoLS.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoLS.png)

A origem (as coordenadas do primeiro pixel no espaço anatômico) é (50, 300) mm e o espaçamento (a distância entre dois pixels) é (50, 50) mm.

Como este é um exemplo 2D, \(\mathbf{A}\) é uma matriz \(2 \times 2\) e \(\vec{t}\) um vetor \(2 \times 1\). Portanto, a equação da transformação afim é:

\[\begin{split}
\begin{pmatrix} L \\ S \\ 1 \end{pmatrix} =
\begin{pmatrix} A_{11} & A_{12} & t_1 \\ A_{21} & A_{22} & t_2 \\ 0 & 0 & 1 \end{pmatrix}
\begin{pmatrix} i \\ j \\ 1 \end{pmatrix}
\end{split}\]

Ao multiplicar a matriz **IJtoLS** e o vetor do lado direito, o seguinte produto será obtido:

![matrix_multiplication](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_matrix_multiplication.png)

A última equação e o produto de matrizes mostram que um total de 6 variáveis desconhecidas \((A_{11}, A_{12}, A_{21}, A_{22}, t_1, t_2)\) precisam ser determinadas. O conhecimento da origem e do espaçamento, no entanto, permite as seguintes relações entre o espaço de imagem e o espaço anatômico:

\[\begin{split}
\begin{pmatrix} L \\ S \end{pmatrix} \equiv \begin{pmatrix} i \\ j \end{pmatrix} \qquad
\begin{pmatrix} 50 \\ 300 \end{pmatrix} \equiv \begin{pmatrix} 0 \\ 0 \end{pmatrix} \qquad
\begin{pmatrix} 100 \\ 300 \end{pmatrix} \equiv \begin{pmatrix} 1 \\ 0 \end{pmatrix} \qquad
\begin{pmatrix} 50 \\ 250 \end{pmatrix} \equiv \begin{pmatrix} 0 \\ 1 \end{pmatrix} \qquad \dots
\end{split}\]

Assim, pelo menos seis equações podem ser derivadas:

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

Como mencionado acima, a translação \(\vec{t}\) contém as informações sobre a posição geométrica do primeiro pixel e, portanto, é equivalente à origem. Esse resultado também é confirmado pelas primeiras equações.

A solução das demais equações leva à seguinte matriz **IJtoLS**:

\[\begin{split}
IJtoLS = \begin{pmatrix} 50 & 0 & 50 \\ 0 & -50 & 300 \\ 0 & 0 & 1 \end{pmatrix}
\end{split}\]

Caso uma base R(A)S fosse usada, apenas os eixos esquerdo e anterior do espaço anatômico são invertidos, e o sistema de coordenadas da imagem aparece da mesma forma que no caso L(P)S.

[![IJtoRS](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoRS.png)](https://github.com/Slicer/Slicer/releases/download/docs-resources/coordinate_systems_IJtoRS.png)

Para este exemplo 2D, a matriz **IJtoRS** seria:

\[\begin{split}
IJtoRS = \begin{pmatrix} -50 & 0 & 250 \\ 0 & -50 & 300 \\ 0 & 0 & 1 \end{pmatrix}
\end{split}\]

Essa matriz é muito parecida com a matriz **IJtoLS**, com 2 diferenças:

- A translação \(\vec{t}\) mudou por causa de uma origem diferente.

- O eixo direito está invertido, portanto a primeira coluna da matriz **IJtoRS** tem apenas o sinal invertido.

## Convenção de sistema de coordenadas no Slicer

O DICOM e a maioria dos softwares de imagem médica usam o **sistema de coordenadas LPS** para armazenar todos os dados. A escolha da origem é arbitrária, pois apenas as diferenças relativas têm significado, portanto não há um padrão universal, mas ela costuma ser definida em algum centro geométrico do sistema de imagem, ou é escolhida próxima ao centro de um objeto de interesse.

Tanto LPS quanto RAS eram amplamente usados no início dos anos 2000, quando o desenvolvimento do Slicer foi iniciado, e os desenvolvedores do Slicer optaram por usar o sistema de coordenadas RAS. Historicamente, as varreduras feitas por equipamentos da GE usavam RAS, enquanto a Siemens e outros usavam LPS. Como vários pesquisadores da GE foram dos primeiros colaboradores do Slicer, o RAS foi adotado para a representação interna.

O Slicer ainda **usa o sistema de coordenadas RAS para armazenar internamente os valores de coordenadas** de todos os tipos de dados, mas, para compatibilidade com outros softwares, ele **assume que todos os dados nos arquivos estão armazenados no sistema de coordenadas LPS** (a menos que o sistema de coordenadas no arquivo seja explicitamente declarado como RAS). Para isso, sempre que o Slicer lê ou grava um arquivo, ele pode precisar inverter o sinal dos dois primeiros eixos de coordenadas para converter os dados para o sistema de coordenadas RAS.

### Relações com outros softwares/convenções

#### ITK

O [ITK](https://itk.org/) usa a convenção LPS.

#### Usar o MATLAB para mapear coordenadas RAS do Slicer (por exemplo, marcadores fiduciais) para o espaço de voxels de uma imagem NIfTI

Para extrair a matriz de transformação "voxel para mundo" do cabeçalho de um arquivo NIfTI (entrada: `qto_xyz:1-4`) no MATLAB:

```
d = inv(M) * [ R A S 1 ]'

```

onde `M` é a matriz e `R A S` são coordenadas no Slicer, então `d` fornece um vetor de coordenadas de voxel.

(Solução cortesia de András Jakab, Universidade de Debrecen)

## Referências

- <https://people.cs.uchicago.edu/~glk/unlinked/nrrd-iomf.pdf>

- <http://www.grahamwideman.com/gw/brain/orientation/orientterms.htm>

- <https://nifti.nimh.nih.gov/nifti-1/documentation/faq>

- <https://teem.sourceforge.net/nrrd/format.html>

- [DICOM 2013 PS3.3 Image Position and Image Orientation](https://dicom.nema.org/dicom/2013/output/chtml/part03/sect_C.7.html#sect_C.7.6.2.1.1)
