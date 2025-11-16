---
title: Autovetores e Autovalores
subject: Fundamentos
---

Os conceitos de autovalores e autovetores são um dos mais centrais na Álgebra Linear, possuindo inúmeras consequências e aplicações. Aqui, voltaremos nossa atenção para o estudo dos operadores lineares (transformações lineares de um espaço vetorial para ele mesmo), em particular, subespaços do espaço domínio com propriedades especiais em relação a um dado operador.

Lembre-se que $\mathcal{L}(V)$ denota o conjunto dos operadores lineares em um espaço vetorial $V$ de dimensão finita.

### Noções iniciais - Subespaços invariantes

:::{prf:definition} Subespaço invariante

Seja $T \in \mathcal{L}(V)$ e $U$ um subespaço de $V$. Dizemos que $U$ é ***invariante*** sobre $T$ quando para todo $u \in U$ temos $Tu \in U$.

:::

Um subespaço invariante é um subespaço "fechado" sobre um operador $T$, todos os vetores desse subespaço são levados por $T$ em vetores também desse subespaço.

É comum denotarmos $T|_{U}$ para o operador $T$ restrito ao subespaço $U$ como domínio, ou seja, $T|_{U} \in \mathcal{L}(U,V)$ com $U \subseteq V$ e a transformação dada por $T$. Nesse sentido, $U$ é um subespaço invariante sobre $T$ quando $T|_{U}$ é um operador em $U$ ($T|_{U} \in \mathcal{L}(U)$).

:::{prf:example} Exemplos de subespaços invariantes

Exemplos triviais de subespaços invariantes são $\{ 0 \}$ e o próprio $V$. Além desses, $N(T)$ e $\mathrm{Im}(T)$ também são invariantes: Se $u \in N(T)$ temos $Tu=0 \in N(T)$; se $u \in \mathrm{Im}(T)$, temos $Tu \in \mathrm{Im}(T)$ (pela própria definição da imagem de $T$).

Em um caso menos óbvio, mas ainda fácil de enxergar, se $T \in \mathcal{L}(\mathcal{P}_{n})$ é o operador derivada, todos os subespaço de $\mathcal{P}_{n}$ da forma $\mathcal{P}_{i}$, com $i \leq n$, são invariantes sobre $T$ (afinal, se $p \in \mathcal{P}_{i}$ então $p$ possui grua máximo $i$. A derivada de $p$ também possuirá grau máximo $i$).

:::

### Autovetores e autovalores

O estudo dos autovetores e autovalores se inicia com o enfoque em subespaços invariantes de dimensão 1.

:::{prf:remark} Formato de subespaços de dimensão 1

Pelas definições de dimensão e base, um subespaço de dimensão 1 consiste no conjunto dos múltiplos escalares de um vetor não nulo. Seja $v \in V$ um vetor não nulo, o conjunto $U=\{ \alpha u: \alpha \in \mathbb{R} \}$ é um subespaço de dimensão 1, e todo subespaço de $V$de dimensão 1 será dessa forma para algum $v \in V$ não nulo.

:::

Veja que se um subespaço $U \subseteq V$ de dimensão 1 é invariante sobre $T \in \mathcal{L}(V)$ e $u \in V$ é uma base desse subespaço, então $Tu$ deve corresponder a um múltiplo escalar de $u$. Ou seja,

$$
Tu=\lambda u, \quad \lambda \in \mathbb{R}.
$$

Reciprocamente, se $u \in V$ é não nulo e tal que $Tu = \lambda u$, para algum $\lambda \in \mathbb{R}$, então o subespaço $U=\{ \alpha u: \alpha \in \mathbb{R} \}$ é um subespaço invariante de dimensão 1 com relação à $T$.

Essa noção nos leva à seguinte definição:

:::{prf:definition} Autovetor e autovalor

Sejam $T \in \mathcal{L}(V)$ e $\lambda \in \mathbb{R}$. Se existe $v \in V$ não nulo[^1] tal que

$$
Tv=\lambda v,
$$

então $v$ é dito um ***autovetor*** de $T$. O escalar $\lambda$ é chamado de ***autovalor*** associado a $v$.

:::

[^1]: A restrição de que $v$ seja não nulo provém do fato de que caso $v=0$, para qualquer $\lambda \in \mathbb{R}$ teríamos $Tv=T0=0=\lambda0$, então $0$ seria sempre autovetor de qualquer autovalor $\lambda$. Essa restrição remove esse caso trivial e torna a definição mais "limpa", focando somente nos casos relevantes.

