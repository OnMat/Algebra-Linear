---
title: Propriedades de espaços vetoriais de dimensão finita
subject: Fundamentos
---

Os conceitos discutidos no tópico anterior são válidos para espaços vetoriais arbitrários. **Daqui em diante, os espaços vetoriais considerados possuem dimensão finita** (o significado de dimensão ficará claro futuramente). Tenha em mente que sempre que nos referirmos a uma lista de vetores $(v_{1},\dots,v_{n})$ teremos $n\in \mathbb{N}$, ou seja, a lista é finita. 

### Combinações lineares e espaço gerado

:::{prf:definition} Combinação linear

Seja $(v_{1},\dots,v_{n})$ uma lista de vetores de um espaço vetorial $V$ e $\alpha_{1},\dots,\alpha_{n}\in \mathbb{R}$. Considere o seguinte vetor $w$:

$$
w=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}
$$

Dizemos que $w$ é uma ***combinação linear*** de $(v_{1},\dots,v_{n})$, em relação aos escalares  reais $\alpha_{1},\dots,\alpha_{n}$.

:::

:::{prf:definition} Espaço gerado

Seja $(v_{1},\dots, v_{n})$ uma lista de vetores em $V$. Considere o seguinte conjunto:

$$
S=\{ \alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}:\alpha_{1},\dots,\alpha_{n}\in \mathbb{R} \}
$$

Isto é, $S$ é o conjunto de todas as combinações lineares possíveis entre os vetores $v_{1},\dots,v_{n}$. Utilizando os resultados do tópico anterior, verificamos facilmente que $S$ é um subespaço vetorial de $V$. Dizemos que $S$ é o ***espaço gerado*** por $(v_{1},\dots,v_{n})$ e denotaremos-o por $\text{span}(v_{1},\dots,v_{n})$ (notação mais comum, proveniente do termo em inglês para o espaço gerado[^1]).

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

Quando $\text{span}(v_{1},\dots,v_{n})=V$, dizemos que $(v_{1},\dots,v_{n})$ **gera** $V$. Logo, dizemos que um espaço vetorial tem dimensão finita quando uma quantidade finita de seus elementos o gera.

### Independência linear

De maneira similar à definição de soma direta para um conjunto de subespaços, definimos o conceito de independência linear para uma lista de vetores.

:::{prf:definition} Vetores linearmente independentes

Seja $(v_{1},\dots,v_{n})$ uma lista de vetores em $V$, dizemos que $(v_{1},\dots,v_{n})$ é ***linearmente independente*** se a única maneira de escrever o vetor nulo como uma combinação linear entre esses vetores é fazendo cada escalar igual a zero. Isto é, sejam $\alpha_{1},\dots,\alpha_{n} \in \mathbb{R}$, tais vetores são linearmente independentes se, e somente se,

$$
\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0\implies\alpha_{1},\dots,\alpha_{n}=0
$$

:::

:::{prf:observation}

Com um raciocínio análogo ao que fizemos para a soma direta, verifica-se que ${} (v_{1},\dots,v_{n}) {}$ é linearmente independente se, e somente se, todo vetor pertencente ao espaço gerado por ${} (v_{1},\dots,v_{n}) {}$ possui representação única como combinaçao linear entre esses vetores.

:::

:::{prf:example}
:label: exbasecanonica

Seja $n \in \mathbb{N}$, os $n$ vetores do $\mathbb{R}^{n}$ (ou seja, com $n$ entradas reais)

$$
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
$$

são linearmente independentes. É fácil de observar que $0=\alpha_{1}(1,0,\dots,0)+\dots+\alpha_{n}(0,\dots,0,1)$ somente quando $\alpha_{1},\dots,\alpha_{n}=0$, afinal, cada vetor controla apenas uma única entrada.

:::

Através da definição, verifica-se sem muita dificuldade que toda lista de vetores que está contida em uma lista linearmente independente também será linearmente independente.

