---
title: Operadores Auto-Adjuntos
subject: Tópicos Avançados
---

Vejamos a definição e alguns resultados sobre ***operadores auto-adjuntos***, um caso particular de operador linear que é igual a sua adjunta. Os operadores auto-adjuntos são o objeto central do [*Teorema Espectral*](teorema-espectral.md), um dos principais resultados da Álgebra Linear e tópico subsequente.

:::{prf:definition} Operador auto-adjunto
:label: autoadjunto

Seja $V$ um espaço vetorial com produto interno e dimensão finita, dizemos que $T\in \mathcal{L}(V)$ é ***auto-adjunto*** se $\forall v,w\in V$ temos
$$
\langle Tv , w \rangle=\langle v , Tw \rangle.
$$
Ou seja, $\boxed{T=T^{*}}$.

:::

:::{prf:example} Reflexão em torno do eixo $x$
:label: exemplo-1-operador-auto-adjunto

Geometricamente, o operador $T\in \mathcal{L}(\mathbb{R}^{2})$ definido por $T(x,y)=(x,-y)$ descreve uma reflexão em torno do eixo $x$. Verifiquemos que ele é auto-adjunto.

Sejam $u=(u_{1},u_{2})$ e $v=(v_{1},v_{2})$ pertencentes ao $\mathbb{R}^{2}$, temos que

$$
\begin{align}
\langle Tu , v \rangle & =\langle (u_{1},-u_{2}) ,(v_{1},v_{2})  \rangle \\
 & =u_{1}v_{1}-u_{2}v_{2} \\
 & =\langle u ,T^{*}v  \rangle.
\end{align}
$$

Por outro lado, $\langle u , Tv \rangle=\langle (u_{1},u_{2}) , (v_{1},-v_{2}) \rangle=u_{1}v_{1}-u_{2}v_{2}=\langle Tu , v \rangle$. Logo, $T=T^{*}$, auto-adjunto.

A auto-adjunção significa que, de uma certa forma, o operador preserva o produto interno, e reflexões são bons exemplos disso.

:::

:::{prf:proposition}

Sejam $A$ e $B$ operadores auto-adjuntos e $\alpha \in \mathbb{R}$, então os operadores $(A+B)$ e $\alpha A$ também são auto-adjuntos.

:::

```{admonition} Demonstração
:class: dropdown

Utilizando as propriedades da adjunta:

$$
\begin{align}
&(A+B)^{*}=A^{*}+B^{*}=A+B \\
&(\alpha A)^{*}= \alpha A^{*}=\alpha A
\end{align}
$$


```

:::{prf:proposition}

Seja $T\in \mathcal{L}(V)$ auto-adjunto e um isomorfismo, então $T^{-1}$ também é auto-adjunto.

:::

```{admonition} Demonstração
:class: dropdown

Dada a propriedade que $(T^{-1})^{*}=(T^{*})^{-1}$, substituímos $T^{*}$ por $T$ (pois $T=T^{*}$), obtendo que
$$
(T^{-1})^{*}=T^{-1}.
$$
Logo, $T^{-1}$ é auto-adjunto.

```

:::{prf:proposition}
:label: autovetores-associados-a-autovalores-distintos-ortogonais
Seja $T \in \mathcal{L}(V)$ auto-adjunto, então autovetores associados a autovalores distintos são ortogonais.
:::

```{admonition} Demonstração
:class: dropdown
Sejam $v,w\in V$ autovetores associados a autovalores distintos $\lambda$ e $\mu$, respectivamente. Ou seja, $Tv=\lambda v$ e $Tw=\mu w$. Dado que $T$ é auto-adjunto, temos que $$
\langle Tv , w \rangle=\langle v , Tw \rangle.
$$
Logo, 
\begin{align}
\langle \lambda v ,  w \rangle &= \langle v , \mu w \rangle \\
\lambda \langle v , w \rangle &= \mu \langle v , w \rangle \\
(\lambda-\mu)\langle v , w \rangle &= 0
\end{align}

Como $\lambda \neq \mu$, então necessariamente $\langle v , w \rangle= 0$. Ou seja, $v$ e $w$ são ortogonais.
```

### Matrizes de operadores auto-adjuntos

Como é de se esperar, operadores auto-adjuntos possuem uma equivalência matricial. Tal equivalência relaciona-se com matrizes simétricas (ver {ref}`def-matriz-simetrica`).

:::{prf:theorem} Caracterização de operadores auto-adjuntos
:label: teorema1-autoadjunto

Seja $T\in \mathcal{L}(V)$, então $T$ é auto-adjunto se, e somente se, $[T]_\beta$ é simétrica, onde $\beta$ é uma base ortonormal de $V$.

:::