Chamamos o subespaço invariante de dimensão 1 gerado por $v$ de ***autoespaço*** associado a $v$. Note que todo vetor pertencente ao autoespaço de $v$ (ou seja, os múltiplos de $v$) também será um autovetor associado ao mesmo autovalor $\lambda$. Se pensarmos no caso do $\mathbb{R}^{n}$, todo autoespaço de um operador linear corresponde a uma reta (a gerada pelo autovetor correspondente) que é preservada (mantida no lugar) com a aplicação do operador. 

Observe também que não é feita nenhuma restrição em relação ao valor de $\lambda$. Em particular, quando existem autovetores associados ao autovalor $\lambda=0$, o operador não será invertível, pois o seu núcleo é não trivial (lembre-se que autovetores são não nulos por definição).

Um exemplo trivial de autovetores e autovalores provém do operador identidade, $I \in \mathcal{L}(V)$. Para todo $v \in V$ temos $Iv=v$, logo, todo vetor do espaço $V$ é um autovetor de $I$, com autovalor associado igual a 1.

Antes de partirmos para um exemplo prático, considere a seguinte observação:

:::{prf:observation}
:label: equivalencia-autovetores

Sejam $T\in \mathcal{L}(V)$, ${} v \in V {}$ e $\lambda \in \mathbb{R}$, temos a seguinte equivalência:

$$
\begin{align}
Tv=\lambda v  & \iff Tv-\lambda v  =0 \\
 & \iff Tv-\lambda Iv=0 \\
 & \iff (T-\lambda I)v=0.
\end{align}
$$

