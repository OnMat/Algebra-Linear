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

### Produto interno

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

### Norma

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
:label: prop-escalar-norma

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

### Ortogonalidade

:::{prf:definition} Ortogonalidade

Dois vetores $u,v \in V$ são ***ortogonais*** quando 

$$
\langle u , v \rangle= 0.
$$

:::

Note que $0$ é ortogonal a todos os vetores.

:::{prf:property} Teorema de Pitágoras
:label: teo-pitagoras

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

Um exemplo imediato de vetores ortonormais é a base canônica de $\mathbb{R}^{n}$, considerando o produto interno e a norma canônicos.

:::{prf:proposition}
:label: prop-norma-combinacao-ortonormal

Seja $(v_{1},\dots,v_{n})$ uma lista ortonormal de vetores em $V$, então 

$$
\lVert a_{1}v_{1}+\dots+a_{n}v_{n} \rVert ^{2}=a_{1}^{2}+\dots+a_{n}^{2},
$$

para quaisquer $a_{1},\dots,a_{n} \in \mathbb{R}$.

:::

:::{prf:proof}

Separemos o vetor $a_{1}v_{1}+\dots+a_{n}v_{n}$ em dois vetores, $a_{1}v_{1}$ e $a_{2}v_{2}+\dots a_{n}v_{n}$. Utilizando o fato que $(v_{1},\dots,v_{n})$ é ortonormal obtemos

$$
\begin{align}
\langle a_{1}v_{1} , a_{2}v_{2}+\dots+a_{n}v_{n} \rangle & =a_{1}a_{2}\langle v_{1} , v_{2} \rangle+\dots+a_{1}a_{n}\langle v_{1} , v_{n} \rangle \\
 & =a_{1}a_{2}\cdot 0+\dots+a_{1}a_{n}\cdot 0 \\
 & = 0.
\end{align}
$$

