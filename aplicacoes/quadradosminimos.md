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
$$ (sistema-exemplo)

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

Apesar de podermos determinar $\bar{x}$ exatamente nesse caso, é importante destacar que ele corresponde à solução da equação normal $A^{T}A\bar{x}=A^{T}b$, e não ao problema original $Ax=b$ que, como vimos, pode nem mesmo possuir soluções. Esse é o caso do sistema linear {eq}`sistema-exemplo`, uma vez que tal $A$ possui 3 linhas e 2 colunas ($m > n$) e posto completo ($\min\{ 3,2 \}=2$), mas o sistema é impossível.

Quando, no entanto, $A$ é quadrada e invertível, a solução da equação normal coincide exatamente com a solução do sistema original, pois:

$$
\bar{x}=(A^{T}A)^{-1}A^{T}b=A^{-1}(A^{T})^{-1}A^{T}b=A^{-1}b=x
$$

O mesmo acontece quando $Ax=b$ é **possível e indeterminado**. Nesse caso, $A^{T}A$ não será invertível e as infinitas soluções de $A^{T}A\bar{x}=A^{T}b$ irão coincidir com as de $Ax=b$. 

Uma vez que $Ax=b$ é um **sistema impossível**, as soluções (ou a solução única, no caso $m \geq n$ e posto completo) de $A^{T}A\bar{x}=A^{T}b$ são **soluções aproximadas** de $Ax=b$, com base no critério de minimizar $\lVert b - A\bar{x} \rVert$.

### Caso geral e pseudoinversa

A decomposição SVD de $A$ nos permite construir uma ferramenta para resolver $A^{T}Ax=A^{T}b$ no caso geral, que independe da quantidade de linhas e colunas, assim como do posto de $A$. 

Começamos definindo a **pseudoinversa** de uma matriz e constatando algumas de suas propriedades.

:::{prf:definition} Pseudoinversa de Moore-Penrose

Seja $A=U\Sigma V^{T}$. A *pseudoinversa* de $A$ é a matriz:

$$
A^{+}=V\Sigma^{+}U^{T}
$$

Onde $\Sigma^{+}$ é obtida invertendo os valores singulares não nulos de $\Sigma$ (isto é, se $\sigma_{i}\neq 0$ faz-se $\frac{1}{\sigma_{i}}$) e tomando a transposta. 

:::

Para ilustrar melhor como obter ${} \Sigma^{+} {}$, se posto de $A$ é igual a $r$ e seja: 

$$
\Sigma =
\begin{bmatrix}
\sigma_1 &        &        &        & \cdots &        & 0 \\
         & \sigma_2 &      &        & \cdots &        & 0 \\
         &        & \ddots &        &        &        & \vdots \\
         &        &        & \sigma_r &       &        & 0 \\
         &        &        &        & 0      &        & 0 \\
\vdots   & \vdots &        &        & \vdots & \ddots & \vdots \\
0        & 0      & \cdots &        & 0      & \cdots & 0
\end{bmatrix}
$$

A matriz resultante da inversão dos $\sigma_{i}$ ($i=1,\dots,r$) é:

$$
\Sigma' =
\begin{bmatrix}
\frac{1}{\sigma_{1}} &        &        &        & \cdots &        & 0 \\
         & \frac{1}{\sigma_{2}} &      &        & \cdots &        & 0 \\
         &        & \ddots &        &        &        & \vdots \\
         &        &        & \frac{1}{\sigma_{r}} &       &        & 0 \\
         &        &        &        & 0      &        & 0 \\
\vdots   & \vdots &        &        & \vdots & \ddots & \vdots \\
0        & 0      & \cdots &        & 0      & \cdots & 0
\end{bmatrix}
$$

