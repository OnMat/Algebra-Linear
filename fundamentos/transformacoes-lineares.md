---
title: Transformações Lineares
subject: Fundamentos
---

Agora que já conhecemos os conceitos básicos relacionados a espaços vetoriais, assim como algumas propriedades fundamentais, começaremos a lidar com **Transformações Lineares**: funções em que o domínio e contradomínio são espaços vetoriais (e que possuem duas propriedades importantes). Juntamente com os vetores e espaços vetoriais, esse é o principal objeto de estudo da Álgebra Linear.

### Definição

:::{prf:definition} Transformação Linear
:label: deftransformacaolinear

Sejam $V$e $W$ espaços vetoriais, uma ***transformação linear*** $T$ de $V$ para $W$ é uma função $T:V\to W$, satisfazendo as duas propriedades a seguir:

1. **(Aditividade)** $T(u+v)=Tu+Tv, \;\forall u,v \in V$;
2. **(Homogeneidade)** $T(\alpha v)=\alpha Tv,\;\forall\alpha \in \mathbb{R}$ e $\forall v \in V$.

:::

Satisfazer essas duas propriedades é o que torna a transformação/função **linear**.[^1] Elas podem ser unidas em uma única propriedade: $T(\alpha v+w)=\alpha Tv+Tw,\; \forall\alpha \in \mathbb{R}$ e $\forall v,w \in V$.

Note que, quando o argumento da transformação for um único vetor $v$, utilizaremos a notação mais enxuta $Tv$, ao invés da notação funcional mais comum $T(v)$. Para argumentos "compostos", como no caso $T(u+v)$, preservaremos os parênteses.

[^1]: Funções não lineares (que não satisfazem essas propriedades), como $f(x)=x^{2}$, são objetos de estudo da área da Matemática chamada de **Análise** (cujo Cálculo Diferencial e Integral faz parte).

Também denotaremos por $\mathcal{L}(V,W)$ o conjunto de todas as transformações lineares de $V$ para $W$. Logo, $T\in \mathcal{L}(V,W)$ significa que $T$ é uma transformação linear do espaço vetorial $V$ para o espaço vetorial $W$. Em particular, $\mathcal{L}(V,W)$ também é um espaço vetorial, considerando as operações de adição e multiplicação por escalar análogas as de funções: definimos a soma entre duas transformações, ${} T,S\in \mathcal{L}(V,W) {}$ como ${} (T+S)v=Tv+Sv {}$ e o produto por escalar como $(\alpha T)v=\alpha(Tv)$, para $\alpha \in \mathbb{R}$. Os elementos neutros da adição e multiplicação são a transformação nula e a identidade, respectivamente (apresentadas nos exemplos abaixo).

É importante destacar uma propriedade clássica de transformações lineares que é consequência direta da condição de homogeneidade:

:::{prf:proposition} Transformações lineares preservam o vetor nulo
:label: prop-transformacoes-preservam-o-vetor-nulo

Seja $T \in \mathcal{L}(V,W)$. O vetor nulo de $V$ é sempre levado ao vetor nulo de $W$. Isto é,

$$
T0=0
$$

:::

:::{prf:proof}