Logo, os vetores $a_{1}v_{1}$ e $a_{2}v_{2}+\dots+a_{n}v_{n}$ também são ortogonais. Em particular, podemos aplicar [](#teo-pitagoras) para eles, obtendo que 

$$
\lVert a_{1}v_{1}+\dots+a_{n}v_{n} \rVert ^{2}=\lVert a_{1}v_{1} \rVert ^{2}+\lVert a_{2}v_{2}+\dots+a_{n}v_{n} \rVert ^{2}.
$$

Agora, decompomos $a_{2}v_{2}+\dots+a_{n}v_{n}$ em $a_{2}v_{2}$ e $a_{3}v_{3}+\dots a_{n}v_{n}$. Com uma análise análoga, temos que esses vetores também são ortogonais. Seguindo esse processo, com uma aplicação sucessiva de [](#teo-pitagoras), obtemos 

$$
\begin{align}
\lVert a_{1}v_{1}+\dots a_{n}v_{n} \rVert ^{2} & =\lVert a_{1}v_{1} \rVert ^{2}+\dots+\lVert a_{n}v_{n} \rVert ^{2} \\
 & =a_{1}^{2}\lVert v_{1} \rVert ^{2}+\dots a_{n}^{2}\lVert v_{n} \rVert ^{2} \\
 & =a_{1}^{2}\cdot 1+\dots+a_{n}^{2}\cdot 1 \\
 & =a_{1}^{2}+\dots+a_{n}^{2},
\end{align}
$$

utilizando [](#prop-escalar-norma) e o fato de que $\lVert v_{j} \rVert=1$ para todo $v_{j}$ em $(v_{1},\dots,v_{n})$, uma vez que a lista é ortonormal.

:::

:::{prf:corollary}
:label: corol-ortonormal-li

Seja $(v_{1},\dots,v_{n})$ uma lista ortonormal de vetores em $V$, então $(v_{1},\dots,v_{n})$ é linearmente independente.

:::

:::{prf:proof}

Sejam $a_{1},\dots,a_{n} \in \mathbb{R}$ tais que 

$$
a_{1}v_{1}+\dots+a_{n}v_{n}=0.
$$

Como $\lVert 0 \rVert=0$, utilizando [](#prop-norma-combinacao-ortonormal) obtemos que 

$$
a_{1}^{2}+\dots+a_{n}^{2}=0.
$$

Uma vez que cada parcela é não negativa, necessariamente devemos ter $a_{1}=\dots=a_{n}=0$, mostrando que $(v_{1},\dots,v_{n})$ é linearmente independente.

:::

:::{prf:definition} Base ortonormal

Uma lista $(v_{1},\dots,v_{n})$ ortonormal que constitui uma base de $V$ é dita uma ***base ortonormal*** de $V$.

:::

Como já mencionado, a base canônica de $\mathbb{R}^{n}$ é uma lista ortonormal, portanto é uma base ortonormal.

:::{prf:theorem} 

Seja $(v_{1},\dots,v_{n})$ uma base ortonormal de $V$, então para todo $v \in V$ tem-se

$$
v=\langle v , v_{1} \rangle v_{1}+\dots+\langle v , v_{n} \rangle v_{n}.
\label{eq:teorema-base-ortonormal}
$$

:::

:::{prf:proof}

Uma vez que $(v_{1},\dots,v_{n})$ forma uma base de $V$, para todo $v \in V$ existem escalares únicos $a_{1},\dots,a_{n}$ tais que 

$$
v=a_{1}v_{1}+\dots+a_{n}v_{n}.
$$

Sendo assim, para todo $v_{j}$ em $(v_{1},\dots,v_{n})$ tem-se

$$
\begin{align}
\langle v , v_{j} \rangle & =\langle a_{1}v_{1}+\dots+a_{n}v_{n} , v_{j} \rangle \\
 & =a_{1}\langle v_{1} , v_{j} \rangle+\dots+a_{j}\langle v_{j} , v_{j} \rangle+\dots+a_{n}\langle v_{n} , v_{j} \rangle \\
 & =a_{j}\quad \text{(pois }(v_{1},\dots,v_{n})\text{ é ortonormal)}.
\end{align}
$$

Portanto, vale a igualdade {eq}`eq:teorema-base-ortonormal`.

:::

### Processo de Gram-Schmidt

O importante resultado a seguir mostra que dada qualquer lista de vetores linearmente independentes é possível encontrar uma lista ortonormal que gera o mesmo subespaço que tal lista dada.

:::{prf:theorem} Gram-Schmidt
:label: teo-gram-schmidt

Seja $(v_{1},\dots,v_{n})$ uma lista linearmente independente de vetores em $V$, existe uma lista **ortonormal** $(u_{1},\dots,u_{n})$ de vetores em $V$ tal que

$$
\text{span}(v_{1},\dots,v_{j})=\text{span}(u_{1},\dots,u_{j})
$$

para $j=1,\dots,n$.

:::

A demonstração desse teorema é feita fornecendo um procedimento para encontrar tal lista ortonormal, o qual é denominado ***Processo de Gram-Schmidt*** ou ***Algoritmo de Gram-Schmidt***.

:::{prf:proof} Processo de Gram-Schmidt
:label: processo-gram-schmidt

Dada a lista linearmente independente $(v_{1},\dots,v_{n})$, começamos fazendo $u_{1}=\frac{v_{1}}{\lVert v_{1} \rVert}$, um vetor de norma unitária que satisfaz [](#teo-gram-schmidt) para $j=1$. O processo de escolha de $u_{2},\dots,u_{n}$ é feito indutivamente, da seguinte forma:

Suponha que $j>1$ e tem-se uma lista ortonormal $(u_{1},\dots,u_{j-1})$ que satisfaz [](#teo-gram-schmidt). Faça

$$
u_{j}=\frac{v_{j}-\langle v_{j} , u_{1} \rangle u_{1} - \dots - \langle v_{j} , u_{j-1} \rangle u_{j-1}}{\lVert v_{j}-\langle v_{j} , u_{1} \rangle u_{1} - \dots - \langle v_{j} , u_{j-1} \rangle u_{j-1} \rVert }.
$$

Como $(v_{1},\dots,v_{n})$ é linearmente independente, $v_{j}$ não pertence ao espaço gerado por $(v_{1},\dots,v_{j-1})$, implicando que $v_{j}$ não pertence ao espaço gerado por $(u_{1},\dots,u_{j-1})$ (uma vez que vale $\text{span}(v_{1},\dots,v_{j-1})=\text{span}(u_{1},\dots,u_{j-1})$). Isso nos garante que $v_{j} \neq\langle v_{j} , u_{1} \rangle u_{1} + \dots + \langle v_{j} , u_{j-1} \rangle u_{j-1}$ e, portanto, não estamos dividindo por zero na definição de $u_{j}$, que é então um vetor de norma unitária. Agora, note que para $1 \leq k < j$ tem-se

$$
\begin{align}
\langle u_{j} , u_{k} \rangle  & = \left\langle  \frac{v_{j}-\langle v_{j} , u_{1} \rangle u_{1} - \dots - \langle v_{j} , u_{j-1} \rangle u_{j-1}}{\lVert v_{j}-\langle v_{j} , u_{1} \rangle u_{1} - \dots - \langle v_{j} , u_{j-1} \rangle u_{j-1} \rVert } , u_{k}  \right\rangle \\
 & =\frac{\langle v_{j} , u_{k} \rangle - \langle v_{j} , u_{k} \rangle}{\lVert v_{j}-\langle v_{j} , u_{1} \rangle u_{1} - \dots - \langle v_{j} , u_{j-1} \rangle u_{j-1} \rVert } \\
 & = 0.
\end{align}
$$

Provando que $(u_{1},\dots,u_{j})$ é ortonormal. Observe que, da definição de $u_{j}$, temos que $v_{j} \in \text{span}(u_{1},\dots,u_{j})$. Por outro lado, temos também que $\text{span}(v_{1},\dots,v_{j-1})=\text{span}(u_{1},\dots,u_{j-1})$, logo

$$
\text{span}(v_{1},\dots,v_{j}) \subseteq \text{span}(u_{1},\dots,u_{j}).
$$

No entanto, uma vez que tanto $(v_{1},\dots,v_{j})$ e $(u_{1},\dots,u_{j})$ são linearmente independentes, ambos os subespaços acima possuem dimensão igual a $j$, concluindo que devem ser iguais (pois um está contido no outro e possuem mesma dimensão). Dessa forma, construímos uma lista ortonormal tal que vale [](#teo-gram-schmidt).

:::

:::{prf:corollary}

Todo espaço vetorial de dimensão finita e munido de produto interno possui uma base ortonormal.

:::

:::{prf:proof}

Dada uma base desse espaço, que é uma lista linearmente independente, pelo [](#teo-gram-schmidt) existe uma lista ortonormal que também gera esse espaço. Além disso, essa lista é linearmente independente (pelo [](#corol-ortonormal-li)). Logo, é uma base ortonormal desse espaço.

:::

:::{prf:corollary}

Toda lista ortonormal de vetores em $V$ pode ser estendida para uma base ortonormal de $V$.

:::

:::{prf:proof}

Seja $(u_{1},\dots,u_{m})$ uma lista ortonormal de $V$, pelo [](#teoestenderbase) ela pode ser estendida em uma base $(u_{1},\dots,u_{m},v_{1},\dots,v_{n})$ de $V$. Aplicando o processo de Gram-Schmidt (descrito em [](#processo-gram-schmidt)) nessa base, é produzida uma base ortonormal de $V$. Mas, note que pela maneira como é realizado o processo e considerando que $(u_{1},\dots,u_{m})$ já é ortonormal, tal base ortonormal produzida será da forma $(u_{1},\dots,u_{m},w_{1},\dots,w_{m})$, isto é, os vetores $u_{1},\dots,u_{m}$ são preservados pelo processo. Portanto, no fim o que foi feito foi estender a lista ortonormal em uma base ortonormal de $V$.

:::

### Complemento ortogonal

:::{prf:definition} Complemento ortogonal

Seja $U$ um subespaço de $V$. O ***complemento ortogonal*** de $U$, denotado por $U^{\perp}$ (lê-se "$U$ perp") é o conjunto de todos os vetores de $V$ que são ortogonais a todos os vetores de $U$. Isto é,

$$
U^{\perp}=\{ v \in V: \langle v , u \rangle = 0,\;\forall u \in U \}.
$$

:::

É fácil verificar que $U^{\perp}$ é um subespaço de $V$. Além disso, tem-se $V^{\perp}=\{ 0 \}$ e $\{ 0 \}^{\perp}=V$.

O complemento ortogonal de um subespaço nos permite escrever o espaço o qual ele faz parte como uma soma direta envolvendo esse subespaço:

:::{prf:theorem}
:label: teo-soma-direta-complemento

Seja $U$ um subespaço de $V$, então

$$
V=U\oplus U^{\perp}.
$$

:::

:::{prf:proof}

Devemos mostrar que $V=U+U^{\perp}$ e $U\cap U^{\perp}=\{ 0 \}$. Para o primeiro, seja $v \in V$, considere $(u_{1},\dots,u_{n})$ uma base ortonormal de $U$. Note que

$$
\begin{align}
v & =v+0 \\
 & =v+(\langle v , u_{1}  \rangle u_{1}+\dots+\langle v , u_{n} \rangle u_{n}-\langle v , u_{1} \rangle u_{1}-\dots-\langle v , u_{n} \rangle u_{n}) \\
 & = \underbrace{ \langle v , u_{1}  \rangle u_{1}+\dots+\langle v , u_{n} \rangle u_{n}  }_{ u }+\underbrace{  v-\langle v , u_{1} \rangle u_{1}-\dots-\langle v , u_{n} \rangle u_{n} }_{ w }.
\end{align}
$$

É fácil ver que $u \in U$ (pois é uma combinação linear de uma base de $U$). Além disso, observe que para cada $u_{j}$ em $(u_{1},\dots,u_{n})$, que é ortonormal, tem-se

$$
\begin{align}
\langle w , e_{j} \rangle &  = \langle v-\langle v , u_{1} \rangle u_{1}-\dots-\langle v , u_{n} \rangle u_{n} , e_{j} \rangle \\
 & =\langle v , e_{j} \rangle -\langle v , e_{j} \rangle \\
 & =0.
\end{align}
$$

O fato de $w$ ser ortogonal a todos os $e_{j}$ implica que $w$ é ortogonal a todos os vetores em $U$ (pois os $e_{j}$ formam uma base de $U$). Logo, $w \in U^{\perp}$. Sendo assim, escrevemos $v=u+w$, com $u \in U$ e $w \in U^{\perp}$, para um vetor  $v$ arbitrário de $V$, o que mostra que $V=U+U^{\perp}$.

Para completar a prova, suponha $u \in U\cap U^{\perp}$. Note que, por um lado, $u \in U^{\perp}$ e, portanto, é ortogonal a todo vetor em $U$. Mas, por outro lado, $u \in U$, implicando que $u$ é ortogonal a si mesmo, ou seja

$$
\langle u , u \rangle= 0.
$$

Mas isso faz com que $u = 0$ (lembre-se do item 1 de [](#def-produto-interno)). Portanto, $U\cap U^{\perp}=\{ 0 \}$, concluindo que $V=U\oplus U^{\perp}$.

:::

:::{prf:corollary} Complemento do complemento

Seja $U$ um subespaço de $V$, então

$$
U=(U^{\perp})^{\perp}.
$$

:::

:::{prf:proof}

Começamos mostrando $U\subseteq (U^{\perp})^{\perp}$. Seja $u \in U$, pela definição de $U^{\perp}$ temos que $\langle u , v \rangle= 0$ para todo $v \in U^{\perp}$. Logo, $u$ é ortogonal a todo vetor em $U^{\perp}$, implicando que $u \in (U^{\perp})^{\perp}$.

Para mostrar $(U^{\perp})^{\perp}\subseteq U$, suponha $v \in (U^{\perp})^{\perp}$. Como, em particular, $v \in V$, [](#teo-soma-direta-complemento) garante que podemos escrever $v=u+w$, com $u \in U$ e $w \in U^{\perp}$. Assim, temos $v-u=w \in U^{\perp}$. Mas, note que temos $v \in (U^{\perp})^{\perp}$ e $u \in (U^{\perp})^{\perp}$ (pela inclusão $U\subseteq (U^{\perp})^{\perp}$ provada anteriormente), logo, $v-u \in U^{\perp}\cap(U^{\perp})^{\perp}$. Ou seja, isso nos diz que $v-u$ é ortogonal a si mesmo (pelo mesmo raciocínio utilizado na demonstração de [](#teo-soma-direta-complemento)), implicando que $v-u=0$. Sendo assim, $v=u \in U$, mostrando que $(U^{\perp})^{\perp}\subseteq U$ e, consequentemente, a igualdade $U = (U^{\perp})^{\perp}$.

:::
