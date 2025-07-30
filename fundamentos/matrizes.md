---
title: Matrizes
subject: Fundamentos
---

O tópico seguinte a este é um ponto extremamente importante no estudo da Álgebra Linear, pois mostra como matrizes e transformações lineares estão intimamente relacionadas. Mas antes, devemos definir e relembrar alguns fatos acerca de matrizes.

:::{prf:definition} Matriz

Uma matriz de dimensão $m\times n$ (lê-se $m$ por $n$), com $m$ e $n$ inteiros positivos, é o conjunto de *entradas* $a_{ij}\in \mathbb{R}$, onde $i=1,\dots,m$ e $j=1,\dots,n$. 

Matrizes são representadas dispondo as entradas em $m$ linhas e $n$ colunas, onde cada entrada $a_{ij}$ está localizada na $i$-ésima linha e $j$-ésima coluna:

$$
\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2n} \\
\vdots   & \vdots & \vdots  & \vdots\\ 
a_{m1} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

:::

O conjunto das matrizes com entradas reais e dimensão $m\times n$ é representado por ${} \mathcal{M}_{m\times n}(\mathbb{R}) {}$.

Naturalmente, dizemos que duas matrizes são iguais quando possuem mesma dimensão e entradas iguais. Formalmente:

:::{prf:definition} Igualdade de matrizes

Sejam $A\in \mathcal{M}_{m\times n}(\mathbb{R})$ e $B\in \mathcal{M}_{m\times n}(\mathbb{R})$, com respectivas entradas $a_{ij}$ e $b_{ij}$ ($i=1,\dots,m$ e $j=1,\dots,n$), temos que $A=B$ quando $a_{ij}=b_{ij}$ para todo $i=1,\dots,m$ e $j=1,\dots,n$.

::: 

O conjunto ${} \mathcal{M}_{m\times n}(\mathbb{R}) {}$ constitui, também, um espaço vetorial. Mas, para isso, devemos definir as operações de soma e multiplicação por escalar para matrizes.

### Operações matriciais

:::{prf:definition} Soma de matrizes

Sejam $A$ e $B$ matrizes em $\mathcal{M}_{m\times n}(\mathbb{R})$, com respectivas entradas $a_{ij}$ e $b_{ij}$ ($i=1,\dots,m$ e $j=1,\dots,n$), a *soma matricial* de $A$ e $B$ é dada pela matriz $C$ ($C=A+B$), onde $C\in \mathcal{M}_{m\times n}(\mathbb{R})$ e sua entrada da $i$-ésima linha e $j$-ésima coluna é dada por $c_{ij}=a_{ij}+b_{ij}$ .

:::

Por exemplo, 

$$
\begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix} + \begin{pmatrix}
5 & 6  \\
7 & 8
\end{pmatrix}=\begin{pmatrix}
1+5 & 2+6 \\
3+7 & 4+8
\end{pmatrix}=\begin{pmatrix}
6 & 8 \\
10 & 12
\end{pmatrix}
$$

Observe que a adição só está definida para matrizes que possuem mesma dimensão.

:::{prf:definition} Multiplicação de matriz por escalar

Seja $k\in \mathbb{R}$ e $A\in \mathcal{M}_{m\times n}(\mathbb{R})$, com entradas $a_{ij}$, o produto de $A$ pelo escalar $k$ é dado pela matriz $kA\in \mathcal{M}_{m\times n}(\mathbb{R})$, que possui a entrada da $i$-ésima linha e $j$-ésima coluna dada por $k\cdot a_{ij}$.

:::

Naturalmente,

$$
2\cdot \begin{pmatrix}
1 & 2 \\
3 & 4
\end{pmatrix}=\begin{pmatrix}
2\cdot1 & 2\cdot2 \\
2\cdot 3 & 2 \cdot 4
\end{pmatrix}=\begin{pmatrix}
2 & 4 \\
6 & 8
\end{pmatrix}
$$

Com estas duas operações, verifica-se facilmente que $\mathcal{M}_{m\times n}(\mathbb{R})$ é um espaço vetorial.

Por fim, temos o *produto matricial*. Essa operação cumpre um papel central no [tópico seguinte](transformacoes-e-matrizes.md).

