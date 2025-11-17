---
title: Produto interno
subject: Fundamentos
---

Começaremos a trabalhar com uma ferramenta provavelmente já conhecida, o produto interno. Em cursos de álgebra vetorial e geometria analítica temos contato com o chamado *produto interno euclidiano* ou *produto interno canônico* para os espaços $\mathbb{R}^{2}$ e $\mathbb{R}^{3}$. No caso do espaço $\mathbb{R}^{2}$, o produto interno euclidiano entre os vetores $x=(x_{1},x_{2})$ e $y=(y_{1},y_{2})$ é dado por 

$$
\langle x , y \rangle = x_{1}y_{1}+x_{2}y_{2}.
$$

Com esse produto interno em $\mathbb{R}^{2}$ e $\mathbb{R}^{3}$ temos uma versátil ferramenta de análise geométrica, que permite relacionar ângulos e distâncias entre vetores (este último a partir da norma euclidiana, diretamente relacionada com o produto interno).

A ideia agora é generalizarmos o conceito de produto interno, considerando um espaço vetorial qualquer. Possuindo espaços vetoriais munidos de produto interno, poderemos definir uma importante transformação linear, chamada de **adjunta**.

### Conceitos iniciais

O produto interno, em um sentido geral, é definido como uma função entre vetores de um espaço que obedece algumas propriedades.

:::{prf:definition} Produto interno

Seja $V$ um espaço vetorial. Um ***produto interno*** em $V$ é uma função $\langle \cdot , \cdot \rangle:V\times V\to \mathbb{R}$ que leva cada par de vetores $(u,v)$ de $V$ em um número $\langle u , v \rangle \in \mathbb{R}$, satisfazendo as seguintes propriedades:

1. (**Positivo-definido**) $\langle v , v \rangle \geq 0$, $\forall v\in V$, valendo a igualdade se, e somente se, $v = 0$;
2. (**Aditividade na primeira entrada**) $\langle u+w , v \rangle=\langle u , v \rangle+\langle w , v \rangle,\, \forall u,w,v \in V$;
3. (**Homogeneidade na primeira entrada**) $\langle av , w \rangle=a\langle v , w \rangle,\, \forall a \in \mathbb{R}$ e $\forall v,w \in V$;
4. (**Simétrico**) $\forall u,v \in V$ tem-se $\langle u , v \rangle=\langle v , u \rangle$.

:::

Note que as condições de aditividade e homogeneidade juntas formam uma condição de linearidade na primeira entrada. Com a condição de simetria, temos na verdade a linearidade nas duas entradas. Por isso, um produto interno é dito ***bilinear***.

:::{prf:example} Produto interno euclidiano em ${} \mathbb{R}^{n} {}$

Sejam $x=(x_{1},\dots,x_{n})$ e $y=(y_{1},\dots,y_{n})$ vetores de $\mathbb{R}^{n}$, a função $\langle \cdot , \cdot \rangle: \mathbb{R}^{n} \times \mathbb{R}^{n}\to \mathbb{R}$ dada por 

$$
\langle x , y \rangle=x_{1}y_{1}+\dots+x_{n}y_{n},
$$

define um produto interno em $\mathbb{R}^{n}$.

:::
