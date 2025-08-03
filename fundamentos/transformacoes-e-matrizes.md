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

Vimos que todo espaço vetorial possui bases que o geram, logo, quando discutimos uma transformação linear podemos pensar em relação a ela considerando bases específicas dos espaços envolvidos. Essa ideia é o cerne da relação entre transformações lineares e matrizes.

:::{prf:definition} Matriz de uma transformação linear
:label: def-matrizdeumatransformacaolinear

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

Assim, fixadas as bases dos espaços vetoriais envolvidos, toda transformação linear entre esses espaços está relacionada univocamente a uma matriz, o que decorre da unicidade das coordenadas em uma base ordenada (mas note que uma mesma transformação pode ter matrizes diferentes, mas de mesma dimensão, em relação a bases diferentes). Logo, conseguimos "encapsular" uma transformação linear em uma matriz, de modo que somente com suas entradas e conhecendo os espaços vetoriais e bases em contexto podemos determinar de qual transformação se trata. Isso é extremamente interessante e poderoso, principalmente do ponto de vista computacional (veremos adiante como isso nos permite determinar a imagem de um vetor utilizando a matriz associada à transformação), conseguimos resumir qualquer transformação linear em um conjunto de números.

:::{prf:example}

Qual a matriz associada à transformação linear $T:\mathbb{R}^{2}\to \mathbb{R}^{3}$, nas bases canônicas, dada por $T(x,y)=(x+y,2x-y,y)$?

Devemos determinar as imagens dos vetores da base do espaço vetorial de saída, no caso, a base canônica de $\mathbb{R}^{2}$. Depois, reescrevemos tais imagens na base ordenada do espaço vetorial de chegada, as coordenadas obtidas nos dão as entradas da matriz. No caso, como a base de chegada considerada também é a canônica, basta apenas calcular as imagens:

$$
\begin{align}
 & T(1,0)=(1+0,2\cdot1-0,0)=(1,2,0) \\
 & T(0,1)=(0+1,2\cdot 0-1,1)=(1,-1,1)
\end{align}
$$

Logo, sejam $c_{1}$ e $c_{2}$ as bases canônicas de $\mathbb{R}^{2}$ e $\mathbb{R}^{3}$, respectivamente,

$$
[T]^{c_{1}}_{c_{2}}=\begin{pmatrix}
1 & 1 \\
2 & -1 \\
0 & 1
\end{pmatrix}
$$

:::