:::{prf:definition} Produto de matrizes

Seja $A\in \mathcal{M}_{m\times n}(\mathbb{R})$ e $B\in \mathcal{M}_{n\times p}(\mathbb{R})$, com respectivas entradas $a_{ij}$ e $b_{ij}$, o produto $AB$ é dado pela matriz $C\in \mathcal{M}_{m\times p}(\mathbb{R})$, de forma que sua entrada da linha $i$ e coluna $j$ é dada por

$$
c_{ij}=\sum_{k=1}^{n}a_{ik}\cdot b_{kj}
$$

:::

Primeiramente, note que o produto $AB$ só está definido se o número de colunas da matriz $A$ for igual ao número de linhas da matriz $B$, e que a matriz resultante terá o número de linhas de $A$ e o número de colunas de $B$. Como exemplo,

$$
\underbrace{ \begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6
\end{pmatrix} }_{ 2\times3 }\cdot \underbrace{ \begin{pmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{pmatrix} }_{ 3\times2 }=\begin{pmatrix}
1\cdot1+2\cdot3+3\cdot 5 & 1\cdot 2+2\cdot 4+3\cdot 6 \\
4\cdot 1+5\cdot 3+6\cdot 5 & 4\cdot 2+5\cdot 4+6\cdot 6
\end{pmatrix}=\underbrace{ \begin{pmatrix}
22 & 28 \\
49 & 64
\end{pmatrix} }_{ 2\times2 }
$$

Além disso, verificam-se algumas propriedades importantes (considere que todos os produtos abaixo são bem definidos):

1. Não necessariamente $AB=BA$ ;
2. Vale a associatividade: $(AB)C=A(BC)$ ;
3. Vale a distributividade em relação à adição: $A(B+C)=AB+AC$ e $(A+B)C=AC+BC$ ;
4. Vale a multiplicação por escalar: $k(AB)=(kA)B=A(kB)$.


### Outros conceitos importantes

:::{prf:definition} Matriz transposta

A transposta de uma matriz $A$, denotada por $A^{T}$ é a matriz obtida ao trocarem-se as suas linhas pelas colunas (ou vice-versa). Isto é, para cada entrada $a_{ij}$ de $A$, $a_{ij}=a_{ji}$ em $A^{T}$.

:::

Seja $A=\begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}$, então $A^{T}=\begin{pmatrix}1 & 4 \\ 2 & 5 \\ 3 & 6\end{pmatrix}$.

Note que se $A$ tem dimensão $m\times n$, então $A^{T}$ tem dimensão $n\times m$.

#### Matrizes quadradas

:::{prf:definition} Matriz quadrada

Matrizes que possuem o mesmo número de linhas e colunas são denominadas *quadradas*.

:::

Por exemplo, a matriz $\begin{pmatrix}1 & 2 \\ 3 & 4\end{pmatrix}$ é quadrada (2 linhas e 2 colunas).

A notação utilizada para representar o conjunto das matrizes quadradas com entradas reais, $n$ linhas e $n$ colunas é $\mathcal{M}_{n}(\mathbb{R})$. Uma matriz não quadrada é chamada de *retangular*.

Uma característica presente em matrizes quadradas, utilizada em outras definições, é o conceito de *diagonal principal*.

:::{prf:definition} Diagonal principal de uma matriz quadrada

A diagonal principal de uma matriz quadrada é constituída dos elementos $a_{jj}$. Isto é, cujos índices de linha e coluna são iguais.

:::

Visualmente, a diagonal principal constitui as entradas que estão no sentido da esquerda para direita e cima para baixo na matriz.

Por exemplo, a diagonal principal da matriz $\begin{pmatrix}1 & 2 \\ 3 & 4\end{pmatrix}$ é formada pelas entradas $1$ e $4$.

:::{prf:definition} Matriz simétrica
:label: def-matriz-simetrica

Uma matriz quadrada é dita *simétrica* quando é igual a sua transposta. Isto é, seja $A \in \mathcal{M}_{n}(\mathbb{R})$, $A$ é simétrica se, e somente se, $A^{T}=A$.

:::

A matriz $\begin{pmatrix}1 & 2 \\ 2 & 3\end{pmatrix}$ é simétrica.

