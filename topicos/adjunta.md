---
title: Adjunta
subject: Tópicos Avançados
---

Quando estamos trabalhando com dois espaços vetoriais $V$ e $W$ munidos de produto interno, podemos associar a cada transformação linear de $V$ para $W$ uma transformação linear de $W$ para $V$ que possui algumas propriedades interessantes. Essa transformação é chamada de ***adjunta*** de $T$ e serve de alicerce para um dos principais resultados da Álgebra Linear, o [Teorema Espectral](teorema-espectral.md).

Antes de falarmos sobre a adjunta propriamente, precisamos de um teorema central acerca de um tipo especial de transformações lineares, os funcionais lineares.

:::{prf:definition} Funcional linear

Seja $V$ um espaço vetorial, um ***funcional linear*** em $V$ é uma transformação linear $T$ de $V$ para $\mathbb{R}$, ou seja, $T \in \mathcal{L}(V,\mathbb{R})$ . [^1]

:::

[^1]: É comum denotar o conjunto de todos os funcionais lineares de um espaço $V$ como $V^{*}$. Verifica-se que $V^{*}$ constitui um espaço vetorial, que é chamado de ***dual*** de $V$.

:::{prf:example}

A função $F:\mathbb{R}^{3}\to \mathbb{R}$ definida por

$$
F(x,y,z)=x+y+z
$$

é um funcional linear em $\mathbb{R}^{3}$. Ademais, é fácil verificar que combinações lineares das coordenadas de um vetor do $\mathbb{R}^{n}$ definem um funcional linear. Isto é, fixados $a_{1},\dots,a_{n} \in \mathbb{R}$, seja $x = (x_{1},\dots,x_{n}) \in \mathbb{R}^{n}$, a função $G:\mathbb{R}^{n}\to \mathbb{R}$ dada por

$$
G(x_{1},\dots,x_{n})=a_{1}x_{1}+\dots+a_{n}x_{n}
$$

é um funcional linear em $\mathbb{R}^{n}$. 

:::

Em relação ao funcional ${} G \in \mathcal{L}(\mathbb{R}^{n},\mathbb{R}) {}$ do exemplo anterior, se considerarmos $y=(a_{1},\dots,a_{n}) \in \mathbb{R}^{n}$, então dado $x \in \mathbb{R}^{n}$ temos

$$
Gx=\langle x , y \rangle,
$$

onde $\langle \cdot , \cdot \rangle$ denota o produto interno euclidiano. De maneira geral, em um espaço $V$ munido de produto interno $\langle \cdot , \cdot \rangle$ (um produto interno qualquer, não necessariamente o euclidiano), ao fixarmos $u \in V$, a função $F:V\to \mathbb{R}$ dada por 

$$
Fv=\langle v , u \rangle
$$

define um funcional linear em $V$ (a linearidade de $F$ é evidente pela [linearidade do próprio produto interno](#def-produto-interno)). O teorema a seguir mostra que, na verdade, vale a recíproca: todo funcional linear pode ser representado dessa forma, através do produto interno.

:::{prf:theorem} Teo. da representação de Riesz

Seja $V$ um espaço vetorial munido de produto interno $\langle \cdot , \cdot \rangle$ e $F$ um funcional linear em $V$. Então, existe um único $u \in V$ tal que 

$$
Fv=\langle v , u \rangle
$$

para todo $v \in V$.

:::

:::{prf:proof}

Começamos provando a existência de $u$. Seja $v \in V$ e $(e_{1},\dots,e_{n})$ uma base ortonormal de $V$, então

$$
\begin{align}
Fv & =F(\langle v , e_{1} \rangle e_{1}+\dots+\langle v , e_{n} \rangle e_{n}) \\
 & = \langle v , e_{1} \rangle Fe_{1}+\dots+\langle v , e_{1} \rangle Fe_{n} \quad \text{(lembre-se que }Fe_{i}\text{ é um escalar)} \\
 & =\langle v , (Fe_{1})e_{1} \rangle+\dots+\langle v , (Fe_{n})e_{n} \rangle \\
 & =\langle v , (Fe_{1})e_{1}+\dots+(Fe_{n})e_{n} \rangle.
\end{align}
$$

Portanto, definindo $u:= (Fe_{1})e_{1}+\dots+(Fe_{n})e_{n}$, temos $Fv=\langle v , u \rangle,\,\forall v \in V$.

Agora, provamos a unicidade de $u$. Suponha que existam $u$ e $u'$  em $V$ tais que, para todo $v \in V$, tenha-se 

$$
Fv=\langle v , u \rangle = \langle v , u' \rangle.
$$

Logo, 

$$
0=\langle v , u \rangle - \langle v , u' \rangle = \langle v , u - u' \rangle
$$

para todo $v \in V$. Em particular, se tomarmos $v = u-u'$ teríamos $\langle u-u' , u-u' \rangle=0$, implicando que $\lVert u-u' \rVert = 0$, pois $\langle u-u' , u-u' \rangle = \lVert u-u' \rVert^{2}$. Como $u-u'$ possui norma igual a zero,  devemos ter que $u-u' = 0$, ou seja, $u=u'$, mostrando a unicidade de $u$.

:::
