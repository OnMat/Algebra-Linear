---
title: Teorema Espectral
subject: Tópicos Avançados
---

O *Teorema Espectral* é um importante resultado na Álgebra Linear, diz respeito à existência de uma base ortonormal formada por autovetores de um operador auto-adjunto para o espaço vetorial o qual ele atua. Dividiremos-o em dois casos que, na prática, são correspondentes: Operadores auto-adjuntos e matrizes simétricas. Naturalmente, o segundo caso é um corolário do primeiro.

### Teorema Espectral (Operadores auto-adjuntos)

:::{prf:theorem} Teorema Espectral para operadores auto-adjuntos
:label: teorema-espectral
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$, de dimensão finita e munido de produto interno, então existe uma **base ortonormal** de $V$ formada por **autovetores** de $T$.
:::

A sua prova requer dois resultados prévios.

:::{prf:lemma}
:label: lema1
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
:label: lema2
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

Agora, podemos provar o Teorema Espectral.

:::{prf:proof} Teorema Espectral para operadores auto-adjuntos 
A prova se dá por indução sobre a dimensão de $V$. Consideremos $dim\;V = n$.

Como caso base, se $n=1$, qualquer ${} v\in V-\{ 0_{V} \} {}$ forma uma base do espaço. Naturalmente, $\left\{  \frac{v}{\lvert |v| \rvert}  \right\}$ é uma base ortonormal de $V$. Ademais, também é formada por um autovetor, uma vez que se $T(v)\in V$, então $T(v)=\lambda v$, para algum $\lambda \in \mathbb{R}$, dado que $\{ v \}$ é uma base.