Note que, visualmente, matrizes simétricas são aquelas cujas entradas acima e abaixo da diagonal principal são "refletidas" em torno dela.

:::{prf:definition} Matriz diagonal
:label: def-matriz-diagonal

Uma matriz quadrada é *diagonal* quando, exceto por entradas em sua diagonal principal, todas as entradas são nulas.

:::

A matriz $\begin{pmatrix}1 & 0 \\ 0 & 2\end{pmatrix}$ é diagonal. 

Note que a definição permite que a diagonal principal possua entradas nulas, apenas não pode haver nenhuma entrada fora da diagonal principal que não seja nula. Toda matriz diagonal também é simétrica.

#### Matrizes especiais

Algumas matrizes aparecerão de maneira recorrente e possuem propriedades particulares.

:::{prf:definition} Matriz identidade

A matriz $I\in \mathcal{M}_{n}(\mathbb{R})$ é chamada de *matriz identidade*, tal que $I$ é uma matriz **diagonal** cujas entradas da diagonal principal são todas iguais a $1$.

:::

No caso da dimensão $2\times2$,

$$
I=\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$

Seja $A\in \mathcal{M}_{m\times n}(\mathbb{R})$, a matriz identidade possui a propriedade que $AI_{n}=I_{m}A=A$ (o subíndice representa a dimensão da matriz identidade), atuando como *elemento neutro do produto matricial*.

:::{prf:definition} Matriz nula

A matriz $\mathbf{0}\in \mathcal{M}_{m\times n}(\mathbb{R})$ é chamada de *matriz nula*, tal que **todas as suas entradas são nulas**.

:::

Na dimensão $2\times2$,

$$
\mathbf{0}=\begin{pmatrix}
0 & 0 \\
0 & 0
\end{pmatrix}
$$

Naturalmente, seja $A\in \mathcal{M}_{m\times n}(\mathbb{R})$, temos que $A+\mathbf{0}_{m\times n}=A$. Logo, a matriz nula atua como *elemento neutro da adição matricial*. Também verifica-se que $\mathbf{0}_{p\times m}\cdot A$ e $A\cdot \mathbf{0}_{n\times p}$ resultarão na matriz nula de dimensão correspondente.

:::{prf:definition} Matriz inversa

Seja $A\in \mathcal{M}_{n}(\mathbb{R})$, a *matriz inversa* de $A$, denotada por $A^{-1}\in \mathcal{M}_{n}(\mathbb{R})$, é a matriz **única** que satisfaz $AA^{-1}=A^{-1}A=I$.

:::

É importante destacar que a inversa de uma matriz quadrada nem sempre existe. Utilizando a definição, podemos verificar a existência e determinar (se existir) a inversa de uma matriz quadrada $A$ da seguinte forma: Supomos que ela existe, onde suas entradas são incógnitas a serem determinadas, e resolvemos o sistema linear associado à $AA^{-1}=I$ (aplicando a definição do produto e a igualdade de matrizes). Se o sistema não possuir solução determinada a inversa não existe. Caso contrário, obtemos as entradas de $A^{-1}$.

Uma ilustração simples desse método é determinar a inversa da matriz identidade. No caso $2\times 2$, temos

$$
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}\begin{pmatrix}
a & b \\
c & d
\end{pmatrix}=\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$

Resolvendo o sistema linear associado encontramos $a=1,b=0,c=0$ e $d=1$. Logo,

$$
\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}^{-1}=\begin{pmatrix}
1 & 0 \\
0 & 1
\end{pmatrix}
$$

(note que $I^{-1}=I$ para qualquer dimensão)

:::{prf:definition} Matriz ortogonal

Seja $A\in \mathcal{M}_{n}(\mathbb{R})$, $A$ é *ortogonal* quando $AA^{T}=A^{T}A=I$. Isto é, $A^{T}=A^{-1}$.

:::

Mais uma vez, a  matriz identidade também recai nessa categoria. Havíamos constatado na definição anterior que a identidade é igual a sua inversa, e por ser diagonal é também simétrica. Logo, ${} I=I^{T}=I^{-1} {}$.

### Determinante