E então, $\Sigma^{+}=(\Sigma')^{T}$.

$A^{+}$ é uma generalização da ideia de inversa para uma matriz qualquer, daí o nome de pseudoinversa. Existem outros tipos de pseudoinversas, esta em específico satisfaz as chamadas **condições de Penrose**:

1. $AA^{+}A=A$
2. $A^{+}AA^{+}=A^{+}$
3. $(AA^{+})^{T}=AA^{+}$
4. $(A^{+}A)^{T}=A^{+}A$

Essas condições são verificadas sem muita dificuldade considerando-se a decomposição SVD de $A$ e as propriedades das matrizes $U$, $V$, $\Sigma $ e $\Sigma^{+}$. 

:::{prf:theorem}
:label: teo-pseudoinversa-postocompleto

Quando $A \in \mathbb{R}^{m\times n}$ possui $m\geq n$ e posto completo, a solução única da equação normal $A^{T}A\bar{x}=A^{T}b$ é dada por:

$$
\bar{x}=A^{+}b
$$

:::

:::{prf:proof}

Uma vez que $A$ tem $m\geq n$ e posto completo, então seu posto é igual a $n$. Consequentemente, $A^{T}A$ é invertível e a solução da equação normal é dada unicamente por $\bar{x}=(A^{T}A)^{-1}A^{T}b$. Seja $A=U\Sigma V^{T}$, substituindo e utilizando o fato que $U$ e $V$ são matrizes ortogonais, obtemos o seguinte:

$$
\begin{align}
\bar{x} & =((U \Sigma V^{T})^{T}\; U \Sigma V^{T})^{-1}(U \Sigma V^{T})^{T}b \\
 & =(V\Sigma^{T}U^{T}U\Sigma V^{T})^{-1}(V\Sigma^{T}U^{T})b \\
 & =(V(\Sigma^{T}\Sigma)^{-1}V^{T}V\Sigma^{T}U^{T})b \\
 & =(V(\Sigma^{T}\Sigma)^{-1}\Sigma^{T}U^{T})b
\end{align}
$$

Agora, note que a matriz $\Sigma^{T}\Sigma$ tem dimensão $n\times n$ e é diagonal, contendo os $n$ valores singulares não nulos de $A$ ao quadrado. Logo, $(\Sigma^{T}\Sigma)^{-1}$ existe e é dada por $\Sigma^{T}\Sigma$ com os inversos dos quadrados dos valores singulares. Então, ao fazermos $(\Sigma^{T}\Sigma)^{-1}\Sigma^{T}$ o que obtemos é uma matriz $n\times m$ diagonal, contendo os inversos dos valores singulares de $A$ (que, neste caso, são todos não nulos), o que corresponde exatamente à matriz $\Sigma^{+}$. Logo,

$$
\bar{x}=(V\Sigma^{+}U^{T})b=A^{+}b
$$

:::

Concluímos que, quando $m\geq n$ e $A$ tem posto completo, $(A^{T}A)^{-1}A^{T}=A^{+}$. Em geral, calcular a decomposição SVD de $A$ e determinar sua pseudoinversa tem menor custo computacional que calcular $(A^{T}A)^{-1}A^{T}$, uma vez que inversão de matrizes tem alto custo.

Agora, estendemos esse resultado para o caso geral, onde $A^{+}b$ nos dará uma solução única para a equação normal em função de um critério específico.

:::{prf:theorem} 

$A^{+}b$ fornece a solução da equação normal $A^{T}A\bar{x}=A^{T}b$ **que possui norma mínima**, seja qual for a matriz $A$. Isto é, se $\hat{x}=A^{+}b$, então:

$$
\lVert \hat{x} \rVert =\min \{ \lVert \bar{x} \rVert:\bar{x}\text{ é solução de }A^{T}A\bar{x}=A^{T}b  \}
$$

:::

:::{prf:proof}

Começamos verificando que $A^{+}b$ é solução de $A^{T}A\bar{x}=A^{T}b$. Seja $A=U\Sigma V^{T}$,

$$
\begin{align}
A^{T}A(A^{+}b) & =(U\Sigma V^{T})^{T}(U\Sigma V^{T})(V\Sigma^{+} U^{T})b \\
 & =(V\Sigma^{T}U^{T}U\Sigma V^{T}V\Sigma^{+}U^{T})b \\
 & =(V(\Sigma^{T}\Sigma \Sigma^{+})U^{T})b
\end{align}
$$

Mais uma vez, $\Sigma^{T}\Sigma$ é uma matriz diagonal $n\times n$ contendo os valores singulares ao quadrado. Quando fazemos seu produto por $\Sigma^{+}$, que é uma matriz $n\times m$ contendo o inverso dos valores singulares não nulos, o que obtemos é uma matriz $n\times m$ contendo os valores singulares, que é propriamente $\Sigma^{T}$. Logo, 

$$
A^{T}A(A^{+}b)=(V\Sigma^{T}U^{T})b=A^{T}b
$$

Assim, $A^{+}b$ é solução da equação normal.

Agora, verificamos que $A^{+}b$ possui norma mínima entre as soluções da equação normal.

Começamos notando que, pela construção que fizemos de $A^{T}A\bar{x}=A^{T}b$ no início do tópico, qualquer solução $\bar{x}$ é tal que $A\bar{x}$ é o vetor no espaço coluna de $A$ de forma que $\lVert b-A\bar{x} \rVert$ é mínimo, onde tal distância é a distância perpendicular entre o ponto $b$ e o espaço coluna de $A$, que por sua vez é única. Logo, o vetor $A\bar{x}$, onde $\bar{x}$ é uma solução da equação normal, **é o mesmo** para todas as soluções $\bar{x}$, denominado *projeção de $b$* no espaço coluna de $A$. Portanto, seja $A^{+}b=\hat{x}$, temos que:

$$
A\bar{x}=A\hat{x}\implies A(\bar{x}-\hat{x})=0
$$

O que por sua vez nos dá que $\bar{x}-\hat{x}$ é um vetor do núcleo de $A$. Em particular, seja $z=\bar{x}-\hat{x}$, então todo vetor $\bar{x}$ solução da eq. normal pode ser escrito como $\bar{x}=z+\hat{x}$. Agora, considere a decomposição SVD de $A$. Pela construção que se tem a pseudoinversa, note que o vetor $\hat{x}=A^{+}b$ irá pertencer ao espaço coluna de $A^{T}$. Mas temos que o núcleo de $A$ é ortogonal ao espaço coluna de $A^{T}$, consequentemente $\langle \hat{x} , z \rangle = 0$.

Assim, temos enfim que:

$$
\lVert \bar{x} \rVert^{2}=\lVert z+\hat{x} \rVert  ^{2}=\lVert z \rVert ^{2}+\lVert \hat{x} \rVert ^{2}\geq \lVert \hat{x} \rVert ^{2}
$$

(veja que a quebra da norma nas duas parcelas é consequência do fato de $\hat{x}$ e $z$ serem ortogonais)

Donde concluímos que $\lVert \bar{x} \rVert\geq \lVert \hat{x} \rVert$ e teremos a igualdade somente quando $z=0$ e $\bar{x}=\hat{x}$. Portanto, $\hat{x}$ é a solução da equação normal de norma mínima.




:::

Com isso, temos uma solução geral para o problema de Quadrados Mínimos, e ainda, única pelo critério de norma mínima (mesmo que a equação normal possua infinitas soluções).

### Exemplos numéricos

Voltando ao sistema inicial {eq}`sistema-exemplo`, encontraremos sua solução aproximada via quadrados mínimos utilizando a inversa da matriz $A^{T}A$ (pois como já vimos, a matriz associada a esse sistema tem posto completo).

A equação normal associada é dada por:

$$
\begin{bmatrix}
1 & 3 & 5 \\
2 & 4 & 6
\end{bmatrix} \begin{bmatrix}
1 & 2 \\
3 & 4 \\
5 & 6
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
1 & 3 & 5 \\
2 & 4 & 6
\end{bmatrix}\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}
$$

