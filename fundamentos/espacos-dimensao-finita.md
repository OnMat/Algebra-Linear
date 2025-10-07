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

De maneira similar à definição de soma direta para um conjunto de subespaços, definimos o conceito de independência linear para um conjunto de vetores.

:::{prf:definition} Vetores linearmente independentes

Sejam $v_{1},\dots,v_{n} \in V$, dizemos que $v_{1},\dots,v_{n}$ são ***linearmente independentes*** se a única maneira de escrever o vetor nulo como uma combinação linear entre eles é fazendo cada escalar igual a zero. Isto é, sejam $\alpha_{1},\dots,\alpha_{n} \in \mathbb{R}$, tais vetores são linearmente independentes se, e somente se,

$$
\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0\implies\alpha_{1},\dots,\alpha_{n}=0
$$

:::

:::{prf:observation}

Com um raciocínio análogo ao que fizemos para a soma direta, verifica-se que um conjunto de vetores ${} v_{1},\dots,v_{n} {}$ é linearmente independente se, e somente se, todo vetor pertencente ao espaço gerado por ${} v_{1},\dots,v_{n} {}$ possui representação única como combinaçao linear entre eles.

:::

:::{prf:example}

Seja $n \in \mathbb{N}$, os $n$ vetores do $\mathbb{R}^{n}$ (ou seja, com $n$ entradas reais)

$$
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
$$

são linearmente independentes. É fácil de observar que $0=\alpha_{1}(1,0,\dots,0)+\dots+\alpha_{n}(0,\dots,0,1)$ somente quando $\alpha_{1},\dots,\alpha_{n}=0$, afinal, cada vetor controla apenas uma única entrada.

:::

Naturalmente, um conjunto de vetores $v_{1},\dots,v_{n} \in V$ é ***linearmente dependente*** quando não é linearmente independente. Logo, existe pelo menos um $\alpha_{i}$ não nulo de modo que $0=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$.

Um exemplo típico de vetores linearmente dependentes são múltiplos (quando um vetor é o outro multiplicado por um escalar).

:::{prf:example}

Considere os vetores $(1,2)$ e $(2,4)$, do $\mathbb{R}^{2}$. Como $(2,4)=2(1,2)$, então

$$
0=\alpha_{1}(1,2)+\alpha_{2}(2,4)=\alpha_{1}(1,2)+2\alpha_{2}(1,2)=(\alpha_{1}+2\alpha_{2})(1,2)
$$

Se considerarmos $\alpha_{1}+2\alpha_{2}=0$, então basta escolhermos $\alpha_{1},\alpha_{2}\in \mathbb{R}$ que satisfaçam $\alpha_{1}=-2\alpha_{2}$. Por exemplo, com $\alpha_{1}=2$ e $\alpha_{2}=-1$ temos

$$
2(1,2)+(-1)(2,4)=(2,4)+(-2,-4)=(0,0)
$$

Como temos o vetor nulo resultante de uma combinação linear entre $(1,2)$ e $(2,4)$ cujos escalares não são ambos nulos, então $(1,2)$ e $(2,4)$ são linearmente dependentes.

:::

De maneira geral, sempre que tivermos o vetor nulo pertencente ao conjunto de vetores considerado, eles serão linearmente dependentes. Se considerarmos $0=\alpha_{0}0+\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$, dados valores de $\alpha_{1},\dots,\alpha_{n}$ que satisfaçam $\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0$ (mesmo que sejam todos nulos), então qualquer $\alpha_{0} \in \mathbb{R}$ irá satisfazer a igualdade. Logo, mesmo que $v_{1},\dots,v_{n}$ sejam linearmente independentes, ao adicionarmos o vetor nulo o conjunto de vetores se torna linearmente dependente.
