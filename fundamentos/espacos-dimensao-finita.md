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

Isto é, $S$ é o conjunto de todas as combinações lineares possíveis entre $v_{1},\dots,v_{n}$. Utilizando os resultados do tópico anterior, verificamos facilmente que $S$ é um subespaço vetorial de $V$. Dizemos que $S$ é o ***espaço gerado*** pelos vetores $v_{1},\dots,v_{n}$ e denotaremos-o por $\text{span}(v_{1},\dots,v_{n})$ (notação mais comum, proveniente do termo em inglês para o espaço gerado[^1]).

:::

[^1]: Alternativamente, encontra-se a notação $[\{ v_{1},\dots,v_{n} \}]$.

:::{prf:example}

Considere os vetores $(1,2,3)$ e $(4,5,6)$, do $\mathbb{R}^{3}$. Observe que ${} (10,14,18)\in \text{span}((1,2,3),(4,5,6))$, pois $(10,14,18)=2\cdot(1,2,3)+2\cdot(4,5,6)$. 

Similarmente, $(1,2,3)$ e $(4,5,6)$ também são elementos de seu próprio espaço gerado, pois

$$
\begin{align}
 & (1,2,3)=1\cdot (1,2,3)+0\cdot (4,5,6) \\
 & (4,5,6)=0\cdot (1,2,3)+1\cdot (4,5,6)
\end{align}
$$

:::

Quando $\text{span}(v_{1},\dots,v_{n})=V$, dizemos que $v_{1},\dots,v_{n}$ **geram** $V$. Logo, dizemos que um espaço vetorial tem dimensão finita quando uma quantidade finita de seus elementos o gera.

### Independência linear

De maneira similar à definição de soma direta para um conjunto de subespaços, definimos o conceito de independência linear para uma lista de vetores.

:::{prf:definition} Vetores linearmente independentes

Sejam $v_{1},\dots,v_{n} \in V$, dizemos que $v_{1},\dots,v_{n}$ são ***linearmente independentes*** se a única maneira de escrever o vetor nulo como uma combinação linear entre eles é fazendo cada escalar igual a zero. Isto é, sejam $\alpha_{1},\dots,\alpha_{n} \in \mathbb{R}$, tais vetores são linearmente independentes se, e somente se,

$$
\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0\implies\alpha_{1},\dots,\alpha_{n}=0
$$

:::

:::{prf:observation}

Com um raciocínio análogo ao que fizemos para a soma direta, verifica-se que uma lista de vetores ${} v_{1},\dots,v_{n} {}$ é linearmente independente se, e somente se, todo vetor pertencente ao espaço gerado por ${} v_{1},\dots,v_{n} {}$ possui representação única como combinaçao linear entre eles.

:::

:::{prf:example}

Seja $n \in \mathbb{N}$, os $n$ vetores do $\mathbb{R}^{n}$ (ou seja, com $n$ entradas reais)

$$
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
$$

são linearmente independentes. É fácil de observar que $0=\alpha_{1}(1,0,\dots,0)+\dots+\alpha_{n}(0,\dots,0,1)$ somente quando $\alpha_{1},\dots,\alpha_{n}=0$, afinal, cada vetor controla apenas uma única entrada.

:::

Naturalmente, uma lista de vetores $v_{1},\dots,v_{n} \in V$ é ***linearmente dependente*** quando não é linearmente independente. Logo, existe pelo menos um $\alpha_{i}$ não nulo de modo que $0=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$.

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

De maneira geral, sempre que tivermos o vetor nulo pertencente à lista de vetores considerado eles serão linearmente dependentes: se considerarmos $0=\alpha_{0}0+\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$, dados valores de $\alpha_{1},\dots,\alpha_{n}$ que satisfaçam $\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0$ (mesmo que sejam todos nulos), então qualquer $\alpha_{0} \in \mathbb{R}$ irá satisfazer a igualdade. Logo, mesmo que $v_{1},\dots,v_{n}$ sejam linearmente independentes, ao adicionarmos o vetor nulo a lista de vetores se torna linearmente dependente.

:::{prf:proposition}

Se $v_{1},\dots,v_{n} \in V$ é linearmente dependente e $v_{1} \neq 0$, existe $i \in \{ 2,\dots,n \}$ tal que $v_{i} \in \text{span}(v_{1},\dots,v_{i-1})$. Além disso, se $v_{i}$ for removido de $v_{1},\dots,v_{n}$, o espaço gerado pela lista resultante é igual ao $\text{span}(v_{1},\dots,v_{n})$.

:::

:::{prf:proof}

Se $v_{1},\dots v_{n}$ é linearmente dependente, então $0 = \alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$ de modo que pelo menos um dos escalares é não nulo. Como $v_{1} \neq 0$, não podemos ter $\alpha_{2}=\alpha_{3}=\dots=\alpha_{n}=0$, (pois, nesse caso, para a igualdade valer deveríamos ter $\alpha_{1}=0$ também, logo, todos os escalares seriam nulos, uma contradição). Dessa forma, existe pelo menos um $k\in \{ 2,\dots,n \}$ tal que $\alpha_{k}\neq 0$. Seja $i$ o maior elemento em $\{ 2,\dots,n \}$ com essa propriedade, podemos escrever:

$$
v_{i}=-\frac{\alpha_{1}}{\alpha_{i}}v_{1}-\dots-\frac{\alpha_{i-1}}{\alpha_{i}}v_{i-1}
\label{eq:prova-dependencia-linear} 
$$

(observe que, pela escolha de $i$, os escalares com índice maior que $i$ são nulos).

Para a segunda parte, considere $u \in \text{span}(v_{1},\dots,v_{n})$. Logo, existem $\alpha_{1},\dots,\alpha_{n}\in \mathbb{R}$ tais que

$$
u=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}
$$

Substituir $v_{i}$ na equação acima pelo lado direito da equação {eq}`eq:prova-dependencia-linear` mostra que $u$ pertence ao espaço gerado pela lista resultante da remoção de $v_{i}$ de $v_{1},\dots,v_{n}$, logo, os dois espaços gerados são iguais (pois $u$ é um elemento arbitrário de $\text{span}(v_{1},\dots,v_{n})$ e, por outro lado, o espaço gerado pela lista sem $v_{i}$ está contido no espaço gerado pela lista completa).

:::

Esse resultado nos diz que é possível "simplificar" uma lista de vetores linearmente dependentes em uma lista linearmente independente, removendo vetores que são combinação linear de outros vetores da lista (no caso da lista conter somente o vetor nulo, a lista resultante desse processo é vazia, assumida como linearmente independente por convenção).