:::{prf:proof} Caracterização de operadores auto-adjuntos

Seja $\beta$ uma base ortonormal de $V$.

$(\implies):$ Se $T$ é auto-adjunto, então
$$
[T]_{\beta}=[T^{*}]_{\beta}=([T]_{\beta})^{T}.
$$
Portanto, $[T]_{\beta}$ é simétrica.

$(\impliedby):$ Se $[T]_{\beta}=([T]_{\beta})^{T}$, suponha que $\beta = \{ v_{1},\dots,v_{n} \}$. Logo, 
$$
\langle Tv_{i} , v_{j} \rangle=\langle Tv_{j} , v_{i} \rangle,
\label{eq:igualdade-prova-caracterizacao-op-auto-adjunto}
$$
para todo $i,j$, onde estas são as entradas de $[T]_\beta$ e $([T]_{\beta})^{T}$, respectivamente.

Sejam $u,v\in V$, pela definição de base temos que $u=\sum_{i}x_{i}v_{i}$ e $v=\sum_{j}y_{j}v_{j}$. Logo,

$$
\begin{align}
\langle u , Tv \rangle &= \left\langle  \sum_{i}x_{i}v_{i} , T\left( \sum_{j}y_{j}v_{j} \right)  \right\rangle \\
 &= \sum_{i}x_{i}\sum_{j}y_{j}\langle v_{i} , Tv_{j} \rangle \\
&= \sum_{i}x_{i}\sum_{j}y_{j}\langle Tv_{j} , v_{i} \rangle \\
&= \sum_{i}x_{i}\sum_{j}y_{j}\langle Tv_{i} , v_{j} \rangle,
\end{align} $$

onde na última igualdade usamos {eq}`eq:igualdade-prova-caracterizacao-op-auto-adjunto`.

Portanto, temos que 
$$
\langle u , Tv \rangle=\left\langle  \sum_{i}x_{i}Tv_{i} , \sum_{j}y_{j}v_{j}  \right\rangle=\left\langle  T\left( \sum_{i}x_{i}v_{i} \right) , \sum_{j}y_{j}v_{j}  \right\rangle=\langle Tu , v \rangle,
$$
concluindo que $T=T^{*}$.

:::

:::{prf:example}

