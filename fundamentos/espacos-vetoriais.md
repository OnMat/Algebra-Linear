---
title: Espaços Vetoriais
subject: Fundamentos
---

### Conceitos iniciais

O conceito de **Espaço Vetorial** é a base onde se constrói a Álgebra Linear. Começamos com sua definição.

:::{prf:definition} Espaço Vetorial
:label: def-espaco-vetorial

Seja $V$ um conjunto não vazio que estejam definidas duas operações:

- A ***adição*** em $V$, uma função que associa um elemento $u+v \in V$ para cada par $u,v \in V$;
- A ***multiplicação por escalar***, um função que associa um elemento $\alpha v \in V$ para cada *escalar* real $\alpha \in \mathbb{R}$ e elemento $v \in V$.

$V$ irá constituir um ***Espaço Vetorial*** se as seguintes propriedades são válidas:

1. **Comutatividade:** $u+v=v+u$ para todo $u,v \in V$;
2. **Associatividade:** $(u+v)+w=u+ (v+w)$ e $(\alpha\beta)v=\alpha(\beta v)$ para todo $u,v,w \in V$ e $\alpha,\beta \in \mathbb{R}$;
3. **Elemento neutro da adição:** Existe um elemento $0 \in V$ tal que $v+0=v$ para todo $v \in V$;
4. **Inverso aditivo:** Para todo $v \in V$, existe $w \in V$ tal que $v+w=0$;
5. **Identidade multiplicativa:** Para todo $v \in V$, tem-se $1v=v$;
6. **Distributividade:** $\alpha(u+v)=\alpha u+\alpha v$ e $(\alpha+\beta)v=\alpha v+\beta v$ para todo $\alpha,\beta \in \mathbb{R}$ e $u,v \in V$.

Os elementos de $V$ são chamados de ***vetores***.

:::

Essas 6 propriedades são chamadas de **axiomas do Espaço Vetorial** (são comuns variações equivalentes desses axiomas).

Em particular, esta é a definição de um **Espaço Vetorial Real**, uma vez que a multiplicação por escalar está definida sobre o conjunto $\mathbb{R}$ dos números reais. A teoria da Álgebra Linear abrange também o conjunto dos números complexos (na verdade, qualquer estrutura algébrica que constitua um **corpo**), no entanto, lidaremos aqui apenas com os espaços vetoriais definidos sobre $\mathbb{R}$, mas tenha em mente que grande parte dos resultados podem ser estendidos para os números complexos, com as devidas adaptações.

Observe como os axiomas dependem das operações de adição e multiplicação por escalar. Nos principais espaços vetoriais que iremos lidar, essas operações são definidas de maneiras distintas, no entanto, serão bastante similares na prática. É importante destacar que, a priori, essas são as únicas operações definidas para vetores. Logo, se $u$ e $v$ são ambos vetores, **a multiplicação $uv$ não está definida**. As operações e propriedades usuais dos números reais mantêm-se normalmente para os escalares (note que os axiomas 2 e 6 utilizam o produto e adição de números reais, respectivamente).

Vejamos o principal exemplo de espaço vetorial.

:::{prf:example}

As n-uplas ordenadas com entradas reais, representadas por $(a_{1},a_{2},\dots,a_{n})$ com $a_{1},a_{2},\dots,a_{n} \in \mathbb{R}$, compõem o conjunto denotado por $\mathbb{R}^{n}$. A adição e o produto escalar são definidos como se espera:

$$
\begin{align}
 & (a_{1},\dots,a_{n})+(b_{1},\dots,b_{n})=(a_{1}+b_{1},\dots,a_{n}+b_{n}) \\
 & \alpha(a_{1},\dots,a_{n})=(\alpha a_{1},\dots,\alpha a_{n}),\; \alpha \in \mathbb{R}
\end{align}
$$

Com estas operações, $\mathbb{R}^{n}$ constitui um espaço vetorial. Verifique que os axiomas do espaço vetorial são satisfeitos.

:::

O terceiro axioma em [](def-espaco-vetorial) diz respeito ao elemento neutro da adição em um espaço vetorial. Tal elemento é denominado ***vetor nulo*** e denotado por $0$ (apesar de poder causar confusão com o escalar real $0$, em geral o contexto deixa claro qual elemento se trata. Por exemplo, se $v$ é um vetor, entao em $v + 0$ temos o vetor nulo, enquanto que $0v$ temos o escalar nulo). O resultado a seguir constata a unicidade desse elemento, em quaquer espaço vetorial.

