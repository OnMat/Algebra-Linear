---
title: Operadores Auto-Adjuntos
subject: Tópicos Avançados
---

Vejamos a definição e alguns resultados sobre *operadores auto-adjuntos*, um tipo de operador normal. Os operadores auto-adjuntos são o objeto central do [*Teorema Espectral*](teorema-espectral.md), um dos principais resultados da Álgebra Linear e tópico subsequente.

:::{prf:definition}
:label: autoadjunto

Seja $V$ um espaço vetorial com produto interno, dizemos que $T\in \mathcal{L}(V)$ é *auto-adjunto* se $\forall v,w\in V$ temos
$$
\langle Tv , w \rangle=\langle v , Tw \rangle.
$$
Ou seja, $\boxed{T=T^{*}}$.

:::

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

Como é de se esperar, operadores auto-adjuntos possuem uma equivalência matricial.

:::{prf:remark} Matriz simétrica

Uma matriz é dita *simétrica* quando é igual a sua transposta. Isto é, seja $A \in \mathcal{M}_{n}(\mathbb{R})$, $A$ é simétrica se, e somente se, $A^{T}=A$.

:::

:::{prf:theorem} Caracterização de operadores auto-adjuntos

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
\label{eq:igualdade}
$$
para todo $i,j$, e estas são as entradas de $[T]_\beta$ e $([T]_{\beta})^{T}$, respectivamente.

Sejam $u,v\in V$, então, pela definição de base, $u=\sum_{i}x_{i}v_{i}$ e $v=\sum_{j}y_{j}v_{j}$. Portanto,

$$
\begin{align}
\langle u , Tv \rangle &= \left\langle  \sum_{i}x_{i}v_{i} , T\left( \sum_{j}y_{j}v_{j} \right)  \right\rangle \\
 &= \sum_{i}x_{i}\sum_{j}y_{j}\langle v_{i} , Tv_{j} \rangle \\
&= \sum_{i}x_{i}\sum_{j}y_{j}\langle Tv_{j} , v_{i} \rangle \\
&= \sum_{i}x_{i}\sum_{j}y_{j}\langle Tv_{i} , v_{j} \rangle,
\end{align} $$

(na última igualdade usamos {eq}`eq:igualdade`).

Portanto, temos que 
$$
\langle u , Tv \rangle=\left\langle  \sum_{i}x_{i}Tv_{i} , \sum_{j}y_{j}v_{j}  \right\rangle=\left\langle  T\left( \sum_{i}x_{i}v_{i} \right) , \sum_{j}y_{j}v_{j}  \right\rangle=\langle Tu , v \rangle,
$$
concluindo que $T=T^{*}$.

:::