Uma vez que $T$ é uma transformação linear, vale a condição de homogeneidade (propriedade 2 de [](#deftransformacaolinear)). Logo,

$$
T0=T(0\cdot0)=0\cdot T0=0 \quad (0w=0,\;\forall w \in W).
$$

Observe que o $0$ aparece representando o vetor nulo de $W$ (no membro direito da última igualdade) e o de $V$ (nos demais membros), assim como o escalar real nulo.

:::

### Exemplos

Vejamos alguns exemplos de transformações lineares (a transformação nula e a identidade aparecerão com frequência e serão importantes em momentos futuros). Em todos os exemplos, a verificação das propriedades 1 e 2 da [](#deftransformacaolinear) é simples.

:::{prf:example} Transformação nula

A transformação linear nula entre dois espaços vetoriais é aquela que leva todos os vetores do espaço domínio no vetor nulo do espaço contradomínio. Isto é, $T\in \mathcal{L}(V,W)$ tal que

$$
Tv=0,\;\forall v \in V.
$$

(com $0$ representando o vetor nulo de $W$)

:::

:::{prf:example} Transformação identidade

A transformação linear identidade (ou simplesmente identidade) de um espaço vetorial é aquela que leva todos os seus vetores neles mesmos. Isto é, $I \in \mathcal{L}(V,V)$ tal que

$$
Iv=v,\;\forall v \in V.
$$

:::

:::{prf:example} Derivada de um polinômio

$T \in \mathcal{L}(\mathcal{P_{n}},\mathcal{P}_{n-1})$ tal que 

$$
Tp=p'.
$$

(onde $p'$ representa a derivada de um polinômio $p \in \mathcal{P}_{n}$). 

A aditividade e homogeneidade da derivada são resultados clássicos do Cálculo.

:::

:::{prf:example} Uma transformação de $\mathbb{R}^{2}$ para $\mathbb{R}^{3}$

$T\in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{3})$ tal que

$$
T(x,y)=(x+2y,3x+4y,5x+6y).
$$

:::

O último exemplo de transformação linear possui um interessante sentido geométrico.

:::{prf:example} Rotação do plano
:label: exemplo-rotacao-do-plano

$T \in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{2})$ tal que 

$$
T(x,y)=(-y,x).
$$

:::

Essa transformação representa uma rotação do plano $\mathbb{R}^{2}$ em 90 graus no sentido anti-horário com centro na origem, como ilustra a animação abaixo:

:::{figure} ./videos/exemplorotacao.mp4
Animação feita com o software Manim
:::

Observe que, nessa ilustração, os vetores $\vec{v_{1}}$ e $\vec{v_{3}}$ formam uma base do $\mathbb{R}^{2}$, são os vetores ${} (0,2)$ e $(2,0)$, respectivamente. Enquanto que o vetor do meio, $\vec{v_{2}}$, corresponde ao vetor $(1,1)$. Perceba como $\vec{v_{2}}$ "acompanha" o movimento dos outros dois vetores, que para $\vec{v_{1}}$ e $\vec{v_{3}}$ fica evidente que é uma rotação anti-horária de 90 graus. É de se esperar que por $\vec{v_{1}}$ e $\vec{v_{3}}$ formarem uma base do $\mathbb{R}^{2}$, a transformação $T$ de qualquer vetor $\vec{v_{2}} \in \mathbb{R}^{2}$ seja dependente de $T\vec{v_{1}}$ e $T\vec{v_{3}}$, afinal, $\vec{v_{2}}$ é escrito como combinação linear de $\vec{v_{1}}$ e $\vec{v_{3}}$. É isso que discutiremos na seção a seguir.

### Determinação de transformações através de uma base

Até agora, com os exemplos dados, vimos transformações lineares definidas como estamos acostumados com funções: uma regra/fórmula que atribui a cada vetor do domínio um vetor no contradomínio. Acontece que, no caso de uma transformação linear,  ao escolhermos uma base do domínio podemos defini-la completamente somente pelas imagens dos vetores que compõem essa base, sem necessariamente saber qual regra a transformação aplica a um vetor genérico do domínio (mas podemos obtê-la, se quisermos). Tal fato é uma consequência natural das propriedades de uma base e da linearidade da transformação, como evidenciado abaixo.

:::{prf:observation}

Seja $T \in \mathcal{L}(V,W)$ e $(v_{1},\dots,v_{n})$ uma base de $V$. Veja que $T$ é inteiramente determinada pelas imagens de cada $v_{i}$, isto é, $Tv_{i}=w_{i} \in W$: Seja $v \in V$, $v$ pode ser escrito **de maneira única** como $v= a_{1}v_{1}+\dots+a_{n}v_{n}$, para $a_{i} \in \mathbb{R}$. Logo, 

$$
\begin{align}
Tv & =T(a_{1}v_{1}+\dots+a_{n}v_{n}) \\
 & =a_{1}Tv_{1}+\dots+a_{n}Tv_{n} \quad (\text{pela linearidade de }T) \\
 & =a_{1}w_{1}+\dots+a_{n}w_{n}
\end{align}
$$

Assim, conhecendo cada $w_{i}$, determinamos univocamente $Tv$ para todo $v \in V$.

:::

Para ilustrar isso na prática, voltemos ao [](#exemplo-rotacao-do-plano):

:::{prf:example}

Sabendo que a transformação $T\in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{2})$ no [](#exemplo-rotacao-do-plano) se trata de uma rotação do plano em 90 graus no sentido anti-horário, vejamos como poderíamos defini-la através da base canônica $((1,0),(0,1))$ de $\mathbb{R}^{2}$ e obter a fórmula geral que foi fornecida.

Claramente, com uma simples análise geométrica, obtemos que dada rotação do vetor $(1,0)$ resultará no vetor $(0,1)$, enquanto que do vetor $(0,1)$ resultará no vetor $(-1,0)$. Ou seja,

$$
\begin{cases}
Te_{1}=(0,1) \\
Te_{2}=(-1,0).
\end{cases}
$$

A partir disso, já conseguimos determinar $Tv$ para qualquer $v \in \mathbb{R}^{2}$. Para encontrar a fórmula geral de $T$, consideramos um vetor genérico $(x,y) \in \mathbb{R}^{2}$. De maneira imediata, temos que $(x,y)=xe_{1}+ye_{2}$. Sendo assim,

$$
\begin{align}
T(x,y) & =T(xe_{1}+ye_{2}) \\
 & =xTe_{1}+yTe_{2} \\
 & =x(0,1)+y(-1,0) \\
 & =(0,x)+(-y,0) \\
 & =(-y,x).
\end{align}
$$

Coincidindo com a fórmula de $T$ dada em [](#exemplo-rotacao-do-plano).

:::

Veja que, com um procedimento similar, podemos definir transformações que caracterizam rotações ao redor da origem em quaisquer direções e ângulos, apenas analisando geometricamente quais serão as imagens de uma base escolhida (onde normalmente a base canônica é a mais simples de se analisar).

Assim, podemos definir transformações lineares arbitrárias de maneira bastante simples, atribuindo as imagens dos vetores de uma base escolhida, sem se preocupar em definir uma fórmula geral e se ela garantirá a linearidade. 
 
### Composição/produto de transformações lineares

Assim como para funções, é natural que se tenha a composição de transformações lineares. A linearidade faz com que a composição possua algumas propriedades típicas da operação de produto, como distributividade e associatividade (mas não comutatividade, como será mostrado). Por isso, é comum também se referir a composição de transformações lineares como produto.

:::{prf:definition} Composição/produto de transformações lineares

Sejam $S \in \mathcal{L}(V,W)$ e $T \in \mathcal{L}(W,U)$. A ***composição*** ou ***produto*** de $T$ e $S$ é dado por $TS \in \mathcal{L}(V,U)$[^2], tal que

$$
(TS)v=T(Sv).
$$

Ou seja, dado $v \in V$, aplica-se $S$ e depois aplica-se $T$. Note que a imagem de $S$ deve pertencer ao domínio de $T$.



:::

[^2]: Utilizando o fato que $S$ e $T$ são lineares, é fácil verificar que $TS$ definido dessa forma será linear.

Com essa definição, valem as seguintes propriedades:

:::{prf:property} Associatividade

Sejam $S_{1},S_{2}$ e $S_{3}$ transformações lineares tais que o produto $S_{1}S_{2}S_{3}$ está definido (ou seja, a imagem de $S_{3}$ está no domínio de $S_{2}$ e a imagem de $S_{2}$ está no domínio de $S_{1}$). Vale que

$$
(S_{1}S_{2})S_{3}=S_{1}(S_{2}S_{3}).
$$

Isto é, aplicar $S_{3}$ e depois $S_{2}$ e $S_{1}$ é o mesmo que aplicar $S_{3}$ e $S_{2}$ e depois $S_{1}$ para todos os vetores no domínio de $S_{1}S_{2}S_{3}$.

:::

:::{prf:property} Distributividade

Sejam $S,S_{1},S_{2} \in \mathcal{L}(V,W)$ e $T,T_{1},T_{2} \in \mathcal{L}(U,V)$. Valem

1. $(S_{1}+ S_{2})T=S_{1}T+S_{2}T$;
2. $S(T_{1}+T_{2})=ST_{1}+ST_{2}$.

:::

:::{prf:property} Identidade

Sejam $I_{v}$ a identidade em $V$, $I_{w}$ a identidade em $W$ e $T \in \mathcal{L}(V,W)$. Vale que

$$
I_{w}T=TI_{v}=T.
$$

:::

Essas 3 propriedades são imediatas a partir das definições (composição, linearidade, soma de transformações e transformação identidade).

Como mencionado, **não vale a comutatividade para o produto de transformações**:

:::{prf:observation}

Sejam $S$ e $T$ transformações lineares tais que o produto $ST$ esteja definido. Não há garantia que $ST=TS$ (mesmo que $TS$ esteja definido).

:::

O caso mais óbvio de que a comutatividade não é garantida é quando $TS$ não está nem mesmo definido (a imagem de $S$ não pertence ao domínio de $T$). Como exemplo de um caso em que $ST$ e $TS$ estão ambos definidos, considere $S \in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{2})$ como a rotação do [](#exemplo-rotacao-do-plano) e $T \in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{2})$ como a reflexão em torno do eixo x dada por $T(x,y)=(x,-y)$. Basta um vetor $v \in \mathbb{R}^{2}$ tal que $STv \neq TSv$ para que $ST \neq TS$. Geometricamente, fica clara a diferença quando consideramos o vetor $(1,0)$:

:::{figure} ./videos/naocomut.mp4
:::

Algebricamente, temos que $ST(x,y)=S(x,-y)=(y,x)$, enquanto que $TS(x,y)=T(-y,x)=(-y,-x)$.

### Núcleo de uma transformação linear

O **núcleo** (comumente também referido como *kernel*) é um importante subconjunto do espaço vetorial do domínio de uma transformação linear.

:::{prf:definition} Núcleo de uma transformação linear

Seja $T \in \mathcal{L}(V,W)$. O ***núcleo*** de $T$, denotado por $N(T)$, é o seguinte subconjunto de $V$:

$N(T)=\{ v \in V/Tv=0 \}$.

Ou seja, o conjunto de vetores em $V$ que são mapeados por $T$ para o vetor nulo em $W$.

:::

Lembrando da [](#prop-transformacoes-preservam-o-vetor-nulo), sempre temos que $N(T) \neq \emptyset$, pois o núcleo possui como elemento, pelo menos, o vetor nulo do domínio.

:::{prf:example}

Seja $p \in \mathcal{P}_{n}$, um polinômio de grau máximo $n$, e $T \in \mathcal{L}(\mathcal{P}_{n},\mathcal{P}_{n-1})$ a derivada ($Tp=p'$). Sabemos, pelas regras de derivação de polinômios, que a derivada de um polinômio é nula se, e somente se, o polinômio for constante. Ou seja,

$$
N(T)=\mathcal{P}_{0}.
$$

Onde $\mathcal{P}_{0}$ é o conjunto dos polinômios de grau máximo zero, ou seja, o conjunto dos polinômios constantes, que é um subconjunto de $\mathcal{P}_{n}$, o domínio de $T$.

:::

Por outro lado, observe que no caso da transformação de rotação do [](#exemplo-rotacao-do-plano) é evidente que o núcleo é somente o vetor nulo (a origem do plano).

Além de um subconjunto, o núcleo é também um subespaço:

:::{prf:proposition} O núcleo é um subespaço

Seja $T \in \mathcal{L}(V,W)$. $N(T)$ é um subespaço de $V$.

:::

:::{prf:proof}

Uma vez que $N(T)\subseteq V$, utilizamos [](#def-subespaco). Pela [](#prop-transformacoes-preservam-o-vetor-nulo) já temos que $0 \in N(T)$. Observe que, sejam $v,w \in N(T)$, temos

$$
T(v+w)=Tv+Tw=0+0=0
$$

Logo, $v+w \in N(T)$. O núcleo é fechado na soma. Similarmente, seja $v \in N(T)$ e $\alpha \in \mathbb{R}$, temos

$$
T(\alpha v)=\alpha Tv=\alpha \cdot 0=0
$$

Portanto, o núcleo é fechado na multiplicação por escalar. Consequentemente, $N(T)$ é um subespaço de $V$.

:::

#### Injetividade

O conceito de **injetividade**, assim como para funções, também vale para transformações lineares.

:::{prf:definition} Injetividade

Seja $T\in \mathcal{L}(V,W)$. Dizemos que $T$ é ***injetiva*** se para todo $v,w \in V$, sempre que $Tv=Tw$ tivermos $v=w$.

:::

Essa definição de injetividade é basicamente a mesma da usual para funções. Quer dizer que $T$, quando é injetiva, mapeia elementos distintos do domínio em elementos distintos do contradomínio.

A grande diferença em relação à injetividade usual de funções é, no caso de transformações lineares, como essa propriedade se relaciona com o núcleo:

:::{prf:proposition}

Seja $T\in \mathcal{L}(V,W)$. $T$ é injetiva se, e somente se, $N(T)=\{ 0 \}$.

:::

:::{prf:proof}

$(\implies)$ Seja $T$ injetiva e $v \in N(T)$. Temos que $Tv=0=T0$. Logo, pela injetividade de $T$, $v=0$. Portanto, o único elemento no núcleo de $T$ é o vetor nulo: $N(T)=\{ 0 \}$.

$(\impliedby)$ Seja $N(T)=\{ 0 \}$ e $v,w \in V$ tais que $Tv = Tw$. Temos,

$$
\begin{align}
T(v-w) & =Tv-Tw \\
 & =0.
\end{align}
$$

Ou seja, $v-w \in N(T)$. Consequentemente, uma vez que $N(T)=\{ 0 \}$, $v-w = 0$, donde temos $v=w$. Logo, $T$ é injetiva.

:::

### Imagem de uma transformação linear

Para transformações lineares, o conceito de **imagem** é análogo ao usual para funções.

:::{prf:definition} Imagem de uma transformação linear

Seja $T\in \mathcal{L}(V,W)$. A ***imagem*** de $T$, denotada por $\text{Im}(T)$, é o seguinte subconjunto de $W$:

$$
\text{Im}(T)=\{ Tv/v \in V \}.
$$

:::

:::{prf:example}
:label: exemplo-sobrejeitividade

Mais uma vez considerando o exemplo da derivada, se $T \in \mathcal{L}(\mathcal{P}_{n},\mathcal{P_{n-1}})$ com $Tp=p'$, é evidente que $\mathrm{Im}(T)=\mathcal{P_{n-1}}$ (lembre-se que todo polinômio é integrável. Logo, para todo elemento $q$ em $\mathcal{P}_{n-1}$ existe um elemento $p$ em $\mathcal{P}_{n}$ tal que $p'=Tp=q$).

:::

Assim como no caso do núcleo, a imagem de uma transformação linear também é um subespaço, agora do contradomínio.

:::{prf:proposition} A imagem é um subespaço

Seja $T\in \mathcal{L}(V,W)$. $\mathrm{Im}(T)$ é um subespaço de $W$.

:::

:::{prf:proof}

Utilizamos a [](#def-subespaco) novamente. Como $T0=0$, temos que $0 \in \mathrm{Im}(T)$. Sejam $Tv,Tw \in \mathrm{Im}(T)$, observe que

$$
Tv+Tw=T(v+w),\;\text{para }v,w \in V.
$$

Logo, $Tv+Tw \in \mathrm{Im}(T)$ (lembre-se que $v+w \in V$ e $T$ está definida para todos os elementos em $V$). Além disso, seja $\alpha \in \mathbb{R}$,

$$
\alpha Tv=T(\alpha v).
$$

Mostrando que $\alpha Tv \in \mathrm{Im}(T)$ também. Logo, $\mathrm{Im}(T)$ é um subespaço de $W$.

:::

#### Sobrejetividade

Do mesmo modo que com a injetividade, o conceito de sobrejetividade para transformações lineares também é análogo ao de funções.

:::{prf:definition} Sobrejetividade

Seja $T\in \mathcal{L}(V,W)$. $T$ é ***sobrejetiva*** quando $\mathrm{Im}(T)=W$.

:::

A transformação do [](#exemplo-sobrejeitividade) é sobrejetiva. Veja que, no entanto, **a sobrejetividade depende do espaço considerado no contradomínio**. Poderíamos, nesse mesmo exemplo, considerar o contradomínio como $\mathcal{P}_{n}$ ao invés de $\mathcal{P}_{n-1}$, sem alterar de fato a transformação. Mas, nesse caso, ela não seria sobrejetiva. 

### Teorema do Núcleo e Imagem

Os conceitos de núcleo e imagem de transformações lineares se unem em um dos principais resultados da Álgebra Linear, que diz que dada uma transformação, a dimensão de seu domínio é sempre igual a dimensão de seu núcleo mais a dimensão de sua imagem. Lembramos que os espaços considerados possuem dimensão finita.

:::{prf:theorem} Teo. do núcleo e imagem
:label: teo-nucleo-imagem

Seja $T \in \mathcal{L}(V,W)$. Então,

$$
\dim V=\dim N(T)+\dim \mathrm{Im}(T).
$$

:::

:::{prf:proof}

Começamos considerando uma base $(u_{1},\dots,u_{n})$ de $N(T)$. Logo, $\dim N(T)=n$. Então, podemos estender essa base de $N(T)$ (que é uma lista linearmente independente de vetores em $V$) em uma base de $V$: $(u_{1},\dots,u_{n},w_{1},\dots,w_{m})$. Donde temos que $\dim V=n+m$. A partir disso, basta provarmos que $\dim \mathrm{Im}(T)=m$; em particular, provaremos que $(Tw_{1},\dots,Tw_{m})$ é uma base de $\mathrm{Im}(T)$.

Primeiro, devemos mostrar que $(Tw_{1},\dots,Tw_{m})$ gera $\mathrm{Im}(T)$. Seja $Tv \in \mathrm{Im}(T)$, para algum $v \in V$, temos que (uma vez que $(u_{1},\dots,u_{n},w_{1},\dots,w_{m})$ é uma base de $V$)

$$
v  =\alpha_{1}u_{1}+\dots+\alpha_{n}u_{n}+\beta_{1}w_{1}+\dots+\beta_{m}w_{m},\; \alpha_{i},\beta_{i} \in \mathbb{R}.
$$

Ao aplicarmos $T$ em ambos os lados dessa igualdade, obtemos (considerando que $(u_{1},\dots,u_{n})$ é uma base de $N(T)$, logo, $Tu_{i}=0$)

$$
Tv=\beta_{1}Tw_{1}+\dots+\beta_{m}Tw_{m}.
$$

Como $Tv$ é um elemento arbitrário de $\mathrm{Im}(T)$ e pode ser escrito como combinação linear de $(Tw_{1},\dots,Tw_{m})$, então $(Tw_{1},\dots,Tw_{m})$ gera $\mathrm{Im}(T)$.

Para mostrar que $(Tw_{1},\dots,Tw_{m})$ é linearmente independente. Considere $c_{1},\dots,c_{m} \in \mathbb{R}$ tais que

$$
c_{1}Tw_{1}+\dots+c_{m}Tw_{m}=0.
\label{eq:Twi-li}
$$

Então, utilizando a linearidade de $T$,

$$
T(c_{1}w_{1}+\dots+c_{m}w_{m})=0.
$$

O que nos diz que $c_{1}w_{1}+\dots+c_{m}w_{m} \in N(T)$. Logo, $c_{1}w_{1}+\dots+c_{m}w_{m}$ pode ser escrito como combinação linear da base $(u_{1},\dots,u_{n})$ de $N(T)$:

$$
c_{1}w_{1}+\dots+c_{m}w_{m}=d_{1}u_{1}+\dots+d_{n}u_{n},\;d_{i} \in \mathbb{R}.
$$

Por outro lado, $(u_{1},\dots,u_{n},w_{1},\dots,w_{m})$ é uma base de $V$ e, em particular, é linearmente independente. Portanto, nesta última igualdade temos $c_{1}=\dots=c_{m}=d_{1}=\dots=d_{n}=0$. Voltando à igualdade {eq}`eq:Twi-li`, temos então que $(Tw_{1},\dots,Tw_{m})$ é linearmente independente e, logo, uma base de $\mathrm{Im}(T)$, como queríamos mostrar.

:::

A maneira como é feita a demonstração nos revela um panorama geral desse resultado que vai além da igualdade numérica entre as dimensões: dada uma transformação linear, podemos obter uma base do espaço vetorial do domínio formada pela concatenação de uma base do núcleo e uma base da imagem dessa transformação. É como se dividíssemos o espaço do domínio em duas partes em relação à transformação considerada, uma é mapeada no vetor nulo do contradomínio enquanto a outra gera a imagem.

Os próximos corolários ilustram parte da importância do [](#teo-nucleo-imagem). Quando o unimos aos conceitos de injetividade e sobrejetividade, podemos obter informações importantes acerca da transformação linear apenas relacionando as dimensões dos espaços vetoriais envolvidos.
