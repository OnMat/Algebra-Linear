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
$$

Claramente, o sistema não possui solução exata (a matriz não é sequer quadrada, menos ainda invertível). Analisando do ponto de vista de transformações lineares, sabemos que o sistema será **possível e indeterminado** se $(1,0,0)\in [(1,3,5),(2,4,6)]$. No entanto, 

$$
\begin{vmatrix}
1 & 2 & 1 \\
3 & 4 & 0 \\
5 & 6 & 0
\end{vmatrix}=-2\neq 0
$$

Logo, os 3 vetores são linearmente independentes e o sistema é **impossível**, pois não existem vetores $v$ em $\mathbb{R}^{2}$ tais que $Av=(1,0,0)$, onde $A$ é a matriz associada ao sistema.

Supondo que a modelagem foi feita corretamente (sistemas como esses são perfeitamente possíveis e comuns em problemas reais, principalmente quando se tem mais dados observados que incógnitas a serem determinadas), uma resposta aproximada seria determinar o vetor pertencente ao espaço gerado pelas colunas de $A$ (nesse caso, uma combinação linear entre os vetores $(1,3,5)$ e $(2,4,6)$) que está "mais próximo" do vetor $(1,0,0)$. Isto é, utilizando a norma vetorial, queremos determinar $\bar{x}\in \mathbb{R}^{2}$ que minimize $\lVert A\bar{x}-b \rVert$ ($b=(1,0,0)$).

Considere, então, o caso geral $Ax=b$ (com $A\in \mathbb{R}^{m\times n}$). O que procuramos é:

$$
\bar{x}=\min_{x \in \mathbb{R}^{n}}\lVert Ax-b \rVert 
$$

...