Naturalmente, uma lista de vetores $(v_{1},\dots,v_{n})$ é ***linearmente dependente*** quando não é linearmente independente. Logo, existe pelo menos um $\alpha_{i}$ não nulo de modo que $0=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$.

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

De maneira geral, sempre que tivermos o vetor nulo pertencente à lista de vetores, então ela será linearmente dependente: se considerarmos $0=\alpha_{0}0+\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$, dados valores de $\alpha_{1},\dots,\alpha_{n}$ que satisfaçam $\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}=0$ (mesmo que sejam todos nulos), então qualquer $\alpha_{0} \in \mathbb{R}$ irá satisfazer a igualdade. Logo, mesmo que $(v_{1},\dots,v_{n})$ seja linearmente independente, ao adicionarmos o vetor nulo a lista se torna linearmente dependente.

:::{prf:proposition}
:label: prop-aux-teo-li

Se $(v_{1},\dots,v_{n})$ é linearmente dependente e $v_{1} \neq 0$, existe $i \in \{ 2,\dots,n \}$ tal que $v_{i} \in \text{span}(v_{1},\dots,v_{i-1})$. Além disso, se $v_{i}$ for removido de $(v_{1},\dots,v_{n})$, o espaço gerado pela lista resultante é igual ao $\text{span}(v_{1},\dots,v_{n})$.

:::

:::{prf:proof}

Se $(v_{1},\dots, v_{n})$ é linearmente dependente, então $0 = \alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$ de modo que pelo menos um dos escalares é não nulo. Como $v_{1} \neq 0$, não podemos ter $\alpha_{2}=\alpha_{3}=\dots=\alpha_{n}=0$, (pois, nesse caso, para a igualdade valer deveríamos ter $\alpha_{1}=0$ também, logo, todos os escalares seriam nulos, uma contradição). Dessa forma, existe pelo menos um $k\in \{ 2,\dots,n \}$ tal que $\alpha_{k}\neq 0$. Seja $i$ o maior elemento em $\{ 2,\dots,n \}$ com essa propriedade, podemos escrever:

$$
v_{i}=-\frac{\alpha_{1}}{\alpha_{i}}v_{1}-\dots-\frac{\alpha_{i-1}}{\alpha_{i}}v_{i-1}
\label{eq:prova-dependencia-linear} 
$$

(observe que, pela escolha de $i$, os escalares com índice maior que $i$ são nulos).

Para a segunda parte, considere $u \in \text{span}(v_{1},\dots,v_{n})$. Logo, existem $\alpha_{1},\dots,\alpha_{n}\in \mathbb{R}$ tais que

$$
u=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}
$$

Substituir $v_{i}$ na equação acima pelo lado direito da equação {eq}`eq:prova-dependencia-linear` mostra que $u$ pertence ao espaço gerado pela lista resultante da remoção de $v_{i}$ de $(v_{1},\dots,v_{n})$, logo, os dois espaços gerados são iguais (pois $u$ é um elemento arbitrário de $\text{span}(v_{1},\dots,v_{n})$ e, por outro lado, o espaço gerado pela lista sem $v_{i}$ está contido no espaço gerado pela lista completa).

:::

Esse resultado nos diz que é possível reduzir uma lista de vetores linearmente dependentes em uma lista linearmente independente, removendo vetores que são combinação linear de outros vetores da lista (no caso da lista conter somente o vetor nulo, a lista resultante desse processo é vazia, assumida como linearmente independente por convenção).

:::{prf:theorem}
:label: teocomprimentoentreespanebase

Seja $V$ um espaço vetorial de dimensão finita, toda lista de vetores que gera $V$ tem comprimento maior ou igual a toda lista de vetores linearmente independentes em $V$. Isto é, se $\text{span}( v_{1},\dots,v_{n})=V$ e $(u_{1},\dots,u_{m})$ é linearmente independente em $V$, então $m \leq n$.

:::

:::{prf:proof}

