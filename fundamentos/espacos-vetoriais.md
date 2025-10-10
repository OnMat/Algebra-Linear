---
title: Espaços Vetoriais
subject: Fundamentos
---

### Conceitos iniciais

O conceito de **Espaço Vetorial** é o alicerce onde se constrói a Álgebra Linear. Começamos com sua definição.

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

:::{prf:remark}

Nos exemplos utilizaremos principalmente o $\mathbb{R}^{n}$, mas existem outros tipos de espaços vetoriais, por exemplo, o conjunto dos polinômios de grau máximo $n \in \mathbb{N}$, denotado por $\mathcal{P_{n}}$. Alguns desses espaços serão mencionados posteriormente (como o espaço das matrizes), outros não. Tenha em mente que os resultados apresentados, no entanto, valem para qualquer espaço vetorial (caso não seja especificado o contrário).

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
:label: def-subespaco

Seja $V$ um espaço vetorial e $U \subseteq  V$, $U$ será um espaço vetorial se satisfaz as seguintes condições, considerando as mesmas operações de soma e multiplicação por escalar definidas em $V$:

1. $0 \in U$;
2. $v,w \in U \implies v + w \in U$ (**fechado na adição**);
3. $v \in U$ e $\alpha \in \mathbb{R}\implies\alpha v \in U$ (**fechado na mult. por escalar**).

Neste caso, dizemos que $U$ é um ***subespaço*** de $V$.

:::

