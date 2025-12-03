---
title: Adjunta
subject: Tópicos Avançados
---

Quando estamos trabalhando com dois espaços vetoriais $V$ e $W$ munidos de produto interno, podemos associar a cada transformação linear de $V$ para $W$ uma transformação linear de $W$ para $V$ que possui algumas propriedades interessantes. Essa transformação é chamada de ***adjunta*** de $T$ e serve de alicerce para um dos principais resultados da Álgebra Linear, o [Teorema Espectral](teorema-espectral.md).

### Conceitos iniciais - Funcionais lineares

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
:label: teo-riesz

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

para todo $v \in V$. Em particular, se tomarmos $v = u-u'$ teríamos $\langle u-u' , u-u' \rangle=0$, implicando que $u-u' = 0$, pela [propriedade 1 do produto interno](#def-produto-interno). Ou seja, $u=u'$, mostrando a unicidade de $u$.

:::

### Definição e exemplo

A definição de adjunta tem uma construção um pouco mais sofisticada, onde utilizamos o [](#teo-riesz).

:::{prf:definition} Adjunta
:label: def-adjunta

Sejam $V$ e $W$ espaços vetoriais munidos de produto interno e $T \in \mathcal{L}(V,W)$. A ***adjunta*** de $T$, denotada por $T^{*}$, é a função de $W$ para $V$ definida da seguinte forma: Fixe $w \in W$ e considere o funcional linear sobre $V$ que mapeia $v \in V$ para $\langle Tv , w \rangle$. $T^{*}w$ será o único vetor de $V$ que representa esse funcional linear como um produto interno em $V$, garantido pelo [](#teo-riesz). Isto é, $T^{*}w \in V$ é o único tal que

$$
\langle Tv , w \rangle= \langle v , T^{*}w \rangle
$$

para todo $v \in V$.

:::

É importante perceber bem como é feita essa definição. Primeiramente, note que consideramos uma transformação $T \in \mathcal{L}(V,W)$ qualquer, é a partir dela que construímos a função $T^{*}$ associada. Então, fixando um vetor $w \in W$, através da construção feita associamos a ele um único vetor $T^{*}w$, com a propriedade de que $\langle Tv , w \rangle=\langle v , T^{*}w \rangle$ para todo $v \in V$ (note que na esquerda temos o produto interno de $W$, enquanto na direita temos o produto interno em $V$). Como o vetor $w$ considerado é arbitrário, o que fazemos é associar a cada $w \in W$, um **único** vetor $T^{*}w$ em $V$. Assim, temos uma função $T^{*}$ de $W$ para $V$. Em particular, essa função possui uma propriedade muito importante: 

$$
\langle Tv , w \rangle = \langle v , T^{*}w \rangle,
\label{eq:igualdade-adjunta}
$$

para quaisquer $v \in V$ e $w \in W$.

Na prática, podemos pensar na adjunta como uma "inversa em relação ao produto interno". Mas, claro, não é exatamente isso em um sentido técnico. 

Antes de prosseguirmos, devemos constatar um fato essencial sobre essa nova função que definimos.

:::{prf:proposition} A adjunta é linear

A adjunta de uma transformação linear também é uma transformação linear. Mais simbolicamente, se $T\in \mathcal{L}(V,W)$ então ${} T^{*} \in \mathcal{L}(W,V) {}$.

:::

:::{prf:proof}
:label: prova-linearidade-adjunta

Consideremos $w,w' \in W$ e $a \in \mathbb{R}$. Veja que para todo $v \in V$ temos

$$
\begin{align}
\langle Tv , w+w' \rangle & =\langle Tv , w \rangle+\langle Tv , w' \rangle \\
 & =\langle v , T^{*}w \rangle+\langle v , T^{*}w' \rangle \\
 & = \langle v , T^{*}w+T^{*}w' \rangle.
\end{align}
$$

Logo, o vetor dado por $T^{*}w + T^{*}w'$ satisfaz $\langle Tv , w+w' \rangle=\langle v , T^{*}w+T^{*}w' \rangle$ para todo $v \in V$. Mas, pelo [](#teo-riesz) e pela definição da adjunta, esse vetor é único e corresponde exatamente a $T^{*}(w+w')$. Isto é, $T^{*}(w+w')=T^{*}w+T^{*}w'$, mostrando a aditividade da adjunta.

Além disso, veja que

$$
\begin{align}
\langle Tv , aw \rangle & =a\langle Tv , w \rangle \\
 & =a\langle v , T^{*}w \rangle \\
 & = \langle v , aT^{*}w \rangle.
\end{align}
$$

Pelo mesmo raciocínio empregado no caso da aditividade, temos $T^{*}(aw)=aT^{*}w$, mostrando a homogeneidade de $T^{*}$ e, portanto, sua linearidade.

:::

Vejamos como determinar algebricamente a adjunta de uma transformação linear.

:::{prf:example}

Vamos determinar a adjunta da transformação linear do $\mathbb{R}^{2}$
 para o $\mathbb{R}^{3}$ (produtos internos canônicos) dada por

$$
T(x,y) = (x+y, 2x+2y,3x+3y).
$$

Antes de partirmos diretamente para o objetivo, é importante ter uma noção geral do que está sendo feito. Quando queremos determinar uma transformação linear, no fim o que queremos é saber para quais vetores do contradomínio ela mapeia cada vetor de uma base fixada, sendo usual considerar a base canônica. 

Isso também vale para a adjunta, mas nesse caso costuma ser mais prático considerar um vetor genérico do domínio e, através da igualdade {eq}`eq:igualdade-adjunta`, determinar a sua imagem, assim determinando inteiramente a transformação. Dessa maneira, condensamos as informações que buscamos sobre as imagens de cada vetor da base canônica em uma coisa só. Mas, é claro, a abordagem de determinar a imagem de cada vetor da base separadamente também funciona.

Voltando ao exemplo, uma vez que $T\in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{3})$ então $T^{*} \in \mathcal{L}(\mathbb{R}^{3},\mathbb{R}^{2})$. Logo, consideramos ${} (a,b,c) {}$ como um vetor qualquer do $\mathbb{R}^{3}$ e devemos determinar $T^{*}(a,b,c)$ utilizando a igualdade entre os produtos internos (perceba que usaremos a informação sobre $T(x,y)$ fornecida). Em particular, consideramos $T^{*}(a,b,c)=(\alpha, \beta)$ e devemos determinar cada coordenada em função de $a,b$ e $c$. 

Note que podemos fixar $(1,0) \in \mathbb{R}^{2}$, uma vez que a igualdade {eq}`eq:igualdade-adjunta` vale para quaisquer vetores de $\mathbb{R}^{2}$ e $\mathbb{R}^{3}$. Assim, temos

$$
\begin{align}
\langle T(1,0) , (a,b,c) \rangle  & = \langle (1,2,3) , (a,b,c) \rangle\\
 & =a+2b+3c \\
 & =\langle (1,0) , T^{*}(a,b,c) \rangle \\
 & =\langle (1,0) , (\alpha,\beta) \rangle \\
 & =\alpha.
\end{align}
$$

Donde obtemos que $\alpha=a+2b+3c$. Similarmente, considerando o vetor $(0,1) \in \mathbb{R}^{2}$ temos

$$
\begin{align}
\langle T(0,1) , (a,b,c) \rangle  & = \langle (1,2,3) , (a,b,c) \rangle \\
 & = a+2b+3c \\
 & =\langle (0,1) , T^{*}(a,b,c) \rangle \\
 & =\langle (0,1) , (\alpha,\beta) \rangle \\
 & =\beta.
\end{align}
$$

Obtendo que $\beta$ também vale $a+2b+3c$. Portanto, determinamos que $T^{*}(a,b,c)=(a+2b+3c,a+2b+3c)$. 

Mas, ao considerar essa abordagem, é natural que fique a questão: Tal função $T^{*}$ encontrada dessa forma é de fato a adjunta de $T$, uma vez que consideramos somente dois vetores do domínio de $T$ (nesse caso, $(1,0)$ e $(0,1)$) e a [](#def-adjunta) diz respeito a todos os vetores do domínio de $T$? A resposta é afirmativa e a justificativa provém do fato que $(1,0)$ e $(0,1)$ formam uma base do domínio de $T$, que é $\mathbb{R}^{2}$. Se considerássemos um vetor qualquer $(x,y) \in \mathbb{R}^{2}$ no intuito de seguir rigorosamente a [](#def-adjunta), poderíamos reescrevê-lo como uma combinação linear de $(1,0)$ e $(0,1)$. Utilizando as propriedades de linearidade de $T$ e do produto interno, no fim obteríamos os mesmos resultados encontrados quando consideramos diretamente os vetores $(1,0)$ e $(0,1)$.

Portanto, essa abordagem de fixar vetores do domínio da transformação considerada para determinar sua adjunta funciona no caso geral, **contanto que os vetores fixados formem uma base do domínio**. Em particular, costuma ser mais prático fixar os vetores da base canônica, uma vez que os zeros e uns facilitam os cálculos.

:::

### Propriedades da adjunta

Utilizando a [](#def-adjunta) e a linearidade do produto interno, de maneira similar ao que é feito em [](#prova-linearidade-adjunta), é possível verificar as seguintes propriedades da adjunta:

:::{prf:property} Propriedades principais da adjunta

(**aditividade**) $(S+T)^{*}=S^{*}+T^{*}$, $\forall S,T \in \mathcal{L}(V,W)$;

(**homogeneidade**) $(aT)^{*}=aT^{*}$, $\forall a \in \mathbb{R}$ e $\forall T \in \mathcal{L}(V,W)$;

(**adjunta da adjunta**) $(T^{*})^{*}=T$, $\forall T \in \mathcal{L}(V,W)$;

(**adjunta da identidade**) $I^{*}=I$, onde $I$ é o operador identidade em $V$;

(**adjunta do produto**) $(ST)^{*}=T^{*}S^{*}$, $\forall T \in \mathcal{L}(V,W)$ e $\forall S \in \mathcal{L}(W,U)$.

:::

Além dessas propriedades fundamentais, temos relações importantes entre os núcleos e imagens de uma transformação e sua adjunta.

:::{prf:proposition}

Seja $T \in \mathcal{L}(V,W)$, valem as seguintes igualdades:

1. $N(T^{*})=\mathrm{Im}(T)^{\perp}$;
2. $\mathrm{Im}(T^{*})=N(T)^{\perp}$;
3. $N(T)=\mathrm{Im}(T^{*})^{\perp}$;
4. $\mathrm{Im}(T)=N(T^{*})^{\perp}$.

:::

:::{prf:proof}

Provaremos **1.** inicialmente. Seja $w \in W$, então

$$
\begin{align}
w \in N(T^{*})  & \iff T^{*}w=0 \\
 &  \iff \langle v , T^{*}w \rangle= 0,\;\forall v \in V \\
 &  \iff \langle Tv , w \rangle = 0, \; \forall v \in V \\
 &  \iff w \in \mathrm{Im}(T)^{\perp}.
\end{align}
$$

A partir de **1.** podemos obter as outras: ao tomarmos o complemento ortogonal em ambos os lados da igualdade obtemos **4.** Então, substituindo $T$ por $T^{*}$ em **1.** e **4.** obtemos **3.** e **2.**, respectivamente. 

:::