Suponha que $\text{span}(v_{1},\dots,v_{n})=V$ e $(u_{1},\dots,u_{ m})$ é linearmente independente. Observe que $(u_{1},v_{1},\dots,v_{n})$ ainda gera $V$ e é linearmente dependente (pois como $v_{1},\dots,v_{n}$ geram $V$, $u_{1}$ pode ser escrito como combinação linear deles). Logo, uma vez que ${} u_{1} \neq 0$ (pois ${} (u_{1},\dots,u_{m})$ é linearmente independente), podemos remover um dos $v$'s de modo que a lista resultante ainda gera $V$ (utilizando [](#prop-aux-teo-li)). 

A partir dessa lista resultante, continuamos o processo, fazendo o mesmo para ${} u_{2}$, ${} u_{3}$... até ${} u_{m-1} {}$. Em cada etapa, substituímos um $v$ por um $u$, com a lista resultante ainda gerando $V$. Logo, ao adicionarmos ${} u_{m}$, na $m$-ésima etapa, a lista resultante será linearmente dependente. Se não tivéssemos um $v$ para remover teríamos uma contradição, pois a lista resultante seria $(u_{1},\dots,u_{m})$, que é linearmente independente. 

Isso implica que devemos ter uma quantidade de $v$'s pelo menos igual a quantidade de $u$'s. Ou seja, $m \leq n$.

:::

A partir desses resultados também obtemos que qualquer subespaço de um espaço de dimensão finita terá, da mesma forma, dimensão finita. Como é de se esperar.

### Bases

A união entre os conceitos de espaço gerado e independência linear origina a ideia de *base*, central na Álgebra Linear.

:::{prf:definition} Base
:label: defbase

Seja $V$ um espaço vetorial. Uma lista $(v_{1},\dots,v_{n})$ de vetores em $V$ é uma ***base*** de $V$ se satisfaz as seguintes condições:

1. Gera $V$;
2. É linearmente independente.

:::

:::{prf:example} Base canônica de $\mathbb{R}^{n}$

Considere os seguintes $n$ vetores de $\mathbb{R}^{n}$:

$$
(1,0,\dots,0),(0,1,0,\dots,0),\dots,(0,\dots,0,1)
$$