Voltando ao operador do [](#exemplo-1-operador-auto-adjunto), vamos verificar sua auto-adjunção utilizando o [](#teorema1-autoadjunto).

Primeiro, escrevemos a matriz associada a ele na base canônica, a base ortonormal mais fácil de lidarmos:

$$
\begin{align}
T(1,0)&=(1,0) \\
T(0,1)&=(0,-1)
\end{align}
\implies [T]_{c}=\begin{bmatrix}
1 & 0 \\
0 & -1
\end{bmatrix}
$$

Como $([T]_{c})^{T}=[T]_{c}$, o [](#teorema1-autoadjunto) nos garante que $T$ é auto-adjunto. Já havíamos verificado tal fato no [](#exemplo-1-operador-auto-adjunto), mas note como o teorema nos proporciona um método mais direto de verificação (não precisamos nos preocupar em definir vetores arbitrários $u$ e $v$ nem verificar a forma do produto interno entre eles).

:::

### Positividade de operadores auto-adjuntos

Existem certos tipos de operadores auto-adjuntos que merecem uma atenção especial, pois a partir de suas propriedades obtemos alguns resultados que têm destaque no campo mais prático e aplicado da Álgebra Linear, como a resolução de sistemas lineares e métodos de aproximação numérica.

:::{prf:definition} Operador definido positivo

Seja $V$ um espaço vetorial com produto interno e dimensão finita, dado $T\in \mathcal{L}(V)$ auto-adjunto, dizemos que $T$ é *definido positivo* se $\forall v\in V$, com $v\neq 0$, temos

$$
\langle Tv , v \rangle>0
$$

e escrevemos $T>0$.

:::

:::{prf:example}

Considere o operador identidade em $\mathbb{R}^{2}$. Para $(x,y)\in \mathbb{R}^{2}$, com $(x,y)\neq (0,0)$, temos

$$
\begin{align}
\langle I(x,y) , (x,y) \rangle & =\langle (x,y) , (x,y) \rangle \\
 & =x^{2}+y^{2}>0
\end{align}
$$

Logo, $I$ é um operador definido positivo.

:::

Estendendo para considerar $v = 0$, temos a definição a seguir:

:::{prf:definition} Operador não negativo

Seja $V$ um espaço vetorial com produto interno e dimensão finita, dado $T\in \mathcal{L}(V)$ auto-adjunto, dizemos que $T$ é *não negativo* ou *semi-definido positivo* se $\forall v\in V$, temos

$$
\langle Tv , v \rangle\geq0
$$

e escrevemos $T\geq0$.

:::

No caso do exemplo anterior, é natural que ao incluirmos a possibilidade que $v=0$ verificamos que o operador identidade é não negativo, uma vez que ele já é positivo definido. De fato, todo operador positivo definido é não negativo, mas a recíproca não vale (podemos ter $\langle Tv , v \rangle=0$ mas $v\neq 0$).

Podemos também estender essas definições de maneira análoga para operadores *negativos* ($T<0$) e *não positivos* ($T\leq0$), mas existem operadores que não se enquadram em nenhum destes:

:::{prf:example} Operador indefinido

Considere a base ortonormal $\beta=\{ (1,0),(0,1) \}$ e $T(x,y)=(y,x),\forall(x,y)\in \mathbb{R}²$. Temos que:

$$
[T]_{\beta}=
\begin{bmatrix}
0 & 1 \\
1 & 0
\end{bmatrix}
$$
 
Observe que $[T]_{\beta}$ é simétrica, então o [](#teorema1-autoadjunto) garante que $T$ é auto-adjunto. Além disso,

$$
\langle T(x,y) , (x,y) \rangle=\langle (y,x) , (x,y) \rangle=yx+xy=2xy,\forall(x,y)\in \mathbb{R}²
$$
 
Note que, a depender dos valores de $x$ e $y$, $2xy$ pode ser positivo, negativo ou nulo. Portanto, $T$ é um *operador indefinido*.

:::

O teorema a seguir serve como base para uma extensão do [Teorema Espectral](/topicos/teorema-espectral) para transformações lineares quaisquer.

:::{prf:theorem} 
:label: pre-teorema-valores-singulares

Seja $T:V\to W$ uma transformação linear entre espaços vetoriais de dimensão finita e munidos de produto interno, os operadores lineares $T^{*}T:V\to V$ e $TT^{*}:W\to W$ são não negativos e possuem o mesmo posto de $T$ e $T^{*}$.

:::

:::{prf:proof}

Primeiramente, note que $(T^{*}T)^*=T^{*}T$ e $(TT^{*})^{*}=TT^{*}$. Logo, ambos são auto-adjuntos. Agora, considerando $v\in V$, temos

$$
\begin{align}
\langle T^{*}Tv , v \rangle  & =\langle Tv , Tv \rangle \\
 & =\lVert Tv \rVert ^{2} \\
 & \geq0
\end{align}
$$

Similarmente para $w\in W$, temos

$$
\begin{align}
\langle TT^{*}w ,w  \rangle  & = \langle T^{*}w , T^{*}w \rangle \\
 & =\lVert T^{*}w \rVert ^{2}  \\
 & \geq 0
\end{align}
$$

Concluindo que ambos são não negativos. 

Para o posto, observe que

$$
\begin{align}
w\in N(T^{*})  & \iff T^{*}w=0 \\
 & \iff \langle v , T^{*}w \rangle=0, \forall v\in V \\
 & \iff \langle Tv , w \rangle=0,\forall v\in V \\
 & \iff w\in \mathrm{Im}(T)^{\perp}.
\end{align}
$$

Ou seja, $N(T^{*})=\mathrm{Im}(T)^{\perp}$. 

Utilizando esse fato, mostremos que $N(T^{*}T)=N(T)$. Seja $v\in N(T)$, temos $T^{*}Tv=T^{*}0=0$, logo, $N(T)\subset N(T^{*}T)$. Reciprocamente,

$$
\begin{align}
v\in N(T^{*}T)  & \implies T^{*}Tv=0 \\
 & \implies Tv\in N(T^{*})=\mathrm{Im}(T)^{\perp} \\
 & \implies Tv\in(\mathrm{Im}(T)\cap \mathrm{Im}(T)^{\perp})=\{ 0 \} \\
 & \implies Tv=0
\end{align}
$$

Concluindo que $N(T^{*}T)\subset N(T)$ e, portanto, $N(T^{*}T)=N(T)$. Assim, utilizando o Teorema do Núcleo e Imagem,

$$
\dim V   = \dim N(T^{*}T)+\dim \mathrm{Im}(T^{*}T)
$$

$$
\begin{align} 
\implies\dim \mathrm{Im}(T^{*}T) & =\dim V-\dim N(T^{*}T) \\
 & =\dim V - \dim N(T) \\
 & =\dim \mathrm{Im}(T)
\end{align}
$$

Mostrando que o posto de $T^{*}T$ é o mesmo de $T$. Analogamente, obtemos que o posto de $TT^{*}$ é igual ao posto de $T^{*}$ (que é o mesmo de $T$).

:::

Observe que tais operadores são positivos definidos se, e somente se, $T$ é invertível.
