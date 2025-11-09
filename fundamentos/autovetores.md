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
