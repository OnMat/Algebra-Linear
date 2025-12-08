---
title: Teorema Espectral
subject: Tópicos Avançados
---

O *Teorema Espectral* é um importante resultado na Álgebra Linear, diz respeito à existência de uma base ortonormal formada por autovetores de um operador auto-adjunto para o espaço vetorial o qual ele atua. Dividiremos-o em dois casos que, na prática, são correspondentes: Operadores auto-adjuntos e matrizes simétricas. O segundo caso surge naturalmente como um corolário do primeiro, devido a relação entre operadores e matrizes.

### Teorema Espectral (Operadores auto-adjuntos)

:::{prf:theorem} Teorema Espectral para operadores auto-adjuntos
:label: teorema-espectral
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$, de dimensão finita e munido de produto interno, então existe uma **base ortonormal** de $V$ formada por **autovetores** de $T$.
:::

A sua prova requer dois resultados prévios. **Em ambos, $T$ é um operador linear auto-adjunto sobre um espaço vetorial $V$ de dimensão finita e munido de produto interno**.

:::{prf:lemma}
:label: lema1
Se $U$ é um subespaço $T$-invariante de $V$, então $U^{\perp}$ é $T$-invariante. 
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
Os autovalores de $T$ são reais.
:::

```{admonition} Demonstração
:class: dropdown
Considere $\beta$ uma base ortonormal de $V$ e $\dim V = n>0$. Como $T$ é auto-adjunto, então $[T]_{\beta}=A$ é uma matriz simétrica (pelo [](#teorema1-autoadjunto)). 

Sabemos que $\lambda$ é autovalor de $T$ se, e somente se, $p_{A}(\lambda)=0$, onde ${} p_{A}(x)=\det(x I-A) {}$ é o polinômio característico de $T$. Considere que $\lambda$ é uma raiz de $p_{A}(x)$ (cuja existência é garantida pelo *Teorema Fundamental da Álgebra*, podendo ser uma raiz real ou complexa), vamos mostrar então que $\lambda \in \mathbb{R}$.

Dado que $\det(\lambda I-A)=0$, então o sistema linear $AX=\lambda X$ possui infinitas soluções não nulas para $X$. Consideremos que
$$
Y=\begin{bmatrix}
y_{1} \\
y_{2} \\
\vdots \\
y_{n}
\end{bmatrix}
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
A prova se dá por indução sobre a dimensão de $V$. Consideremos $\dim V = n$.

Como caso base, se $n=1$, qualquer ${} v\in V-\{ 0 \} {}$ forma uma base do espaço. Naturalmente, $\left\{  \frac{v}{\lvert |v| \rvert}  \right\}$ é uma base ortonormal de $V$. Ademais, também é formada por um autovetor, uma vez que se $T(v)\in V$, então $T(v)=\lambda v$, para algum $\lambda \in \mathbb{R}$, dado que $\{ v \}$ é uma base.

Como hipótese de indução, considere $n>1$ e suponha que o Teorema vale para todo espaço com dimensão menor que $n$. O [Lema 2](#lema2) garante que existe um autovetor de $T$ (em particular, unitário) $v_{1}\in V$, associado a um autovalor real $\lambda_{1}$. Seja $U=[v_{1}]$, temos então que $\dim U^{\perp}= \dim V - \dim U=n-1<n$. Além disso, seja $u \in U$, $u=\alpha v_{1}$ e $T(\alpha v_{1})=\alpha T(v_{1})=\alpha \lambda_{1}v_{1}\in U$. Logo, $U$ é $T$-invariante. Consequentemente, pelo [Lema 1](#lema1), $U^{\perp}$ também é $T$-invariante.

Dado que $\dim U^{\perp}<n$ e ${} U^{\perp} {}$ é $T$-invariante, vale a hipótese de indução. Logo, existe uma base ortonormal $\{ v_{2},\dots ,v_{n} \}$ de $U^{\perp}$ formada por autovetores de $T$. Naturalmente, como $V=U \oplus U^{\perp}$, $\{ v_{1},v_{2},\dots,v_{n} \}$ é uma base ortonormal de $V$ formada por autovetores de $T$.
:::

Verifica-se sem muita dificuldade que, em espaços vetoriais reais, a recíproca do Teorema Espectral é verdadeira: Se existe uma base ortonormal formada por autovetores de $T$, então $T$ é auto-adjunto.

### Teorema Espectral para matrizes simétricas

:::{prf:corollary} Teorema Espectral para matrizes simétricas
:label: espectral-para-matrizes-simetricas
Seja $A\in M_{n}(\mathbb{R})$ uma matriz simétrica, então existe uma matriz $P\in M_{n}(\mathbb{R})$ ortogonal tal que $D=P^{T}AP$, onde $D$ é uma [matriz diagonal](#def-matriz-diagonal) cuja diagonal principal contém os autovalores de $A$.
:::

```{admonition} Demonstração
:class: dropdown
Seja $T\in \mathcal{L}(V)$ tal que $A=[T]_{c}$. Como $A$ é simétrica e a base canônica é ortonormal, então $T$ é auto-adjunta. Logo, do [Teorema Espectral](#teorema-espectral) sabemos que existe uma base $\beta=\{ v_{1},\dots,v_{n} \}$ de $V$ formada por autovetores de $T$. Seja $T(v_{i})=\lambda_{i}v_{i}$ ($i=1,2,\dots,n$), então
$$
D=[T]_{\beta}=\begin{bmatrix}
\lambda_{1} & 0 & \dots & 0 \\
0 & \lambda_{2} & \dots & 0 \\
0 & 0 & \ddots & 0 \\
0 & 0 & \dots & \lambda_{n}
\end{bmatrix}.
$$
Além disso, $D=P^{-1}AP$, onde $P$ é a matriz mudança de base de $\beta$ para $c$. Dado que $\beta$ é ortonormal, então $P$ é ortogonal. Ou seja, $P^{-1}=P^{T}$.
```

O fato de podermos garantir que matrizes simétricas podem ser diagonalizadas e sabermos como encontrar a matriz diagonal tem grande aplicação prática e computacional, como veremos no exemplo a seguir.

:::{prf:example} Potenciação de uma matriz simétrica

Seja $A$ uma matriz simétrica, podemos determinar $A^{n}$ para um expoente natural qualquer. A chave está em encontrarmos a forma diagonal de $A$, garantida pelo [](#espectral-para-matrizes-simetricas) (neste caso, nos será útil escrever $A$ como $PDP^{T}$), e então verificar o que seria $A^{n}$ neste formato.

O processo para encontrar a forma diagonal é basicamente o mesmo para qualquer matriz simétrica, onde as 3 etapas principais são:
1. Encontrar os autovalores;
2. Encontrar os autovetores associados;
3. Determinar a base ortonormal formada a partir dos autovetores encontrados.

Para ilustrar estas etapas numericamente, considere o caso em que $A=\begin{bmatrix}7 & -1 \\ -1 & 2\end{bmatrix}$.

Para o primeiro passo, fazemos $\det (A-\lambda I)=0$ e resolvemos para $\lambda$ (isto é, encontramos as raízes do polinômio característico). Note que pelo [](#lema2) sabemos que as soluções serão todas reais. Neste caso, temos 

$$
\det\begin{bmatrix}
7-\lambda & -1 \\
-1 & 2-\lambda
\end{bmatrix} = 0 \implies (7-\lambda)(2-\lambda)-1=0
$$

Encontrando então os autovalores $\lambda_{1}=\frac{1}{2}(9+\sqrt{ 29 })$ e $\lambda_{2}=\frac{1}{2}(9-\sqrt{ 29 })$.

Para os autovetores, resolvemos os sistemas associados a

$$
\begin{bmatrix}
7-\lambda_{1} & -1 \\
-1 & 2-\lambda_{1}
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
0 \\
0
\end{bmatrix}
$$

e

$$
\begin{bmatrix}
7-\lambda_{2} & -1 \\
-1 & 2-\lambda_{2}
\end{bmatrix}\begin{bmatrix}
x \\
y
\end{bmatrix}=\begin{bmatrix}
0 \\
0
\end{bmatrix}
$$

encontrando $v_{1}=\left( -5-\sqrt{ 29 },2 \right)$ e $v_{2}=\left( -5+\sqrt{ 29 },2 \right)$, respectivamente.

Note que, como $\lambda_{1}\neq \lambda_{2}$, [](#autovetores-associados-a-autovalores-distintos-ortogonais) garante que $v_{1}$ e $v_{2}$ já são ortogonais. Então, para o terceiro passo resta apenas normalizá-los. Fazendo isso, obtemos os respectivos versores

$$
\begin{align}
\hat{v_{1}}&=\left( \frac{-5-\sqrt{ 29 }}{\sqrt{ 58+10\sqrt{ 29 } }} ,\frac{2}{{\sqrt{ 58+10\sqrt{ 29 } }}}\right)  \\
\hat{v_{2}}&=\left( \frac{-5+\sqrt{ 29 }}{\sqrt{ 58-10\sqrt{ 29 } }} ,\frac{2}{{\sqrt{ 58-10\sqrt{ 29 } }}}\right)
\end{align}
$$

Logo, $\{ \hat{v_{1}},\hat{v_{2}} \}$ é uma base ortonormal de $\mathbb{R}^{2}$ formada por autovetores de $A$.

Voltando ao caso geral (para simplificar consideraremos uma matriz $2\times2$, mas a análise para dimensões maiores é análoga), considere que os autovetores normalizados encontrados no terceiro passo são $\hat{v_{1}}=(a,b)$ e $\hat{v_{2}}=(c,d)$. A demonstração do [](#espectral-para-matrizes-simetricas) nos diz que $P=\begin{bmatrix}a & c \\ b & d\end{bmatrix}$, portanto

$$
A=PDP^{T}=\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}\begin{bmatrix}
\lambda_{1} & 0 \\
0 & \lambda_{2}
\end{bmatrix}\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

Agora, note que 

$$
A^{n}=(PDP^{T})^{n}= \underbrace{ (PDP^{T})(PDP^{T})\dots(PDP^{T}) }_{ n\text{ vezes} }
$$

mas como $P$ é ortogonal, então $P^{T}P=I$. Logo, isto se simplifica em

$$
\begin{align}
A^{n}&=P\underbrace{ DD\dots D }_{ n\text{ vezes} }P^{T} \\
 & =PD^{n}P^{T}
\end{align}
$$

Mais ainda, como $D$ é uma matriz diagonal, observe que $D^{n}$ resultará em $\begin{bmatrix}\lambda_{1}^{n} & 0 \\ 0 & \lambda_{2}^{n}\end{bmatrix}$. Dessa forma, concluímos que

$$
A^{n}=\begin{bmatrix}
a & c \\
b & d
\end{bmatrix}\begin{bmatrix}
\lambda_{1}^{n} & 0 \\
0 & \lambda_{2}^{n}
\end{bmatrix}\begin{bmatrix}
a & b \\
c & d
\end{bmatrix}
$$

:::

Observe como reduzimos um cálculo que seria de $n-1$ produtos de matrizes em dois produtos de matrizes! 

Para um computador, o custo de calcular $\lambda_{1}^{n}$, $\lambda_{2}^{n}$ e dois produtos matriciais é ordens de grandeza menor que o de calcular $n-1$ produtos matriciais (na maioria dos casos).