Como já constatado no [](#exbasecanonica), tais vetores são linearmente independentes. Além disso, observa-se facilmente que eles geram $\mathbb{R}^{n}$. Logo, formam uma base de $\mathbb{R}^{n}$. Chamamos tais vetores de ***base canônica*** de $\mathbb{R}^{n}$, pois constituem a base mais "simples" desse espaço.

Ilustrando mais concretamente, a base canônica de $\mathbb{R}^{2}$ é $( (1,0),(0,1) )$. Similarmente, a de $\mathbb{R}^{3}$ é $( (1,0,0),(0,1,0),(0,0,1) )$.

:::

Veja que multiplicar os vetores da base canônica por escalares quaisquer não altera as duas propriedades que fazem deles uma base. Logo, existem infinitas bases para $\mathbb{R}^{n}$. Existem também bases formadas por vetores que não são somente múltiplos dos vetores da base canônica, como ilustra o próximo exemplo.

:::{prf:example}
:label: exemplobase

$(1,2)$ e $(3,4)$ formam uma base de $\mathbb{R}^{2}$.

A parte da independência linear é clara, uma vez que um vetor não é múltiplo do outro. Para mostrar que eles geram $\mathbb{R}^{2}$ consideramos um elemento qualquer desse espaço, $(x,y) \in \mathbb{R}^{2}$. Se tais vetores geram esse espaço devem existir escalares $a,b \in \mathbb{R}$ tais que:

$$
\begin{align}
(x,y) & =a(1,2)+b(3,4) \\
 & =(a,2a)+(3b,4b) \\
 & =(a+3b,2a+4b)
\end{align}
$$

Isso nos dá o seguinte sistema linear:

$$
\begin{cases}
  a+3b & =x \\
  2a+4b & =y
\end{cases}
$$

Observe que, independente dos valores de $x$ e $y$, podemos determinar valores reais para $a$ e $b$ a partir deles, uma vez que as linhas não são múltiplas (consequência dos vetores associados serem linearmente independentes), impossibilitando que haja qualquer contradição para os valores de $a$ e $b$ (se as linhas fossem múltiplas, as equações só seriam simultaneamente verdadeiras se $x$ e $y$ também fossem múltiplos, pelo mesmo fator. Como não há essa restrição, encontramos soluções para qualquer $(x,y)$). Então, qualquer vetor de $\mathbb{R}^{2}$ pode ser escrito como combinação linear de $(1,2)$ e $(3,4)$, ou seja, esses vetores geram $\mathbb{R}^{2}$.

:::

:::{prf:example}

$(1,2),(3,4)$ e $(2,4)$ não formam uma base de $\mathbb{R}^{2}$.

Apesar de gerarem $\mathbb{R}^{2}$ (no exemplo anterior verificamos que $(1,2)$ e $(3,4)$ geram $\mathbb{R}^{2}$, a inclusão do vetor $(2,4)$ não muda isso), os vetores não são linearmente independentes, pois $(2,4)=2(1,2)$, falhando a segunda condição de [](#defbase).

:::

Esse exemplo nos dá um indício de que bases são **maximais** em relação à quantidade de vetores, pois a inclusão de um novo vetor à base do [](#exemplobase) fez com que uma das condições necessárias em [](#defbase) falhasse. De fato isso é verdadeiro, como será visto posteriormente.

Antes de partirmos para as proposições e teoremas, um último exemplo ilustrando uma base de um espaço vetorial diferente do $\mathbb{R}^{n}$:

:::{prf:example} Base canônica de $\mathcal{P}_{n}$

$\mathcal{P}_{n}$ representa o espaço vetorial formado pelos polinômios de grau máximo $n \in \mathbb{N}$, ou seja, o conjunto dos elementos da forma

$$
a_{0}+a_{1}x+a_{2}x^{2}+\dots+a_{n}x^{n} \quad (a_{0},a_{1},\dots,a_{n} \in \mathbb{R})
$$

Os elementos $1,x,\dots,x^{n}$ formam a base canônica de $\mathcal{P}_{n}$ .

:::

:::{prf:proposition} Caracterização de bases

Os vetores $v_{1},\dots,v_{n} \in V$ formam uma base de $V$ se, e somente se, todo $v \in V$ pode ser escrito de forma única como uma combinação linear entre eles. Isto é,

$$
v=\alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}
$$

com $\alpha_{1},\dots,\alpha_{n} \in \mathbb{R}$.

:::

:::{prf:proof}

$(\implies)$ Se $(v_{1},\dots,v_{n})$ é uma base de $V$, em particular, $(v_{1},\dots,v_{n})$ gera $V$. Logo, para todo $v \in V$, existem $\alpha_{1},\dots,\alpha_{n} \in \mathbb{R}$ de modo que $v= \alpha_{1}v_{1}+\dots+\alpha_{n}v_{n}$. Quanto à unicidade, se existem $\alpha_{1}',\dots,\alpha_{n}'\in \mathbb{R}$ tais que $v=\alpha_{1}'v_{1}+\dots+\alpha_{n}'v_{n}$, então

$$
0=v-v=(\alpha_{1}-\alpha_{1}')v_{1}+\dots+(\alpha_{n}-\alpha_{n}')v_{n}
$$

Pelo fato de $(v_{1},\dots,v_{n})$ ser linearmente independente (pois é uma base), devemos ter $\alpha_{1}-\alpha_{1}'=\dots=\alpha_{n}-\alpha_{n}'=0$, implicando que $\alpha_{1}=\alpha_{1}',\dots,\alpha_{n}=\alpha_{n}'$, provando que os escalares são únicos.

$(\impliedby)$ A volta é direta: se todo vetor em $V$ pode ser escrito como combinação linear de $v_{1},\dots,v_{n}$ então estes vetores geram $V$. Além disso, se essa escrita é única, então o vetor nulo só pode ser escrito trivialmente, ou seja, $\alpha_{1}=\dots=\alpha_{n}=0$ e $v_{1},\dots,v_{n}$ são linearmente independentes. Logo, $(v_{1},\dots,v_{n})$ é uma base de $V$.

:::

:::{prf:theorem} Spans podem ser reduzidos em uma base
:label: teoreducaobase

Toda lista de vetores que geram $V$ pode ser reduzida para uma base de $V$.

:::

:::{prf:proof}

Suponha que $(v_{1},\dots,v_{n})$ gera $V$. Primeiramente, se $v_{1}= 0$ remova-o. A partir disso, uma aplicação sequencial de [](#prop-aux-teo-li) indo de $v_{2}$ até $v_{n}$, removendo os vetores que pertencem ao espaço gerado pelos anteriores, nos dará uma nova lista que ainda gera $V$ e que é agora linearmente independente, ou seja, uma base de $V$.

:::

Esse teorema nos garante que todo espaço vetorial de dimensão finita possui uma base, uma vez que possui uma lista finita de vetores que o gera e então podemos reduzi-la em uma base.

Agora, mostramos o processo contrário ao do teorema anterior, que toda lista linearmente independente pode ser estendida em uma base, adicionando novos vetores.

:::{prf:theorem} Vetores LI podem ser estendidos em uma base
:label: teoestenderbase

Toda lista de vetores de $V$ linearmente independentes pode ser estendida em uma base de $V$.

:::

:::{prf:proof}

Seja $(v_{1},\dots,v_{n})$ linearmente independente e $u_{1},\dots,u_{m} \in V$ tais que $\text{span}( u_{1},\dots,u_{m})=V$. Começamos verificando se $u_{1}$ pertence ao $\text{span}(v_{1},\dots,v_{n})$. Se não pertencer, adicionamos-o a lista $(v_{1},\dots,v_{n})$, caso contrário, não o adicionamos. Repetimos o processo para $u_{2}$, verificando se ele pertence ao espaço gerado pela nova lista (que pode ter ou não novos elementos). Fazendo isso até $u_{m}$, ao final obtemos uma lista linearmente independente (pois nenhum vetor na lista pertence ao span dos anteriores) e que gera $V$ (pois todos os $u_{i}$ pertencem ao span da nova lista, e eles geram $V$). Logo, construímos uma base de $V$.

:::

Um resultado similar, sobre subespaços e somas diretas, pode ser extraído a partir desse teorema: Dado um subespaço $W$ de $V$, existe outro subespaço $U$ de $V$, de modo que $V=W\oplus U$. A ideia é considerar uma base de $W$ (que existe, pelo [](#teoreducaobase)) e completá-la em uma base de $V$ usando o [](#teoestenderbase), os vetores complementares obtidos serão a base do subespaço $U$. É fácil verificar que isso nos dará $V=W\oplus U$. Note que se $W=V$, então $U=\{ 0 \}$.

Por fim, um resultado que é naturalmente esperado e é importante para a definição de *dimensão*:

:::{prf:theorem} Bases possuem mesmo comprimento
:label: teocomprimentobase

Quaisquer duas bases de um mesmo espaço vetorial de dimensão finita possuem a mesma quantidade de vetores.

:::

:::{prf:proof}

Sejam $B_{1} =(v_{1},\dots,v_{n})$ e ${} B_{2}= (u_{1},\dots,u_{m})$ bases de $V$, utilizamos o [](#teocomprimentoentreespanebase): Por um lado, $B_{1}$ é uma lista de vetores linearmente independentes em $V$ e $B_{2}$ é uma lista de vetores que gera $V$, logo, $n\leq m$. Por outro lado, invertendo os papeis de $B_{1}$ e $B_{2}$, obtemos $m\leq n$. Ou seja, $n=m$ e as bases possuem a mesma quantidade de vetores.

:::

### Dimensão

:::{prf:definition} Dimensão de um espaço vetorial

Seja $V$ um espaço vetorial de dimensão finita, sua ***dimensão*** é definida como o número inteiro não negativo dado pelo comprimento de qualquer uma de suas bases (que, pelo [](#teocomprimentobase), é o mesmo para qualquer base) e é denotada por $\dim V$.

:::

A definição de dimensão para um espaço de "dimensão finita" parece circular, mas lembre-se que um espaço possui dimensão finita se pode ser gerado por uma lista finita de vetores, e essa definição não depende do conceito de dimensão definido agora. A necessidade de especificar que o espaço tenha dimensão finita se dá, pois, se o espaço possuir dimensão infinita, então qualquer uma de suas bases conterá infinitos elementos, logo, o conceito de "comprimento" não será mais limitado a um número real, fugindo do escopo elementar da Álgebra Linear.

:::{prf:example}

Como é esperado, seja $n \in \mathbb{N}$, o espaço $\mathbb{R}^{n}$ possui dimensão $n$. Por exemplo, o espaço das duplas ordenadas $\mathbb{R}^{2}=\{ (x,y):x,y \in \mathbb{R} \}$ possui dimensão 2; o espaço das 123-uplas ordenadas, $\mathbb{R}^{123}$, possui dimensão 123...

A dimensão de um espaço fica evidente quando pensamos na sua base canônica, por exemplo, $\mathcal{P}_{m}$ (polinômios de grau menor ou igual a $m$) possui dimensão $m+1$, sua base canônica é $( 1,x,x^{2},\dots,x^{m} )$, que possui $m+1$ elementos.

O espaço que contém somente o vetor nulo, $\{ 0 \}$, possui dimensão zero. Lembre-se que o vetor nulo não é uma base desse espaço pois, por definição, é linearmente dependente. **A base do espaço nulo (ou espaço trivial) é dada pela lista vazia (ou seja, que não contém vetores), representada por $()$**.

:::

Como já mencionado, todo subespaço de um espaço de dimensão finita terá dimensão finita. Então, naturalmente, temos o seguinte resultado:

:::{prf:proposition}
:label: teo-dim-subespaco-menor-ou-igual-dim-espaco

Se $V$ é um espaço de dimensão finita e $U$ é um subespaço de $V$, então $\dim U \leq \dim V$.

:::

:::{prf:proof}

Observe que qualquer base de $U$ é uma lista linearmente independente de vetores que também pertencem a $V$. Logo, pelo [](#teoestenderbase), pode ser estendida em uma base de $V$, o que implica que $\dim U \leq \dim V$.

:::

Os próximos dois resultados mostram que se uma lista de vetores possui comprimento igual a dimensão do espaço, somente uma das condições em [](#defbase) precisa ser verificada para que a lista seja uma base desse espaço. **Em ambos os casos, $V$ é um espaço de dimensão finita.**

:::{prf:proposition}

Se $(v_{1},\dots,v_{n})$ gera $V$ e $n=\dim V$ (ou seja, a lista tem comprimento igual a dimensão de $V$), então $(v_{1},\dots,v_{n})$ é uma base de $V$.

:::

:::{prf:proof}

$(v_{1},\dots,v_{n})$ gera $V$, pelo [](#teoreducaobase) essa lista pode ser reduzida em uma base de $V$. Por outro lado, $(v_{1},\dots,v_{n})$ já possui comprimento igual a $\dim V$. Como todas as bases possuem mesmo comprimento, a redução deve ser a trivial, isto é, $(v_{1},\dots,v_{n})$ já é uma base de $V$. 

:::

:::{prf:proposition}

Se $(v_{1},\dots,v_{n})$ é uma lista linearmente independente de vetores em $V$ e $n= \dim V$ (a lista possui comprimento igual a dimensão de $V$), então $(v_{1},\dots,v_{n})$ é uma base de $V$.

:::

:::{prf:proof}

O raciocínio é similar à proposição anterior. $(v_{1},\dots,v_{n})$ é linearmente independente, que pelo [](#teoestenderbase) pode ser estendida em uma base de $V$. Mas, seu comprimento é igual a dimensão de $V$ (e todas as bases possuem comprimento igual a dimensão de $V$), logo, a extensão é a trivial e $(v_{1},\dots,v_{n})$ já é uma base de $V$. 

:::

:::{prf:example}

Considere os vetores do $\mathbb{R}^{2}$: $(11,237)$ e $(5,3)$. Eles são linearmente independentes (pois um não é múltiplo do outro), como $((11,237),(5,3))$ possui comprimento 2, igual a dimensão de $\mathbb{R}^{2}$, a proposição anterior nos garante que $((11,237),(5,3))$ é uma base de $\mathbb{R}^{2}$, sem precisarmos verificar que gera $\mathbb{R}^{2}$.

:::

O teorema a seguir nos dá uma fórmula para a dimensão da soma de dois subespaços. Observe que ela é análoga à fórmula da cardinalidade da união de dois conjuntos finitos, dada por $|A\cup B|=|A|+|B|-|A\cap B|$.

:::{prf:theorem} Dimensão da soma de dois subespaços

Se $V$ possui dimensão finita e $V_{1}$ e $V_{2}$ são subespaços de $V$, então

$$
\dim (V_{1}+V_{2})=\dim V_{1}+\dim V_{2} - \dim (V_{1}\cap V_{2}).
$$

:::

:::{prf:proof}

Começamos considerando $(v_{1},\dots,v_{n})$ uma base de $V_{1}\cap V_{2}$, logo, temos que $\dim V_{1}\cap V_{2}=n$. Observe que, por ser uma base da interseção entre $V_{1}$ e $V_{2}$, $(v_{1},\dots,v_{n})$ é uma lista de vetores linearmente independentes simultaneamente em $V_{1}$ e em $V_{2}$. Logo, podemos estender $(v_{1},\dots ,v_{n})$ para uma base $(v_{1},\dots,v_{n},u_{1},\dots,u_{i})$ de $V_{1}$, assim como para uma base $(v_{1},\dots,v_{n},w_{1},\dots,w_{j})$ de $V_{2}$ (note que cada $u_{k}$ é elemento de $V_{1}$, enquanto que cada $w_{k}$ é elemento de $V_{2}$). Daí, temos que $\dim V_{1}=n+i$ e $\dim V_{2}=n+j$. Veja que $(v_{1},\dots,v_{n},u_{1},\dots,u_{i},w_{1},\dots,w_{j})$ gera $V_{1}+V_{2}$, logo, se tal lista for linearmente independente será uma base de $V_{1}+V_{2}$, de onde teremos

$$
\begin{align}
\dim V_{1}+V_{2} & =n+i+j \\
 & =n+i+j+n-n  \\
& =(n+i)+(n+j)-n \\
 & =\dim V_{1}+\dim V_{2} - \dim (V_{1}\cap V_{2}).
\end{align}
$$

Para mostrar que $(v_{1},\dots,v_{n},u_{1},\dots,u_{i},w_{1},\dots,w_{j})$ é linearmente independente, consideramos

$$
a_{1}v_{1}+\dots+a_{n}v_{n}+b_{1}u_{1}+\dots+b_{i}u_{i}+c_{1}w_{1}+\dots+c_{j}w_{j}=0
\label{eq:prova-formula-dimensao}
$$

e **devemos mostrar que todos esses escalares são nulos**. Podemos reescrever a igualdade como

$$
b_{1}u_{1}+\dots+b_{i}u_{i}=-a_{1}v_{1}-\dots-a_{n}v_{n}-c_{1}w_{1}-\dots-c_{j}w_{j}.
$$

Lembrando que $(v_{1},\dots,v_{n},w_{1},\dots,w_{j})$ é uma base de $V_{2}$, essa última igualdade nos diz que $b_{1}u_{1}+\dots+b_{i}u_{i} \in V_{2}$. Por outro lado, cada $u_{k}$ está em $V_{1}$, logo, $b_{1}u_{1}+\dots+b_{i}u_{i} \in V_{1}\cap V_{2}$. Assim, utilizando a base $(v_{1},\dots,v_{n})$ de $V_{1} \cap V_{2}$, podemos escrever

$$
b_{1}u_{1}+\dots+b_{i}u_{i}=d_{1}v_{1}+\dots+d_{n}v_{n}
$$

para escalares $d_{1},\dots ,d_{n} \in \mathbb{R}$. Subtraindo o membro da direita em ambos os lados da última igualdade e lembrando que $(v_{1},\dots,v_{n},u_{1},\dots,u_{i})$ é uma base de $V_{1}$ (logo, é linearmente independente), obtemos que $b_{1}=\dots=b_{i}=d_{1}=\dots=d_{n}=0$. Em particular, os escalares $b$'s são todos nulos, logo, considerando esse fato na igualdade {eq}`eq:prova-formula-dimensao` obtemos

$$
a_{1}v_{1}+\dots+a_{n}v_{n}+c_{1}w_{1}+\dots+c_{j}w_{j}=0.
$$

Similarmente, invocamos o fato de que $(v_{1},\dots,v_{n},w_{1},\dots,w_{j})$ é uma base de $V_{2}$ e, portanto, é linearmente independente, donde obtemos que todos os escalares $a$'s e $c$'s são nulos, concluindo a demonstração.

:::

Por fim, temos uma proposição que relaciona dimensão e soma direta.

:::{prf:proposition}

Sejam $U_{1},\dots,U_{n}$ subespaços de um espaço de dimensão finita $V$ tais que valem as duas condições abaixo:

1. $V=U_{1}+\dots+U_{n}$ (a soma dos subespaços gera $V$);
2. $\dim V= \dim U_{1}+\dots+\dim U_{n}$ (a dimensão de $V$ é igual a soma das dimensões dos subespaços).

Então, **$V$ é soma direta desses subespaços:**

$$
V=U_{1}\oplus\dots \oplus U_{n}
$$

:::

:::{prf:proof}

Utilizaremos a [](#prop-caracterizacao1-de-soma-direta) do tópico anterior. Já temos que $V=U_{1}+\dots+U_{n}$ (pela condição 1), restando mostrar que $0=u_{1}+\dots+u_{n}$, com $u_{k} \in U_{k}$, implica que $u_{1}=\dots=u_{n}=0$.

Considere, para cada $U_{k}$, uma base $(u_{1}^{k}\dots u_{m_{k}}^{k})$. Observe que a lista resultante da união dessas bases, dada por $(u_{1}^{1},\dots,u_{m_{1}}^{1},\dots,u_{1}^{n},\dots,u_{m_{n}}^{n})$, gera $V$ (pela condição 1 novamente) e possui comprimento igual a dimensão de $V$ (utilizando a condição 2, uma vez que o comprimento dessa lista é a soma dos comprimentos das bases de cada $U_{k}$, e o comprimento de cada base é exatamente $\dim U_{k}$). Logo, $(u_{1}^{1},\dots,u_{n_{1}}^{1},\dots,u_{1}^{n},\dots,u_{m_{n}}^{n})$ é uma base de $V$ e, em particular, é uma lista linearmente independente. Então, ao reescrevermos cada $u_{k}$ em $0=u_{1}+\dots+u_{n}$ como uma combinação linear da sua respectiva base obtemos que todos os escalares são nulos, consequentemente, cada $u_{k}$ será o vetor nulo, concluindo a demonstração.

:::