:::{prf:proposition} 

Seja $V$ um espaço vetorial, seu vetor nulo é único.

:::

:::{prf:proof}

Suponha que $0$ e $0'$ sejam ambos elementos neutros da adição. Logo, pelos axiomas 1 e 3,

$$
0=0+0'=0'+0=0'
$$

:::

Similarmente, temos a unicidade do inverso aditivo, retratado no axioma 4.

:::{prf:proposition} 

Seja $V$ um espaço vetorial, para todo $v \in V$, seu inverso aditivo é único.

:::

:::{prf:proof}

Suponha que $w$ e $w'$ sejam ambos inversos aditivos de $v$. Pelos axiomas, 

$$
w = w+0 = w + (v + w')=(w+v)+w'=0+w'=w'
$$

:::

Assim, denotamos o inverso aditivo de um vetor $v$ por $-v$ e escrevemos $v+(-v)$ como $v-v$.

Observe que, como é natural de se esperar, temos $0v=0$, pois $0v=(0+0)v=0v+0v$, de onde obtemos $0=0v$ ao adicionarmos $-0v$ em ambos os lados. A partir disso, também temos $-v=(-1)v$, pois $0=0v=(1-1)v=v+(-1)v$ e aplicamos a unicidade do inverso aditivo.

:::{prf:example}

No $\mathbb{R}^{n}$, o vetor nulo é $0=(0,\dots,0)$. Se $v=(a_{1},\dots,a_{n})$, então $-v=(-a_{1},\dots,-a_{n})$.

:::

Agora, voltamos nossa atenção para subconjuntos de espaços vetoriais que também constituem espaços vetoriais.

:::{prf:definition} Subespaço Vetorial

Seja $V$ um espaço vetorial e $U \subseteq  V$, $U$ será um espaço vetorial se satisfaz as seguintes condições, considerando as mesmas operações de soma e multiplicação por escalar definidas em $V$:

1. $0 \in U$;
2. $v,w \in U \implies v + w \in U$ (**fechado na adição**);
3. $v \in U$ e $\alpha \in \mathbb{R}\implies\alpha v \in U$ (**fechado na mult. por escalar**).

Neste caso, dizemos que $U$ é um ***subespaço*** de $V$.

:::

O fato de $U$ ser um subconjunto de um espaço vetorial $V$ faz com que ele já herde grande parte dos axiomas que definem um espaço vetorial (a saber: associatividade, comutatividade, distributividade e identidade multiplicativa). Assim, para manter a conformidade com a [](#def-espaco-vetorial) é suficiente verificar apenas estas 3 condições. A terceira condição, em particular, não só nos garante que a operação de mult. por escalar é fechada no conjunto $U$, mas também nos dá o axioma do inverso aditivo, pois já verificamos que $-v=(-1)v$, logo, se $U$ é fechado na multiplicação temos $-v \in U$ para todo $v \in U$.

Note que a condição 1 impede que um conjunto vazio seja um subespaço. O menor subespaço possível será aquele contendo somente o vetor nulo: $\{ 0 \}$. E, com exceção desse, todo os outros subespaços terão infinitos elementos (consequência do subespaço ser fechado na adição e multiplicação).

:::{prf:example}

Considere o subconjunto do $\mathbb{R}^{n}$ formado pelos vetores cuja primeira entrada é nula. Isto é, $U=\{ (0,a_{2},\dots,a_{n});a_{i} \in \mathbb{R} \}$. 

1. Claramente, $0 \in U$;
2. $(0,a_{2},\dots,a_{n})+(0,b_{2},\dots,b_{n})=(0,a_{2}+b_{2},\dots,a_{n}+b_{n}) \in U$;
3. Seja $\alpha \in \mathbb{R}$, $\alpha(0,a_{2},\dots,a_{n})=(0,\alpha a_{2},\dots,\alpha a_{n}) \in U$.

Portanto, $U$ é um espaço vetorial. Em particular, é um subespaço de $\mathbb{R}^{n}$.

:::

Para o $\mathbb{R}^{n}$, é comum que subespaços sejam interpretados geometricamente. No caso do $\mathbb{R}^{3}$, por exemplo, todo os seus subespaços próprios (que não sejam ele mesmo) e não nulos formam retas ou planos.
