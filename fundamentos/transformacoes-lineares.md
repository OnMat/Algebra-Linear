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

Também denotaremos por $\mathcal{L}(V,W)$ o conjunto de todas as transformações lineares de $V$ para $W$. Logo, $T\in \mathcal{L}(V,W)$ significa que $T$ é uma transformação linear do espaço vetorial $V$ para o espaço vetorial $W$. Em particular, $\mathcal{L}(V,W)$ também é um espaço vetorial, considerando as operações de adição e multiplicação por escalar análogas as de funções.

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

$T \in \mathcal{L}(\mathbb{R}^{2},\mathbb{R}^{2})$ tal que 

$$
T(x,y)=(-y,x).
$$

:::

Essa transformação representa uma rotação do plano $\mathbb{R}^{2}$ em 90 graus no sentido anti-horário com centro na origem, como ilustra a animação abaixo:

:::{figure} ./videos/exemplorotacao.mp4
Animação feita com o software Manim
:::

Observe que, nessa ilustração, os vetores $\vec{v_{1}}$ e $\vec{v_{3}}$ formam uma base do $\mathbb{R}^{2}$, são os vetores ${} (0,2)$ e $(2,0)$, respectivamente. Enquanto que o vetor do meio, $\vec{v_{2}}$, corresponde ao vetor $(1,1)$. Perceba como $\vec{v_{2}}$ "acompanha" o movimento dos outros dois vetores, que para $\vec{v_{1}}$ e $\vec{v_{3}}$ fica evidente que é uma rotação anti-horária de 90 graus. É de se esperar que por $\vec{v_{1}}$ e $\vec{v_{3}}$ formarem uma base do $\mathbb{R}^{2}$, a transformação $T$ de qualquer vetor $\vec{v_{2}} \in \mathbb{R}^{2}$ seja dependente de $T\vec{v_{1}}$ e $T\vec{v_{3}}$, afinal, $\vec{v_{2}}$ é escrito como combinação linear de $\vec{v_{1}}$ e $\vec{v_{3}}$. É isso que discutiremos na seção seguinte.

### Determinação de transformações através de uma base
