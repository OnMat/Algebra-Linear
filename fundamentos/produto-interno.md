---
title: Produto interno e norma
subject: Fundamentos
---

Começaremos a trabalhar com duas ferramentas provavelmente já conhecidas: o produto interno e a norma. Em cursos de álgebra vetorial e geometria analítica temos contato com uma versão do produto interno e norma chamada de *euclidiana* ou *canônica*. No caso do espaço $\mathbb{R}^{2}$, o produto interno euclidiano entre os vetores $x=(x_{1},x_{2})$ e $y=(y_{1},y_{2})$ é dado por 

$$
\langle x , y \rangle = x_{1}y_{1}+x_{2}y_{2},
$$

enquanto que a norma euclidiana é dada por

$$
\lVert x \rVert =\sqrt{ x_{1}^{2}+x_{2}^{2} }.
$$

Eles nos dão em $\mathbb{R}^{2}$ e $\mathbb{R}^{3}$ uma importante ferramenta de análise geométrica, que permite relacionar ângulos e distâncias entre vetores.

A ideia agora é generalizarmos os conceitos de produto interno e norma, considerando um espaço vetorial qualquer. Possuindo espaços vetoriais munidos de produto interno, poderemos definir uma importante transformação linear, chamada de **adjunta**.

### Conceitos iniciais

O produto interno, em um sentido geral, é definido como uma função entre vetores de um espaço que obedece algumas propriedades.

:::{prf:definition} Produto interno
:label: def-produto-interno

Seja $V$ um espaço vetorial. Um ***produto interno*** em $V$ é uma função $\langle \cdot , \cdot \rangle:V\times V\to \mathbb{R}$ que leva cada par de vetores $(u,v)$ de $V$ em um número $\langle u , v \rangle \in \mathbb{R}$, satisfazendo as seguintes propriedades:

1. (**Positivo-definido**) $\langle v , v \rangle \geq 0$, $\forall v\in V$, valendo a igualdade se, e somente se, $v = 0$;
2. (**Aditividade**) $\langle u+w , v \rangle=\langle u , v \rangle+\langle w , v \rangle,\, \forall u,w,v \in V$;
3. (**Homogeneidade**) $\langle av , w \rangle=a\langle v , w \rangle,\, \forall a \in \mathbb{R}$ e $\forall v,w \in V$;
4. (**Simétrico**) $\forall u,v \in V$ tem-se $\langle u , v \rangle=\langle v , u \rangle$.

:::

Note que as condições de aditividade e homogeneidade juntas formam uma condição de linearidade na primeira entrada. Com a condição de simetria, temos na verdade a linearidade nas duas entradas. Por isso, um produto interno é dito ***bilinear***.

:::{prf:example} Produto interno euclidiano em ${} \mathbb{R}^{n} {}$

Sejam $x=(x_{1},\dots,x_{n})$ e $y=(y_{1},\dots,y_{n})$ vetores de $\mathbb{R}^{n}$, a função $\langle \cdot , \cdot \rangle: \mathbb{R}^{n} \times \mathbb{R}^{n}\to \mathbb{R}$ dada por 

$$
\langle x , y \rangle=x_{1}y_{1}+\dots+x_{n}y_{n},
$$

define um produto interno em $\mathbb{R}^{n}$, chamado de ***produto interno euclidiano*** ou ***produto interno canônico***.

A verificação das propriedades da [](#def-produto-interno) é razoavelmente direta.
1. É evidente que $\langle x , x \rangle=x_{1}^{2}+\dots+x_{n}^{2} \geq 0$, para qualquer $x \in \mathbb{R}^{n}$. Em particular, $x_{1}^{2}+\dots+x_{n}^{2}= 0 \iff x = 0$;
2. Sejam $x=(x_{1},\dots,x_{n}),y=(y_{1},\dots,y_{n})$ e $z=(z_{1},\dots,z_{n})$ vetores de $\mathbb{R}^{n}$, então $\langle x+y , z \rangle=(x_{1}+y_{1})z_{1}+\dots+(x_{n}+y_{n})z_{n}=x_{1}z_{1}+\dots+x_{n}z_{n}+y_{1}z_{1}+\dots+y_{n}z_{n}=\langle x , z \rangle+\langle y , z \rangle$;
3. Seja $a \in \mathbb{R}$, $\langle ax , y \rangle=ax_{1}y_{1}+\dots+ax_{n}y_{n}=a(x_{1}y_{1}+\dots+x_{n}y_{n})=a\langle x , y \rangle$;
4. $\langle x , y \rangle=x_{1}y_{1}+\dots+x_{n}y_{n}=y_{1}x_{1}+\dots+y_{n}x_{n}=\langle y , x \rangle$.

:::

De maneira análoga ao que foi feito no exemplo, verifica-se que 

$$
\langle x , y \rangle=a_{1}x_{1}y_{1}+\dots+a_{n}x_{n}y_{n},\quad a_{1},\dots,a_{n} \in \mathbb{R}
$$

define um produto interno em $\mathbb{R}^{n}$, sendo o produto interno euclidiano um caso particular deste, onde $a_{1}=\dots=a_{n}=1$.

A partir de todo produto interno podemos definir uma ***norma***. Normas funcionam como métricas nos espaços vetoriais, medindo o comprimento ou "intensidade" dos vetores, além das distâncias entre eles. 

:::{prf:definition} Norma induzida pelo produto interno
:label: def-norma

Seja $V$ um espaço vetorial munido de produto interno $\langle \cdot , \cdot \rangle$, a ***norma induzida*** por $\langle \cdot , \cdot \rangle$ é a função $\lVert \cdot \rVert:V\to \mathbb{R}$, dada por

$$
\lVert v \rVert =\sqrt{ \langle v , v \rangle },\;\forall v \in V.
$$

:::

Assim como no caso do produto interno, a definição de norma pode ser generalizada de maneira que qualquer função que atenda certas propriedades caracterize uma norma, mesmo que esta não esteja diretamente relacionada com um produto interno[^1]. No caso das normas do tipo da [](#def-norma), as quais voltaremos nossa atenção, essas propriedades são "herdadas" do produto interno.

[^1]: Os principais exemplos de normas não induzidas por produto interno em ${} \mathbb{R}^{n} {}$ são a norma do infinito (ou norma do máximo), usualmente denotada por ${} \lVert \cdot \rVert_{\infty} {}$ e dada pela maior coordenada em módulo do vetor, e a norma da soma (ou norma 1), usualmente denotada por ${} \lVert \cdot \rVert_{S} {}$ e dada pela soma dos módulos das coordenadas.
