---
title: Relação entre transformações lineares e matrizes
subject: Fundamentos
---

Notações utilizadas:

- $c$ é a base *canônica* do espaço $\mathbb{R}^{n}$ em contexto.
- $[T]^{\alpha}_{\beta}$ é a matriz associada a transformação linear $T:V\to W$ em relação a base $\alpha$ de $V$ e a base $\beta$ de $W$. No caso da matriz de um operador em relação a uma mesma base, omitiremos o sobrescrito.
- $\textbf{I}$ é a matriz identidade (dimensão compatível com o contexto em que é utilizada) e $[I]^{\alpha}_{\beta}$ representa a matriz mudança de base de $\alpha$ para $\beta$.

Tendo estudado transformações lineares e as propriedades fundamentais de matrizes, veremos agora como estas estão intrinsecamente relacionadas, de maneira que toda matriz está associada a uma transformação linear (e vice-versa).

### Princípios

Vimos que todo espaço vetorial possui bases que o geram, logo, quando discutimos uma transformação linear podemos pensar em relação a como ela atua em uma base específica deste espaço. Essa ideia é o cerne da relação entre transformaçõe lineares e matrizes.

:::{prf:definition} Matriz de uma transformação linear

Considere $T:V\to W$ uma transformação linear, onde o espaço vetorial $V$ possui dimensão $n$ e o espaço vetorial $W$ possui dimensão $m$. Dadas bases ordenadas $\alpha=\{ v_{1},v_{2},\dots,v_{n} \}$ e $\beta=\{ w_{1},w_{2},\dots,w_{m} \}$ de $V$ e $W$, respectivamente, definimos a matriz $[T]^{\alpha}_{\beta}$, de dimensão $m \times n$, como a *matriz associada à $T$ em relação às bases $\alpha$ e $\beta$*. De forma que:

$$
[T]^{\alpha}_{\beta}=\begin{pmatrix}
a_{11} & a_{12} & \dots & a_{1n} \\
a_{21} & a_{22} & \dots & a_{2}n \\
\vdots   \\
a_{m_{1}} & a_{m2} & \dots & a_{mn}
\end{pmatrix}
$$

onde $a_{ij}$ é a $i$-ésima coordenada de $Tv_{j}$ na base $\beta$.

:::

Note que, a partir desssa definição, toda transformação linear está relacionada univocamente a uma matriz (o que decorre da unicidade de coordenadas em uma base ordenada). Logo, uma mesma transformação pode ter matrizes diferentes (mas de mesma dimensão) em relação a bases diferentes. 

Mas e no caso contrário? Se pensarmos dessa forma geral, dada uma matriz qualquer, ela pode estar relacionada a diferentes transformações em relação a diferentes bases. Então, para fazer a passagem de uma matriz para uma transformação, nós padronizamos as bases, de maneira que nos interessa determinar a transformação relacionada. Dado o isomorfismo entre um espaço vetorial qualquer de dimensão $n$ e o $\mathbb{R}^{n}$, para uma matriz de dimensão $m \times n$, fixamos as bases canônicas de $\mathbb{R}^{m}$  e ${} \mathbb{R}^{n} {}$, de maneira que a matriz está associada univocamente a uma transformação linear $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$, em relação às respectivas bases canônicas.
