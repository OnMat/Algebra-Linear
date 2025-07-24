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

Verificaremos que esse conjunto constitui um espaço vetorial, mas para isso devemos definir as operações de soma e multiplicação por escalar para matrizes.

### Operações matriciais

...

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

A notação utilizada para representar uma matriz quadrada $A$ de entradas reais com $n$ linhas e $n$ colunas é $A\in \mathcal{M}_{n}(\mathbb{R})$.

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

A matriz identidade é diagonal, além de ser simétrica. No caso de dimensão $2\times2$, $I=\begin{pmatrix}1&0 \\0 & 1\end{pmatrix}=I^{T}$.

Note que a definição permite que a diagonal principal possua entradas nulas, apenas não pode haver nenhuma entrada fora da diagonal principal que não seja nula. Neste sentido, a matriz nula é um caso particular de matriz diagonal (em que todas as entradas da diagonal principal são nulas), mas na prática não a consideramos dessa forma.
