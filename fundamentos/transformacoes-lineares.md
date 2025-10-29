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

### Núcleo de uma transformação