Mas e o oposto? Dada uma matriz qualquer, como interpretá-la como uma transformação linear? Com base na [](#def-matrizdeumatransformacaolinear), devemos determinar quais os espaços vetoriais e as respectivas bases envolvidas. Uma escolha natural seria considerarmos, para uma matriz de dimensão ${} m\times n {}$, os espaços vetoriais $\mathbb{R}^{m}$ e $\mathbb{R}^{n}$, com suas respectivas bases canônicas. Dessa forma, a matriz estará associada univocamente a uma transformação linear $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$ em relação às bases canônicas. Essa escolha facilita muitos aspectos (pois são espaços vetoriais e bases simples de lidarmos) e sabemos do isomorfismo que existe entre qualquer espaço vetorial de dimensão $n$ e o $\mathbb{R}^{n}$, então a transformação associada é "equivalente" para quaisquer espaços de dimensões compatíveis com a matriz. 

Portanto, temos a seguinte definição:

:::{prf:definition} Transformação linear associada a uma matriz
:label: def-transformacaoassociadaamatriz

Seja $A\in \mathcal{M}_{m\times n}(\mathbb{R})$, a *transformação linear associada* a $A$ é $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$, tal que cada entrada $a_{ij}$ de $A$ é a $i$-ésima coordenada de ${} Te_{j} {}$ na base canônica de $\mathbb{R}^{m}$, onde $\{ e_{1},e_{2},\dots,e_{n} \}$ é a base canônica de $\mathbb{R}^{n}$.

:::

:::{prf:example}

Qual transformação linear $T$ está associada à matriz $A=\begin{pmatrix}1 & 2 & 3 \\ 4 & 5 & 6\end{pmatrix}$?

Pela [](#def-transformacaoassociadaamatriz) sabemos que:
- $T:\mathbb{R}^{3}\to \mathbb{R}^{2}$, pois $A$ tem dimensão $2\times 3$;
- $Te_{1}=T(1,0,0)=(1,4)$;
- $Te_{2}=T(0,1,0)=(2,5)$;
- $Te_{3}=T(0,0,1)=(3,6)$.

Portanto, seja $(x,y,z)\in \mathbb{R}^{3}$,

$$
\begin{align}
T(x,y,z)&=xTe_{1}+yTe_{2}+zTe_{3} \\
 & =x(1,4)+y(2,5)+z(3,6) \\
 & =(x,4x)+(2y,5y)+(3z,6z) \\
 & =(x+2y+3z,4x+5y+6z)
\end{align}
$$

Determinando assim $T$.

:::

### Releitura das propriedades matriciais

Agora, com a ótica de transformações lineares, podemos interpretar as propriedades de matrizes.

:::{prf:property}

A soma matricial é equivalente a soma de transformações lineares, isto é, sejam $T:V\to W$ e $S:V\to W$:

$$
[T]^{\alpha}_{\beta}+[S]^{\alpha}_{\beta}=[T+S]^{\alpha}_{\beta}
$$

$\alpha$ e $\beta$ são bases de $V$ e $W$, respectivamente. Note que devemos ter as mesmas bases para as duas matrizes/transformações.

:::

:::{prf:property}

A multiplicação de uma matriz por um escalar é equivalente a multiplicação de uma transformação linear por este escalar. Para $k \in \mathbb{R}$,

$$
k[T]^{\alpha}_{\beta}=[k T]^{\alpha}_{\beta}
$$

:::

:::{prf:property}

O produto matricial é equivalente à composição de transformações lineares. Sejam $T:V\to W$ e $S:W\to X$,

$$
[S]^{\alpha}_{\beta}\cdot[T]^{\gamma}_{\alpha}=[ST]^{\gamma}_{\beta}
$$

Note que a base do espaço $W$, em comum entre $T$ e $S$, deve ser a mesma.

:::

Essa terceira propriedade esclarece o porquê do produto matricial ser definido da forma que é. Isso pode ser verificado algebricamente, considerando transformações (cuja composição é válida) e bases fixas, mas é melhor visualizado pensando nas colunas das matrizes como vetores (na verdade, como coordenadas de um vetor em uma base). Vetores na forma matricial (isto é, matrizes $n \times 1$) são chamados de *vetores coluna*.

Perceba como essa interpretação também oferece uma nova maneira de determinar a transformação linear associada à uma matriz $A$ de dimensão ${} m\times n {}$, basta fazermos o produto $A\cdot \begin{pmatrix}x_{1}\\x_{2}\\ \vdots \\ x_{n} \end{pmatrix}$.

Além disso, como é esperado, $\mathbf{I}=[I]_{\alpha}$. Introduziremos agora uma importante ferramenta relacionada com a matriz do operador identidade:

:::{prf:property}

Seja $V$ um espaço vetorial, com $\alpha$ e $\beta$ bases de $V$, a *matriz mudança de base* de $\alpha$ para $\beta$ é $[I]^{\alpha}_{\beta}$ ($I$ o operador identidade em $V$).

:::

O nome vem simplesmente do fato que tal matriz permite determinar as coordenadas na base $\beta$ de qualquer vetor em $V$, a partir das suas coordenadas em $\alpha$. Ou seja, digamos que $(v)_{\alpha}=(x_{1},x_{2},\dots,x_{n})$, então as coordenadas de $(v)_{\beta}$ são dadas pelas entradas do vetor coluna resultante do produto $[I]^{\alpha}_{\beta}\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
\vdots \\
x_{n}
\end{pmatrix}$.

E claro que podemos também fazer o produto matricial entre uma matriz compatível $A$ e ${} [I]^{\alpha}_{\beta} {}$, de maneira que se $A=[T]^{\beta}_{\gamma}$, a matriz resultante é $[T]^{\alpha}_{\gamma}$. Logo, podemos reescrever a matriz de qualquer transformação em bases diferentes, esse fato cumpre um papel importante no [Teorema Espectral para matrizes](#espectral-para-matrizes-simetricas).

Por fim, a transposta de uma matriz também possui um contexto de transformação linear, que é discutido no tópico de *Adjunta*.
