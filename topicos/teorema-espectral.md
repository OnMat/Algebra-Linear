---
title: Teorema Espectral
subject: Tópicos Avançados
---

O *Teorema Espectral* é um importante resultado na Álgebra Linear, diz respeito à existência de uma base ortonormal formada por autovetores de um operador auto-adjunto para o espaço vetorial o qual ele atua. Dividiremos-o em dois casos que, na prática, são correspondentes: Operadores auto-adjuntos e matrizes simétricas. Naturalmente, o segundo caso é um corolário do primeiro.

### Teorema Espectral (Operadores auto-adjuntos)

:::{prf:theorem} Teorema Espectral para operadores auto-adjuntos
:label: teorema-espectral
Para todo operador auto-adjunto $A:V\to V$, num espaço vetorial de dimensão finita munido de produto interno, existe uma base ortonormal $\{ u_{1},\dots,u_{n} \}\subset V$ formada por **autovetores** de $A$.
:::

A demonstração requer alguns resultados prévios.

:::{prf:lemma}
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$ munido de produto interno. Então autovetores associados a autovalores distintos são ortogonais.
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

:::{prf:lemma}
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$ munido de produto interno. Se $U$ é um subespaço $T$-invariante de $V$, então $U^{\perp}$ também o é. 
:::

```{admonition} Demonstração
:class: dropdown
Seja $u\in U$ e $w\in U^{\perp}$. Então, dado que $Tu \in U$ (pois $U$ é $T$-invariante), temos que
$$
\langle Tu , w \rangle=0.
$$
Por outro lado, dado que $T$ é auto-adjunto, $\langle Tu , w \rangle=\langle u , Tw \rangle$. Ou seja, $\langle Tw , u \rangle=0$, para todo $w \in U^{\perp}$ e $u\in U$. Isso implica que $Tw \in U^{\perp}$ e portanto $U^{\perp}$ é $T$-invariante.
```

:::{prf:lemma}
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$ de dimensão finita e munido de produto interno. Então, o conjunto de autovalores de $T$ é não-vazio e está constituído por números reais.
:::

```{admonition} Demonstração
:class: dropdown
Seja $\beta$ uma base ortonormal de $V$ e $dim\;V=n>0$. Como $T$ é auto-adjunto, então $[T]_{\beta}=A$ é uma matriz simétrica. O polinômio característico de $T$ é dado por ${} p_{A}(x)=\det(x I-A) {}$. Logo, $\lambda$ é autovalor de $T$ se, e somente se, $p_{A}(\lambda)=0$. Considere que $\lambda$ é uma raiz de $p_{A}(x)$ (cuja existência é garantida pelo *Teorema Fundamental da Álgebra*, podendo ser uma raiz real ou complexa), vamos mostrar então que $\lambda \in \mathbb{R}$.

Dado que $\det(\lambda I-A)=0$, então o sistema linear $AX=\lambda X$ possui infinitas soluções não nulas para $X$. Consideremos que
$$
Y=\begin{pmatrix}
y_{1} \\
y_{2} \\
\vdots \\
y_{n}
\end{pmatrix}
$$
é uma delas.

Escrevendo $AY=\lambda Y$ na forma de sistema linear, obtemos
$$
\sum_{j=1}^{n}A_{ij}y_{j}=\lambda y_{i}, \; (i=1,2,\dots,n).
$$
Então, multiplicando por $\overline{y_{i}}$, encontramos
$$
\sum_{j=1}^{n}A_{ij}y_{j} \overline{y_{i}}=\lambda y_{i} \overline{y_{i}}, \; (i=1,2,\dots,n).
$$
Dessa forma, somando estes resultados, obtemos
$$
\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}} = \lambda \sum_{i=1}^{n}y_{i}\overline{y_{i}}=\lambda \sum_{i=1}^{n}|y_{i}|^{2}.
\label{eq:igualdade}
$$
(note que $|y_{i}|$ representa o módulo de um número complexo, um valor real, logo o somatório $\sum |y_{i}|^{2} \in \mathbb{R}$).

Mostremos então que o somatório à esquerda das igualdades também pertence aos reais. Ou seja,
$$
\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}}=\overline{\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}}}.
$$
Utilizando as propriedades do conjugado e que $A$ é uma matriz real (logo $A_{ij}\in \mathbb{R}$ e $A_{ij}=\overline{A_{ij}}$), obtemos
$$
\overline{\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}}}=\sum_{i,j=1}^{n}\overline{A_{ij}}\overline{y_{j}}y_{i}=\sum_{i,j=1}^{n}A_{ij}\overline{y_{j}}y_{i}.
$$
Como $A$ é simétrica ($A_{ij}=A_{ji}$), podemos trocar os índices $i$ e $j$ de lugar no somatório à direita das igualdades, obtendo
$$
\overline{\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}}}=\sum_{i,j=1}^{n}A_{ij}y_{j}\overline{y_{i}},
$$
o que procurávamos. 

Assim, dado que os somatórios nas igualdades {eq}`eq:igualdade` são reais, podemos concluir que $\lambda \in \mathbb{R}$.
```