O fato de $U$ ser um subconjunto de um espaço vetorial $V$ faz com que ele já herde grande parte dos axiomas que definem um espaço vetorial (a saber: associatividade, comutatividade, distributividade e identidade multiplicativa). Assim, para manter a conformidade com a [](#def-espaco-vetorial) é suficiente verificar apenas estas 3 condições. A terceira condição, em particular, não só nos garante que a operação de mult. por escalar é fechada no conjunto $U$, mas também nos dá o axioma do inverso aditivo, pois já verificamos que $-v=(-1)v$, logo, se $U$ é fechado na multiplicação temos $-v \in U$ para todo $v \in U$.

Note que a condição 1 impede que um conjunto vazio seja um subespaço. O menor subespaço possível será aquele contendo somente o vetor nulo: $\{ 0 \}$. E, com exceção desse, todo os outros subespaços terão infinitos elementos (consequência do subespaço ser fechado na adição e multiplicação).

:::{prf:example}

Considere o subconjunto do $\mathbb{R}^{n}$ formado pelos vetores cuja primeira entrada é nula. Isto é, $U=\{ (0,a_{2},\dots,a_{n})/ a_{i} \in \mathbb{R} \}$. 

1. Claramente, $0 \in U$;
2. $(0,a_{2},\dots,a_{n})+(0,b_{2},\dots,b_{n})=(0,a_{2}+b_{2},\dots,a_{n}+b_{n}) \in U$;
3. Seja $\alpha \in \mathbb{R}$, $\alpha(0,a_{2},\dots,a_{n})=(0,\alpha a_{2},\dots,\alpha a_{n}) \in U$.

Portanto, $U$ é um espaço vetorial. Em particular, é um subespaço de $\mathbb{R}^{n}$.

:::

Para o $\mathbb{R}^{n}$, é comum que subespaços sejam interpretados geometricamente. No caso do $\mathbb{R}^{3}$, por exemplo, todo os seus subespaços próprios (que não sejam ele mesmo) e não nulos formam retas ou planos.

### União e interseção de subespaços

:::{prf:proposition}

Sejam $U$ e $W$ subespaços de um mesmo espaço vetorial $V$, então $U\cap W$ é também um subespaço de $V$.

:::

:::{prf:proof}

Claramente, $U\cap W \subseteq V$. Além disso, $0 \in U\cap W$, pois $U$ e $W$ são ambos subespaços. 

Observe que se $u,w \in U\cap W$, então $u,w \in U$ e $u,w \in W$. Em particular, uma vez que subespaços são fechados na soma, $u+w \in  U$ e $u+w\in W$, logo $u+w \in U\cap W$.

Similarmente para o produto escalar, se $\alpha \in \mathbb{R}$ e $u \in U \cap W$, teremos $\alpha u \in U$ e $\alpha u \in W$, logo $\alpha u \in U\cap W$.

Com estas condições concluímos que $U\cap W$ é um subespaço vetorial de $V$.

:::

:::{prf:observation}

Através de um argumento indutivo podemos estender este resultado para a interseção de uma família arbitrária de subespaços $U_{1},U_{2},\dots,U_{n}$ de $V$.

:::

A união de subespaços, no entanto, não se comporta da mesma maneira. Há casos em que a união não será um subespaço:

:::{prf:example}

Considere os seguintes subespaços de $\mathbb{R}^{2}$:

- ${} S_{1}=\{ (0,y)/ y \in \mathbb{R} \} {}$;
- $S_{2}=\{ (x,0)/ x \in \mathbb{R} \}$.

Inicialmente, note que $S_{1}\cap S_{2} = \{ 0 \}$. Logo, seja $v \in S_{1} \cup S_{2}$ tal que $v \neq 0$, $v$ só pode ser da forma $(0,y)$ ou $(x,0)$, com $x$ e $y$ diferentes de zero. Assim, considere $v,w \in S_{1}\cup S_{2}$, de forma que $v \in S_{1}$ e $w \in S_{2}$ e ambos diferentes do vetor nulo. Observe que $v+w=(x,y)$, para $x,y \in \mathbb{R}-\{ 0 \}$, o que claramente não é um elemento de $S_{1}$ ou de $S_{2}$, portanto não pertence a união.

Assim, $S_{1}\cup S_{2}$ não é fechado na soma e, logo, não é um subespaço vetorial.

:::

O próximo resultado elucida a condição necessária (e suficiente) para que a união entre subespaços mantenha-se um subespaço.

:::{prf:proposition}

Sejam $U$ e $W$ subespaços de $V$, a união $U\cup W$ é um subespaço de $V$ se, e somente se, $U\subseteq W$ ou $W\subseteq U$ (um dos subespaços está contido no outro).

:::

:::{prf:proof}

$(\implies)$ Seja $U\cup W$ um subespaço. Suponha, por contradição, que $U \not \subset W$ e $W \not \subset U$, isso implica que existem elementos $u \in U-W$ e $w \in W-U$ diferentes do vetor nulo. Pelo fato de que $U \cup W$ é um subespaço e $u,w \in U\cup W$, temos $u+w \in U\cup W$, mas isso significa que (pela definição de união entre conjuntos) $u+w \in U$ ou $u+w \in W$, uma contradição à hipótese de que  $v$ e $w$ não pertencem ao mesmo subespaço (por exemplo, se ${} u+w \in U {}$, pelo fato de $U$ ser fechado na soma e multiplicação por escalar teríamos $u+w-u=w \in U$).

$(\impliedby)$ Suponha, sem perda de generalidade, que $U\subseteq W$. Segue-se então que $U\cup W=W$ e já temos que $W$ é um subespaço vetorial.

:::

### Soma e soma direta de subespaços

:::{prf:definition}

Sejam $U_{1},U_{2},\dots,U_{n}$ subespaços de $V$, define-se a sua soma como:

$$
U_{1}+U_{2}+\dots+U_{n}=\{ u_{1}+\dots+u_{n}/ u_{1} \in U_{1},\dots,u_{n} \in U_{n} \}
$$

Ou seja, é o conjunto de todas as possíveis somas entre elementos de $U_{1},U_{2},\dots,U_{n}$.

:::

:::{prf:example}
:label: exemplo-soma-de-subespacos

Considere novamente os subespaços:

- $S_{1}=\{ (x,0)/ x \in \mathbb{R} \}$
- $S_{2}=\{ (0,y)/ y \in \mathbb{R} \}$

Então, sua soma é dada por:

$$
S_{1}+S_{2}=\{ (x,y)/ x,y \in \mathbb{R} \}
$$

Ou seja, $S_{1}+S_{2}=\mathbb{R}^{2}$.

:::

Observe que a soma entre os subespaços resultou no próprio espaço o qual eles pertencem, que em particular é também um subespaço. O próximo resultado nos mostra que somas de subespaços sempre resultam em subespaços (mas não necessariamente no espaço vetorial inteiro, as condições para que isso ocorra serão discutidas futuramente).

:::{prf:proposition}
:label: prop-soma-de-subespacos-eh-subespaco

Sejam $U_{1},\dots,U_{n}$ subespaços de $V$, então $U_{1}+\dots+U_{n}$ é um subespaço de $V$.

:::

:::{prf:proof}

Verificaremos que para dois subespaços $U$ e $W$ de $V$, $U+W$ é um subespaço de $V$. O caso geral para uma quantidade $n$ de subespaços verifica-se indutivamente a partir disso.

Observe que $U+W \subseteq V$, logo, devemos verificar apenas as 3 condições em [](#def-subespaco):

- Seja $\alpha \in \mathbb{R}$ e $v \in U+W$. Então $v=u+w$, para $u\in U$ e $w\in W$, e $\alpha v=\alpha(u+w)=\alpha u+\alpha w$. Mas $\alpha u\in U$ e $\alpha w \in W$, logo $\alpha v \in U + W$;
- Similarmente, sejam $v_{1},v_{2} \in U+W$, com $v_{1}=u_{1}+w_{1}$ e $v_{2}= u_{2}+w_{2}$, então $v_{1}+v_{2}=(u_{1}+u_{2})+(w_{1}+w_{2})$. Como $u_{1}+u_{2} \in U$ e $w_{1}+w_{2} \in W$, temos $v_{1}+v_{2} \in U+W$;
- Por fim, evidentemente $0 \in U+W$.

Logo, $U+W$ é um subespaço de $V$.

:::

Agora, definimos um tipo diferente de soma entre subespaços, que funciona como um caso especial da soma anterior. 

:::{prf:definition} Soma direta
:label: def-soma-direta

Dizemos que um espaço vetorial $W$ é ***soma direta*** dos subespaços $U_{1},\dots,U_{n}$, denotado por $W=U_{1}\oplus\dots \oplus U_{n}$, se cada elemento $w \in W$ pode ser escrito **de modo único** como:

$$
w=u_{1}+\dots+u_{n}
$$

com $u_{i}\in U_{i}$.


:::

O "modo único" significa que cada vetor $u_{i}$ é fixo, uma vez fixado $w$. Logo, não existe um vetor $u_{k}' \neq u_{k}$ de modo que $w=u_{1}'+\dots+u_{k}'+\dots+u_{n}'$ (com $u_{i}'$ podendo ser igual ou não a $u_{i}$, para $i \neq k$). 

No caso do exemplo [](#exemplo-soma-de-subespacos), observe que além de $\mathbb{R}=S_{1}+S_{2}$ temos $\mathbb{R}=S_{1}\oplus S_{2}$, pois cada subespaço influencia em apenas uma das duas coordenadas.

A grande diferença entre os dois tipos de soma fica evidente fazendo-se uma analogia à união de conjuntos. Sejam $C_{1},C_{2}$ e $C_{3}$ conjuntos não vazios, se tivermos $C_{2}\subseteq C_{3}$, então a união $C_{1} \cup C_{2} \cup C_{3}$ é igual a $C_{1} \cup C_{3}$. O mesmo pode ocorrer com a soma de subespaços. Por exemplo, se um dos subespaços contiver outro, a parcela da soma do que está contido não "contribui" para o subespaço resultante, e isto faria com que a condição de escrita única falhasse, pois para qualquer vetor resultante da soma poderíamos somar a parcela do subespaço contido na do que o contém e substituir sua parcela pelo vetor nulo, originando duas escritas diferentes de um mesmo vetor, então a soma entre aqueles subespaços não seria uma soma direta. Agora, quando os conjuntos $C_{1},C_{2}$ e $C_{3}$ são disjuntos, então temos a garantia de que a união entre eles não pode ser reduzida, este seria o análogo a uma soma direta entre subespaços, que é como o "menor" subespaço que os contém.

O próximo resultado nos dá uma maneira mais prática de verificar se um subespaço é resultante da soma direta de outros.

:::{prf:proposition}
:label: prop-caracterizacao1-de-soma-direta

Sejam $U_{1},\dots,U_{n}$ subespaços de $V$. Então, $V=U_{1}\oplus\dots \oplus U_{n}$ se, e somente se, valem as seguintes condições:

1. $V=U_{1}+\dots+U_{n}$;
2. A única maneira de escrever $0$ como uma soma $u_{1}+\dots+u_{n}$ , com $u_{i}\in U_{i}$, é fazendo cada $u_{i}=0$.

:::

:::{prf:proof}

$(\implies)$ Se vale $V=U_{1}\oplus\dots \oplus U_{n}$, pela [](#def-soma-direta) temos que cada elemento em $V$ pode ser escrito como uma soma de elementos de $U_{1},\dots,U_{n}$, ou seja, $V \subseteq U_{1}+\dots+U_{n}$, logo $V= U_{1}+\dots+U_{n}$ (pela [](#prop-soma-de-subespacos-eh-subespaco) já temos a inclusão contrária). Além disso, a escrita também é única, logo, só deve valer a escrita trivial do elemento nulo, isto é:

$$
0 = 0+\dots+0
$$

$(\impliedby)$ Se valem as condições 1 e 2, pela condição 1 temos que cada elemento em $V$ pode ser escrito como uma soma de elementos de $U_{1},\dots,U_{n}$. Então, seja $v\in V$ de forma que $v=u_{1}+\dots+u_{n}=u_{1}'+\dots+u_{n}'$, com $u_{i},u_{i}' \in U_{i}$, temos

$$
0=v-v=(u_{1}-u_{1}')+\dots+(u_{n}-u_{n}')
$$

Mas, pela condição 2, o elemento nulo só pode ser escrito como uma soma de elementos de $U_{1},\dots,U_{n}$ da maneira trivial, logo $u_{i}-u_{i}'=0\implies u_{i}=u_{i}'$. Ou seja, todo $v\in V$ pode ser escrito como uma soma de elementos de $U_{1},\dots,U_{n}$ e de maneira única. Portanto, pela [](#def-soma-direta), $V=U_{1}\oplus\dots \oplus U_{n}$.

:::

Agora, vejamos como a "disjunção" entre dois subespaços (que é na verdade $U\cap W=\{ 0 \}$, pois todo subespaço contém o vetor nulo) garante que sua soma é direta.

:::{prf:proposition}
:label: prop-caracterizacao2-soma-direta

Sejam $U$ e $W$ subespaços de $V$, então $V=U\oplus W$ se, e somente se, $V=U+W$ e $U\cap W=\{ 0 \}$.

:::

:::{prf:proof}

$(\implies)$ Seja $V=U\oplus W$. Utilizando [](#prop-caracterizacao1-de-soma-direta), temos $V=U + W$. Suponha que $v \in U\cap W$. Então, $0=v-v$ e como $v \in U,W$ e a representação do vetor nulo como soma de elementos desses subespaços é somente a trivial (também por [](#prop-caracterizacao1-de-soma-direta)), então $v=0$. Logo, $U\cap W=\{ 0 \}$.

$(\impliedby)$ Se vale $V=U+W$, por [](#prop-caracterizacao1-de-soma-direta) resta mostrar que a escrita dos elementos é única. Suponha que $v=u+w=u'+w'$, com $u,u'\in U$ e $w,w'\in W$. Logo, $0=v-v=(u-u')+(v-v')$, então $(u-u')=(v'-v)$. Mas $(u-u')\in U$ e $(v'-v)\in W$, ou seja, $(u-u')\in U\cap W$ e $(v'-v)\in U\cap W$. Logo, como também vale $U\cap W=\{ 0 \}$,

$$
\begin{cases}
u-u'=0 \\
v'-v=0
\end{cases}
$$

Concluindo que $u=u'$ e $v=v'$, ou seja, a escrita é única. Donde obtemos que $V=U\oplus W$.

:::

Veja que, diferentemente da [](#prop-caracterizacao1-de-soma-direta), a [](#prop-caracterizacao2-soma-direta) diz respeito apenas a dois subespaços e não a uma quantidade finita arbitrária. O exemplo a seguir mostra que a propriedade de disjunção não garante soma direta para mais de dois subespaços.

:::{prf:example}

Considere os seguintes subespaços de $\mathbb{R}^{3}$:

- $S_{1}=\{ (x,y,0)/x,y\in \mathbb{R} \}$
- $S_{2}=\{ (0,0,z)/z\in \mathbb{R} \}$
- $S_{3}=\{ (0,w,w)/w\in \mathbb{R} \}$

Primeiramente, observe que $\mathbb{R}^{3}=S_{1}+S_{2}+S_{3}$. Além disso, $S_{1}\cap S_{2}=\{ 0 \}$, $S_{1}\cap S_{3}=\{ 0 \}$ e $S_{2}\cap S_{3}=\{ 0 \}$. No entanto, a soma entre esses subespaços não é direta, uma vez que a escrita de qualquer vetor do $\mathbb{R}^{3}$ não será única: Seja ${} (v_{1},v_{2},v_{3}) \in \mathbb{R}^{3} {}$, observe que $(v_{1},v_{2},v_{3})=(v_{1},v_{2},0)+(0,0,v_{3})+(0,0,0)$. Por outro lado, existem infinitas escolhas de $y,w \in \mathbb{R}$, ambas não nulas, de modo que $y+w=a_{2}$ e, a partir do $w$ escolhido, também podemos determinar $z\in \mathbb{R}$ de modo que $z+w=a_{3}$. Um exemplo numérico:

$$
\begin{align}
&(1,1,1)= (1,3,0)+(0,0,3)+(0,-2,-2) \\
&(1,1,1)=(1,1,0)+(0,0,1)+(0,0,0)
\end{align}
$$

Logo, a soma entre esses subespaços, igual ao $\mathbb{R}^{3}$, não é direta.

:::