A última igualdade nos diz que $v$ está no núcleo do operador $(T-\lambda I)$. Para que $v$ seja um autovetor associado ao autovalor $\lambda$, a definição exige que $v$ seja não nulo. Logo, perceba que $v$ será tal autovetor se, e somente se, o operador $(T-\lambda I)$ não for injetivo (consequentemente, [não sobrejetivo e não invertível](#teo-invertibilidade-em-operadores)), caso contrário teríamos $N(T-\lambda I)=\{ 0 \}$, não havendo nenhum $v$ não nulo que satisfaça a primeira igualdade. Em particular, os elementos não nulos do núcleo de $(T-\lambda I)$ irão corresponder a todos os autovetores associados ao autovalor $\lambda$.

:::

É através dessa observação e do [](#teo-invertibilidade-matriz) que encontramos/calculamos os autovetores e autovalores de um operador linear (lembre-se que [toda transformação linear está associada a uma matriz](./transformacoes-e-matrizes.md)).

:::{prf:example} Encontrando os autovalores e autovetores de um operador

Considere o operador linear do $\mathbb{R}^{2}$ dado pela seguinte matriz (na base canônica):

$$
T=\begin{bmatrix}
2 & 0 \\
0 & 1/2
\end{bmatrix}
$$

Pela estrutura diagonal de $T$, já é evidente que os vetores $(1,0)$ e $(0,1)$ são autovetores, com autovalores associados $2$ e $1/2$, respectivamente (lembre-se que cada coluna da matriz corresponde a imagem do respectivo vetor da base canônica). Mas vamos mostrar qual a abordagem adotada para encontrar os autovalores e autovetores em um caso geral, onde normalmente não é evidente apenas analisando a matriz. Aproveitaremos para discutir questões sobre a existência e a quantidade de autovalores de um operador.

Considere um $\lambda \in \mathbb{R}$. Pela [](#equivalencia-autovetores), se existe um autovetor $v \in V$ (nesse caso, $V = \mathbb{R}^{2}$) associado a $\lambda$, então o operador $(T - \lambda I)$ não pode ser invertível. Matricialmente, utilizando o [](#teo-invertibilidade-matriz), o que devemos ter é que 

$$
\det(\begin{bmatrix}
2 & 0 \\ 
0 & 1/2
\end{bmatrix}-\lambda \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix})=0.
$$

Ou seja,

$$
\det(\begin{bmatrix}
2 - \lambda & 0 \\
0 & 1/2-\lambda
\end{bmatrix})=0.
$$

Ao calcularmos o determinante, obtemos

$$
(2-\lambda)(1/2-\lambda)-0=0
$$

$$
\iff \lambda^{2}-\frac{5}{2}\lambda+1=0
$$

O polinômio $\lambda^{2}-\frac{5}{2}\lambda+1$ é chamado de ***polinômio característico*** da matriz/operador $T$ (mais geralmente, o polinômio característico de uma matriz/operador $T$ é $p(\lambda)=\det(T-\lambda I)$). Veja que a existência e quantidade de autovalores está intrinsecamente ligada a este polinômio. A condição $p(\lambda)=0$ nos diz que os autovalores de $T$ são correspondentes às raízes do polinômio característico. 

Logo, no caso geral, podemos ter no máximo $n$ autovalores distintos, pois o grau $n$ de $p(\lambda)$ vem do produto dos $n$ fatores da diagonal principal da matriz associada ao operador considerado (em um espaço de dimensão $n$). Além disso, a existência de autovalores **reais** depende de $p(\lambda)$ possuir raízes reais. Logo, quando estamos trabalhando somente com o corpo $\mathbb{R}$ para os escalares dos espaços vetoriais, operadores podem não possuir autovalores (esse é o caso do [](#exemplo-rotacao-do-plano)). O que não ocorre quando o corpo considerado é $\mathbb{C}$.

Então, sigamos: o próximo passo é encontrar as raízes de $p(\lambda)$, que serão os autovalores. Fazendo isso para $p(\lambda)=\lambda^{2}-\frac{5}{2}\lambda+1$ encontramos os autovalores $\lambda_{1} = 2$ e $\lambda_{2}=1/2$, como esperado da análise inicial. Para encontrar os autovetores, utilizamos novamente a [](#equivalencia-autovetores): se $v$ é um autovetor associado ao autovalor $\lambda$, então $(T-\lambda I)v=0$. Então, no nosso exemplo, para encontrar os autovetores associados ao autovalor $\lambda_{1}=2$, queremos $v=(x,y)$ tal que

$$
\begin{bmatrix}
2 -2 & 0 \\
0 & 1/2 -2
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=0
$$

Isso nos dá

$$
\begin{cases}
0x + 0y=0 \\
0x-\frac{3}{2}y=0,
\end{cases}
$$

um sistema possível e indeterminado (é natural que isso ocorra, pois como vimos, todos os múltiplos de um autovetor são autovetores com o mesmo autovalor associado. Logo, existem infinitos autovetores para um mesmo autovalor). Dele obtemos $y=0$, o que nos diz que o vetor solução $(x,y)$ é da forma $(x,0),\, x \in \mathbb{R}$. Aqui podemos escolher qualquer valor não nulo para $x$ (pois no caso $x = 0$ teríamos o vetor nulo), em particular, $x=1$, correspondendo ao vetor $(1,0)$ da análise inicial (mas qualquer outro valor não nulo de $x$ escolhido estaria correto).

Ao repetirmos o mesmo processo para $\lambda_{2}=1/2$, obtemos o vetor $(0,1)$ (mais uma vez, qualquer vetor não nulo da forma $(0,y)$ estaria correto). Veja que os autovetores encontrados nesse processo são "representantes" da reta que constitui o autoespaço associado. Assim, encontramos os autovalores e autovetores associados para o operador $T$ dado nesse exemplo, que neste caso existiam (eram reais).

Basicamente a mesma abordagem é empregada para qualquer matriz/operador, independentemente da dimensão ou da estrutura da matriz (desde que seja quadrada, é claro). Esse é o método mais utilizado para encontrar os autovalores e autovetores, mas também existe uma abordagem que não utiliza diretamente matrizes e determinantes: Neste caso em particular onde $T \in \mathcal{L}(\mathbb{R}^{2})$, considerando a relação $T(x,y)=\lambda(x,y)$ e substituindo $T(x,y)$ pelo formato da imagem de $T$ sobre um vetor $(x,y)$ obtemos um sistema linear. A análise das soluções desse sistema nos leva aos mesmos autovalores e autovetores encontrados com as matrizes. No entanto, essa abordagem não matricial se torna pouco prática quando o espaço vetorial possui dimensão maior que 2.

:::

Como já comentado algumas vezes, os autoespaços, do ponto de vista geométrico (pensando no $\mathbb{R}^{n}$), são retas preservadas após a aplicação do operador. No exemplo anterior, os autoespaços correspondem aos eixos do plano, com a reta das abcissas correspondendo ao autoespaço gerado por $(1,0)$ e a reta das ordenadas ao autoespaço gerado por $(0,1)$. O vídeo abaixo ilustra visualmente essa ideia. Veja que o comportamento geométrico da transformação $T=\begin{bmatrix}2 & 0 \\ 0 & 1/2\end{bmatrix}$ do exemplo anterior é de alongar a componente horizontal por um fator $2$ e comprimir a componente vertical por um fator $1/2$. Observe o eixo $x$, destacado em amarelo:

:::{figure} ./videos/autovetores.mp4
O eixo $y$ também é preservado, já que $(0,1)$ também é autovetor.
:::

Parte da importância prática de autovetores/autovalores se deve a essa noção de "preservação" sobre uma transformação.

Por último, temos um importante teorema e corolário envolvendo autovalores e autovetores.

:::{prf:theorem} Autovalores distintos possuem autovetores linearmente independentes
:label: teo-autovalores-distintos-autovetores-li

Seja $T\in \mathcal{L}(V)$. Se $\lambda_{1},\dots,\lambda_{m}$ são autovalores distintos de $T$ e $v_{1},\dots,v_{m}$ seus respectivos autovetores, então $(v_{1},\dots,v_{m})$ é linearmente independente. 

:::

:::{prf:proof}

Suponha que $(v_{1},\dots,v_{m})$ é linearmente dependente. [](#prop-aux-teo-li) garante que existe pelo menos um índice $i$ entre $1$ e $m$ tal que $v_{i} \in \text{span}(v_{1},\dots,v_{i-1})$. Escolha $k$ como sendo o menor dos índices que satisfaz essa condição. Logo, existem $a_{1},\dots,a_{k-1} \in \mathbb{R}$ tais que 

$$
v_{k}=a_{1}v_{1}+\dots+a_{k-1}v_{k-1.}
\label{eq:vk-no-span}
$$

Conforme cada $v_{j}$ é um autovetor com autovalor associado ${} \lambda_{j} {}$, aplicando $T$ em ambos os lados da equação obtemos

$$
\lambda_{k} v_{k}=a_{1}\lambda_{1}v_{1}+\dots+a_{k-1}\lambda_{k-1}v_{k-1}.
\label{eq:lambdakvk-no-span}
$$

Ao multiplicarmos a equação {eq}`eq:vk-no-span` por $\lambda_{k}$ e da equação resultante subtrairmos a equação {eq}`eq:lambdakvk-no-span`, obtemos

$$
0=a_{1}(\lambda_{k}-\lambda_{1})v_{1}+\dots+a_{k-1}(\lambda_{k}-\lambda_{k-1})v_{k-1}.
$$

Note que pela escolha de $k$ devemos ter $(v_{1},\dots,v_{k-1})$ linearmente independente. Logo, cada escalar $a_{i}(\lambda_{k}-\lambda_{i})$ na equação acima deve ser igual a zero. Uma vez que, por hipótese, cada autovalor é distinto dos demais, temos $\lambda_{k} - \lambda_{i} \neq 0$ para todo $i \in \{ 1,\dots,k-1 \}$. Assim, a única possibilidade restante é que $a_{1}=\dots=a_{k-1}=0$. Mas, retornando a {eq}`eq:vk-no-span`, isso implicaria que $v_{k}=0$, uma contradição ao fato de que $v_{k}$ é um autovetor (por definição não nulo). Portanto, $(v_{1},\dots,v_{m})$ deve ser linearmente independente.

:::

:::{prf:corollary}

Seja $T \in \mathcal{L}(V)$. $T$ possui no máximo $\dim V$ autovalores distintos. 

:::

:::{prf:proof}

Sejam $\lambda_{1},\dots,\lambda_{m}$ autovalores distintos de $T$ com $v_{1},\dots,v_{m}$ respectivos autovetores associados. Pelo [teorema anterior](#teo-autovalores-distintos-autovetores-li), $(v_{1},\dots,v_{m})$ é linearmente independente. [](#teo-dim-subespaco-menor-ou-igual-dim-espaco) garante que $\dim [\text{span}(v_{1},\dots,v_{m})] \leq \dim V$. Em particular, a dimensão do subespaço $\text{span}(v_{1},\dots,v_{m})$ é $m$, pois os autovetores são linearmente independentes. Portanto, $m \leq \dim V$.

:::