$$
\implies \begin{bmatrix}
35 & 44 \\
44 & 56
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
1 \\
2
\end{bmatrix}
$$

Então, calculamos a inversa da matriz $A^{T}A$:

$$
\begin{bmatrix}
35 & 44 \\
44 & 56
\end{bmatrix}^{-1}=\frac{1}{24}\begin{bmatrix}
56 & -44 \\
-44 & 35
\end{bmatrix}
$$

Obtendo a solução de quadrados mínimos:

$$
\begin{bmatrix}
x \\
y
\end{bmatrix}=\frac{1}{24}\begin{bmatrix}
56 & -44 \\
-44 & 35
\end{bmatrix}\begin{bmatrix}
1 \\
2
\end{bmatrix}=\begin{bmatrix}
-\frac{4}{3} \\
\frac{13}{12}
\end{bmatrix}
$$

Como constatado no [](#teo-pseudoinversa-postocompleto), essa solução é a mesma fornecida pela pseudoinversa.

Para ilustrar a solução de quadrados mínimos via pseudoinversa, considere o seguinte sistema, que não possui solução exata e nem posto completo: 

$$
\begin{bmatrix}
1 & 2 \\
2 & 4 \\
3 & 6
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}
$$

Calculando a pseudoinversa, obtemos:

$$
\begin{bmatrix}
1 & 2 \\
2 & 4 \\
3 & 6
\end{bmatrix}^{+}=\frac{1}{70}\begin{bmatrix}
1 & 2 & 3 \\
2 & 4 & 6
\end{bmatrix}
$$

Logo, a solução de quadrados mínimos de menor norma é dada por:

$$
\bar{x}=\frac{1}{70}\begin{bmatrix}
1 & 2 & 3 \\
2 & 4 & 6
\end{bmatrix}\begin{bmatrix}
1 \\
0 \\
0
\end{bmatrix}=\begin{bmatrix}
\frac{1}{70} \\
\frac{1}{35}
\end{bmatrix}
$$

Assim como no tópico de [Compressão de Imagens](svd.md), podemos utilizar a linguagem *Python* e as funções de Álgebra Linear da biblioteca *NumPy*, dessa vez para resolver quadrados mínimos via pseudoinversa numericamente. Isso normalmente é feito em problemas reais, cujas matrizes possuem dimensões maiores e o cálculo exato da solução é pouco viável:

```{code-block} python
:caption: Solução numérica de quadrados mínimos via pseudoinversa
:linenos:

import numpy as np

# Definir as matrizes
A = np.array([[1, 2],
              [2, 4],
              [3, 6]], dtype=float)
              
b = np.array([[1],
              [0],
              [0]], dtype=float)

# Calcular a pseudoinversa 
A_pinv = np.linalg.pinv(A)

# Calcular a solução
x = A_pinv @ b

print("\nPseudoinversa de A:")
print(A_pinv)
print("Solução:")
print(x)

```

Note que o resultado é determinado numericamente e normalmente não corresponde à solução exata, mas é suficientemente preciso na maioria dos casos práticos.

Obtemos:

$$
\bar{x}\approx \begin{bmatrix}
0.01428571 \\
0.02857143
\end{bmatrix}
$$

Com uma precisão de sete casas decimais em relação à solução exata encontrada.
