---
title: Produto Interno, Norma e Ortogonalidade
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

Assim como no caso do produto interno, a definição de norma pode ser generalizada de maneira que qualquer função que atenda certas propriedades caracterize uma norma, mesmo que esta não esteja diretamente relacionada com um produto interno[^1]. No caso das normas do tipo da [](#def-norma), as quais voltaremos nossa atenção, essas propriedades são "herdadas" do produto interno. Uma dessas heranças imediatas é que $\lVert v \rVert=0$ se, e somente se, $v=0$.

[^1]: Os principais exemplos de normas não induzidas por produto interno em ${} \mathbb{R}^{n} {}$ são a norma do infinito (ou norma do máximo), usualmente denotada por ${} \lVert \cdot \rVert_{\infty} {}$ e dada pela maior coordenada em módulo do vetor, e a norma da soma (ou norma 1), usualmente denotada por ${} \lVert \cdot \rVert_{S} {}$ e dada pela soma dos módulos das coordenadas.

:::{prf:example} Norma euclidiana

No caso do produto interno euclidiano no ${} \mathbb{R}^{n} {}$, a norma induzida é dada por

$$
\lVert x \rVert =\sqrt{ \langle x , x \rangle }=\sqrt{ x_{1}^{2}+\dots+x_{n}^{2} },
$$

onde $x=(x_{1},\dots,x_{n})\in \mathbb{R}^{n}$. Essa norma nos fornece o comprimento do vetor $x$, o que é o mesmo que a distância da origem até o ponto de $\mathbb{R}^{n}$ dado pelas coordenadas de $x$. Para o caso do $\mathbb{R}^{2}$ é fácil verificar esse fato utilizando o teorema de Pitágoras, enquanto que em dimensões maiores temos uma generalização dessa ideia.

:::

### Propriedades da norma

Adiante, consideraremos que $\lVert \cdot \rVert$ é uma norma induzida por produto interno em $V$.

:::{prf:property}

Seja $v \in V$,

$$
\lVert v \rVert = 0 \iff v = 0.
$$

:::

:::{prf:proof}

$$
\begin{align}
\lVert v \rVert =0 &  \iff \sqrt{ \langle v , v \rangle } = 0 \\
 & \iff \langle v , v \rangle= 0 \\
 & \iff v = 0 \quad \text{(pois o produto interno é positivo-definido)}.
\end{align}
$$

:::

Similarmente, também é imediato que $\lVert v \rVert\geq 0,\; \forall v \in V$. Logo, a norma induzida por produto interno também é positiva-definida.

:::{prf:property}

Sejam $v \in V$ e $a \in \mathbb{R}$,

$$
\lVert av \rVert =|a|\cdot \lVert v \rVert .
$$

:::

:::{prf:proof}

$$
\begin{align}
\lVert av \rVert^{2}  & =\langle av , av \rangle \\
 & =a^{2}\langle v , v \rangle \\
 & = a^{2} \lVert v \rVert ^{2} \\
 & = |a|^{2}\lVert v \rVert ^{2}.
\end{align}
$$

Tirando a raiz quadrada em ambos os lados, obtemos $\lVert av \rVert=|a|\lVert v \rVert$.

:::

:::{prf:definition} Ortogonalidade

Dois vetores $u,v \in V$ são ***ortogonais*** quando 

$$
\langle u , v \rangle= 0.
$$

:::

Note que $0$ é ortogonal a todos os vetores.

:::{prf:property} Teorema de Pitágoras

Sejam $u,v \in V$ ortogonais, então

$$
\lVert u+v \rVert ^{2}=\lVert u \rVert ^{2}+\lVert v \rVert ^{2}.
$$

:::

:::{prf:proof}

$$
\begin{align}
\lVert u+v \rVert ^{2} & =\langle u+v , u+v \rangle \\
 & =\lVert u \rVert ^{2}+\lVert v \rVert ^{2}+ 2\underbrace{ \langle u , v \rangle }_{ = \,0 } \\
 & = \lVert u \rVert ^{2}+\lVert v \rVert ^{2}.
\end{align}
$$

:::

A alcunha de "Teorema de Pitágoras" fica clara quando consideramos o caso particular em que $V=\mathbb{R}^{2}$ (neste caso, ortogonalidade entre dois vetores equivale ao ângulo entre eles ser de 90 graus), onde o vetor $u+v$ cumpre o papel de hipotenusa e os vetores $u$ e $v$ de catetos.

### Bases ortonormais

:::{prf:definition} Vetores ortonormais

Uma lista de vetores é dita ***ortonormal*** quando os vetores que a constituem possuem norma igual a 1 e são ortogonais entre si (cada par de vetores da lista é ortogonal).

:::

Especificamente, uma lista $(v_{1},\dots v_{n})$ de vetores em $V$ é ortonormal quando $\langle v_{j} , v_{k} \rangle = 0$ para $j \neq k$ e $\langle v_{j} , v_{k} \rangle = 1$ para $j = k$ (note que isso implica que $\lVert v_{j} \rVert = 1$ para todo $v_{j}$ na lista).
