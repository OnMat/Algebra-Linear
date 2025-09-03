---
title: Resolução de sistemas lineares por Quadrados Mínimos (e Pseudoinversa)
---

### O Problema de Quadrados Mínimos

Suponha que na modelagem de um determinado problema chegue-se ao seguinte sistema linear, o qual deseja-se determinar as incógnitas $x$ e $y$:

$$
\begin{cases}
x+2y=1 \\
3x+4y=0 \\
5x+6y=0
\end{cases}
$$

Esse sistema pode ser reescrito na forma matricial como

$$
\begin{bmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}
\label{eq:sistema-exemplo}
$$

Claramente, o sistema não possui solução exata única (a matriz não é sequer quadrada, menos ainda invertível). Analisando do ponto de vista de transformações lineares, sabemos que o sistema será **possível e indeterminado** se $(1,0,0)\in [(1,3,5),(2,4,6)]$. No entanto, 

$$
\begin{vmatrix}
1 & 2 & 1 \\
3 & 4 & 0 \\
5 & 6 & 0
\end{vmatrix}=-2\neq 0
$$

Logo, os 3 vetores são linearmente independentes e o sistema é **impossível**, pois não existem vetores $v$ em $\mathbb{R}^{2}$ tais que $Av=(1,0,0)$, onde $A$ é a matriz associada ao sistema.

Supondo que a modelagem foi feita corretamente (sistemas como esses são perfeitamente possíveis e comuns em problemas reais, principalmente quando se tem mais dados observados que incógnitas a serem determinadas), uma solução **aproximada** seria determinar o vetor pertencente ao espaço gerado pelas colunas de $A$ (nesse caso, uma combinação linear entre os vetores $(1,3,5)$ e $(2,4,6)$) que está "mais próximo" do vetor $(1,0,0)$. Isto é, utilizando a norma vetorial, queremos determinar $\bar{x}\in \mathbb{R}^{2}$ que minimize $\lVert b - A\bar{x} \rVert$ ($b=(1,0,0)$).

Considere, então, o caso geral $Ax=b$ (com $A\in \mathbb{R}^{m\times n}$). O que procuramos é:

$$
\bar{x}\in \mathbb{R}^{n},\text{ onde }\lVert b - A\bar{x} \rVert =\min_{x \in \mathbb{R}^{n}}\lVert b - Ax \rVert 
$$

Pensando geometricamente, ${} \lVert b-Ax \rVert {}$ corresponde à distância do ponto $b\in \mathbb{R}^{m}$ até o subespaço de $\mathbb{R}^{m}$ gerado pelas colunas de $A$, logo, a menor distância será aquela **ortogonal ao subespaço**. Isso significa que o vetor $\bar{x}\in \mathbb{R}^{n}$ procurado é tal que o vetor $(b-A\bar{x})\in \mathbb{R}^{m}$ é ortogonal ao espaço coluna de $A$ e, em particular, é ortogonal a cada vetor coluna de $A$. 

Portanto, sejam $a_{1},\dots,a_{n}$ as respectivas colunas de $A$, temos:
 
$$
\begin{align}
\langle a_{1} , (b-A\bar{x}) \rangle  =a_{1}^T(b-A\bar{x}) & =0 \\
 a_{2}^T(b-A\bar{x}) & =0 \\
  \vdots \\
a_{n}^T(b-A\bar{x}) & =0  
\end{align}
$$

Utilizando a notação matricial, isso é equivalente a:

$$
\begin{bmatrix}
a_{1}^T \\
\vdots \\
a_{n}^T
\end{bmatrix}\begin{bmatrix}
 \\
b-A\bar{x} \\
\;
\end{bmatrix}=0
$$

O que por sua vez nos dá $A^{T}(b-A\bar{x})=0$. Essa equação, comumente escrita como $\boxed{A^{T}A\bar{x}=A^{T}b}$, é chamada de *equação normal* e é a base para a solução do problema $Ax=b$ através da abordagem desenvolvida até aqui, denominada de *Método dos Quadrados Mínimos* (o nome vem da análise do problema do ponto de vista do Cálculo, que procura **minimizar o erro quadrático** $\lVert b-A\bar{x} \rVert^{2}$, resultando na mesma equação normal). 

### Soluções da Equação Normal

Consideremos primeiramente o caso mais simples, quando $A\in \mathbb{R}^{m\times n}$, com $m\geq n$, possui posto completo (ou seja, $n$). Pelo [](#pre-teorema-valores-singulares) e a equivalência entre transformações lineares e matrizes, sabemos que o posto de $A^{T}A$, que é $n \times n$, também será $n$. Logo, $A^{T}A$ é invertível e podemos resolver $A^{T}A\bar{x}=A^{T}b$ por:

$$
\bar{x}=(A^{T}A)^{-1}A^{T}b
$$

Apesar de podermos determinar $\bar{x}$ exatamente nesse caso, é importante destacar que ele corresponde à solução da equação normal $A^{T}A\bar{x}=A^{T}b$, e não ao problema original $Ax=b$ que, como vimos, pode nem mesmo possuir soluções. Esse é o caso do sistema linear {eq}`eq:sistema-exemplo`, uma vez que tal $A$ possui 3 linhas e 2 colunas ($m > n$) e posto completo ($\min\{ 3,2 \}=2$), mas o sistema é impossível.

Quando, no entanto, $A$ é quadrada e invertível, a solução da equação normal coincide exatamente com a solução do sistema original, pois:

$$
\bar{x}=(A^{T}A)^{-1}A^{T}b=A^{-1}(A^{T})^{-1}A^{T}b=A^{-1}b=x
$$

O mesmo acontece quando $Ax=b$ é **possível e indeterminado**. Nesse caso, $A^{T}A$ não será invertível e as infinitas soluções de $A^{T}A\bar{x}=A^{T}b$ irão coincidir com as de $Ax=b$. 

Uma vez que $Ax=b$ é um sistema impossível, as soluções (ou a solução única, no caso $m \geq n$ e posto completo) de $A^{T}A\bar{x}=A^{T}b$ são **soluções aproximadas** de $Ax=b$, com base no critério de minimizar $\lVert b - A\bar{x} \rVert$.

### Caso geral e pseudoinversa

A decomposição SVD de $A$ nos permite construir um método de resolver $A^{T}Ax=A^{T}b$ no caso geral, que independe da quantidade de linhas e colunas, assim como do posto de $A$. 

...
