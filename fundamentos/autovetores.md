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

Sejam $T \in \mathcal{L}(V)$ e $v \in V$, com $v$ não nulo. Se existe $\lambda \in \mathbb{R}$ tal que 

$$
Tv=\lambda v,
$$

então $v$ é dito um ***autovetor*** de $T$. O escalar $\lambda$ é chamado de ***autovalor*** associado a $v$.

:::

Chamamos o subespaço invariante de dimensão 1 gerado por $v$ de ***autoespaço***. Note que todo vetor pertencente ao autoespaço de $v$ (ou seja, os múltiplos de $v$) também será um autovetor associado ao mesmo autovalor $\lambda$. Se pensarmos no caso do $\mathbb{R}^{n}$, todo autoespaço de um operador linear corresponde a uma reta (a gerada pelo autovetor correspondente) que é preservada (mantida no lugar) com a aplicação do operador. 

Observe também que não é feita nenhuma restrição em relação ao valor de $\lambda$. Em particular, quando existem autovetores associados ao autovalor $\lambda=0$, o operador não será invertível, pois o seu núcleo é não trivial (lembre-se que autovetores são não nulos por definição).

Um exemplo trivial de autovetores e autovalores provém do operador identidade, $I \in \mathcal{L}(V)$. Para todo $v \in V$ temos $Iv=v$, logo, todo vetor do espaço $V$ é um autovetor de $I$, com autovalor associado igual a 1.