O determinante é uma das principais ferramentas quando lidamos com matrizes quadradas (que cumprem um papel central na Álgebra Linear, veja o tópico de Operadores Lineares), fornecendo informações acerca da matriz, como invertibilidade, além de ser utilizado em aspectos computacionais. Para os propósitos dessa seção, iremos apenas enunciar como calculá-lo para matrizes de dimensões $2\times2$ e $3\times 3$, além de algumas propriedades importantes.

:::{prf:remark} Cálculo do determinante

O determinante é uma função $\det(A):\mathcal{M}_{n}(\mathbb{R})\to \mathbb{R}$ (isto é: dada uma matriz quadrada de entradas reais, retorna um valor real).

Para qualquer matriz ${} A=\begin{pmatrix}a & b \\ c & d\end{pmatrix} {}$ de dimensão $2\times 2$, ele é dado por

$$
\det(A)=\begin{vmatrix}
a & b \\
c & d
\end{vmatrix} = ad-bc
$$

e para qualquer matriz $A=\begin{pmatrix}a & b & c \\ d &e& f \\ g & h & i\end{pmatrix}$ de dimensão $3\times 3$

$$
\det(A)=\begin{vmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{vmatrix}=aei+bfg+cdh-ceg-afh-bdi
$$

(as barras verticais são uma notação comumente utilizada para representar o determinante da matriz com tais entradas).

:::

No caso do determinante de matrizes $3 \times 3$, existem algumas "regras" que auxiliam a calculá-lo, visto que a sua fórmula é bem menos intuitiva (além de ser bem mais longa) que no caso $2 \times 2$. Uma das mais conhecidas é a chamada **Regra de Sarrus**, onde repetimos as duas primeiras colunas no lado direito da matriz:

$$
\begin{array}{ccc|cc}
a & b & c & a & b \\
d & e & f & d & e \\
g & h & i & g & h \\
\end{array}
$$

note, comparando com a fórmula, que o determinante é então dado somando os produtos das entradas nas diagonais da esquerda para direita e subtraindo os produtos das entradas nas diagonais da direta para esquerda.

:::{prf:example} 

Seja a matriz:

$$
B=\begin{pmatrix}
1 & 2 & 3 \\
4 & 5 & 6 \\
7 & 8 & 9
\end{pmatrix}
$$

Aplicando a Regra de Sarrus, escrevemos:

$$
\begin{array}{ccc|cc}
1 & 2 & 3 & 1 & 2 \\
4 & 5 & 6 & 4 & 5 \\
7 & 8 & 9 & 7 & 8
\end{array}
$$

obtendo $\det(B)=(1\cdot5 \cdot 9)+(2 \cdot 6 \cdot 7) + (3 \cdot 4 \cdot 8) - (2 \cdot 4 \cdot 9) - (1 \cdot 6 \cdot 8) - (3 \cdot 5 \cdot 7)=45+84+96-72-48-105=0$.

:::

:::{prf:theorem} Invertibilidade de uma matriz

Seja $A$ uma matriz quadrada, então $A$ é invertível (existe a matriz $A^{-1}$) se, e somente se, $\det(A)\neq 0$.

:::

Essa relação entre a invertibilidade de uma matriz e seu determinante ser não nulo fica mais clara quando vemos que uma divisão pelo determinante aparece nas fórmulas utilizadas para se calcular a inversa. A justificativa teórica, no entanto, requer uma fundamentação acerca de *formas multilineares alternadas*, um tópico mais avançado da Álgebra Linear (contudo, parte dessa justificativa pode ser entendida ao se estudar as condições para que um operador linear seja invertível e a relação do determinante com o núcleo de um operador linear, veja o tópico de Operadores Lineares).

Por fim, algumas outras propriedades:

:::{prf:property}

Seja $k\in \mathbb{R}$ e $A$ uma matriz quadrada,

$$
\det(kA)=k\det(A)
$$

:::

:::{prf:property}

Sejam $A$ e $B$ duas matrizes quadradas de mesma ordem,

$$
\det(AB)=\det(A)\det(B)
$$

:::

:::{prf:property}

Seja $A$ uma matriz quadrada, 

$$
\det(A^{T})=\det(A)
$$

:::

:::{prf:property}

Seja $A$ uma matriz quadrada invertível,

$$
\det(A^{-1})=\frac{1}{\det(A)}
$$

:::
