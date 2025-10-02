---
title: Propriedades de espaços vetoriais de dimensão finita
subject: Fundamentos
---

Os conceitos discutidos no tópico anterior são válidos para espaços vetoriais arbitrários. Voltaremos nossa atenção de agora em diante para espaços vetoriais de dimensão finita (o significado de dimensão ficará claro futuramente). Tenha em mente que sempre que nos referirmos a uma lista de vetores $v_{1},\dots,v_{n}$ teremos $n\in \mathbb{N}$, ou seja, a lista é finita. 

### Combinações lineares e espaço gerado

:::{prf:definition} Combinação linear

Sejam $v_{1},\dots,v_{n}$ vetores de um espaço vetorial $V$ e $\alpha_{1},\dots,\alpha_{n}\in \mathbb{R}$. Considere o seguinte vetor $w$:

$$
w=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}
$$

Dizemos que $w$ é uma ***combinação linear*** entre os vetores $v_{1},\dots,v_{n}$, em relação aos escalares  reais $\alpha_{1},\dots,\alpha_{n}$.

:::

:::{prf:definition} Espaço gerado

Sejam $v_{1},\dots v_{n} \in V$. Considere o seguinte conjunto:

$$
S=\{ \alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}/\alpha_{1},\dots,\alpha_{n}\in \mathbb{R} \}
$$

Isto é, $S$ é o conjunto de todas as combinações lineares possíveis entre $v_{1},\dots,v_{n}$. Utilizando os resultados do tópico anterior, verificamos facilmente que $S$ é um subespaço vetorial de $V$. Dizemos que $S$ é o ***espaço gerado*** pelos vetores $v_{1},\dots,v_{n}$ e denotaremos-o por $[v_{1},\dots,v_{n}]$.

:::

Em muitos textos (principalmente em inglês) é comum se referir ao espaço gerado como *span*, utilizando a notação $\text{span}(v_{1},\dots ,v_{n})$. Utilizaremos a notação descrita na definição, por simplicidade.

:::{prf:example}

Considere os vetores $(1,2,3)$ e $(4,5,6)$, do $\mathbb{R}^{3}$. Observe que ${} (10,14,18)\in [(1,2,3),(4,5,6)]$, pois $(10,14,18)=2\cdot(1,2,3)+2\cdot(4,5,6)$. 

Similarmente, $(1,2,3)$ e $(4,5,6)$ também são elementos de seu próprio espaço gerado, pois

$$
\begin{align}
 & (1,2,3)=1\cdot (1,2,3)+0\cdot (4,5,6) \\
 & (4,5,6)=0\cdot (1,2,3)+1\cdot (4,5,6)
\end{align}
$$

:::

Quando $[v_{1},\dots,v_{n}]=V$, dizemos que $v_{1},\dots,v_{n}$ **geram** $V$. Logo, dizemos que um espaço vetorial tem dimensão finita quando uma quantidade finita de seus elementos o gera.