Agora, considere $n>1$ e suponha que o Teorema é válido para todo espaço com dimensão menor que $n$. O [Lema 2](#lema2) garante que existe um autovetor de $T$ (em particular, unitário) $v_{1}\in V$, associado a um autovalor real $\lambda_{1}$. Seja $U=[v_{1}]$, temos então que $dim\,U^{\perp}=dim\,V-dim\,U=n-1<n$. Além disso, seja $u \in U$, $u=\alpha v_{1}$ e $T(\alpha v_{1})=\alpha T(v_{1})=\alpha \lambda_{1}v_{1}\in U$. Logo, $U$ é $T$-invariante. Consequentemente, pelo [Lema 1](#lema1), $U^{\perp}$ também é $T$-invariante.

Dado que $dim\,U^{\perp}<n$ e ${} U^{\perp} {}$ é $T$-invariante, vale a hipótese de indução. Logo, existe uma base ortonormal $\{ v_{2},\dots ,v_{n} \}$ de $U^{\perp}$ formada por autovetores de $T$. Naturalmente, como $V=U \oplus U^{\perp}$, $\{ v_{1},v_{2},\dots,v_{n} \}$ é uma base ortonormal de $V$ formada por autovetores de $T$.
:::

Verifica-se sem muita dificuldade que, em espaços vetoriais reais, a recíproca do Teorema Espectral é verdadeira: Se existe uma base ortonormal formada por autovetores de $T$, então $T$ é auto-adjunto.

### Teorema Espectral para matrizes simétricas

:::{prf:corollary} Teorema Espectral para matrizes simétricas
Seja $A\in M_{n}(\mathbb{R})$ uma matriz simétrica, então existe uma matriz $P\in M_{n}(\mathbb{R})$ ortogonal tal que $D=P^{T}AP$, onde $D$ é uma matriz **diagonal** constituída dos autovalores de $A$.
:::

```{admonition} Demonstração
:class: dropdown
Seja $T\in \mathcal{L}(V)$ tal que $A=[T]_{c}$, onde $c$ é a base canônica. Como $A$ é simétrica e a base canônica é ortonormal, então $T$ é auto-adjunta. Logo, do [Teorema Espectral](#teorema-espectral) sabemos que existe uma base $\beta=\{ v_{1},\dots,v_{n} \}$ de $V$ formada por autovetores de $T$. Seja $T(v_{i})=\lambda_{i}v_{i}$ ($i=1,2,\dots,n$), então
$$
D=[T]_{\beta}=\begin{pmatrix}
\lambda_{1} & 0 & \dots & 0 \\
0 & \lambda_{2} & \dots & 0 \\
0 & 0 & \ddots & 0 \\
0 & 0 & \dots & \lambda_{n}
\end{pmatrix}.
$$
Além disso, $D=P^{-1}AP$, onde $P$ é a matriz mudança de base de $\beta$ para $c$. Dado que $\beta$ é ortonormal, então $P$ é ortogonal. Ou seja, $P^{-1}=P^{T}$.
```

O fato de podermos garantir que matrizes simétricas podem ser diagonalizadas e sabermos como encontrar a matriz diagonal tem grande aplicação prática e computacional. Vejamos como exemplo o cálculo de potências de matrizes ($A^n$).

Seja $A=\begin{pmatrix}1 & 2 \\ 2 & -2\end{pmatrix}$, encontremos $A^{n}$ ($n\in \mathbb{N}$). Primeiramente, note que $A^{T}=A$. A ideia então é diagonalizar $A$ utilizando o teorema espectral, de maneira que podemos determinar $A^{n}$ em um formato mais simples. Começamos calculando os autovalores de $A$, de modo a determinar os autovetores associados e posteriormente uma base ortonormal formada por eles:

$$
\det \begin{pmatrix}
1-\lambda & 2 \\
2 & -2-\lambda
\end{pmatrix}=0 \implies (1-\lambda)(-2-\lambda)-4=0
$$

Encontrando $\lambda_{1}=-3$ e $\lambda_{2}=2$. Para $\lambda_{1}$ temos:

$$
\begin{pmatrix}
1 & 2 \\
2 & -2
\end{pmatrix}\begin{pmatrix}
x \\
y
\end{pmatrix}=-3 \begin{pmatrix}
x \\
y
\end{pmatrix}
$$

Resolvendo o sistema linear associado encontramos o autovetor ${} v_{1}=(1,-2) {}$. Analogamente para $\lambda_{2}$:

$$
\begin{pmatrix}
1 & 2 \\
 2 & -2
\end{pmatrix} \begin{pmatrix}
x \\
y
\end{pmatrix}=2\begin{pmatrix}
x \\
y
\end{pmatrix}
$$

Encontrando ${} v_{2}=(2,1) {}$. Logo, a base $\{ (1,-2),(2,1) \}$ de $\mathbb{R}^{2}$ é formada por autovetores de $A$. Note que, como são associados a autovalores distintos,  $v_{1}$ e $v_{2}$ são ortogonais, restando apenas normalizá-los para que obtenhamos uma base ortonormal de autovetores. Portanto,

$$
\beta =\left\{  \left( \frac{1}{\sqrt{ 5 }},\frac{-2}{\sqrt{ 5 }} \right),\left( \frac{2}{\sqrt{ 5 }},\frac{1}{\sqrt{ 5 }} \right)  \right\}
$$

é uma base ortonormal formada por autovetores de $A$.

Consequentemente, a matriz

$$
[I]^{\beta}_{c}=P=\begin{pmatrix}
\frac{1}{\sqrt{ 5 }} & \frac{2}{\sqrt{ 5 }} \\
\frac{-2}{\sqrt{ 5 }} & \frac{1}{\sqrt{ 5 }}
\end{pmatrix}
$$

é ortogonal, logo $P^{-1}=P^{T}$. Daí seque que ${} A=PDP^{T} {}$. Finalmente, observe que

$$
\begin{align*}
A^{2}&=(PDP^{T})(PDP^{T})=PD^{2}P^{T} \\
A^{3}&=A^{2}A=(PD^{2}P^{T})(PDP^{T})=PD^{3}P^{T} \\
&\,\,\,\vdots \\
A^{n}&=PD^{n}P^{T}
\end{align*}
$$

Concluindo:

$$
A^{n}=\begin{pmatrix}
\frac{1}{\sqrt{ 5 }} & \frac{2}{\sqrt{ 5 }} \\
\frac{-2}{\sqrt{ 5 }} & \frac{1}{\sqrt{ 5 }}
\end{pmatrix}\begin{pmatrix}
(-3)^{n} & 0 \\
0 & 2^{n}
\end{pmatrix}\begin{pmatrix}
\frac{1}{\sqrt{ 5 }} & \frac{-2}{\sqrt{ 5 }} \\
\frac{2}{\sqrt{ 5 }} & \frac{1}{\sqrt{ 5 }} 
\end{pmatrix}.
$$

