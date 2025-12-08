---
title: Decomposição em Valores Singulares (SVD)
subject: Tópicos Avançados
---

### A decomposição SVD

Vimos no [Teorema Espectral](teorema-espectral.md) que é possível decompor qualquer matriz simétrica como o produto entre 3 matrizes, sendo uma delas diagonal (contendo os autovalores) e as outras duas ortogonais (de transição entre a base canônica e a base ortonormal de autovetores). Esse tópico apresenta uma espécie de "generalização" do Teorema Espectral para uma matriz qualquer de dimensão $m \times n$.

A ideia geral é similar, queremos decompor uma matriz $A\in \mathbb{R}^{m\times n}$ como o produto entre 3 matrizes:

$$
A=U\Sigma V^{T}
$$

Em particular, nos seria interessante que tais matrizes tenham propriedades similares ao caso do Teorema Espectral, com $U$ e $V^{T}$ ortogonais e $\Sigma$ diagonal. Mas note que se $A$ não é quadrada essa configuração não é possível, já que para tal deveríamos ter 3 matrizes quadradas, cujo produto não resultaria em uma matriz não quadrada. Como veremos, o que obteremos será o seguinte:

- $U$ é uma matriz ortogonal $m\times m$;
- $\Sigma$ é uma matriz retangular diagonal $m\times n$;
- $V^{T}$ é a transposta de uma matriz ortogonal $n\times n$.

O próximo teorema é a base para essa ideia. Ele nos indica quais serão os valores da diagonal de $\Sigma$, chamados de *valores singulares*, e quais os vetores que irão compor as matrizes $U$ e $V^{T}$. Para demonstrá-lo precisamos do seguinte lema:

:::{prf:lemma}
:label: lema-valores-singulares

Seja $A$ uma matriz $m\times n$ e $v$ um vetor coluna de dimensão $n$, tal que $A^{T}Av=\lambda v$ ($v$ é autovetor de $A^{T}A$), então $AA^{T}(Av)=\lambda Av$ ($Av$ é um autovetor de $AA^{T}$ associado a $\lambda$).

:::

:::{prf:proof}

$$
AA^{T}(Av)=A(A^{T}Av)=A(\lambda v)=\lambda Av
$$

:::

:::{prf:theorem} Valores Singulares
:label: teo-valores-singulares1

Seja $A\in \mathbb{R}^{m\times n}$, com posto igual a $r$. Existem números reais $\sigma_{1}\geq \dots\geq \sigma_{r}>0$, chamados de *valores singulares* de $A$, e bases ortonormais $\{ v_{1},\dots,v_{n} \}$ de $\mathbb{R}^{n}$ e $\{ u_{1},\dots,u_{m} \}$ de $\mathbb{R}^{m}$, tais que:

- $Av_{i}=\sigma_{i}u_{i}$, para $i=1,\dots,r$;
- $Av_{i}=0$, para $i=r+1,\dots,n$;
- $A^{T}u_{i}=\sigma_{i}v_{i}$, para $i=1,\dots,r$;
- $A^{T}u_{i}=0$, para $i=r+1,\dots,m$.

Onde $v_{1},\dots,v_{n}$ são autovetores de $A^{T}A$, $u_{1},\dots,u_{m}$ são autovetores de $AA^{T}$ e $\sigma_{1}^{2},\dots,\sigma_{r}^{2}$ são os autovalores não nulos de $A^{T}A$ e $AA^{T}$.

:::

:::{prf:proof}

Pelo [](#pre-teorema-valores-singulares) sabemos que existe uma base ortonormal $\{ v_{1},\dots,v_{n} \}$ do $\mathbb{R}^{n}$ constituída de autovetores de $A^{T}A$, com $\lambda_{1},\dots,\lambda_{n}$ autovalores associados respectivamente. Além disso, $A^{T}A\geq0$ e portanto todos os seus autovalores são não negativos.

Dessa forma, considere $\{ v_{1} ,\dots,v_{n}\}$ ordenados tais que $\lambda_{1}\geq \dots\geq \lambda_{n}\geq0$. Também de [](#pre-teorema-valores-singulares) sabemos que o posto de $A^{T}A$ é o mesmo de $A$, igual a $r$. Logo, temos que:

$$
\lambda_{1}\geq\dots\geq \lambda_{r}>0 \qquad \text{e} \qquad \lambda_{r+1}=\dots=\lambda_{n}=0
$$

Então, para $i=1,\dots,r$ iremos definir:

$$
\sigma_{i} := \lVert Av_{i} \rVert \qquad \text{e} \qquad u_{i} :=\frac{1}{\sigma_{i}}Av_{i}
$$

Ou seja, para $i=1,\dots,r$ temos $Av_{i}=\sigma_{i}u_{i}$, onde cada $u_{i}$ é um vetor unitário. Além disso, como $\lVert Av_{i} \rVert=\sigma_{i}$, temos

$$
\begin{align}
\sigma_{i}^{2}&=\lVert Av_{i} \rVert^{2} \\
&=\langle Av_{i} , Av_{i} \rangle  \\
&= (Av_{i})^{T}Av_{i} \\
&=v_{i}^{T}A^{T}Av_{i} \\
&=v_{i}^{T}\lambda_{i}v_{i} \\
&=\lambda_{i}v_{i}^{T}v_{i} \\
&=\lambda_{i}
\end{align}
$$

(observe que como $\{ v_{1},\dots,v_{n} \}$ é ortonormal, então $\langle v_{i} , v_{i} \rangle=v_{i}^{T}v_{i}=1$)

Para $i\neq j$ temos que $\langle v_{i} , v_{j} \rangle=0$ (pois compõem uma base ortonormal). Além disso $A^{T}Av_{i}=\lambda_{i}v_{i}$ e $A^{T}Av_{j}=\lambda_{j}v_{j}$, então:

$$
\langle Av_{i} , Av_{j} \rangle=(Av_{i})^{T}Av_{j}=v_{i}^{T}A^{T}Av_{j}=v_{i}^{T}\lambda_{j}v_{j}=\lambda_{j}v_{i}^{T}v_{j}=\lambda_{j}\langle v_{i} , v_{j} \rangle=\lambda \cdot 0=0
$$

Logo, $Av_{i}$ e $Av_{j}$ também são ortogonais. Em particular, $\{ u_{1} ,\dots,u_{r}\}$ são ortonormais. Além disso, para $i=1,\dots,r$,

$$
A^{T}u_{i}=A^{T}\left( \frac{1}{\sigma_{i}}Av_{i} \right)=\frac{1}{\sigma_{i}}A^{T}Av_{i}=\frac{1}{\sigma_{i}}\lambda_{i} v_{i}=\frac{\sigma_{i}^{2}}{\sigma_{i}}v_{i}=\sigma_{i}v_{i}
$$

E como consequência do [](#lema-valores-singulares) temos que, para $i=1,\dots,r$, $u_{i}$ é autovetor de $AA^{T}$ com autovalor não nulo. 

Observe também que a dimensão do espaço nulo de $AA^{T}$ deve ser $m-r$, uma vez que $\text{posto}(AA^{T})=\text{posto}(A)=r$. 

Consideramos então uma base ortonormal $\{ u_{r+1},\dots,u_{m} \}$ de $N(AA^{T})$ (ou seja, cada $u_{i}$ desses é um autovetor de $AA^{T}$ associado ao autovalor $0$). E ainda, $u_{r+1},\dots,u_{m}$ são ortogonais a $u_{1},\dots,u_{r}$, pois a soma direta dos espaços gerados por eles, respectivamente, é igual ao espaço $\mathbb{R}^{m}$, que por sua vez também é igual a soma direta entre o espaço gerado por $u_{1},\dots,u_{r}$ e seu complemento ortogonal. Logo, $\{ u_{1},\dots,u_{m} \}$ constitui uma base ortonormal de $\mathbb{R}^{m}$ formada por autovetores de $AA^{T}$. 

Note que, para $i=r+1,\dots,m$, temos $A^{T}u_{i}=0$, pois $N(AA^{T})=N(A^{T})$, como proposto. Similarmente, para $i=r+1,\dots,n$ temos $\lambda_{i}=0$ e ${} A^{T}Av_{i}=0 {}$, logo $Av_{i}=0$, pois $N(A^{T}A)=N(A)$.

:::

Tais $v_{1},\dots,v_{n}$ constituirão as colunas da matriz $V$ e são chamados de *vetores singulares à direita*, enquanto $u_{1},\dots,u_{m}$ constituirão as colunas de $U$ e são chamados de *vetores singulares à esquerda*.

A partir disso, temos então a chamada *Decomposição em Valores Singulares* (também conhecida como *SVD*, do inglês *Singular Value Decomposition*) de uma matriz:

:::{prf:theorem} Decomposição em valores singulares

Seja $A\in \mathbb{R}^{m\times n}$, existem matrizes ortogonais $V\in \mathbb{R}^{n \times n}$ e $U\in \mathbb{R}^{m \times m}$ e uma matriz retangular diagonal $\Sigma \in \mathbb{R}^{m\times n}$ tais que

$$
A=U\Sigma V^{T}
$$

Em particular, sejam $\sigma_{1},\dots,\sigma_{r}$, $\{ v_{1},\dots,v_{n} \}$ e $\{ u_{1},\dots,u_{m} \}$ os mesmos do [teorema anterior](#teo-valores-singulares1), temos $V=[v_{1}\dots v_{n}]$, $U=[u_{1}\dots u_{m}]$ e $\sigma_{1},\dots,\sigma_{r}$ compondo as entradas não nulas da diagonal principal de $\Sigma$, nesta ordem.

:::

:::{prf:proof}

Novamente, considere $\{ v_{1},\dots,v_{n} \}$, $\{ u_{1},\dots,u_{m} \}$ e $\sigma_{1},\dots,\sigma_{r}$ do [](#teo-valores-singulares1). Claramente as matrizes $V=[v_{1} \dots v_{n}]$ e $U=[u_{1} \dots u_{m}]$ são ortogonais, pois são formadas por vetores ortonormais.

Considere a matriz $\Sigma$ retangular diagonal de dimensão $m \times n$, contendo em sua diagonal principal $\sigma_{1},\dots,\sigma_{r}$ (nesta ordem) e as demais entradas nulas.

Observe que $U\Sigma=[\sigma_{1}u_{1}\dots \sigma_{r}u_{r}\;\; 0\dots0]$. Multiplicando isto por $V^{T}$ à direita, obtemos:

$$
U\Sigma V^{T}=[\sigma_{1}u_{1}\dots \sigma_{r}u_{r}\;\; 0\dots0]\cdot \begin{bmatrix}
v_{1}^{T} \\
v_{2}^{T} \\
\vdots \\
v_{n}^{T}
\end{bmatrix}=\sum_{i=1}^{r}\sigma_{i}u_{i}v_{i}^{T}
$$

Pelo [](#teo-valores-singulares1), sabemos que a ação de $A$ em qualquer vetor $v_{j}$ é dada por:

$$
Av_{j}=\begin{cases}
\sigma_{j}u_{j} & \text{se }j\leq r, \\
0 & \text{se }j>r
\end{cases}
$$

Mas note que isso coincide com a ação de $\Sigma_{i=1}^{r}\sigma_{i}u_{i}v_{i}^{T}$ em $v_{j}$, pois

$$
\left( \sum_{i=1}^{r}\sigma_{i}u_{i}v_{i}^{T} \right)\cdot [v_{j}]=\sum_{i=1}^{r}\sigma_{i}u_{i}v_{i}^{T}v_{j}=\sigma_{j}u_{j} \quad \text{para }j\leq r, \quad \text{e }0\text{ para }j>r.
$$

(consequência do fato que $\{ v_{1},\dots,v_{n} \}$ é ortonormal, logo $v_{i}^{T}v_{j}=0$ se $i \neq j$ e $v_{i}^{T}v_{j}=1$ se $i=j$)

Dado que $\{ v_{1},\dots,v_{n} \}$ é uma base de $\mathbb{R}^{n}$, devemos ter (pela unicidade de uma transformação linear sobre uma base) que

$$
A=\sum_{i=1}^{r}\sigma_{i}u_{i}v_{i}^{T}=U \Sigma V^{T}.
$$

:::

Vejamos agora um exemplo, para entender como a decomposição em valores singulares é feita na prática.

:::{prf:example}

Vamos determinar a decomposição em valores singulares da seguinte matriz:

$$
A=
\begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix}
$$

Antes, observe o seguinte (isso vale para qualquer matriz): Para obter os valores singulares e a matriz $\Sigma$, podemos escolher entre $A^{T}A$ ou $AA^{T}$ para calcular os autovalores, pois sabemos que elas terão exatamente os mesmos autovalores não nulos. Já para determinar $U$ e $V$, uma maneira seria calcular tanto $A^{T}A$ como $AA^{T}$ e encontrar os autovetores associados aos seus respectivos autovalores (incluindo os nulos), normalizá-los (e ortogonalizá-los, se necessário[^nota1]) e obter $V$ e $U$, respectivamente. No entanto, seja $r=\text{posto}(A)$, podemos fazer uso das seguintes relações:

$$
Av_{i}=\sigma_{i}u_{i} \quad \text{e} \quad A^{T}u_{i}=\sigma_{i}v_{i},\;i=1,\dots,r
$$

Logo, podemos adotar a seguinte estratégia: Calculamos somente $A^{T}A$ ou $AA^{T}$, a que possui menor dimensão ($\min\{ m,n \}$). Assim, o processo de encontrar os autovalores (e consequentemente os valores singulares) e uma base ortonormal constituída de autovetores do espaço correspondente ao da matriz escolhida será menos trabalhoso. Para encontrar a outra matriz restante ($U$ ou $V$), fazemos uso das igualdades acima, bastando calcular as imagens $Av_{i}$ ou $A^{T}u_{i}$ e dividir as coordenadas pelo valor singular $\sigma_{i}$ correspondente, obtendo $r$ dos vetores que compõem a matriz restante. Para os $m-r$ ou $n-r$ vetores restantes, correspondentes aos valores singulares nulos, basta completarmos o conjunto dos $r$ vetores que já temos de maneira a formar uma base ortonormal do espaço correspondente (isto é, completamos com uma base ortonormal de $N(A)$ ou $N(A^{T})$)[^nota2].

Com isso em mente, vamos decompor $A$. Observe que $A^{T}A$ é $3\times3$, enquanto que $AA^{T}$ é $2\times 2$. Logo, vamos escolher $AA^{T}$ para trabalharmos e encontraremos primeiramente a matriz $U$.

$$
AA^{T}=\begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix}\cdot \begin{bmatrix}
1 & 0 \\
0 & 1 \\
1 & 0
\end{bmatrix}=\begin{bmatrix}
2 & 0 \\
0 & 1
\end{bmatrix}
$$

Note que $AA^{T}$ já se encontra na forma diagonal, logo seus autovalores são $2$ e $1$ (observe que eles já são distintos, então precisaremos apenas normalizar os autovetores encontrados, obtendo uma base ortonormal de $\mathbb{R}^{2}$ e a matriz $U$). Dessa forma, já obtemos os valores singulares: $\sigma_{1}=\sqrt{ 2 }$ e $\sigma_{2}=\sqrt{ 1 }=1$. Consequentemente, 

$$
\Sigma=\begin{bmatrix}
\sqrt{ 2 } & 0 & 0 \\
0 & 1 & 0
\end{bmatrix}
$$

Mais uma vez, como $AA^{T}$ já está na forma diagonal, a base ortonormal de autovetores é propriamente a base canônica de $\mathbb{R}^{2}$, ou seja, $e_{1}=(1,0)$ está associado ao autovalor $2$ e $e_{2}=(0,1)$ ao autovalor $1$, temos então:

$$
U=\begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix}
$$

Resta apenas determinar $V$. Observe de antemão que como obtemos dois autovalores não nulos, iremos obter as duas primeiras colunas da matriz $V$ (de dimensão $n\times n$, neste caso, ${} 3 \times 3 {}$) por $A^{T}u_{i}=\sigma_{i}v_{i}$, restando apenas determinar a coluna restante (iremos encontrar um vetor unitário ortogonal à $v_{1}$ e $v_{2}$). Logo,

$$
\begin{align}
v_{1}=\frac{1}{\sigma_{1}}\cdot A^{T}u_{1}=\frac{1}{\sqrt{ 2 }}\cdot \begin{bmatrix}
1 & 0 \\
0 & 1 \\
1 & 0
\end{bmatrix}\cdot \begin{bmatrix}
1 \\
0
\end{bmatrix} =\begin{bmatrix}
\frac{1}{\sqrt{ 2 }} \\
0 \\
\frac{1}{\sqrt{ 2 }}
\end{bmatrix}
\end{align}
$$

$$
v_{2}=\frac{1}{\sigma_{2}}\cdot A^{T}u_{2}=1\cdot \begin{bmatrix}
1 & 0 \\
0 & 1 \\
1 & 0
\end{bmatrix}\cdot \begin{bmatrix}
0 \\
1
\end{bmatrix}=\begin{bmatrix}
0 \\
1 \\
0
\end{bmatrix}
$$

Para encontrar $v_{3}$, utilizaremos o processo de Gram-Schmidt. Começamos encontrando um $v_{3}'$ de forma que ${} \{ v_{1},v_{2},v'_{3} \} {}$ seja uma base de $\mathbb{R}^{3}$ (completar a base). Observe que ${} v_{3}'=(1,0,0) {}$ funciona. Agora, utilizaremos $v_{3}'$ para determinar $v_{3}''$ de forma que $\{ v_{1},v_{2},v_{3}'' \}$ seja uma base ortogonal de $\mathbb{R}^{3}$ (ortogonalizar). Temos que

$$
v_{3}''=v_{3}'-\text{proj}_{[v_{1},v_{2}]}\;v_{3}'
$$

será ortogonal a $v_{1}$ e $v_{2}$. Logo,

$$
\begin{align}
v_{3}'' & =v_{3}'-\text{proj}_{v_{1}}v_{3}' -\text{proj}_{v_{2}}v_{3}' \\
 & =v_{3}'-\frac{\langle v_{3}' , v_{1} \rangle}{\lVert v_{1} \rVert^{2} }v_{1}-\frac{\langle v_{3}' , v_{2} \rangle}{\lVert v_{2} \rVert^{2} }v_{2} \\
 & =(1,0,0)-\frac{1}{\sqrt{ 2 }}\cdot \left( \frac{1}{\sqrt{ 2 }},0,\frac{1}{\sqrt{ 2 }} \right)-0\cdot (0,1,0) \\
 & =(1,0,0)+\left( \frac{-1}{2},0,\frac{-1}{2} \right) \\
 & =\left( \frac{1}{2},0,\frac{-1}{2} \right)
\end{align}
$$

Por fim, devemos normalizar $v_{3}''$, ou seja, $v_{3}=\frac{v_{3}''}{\lVert v_{3}'' \rVert}$:

$$
v_{3}= \frac{\left( \frac{1}{2},0,\frac{-1}{2} \right)}{1/\sqrt{ 2 }}=\left( \frac{\sqrt{ 2 }}{2},0,\frac{-\sqrt{ 2 }}{2} \right)
$$

Portanto,

$$
V=\begin{bmatrix}
\frac{1}{\sqrt{ 2 }}  & 0 & \frac{\sqrt{ 2 }}{2} \\
0  & 1 & 0\\
\frac{1}{\sqrt{ 2 }} & 0 & \frac{-\sqrt{ 2 }}{2}
\end{bmatrix}
$$

$$
V^{T}=\begin{bmatrix}
\frac{1}{\sqrt{ 2 }} & 0 & \frac{1}{\sqrt{ 2 }} \\
0 & 1 & 0 \\
\frac{\sqrt{ 2 }}{2} & 0 & \frac{-\sqrt{ 2 }}{2}
\end{bmatrix}
$$

E finalmente:

$$
A=\begin{bmatrix}
1 & 0 & 1 \\
0 & 1 & 0
\end{bmatrix}=\underbrace{ \begin{bmatrix}
1 & 0 \\
0 & 1
\end{bmatrix} }_{ U }\cdot \underbrace{ \begin{bmatrix}
\sqrt{ 2 } & 0 & 0 \\
0 & 1 & 0
\end{bmatrix} }_{ \Sigma }\cdot \underbrace{ \begin{bmatrix}
\frac{1}{\sqrt{ 2 }} & 0 & \frac{1}{\sqrt{ 2 }} \\
0 & 1 & 0 \\
\frac{\sqrt{ 2 }}{2} & 0 & \frac{-\sqrt{ 2 }}{2}
\end{bmatrix} }_{ V^{T} }
$$

[^nota1]: Caso todos os autovalores sejam distintos, por [](#autovetores-associados-a-autovalores-distintos-ortogonais) sabemos que todos os autovetores encontrados serão ortogonais. Mas, caso hajam autovalores repetidos, não há essa garantia. Logo, talvez seja necessário ortogonalizar alguns autovetores, o que pode ser feito via processo de Gram-Schmidt.

[^nota2]: O que mais uma vez pode ser feito via processo de Gram-Schmidt.

:::

### Aproximação de matrizes utilizando SVD

Entre uma das muitas aplicações da decomposição SVD está a aproximação de matrizes. Em um cenário computacional, é comum que seja mais vantajoso trabalharmos com uma aproximação de determinado objeto matemático do que com sua forma exata. Para matrizes isso ocorre com bastante frequência.

Por exemplo, suponha que uma matriz $A$ de posto $r$ possua os valores singulares não nulos $\sigma_{1},\dots,\sigma_{r-1},0.0001$. Ou seja, $\sigma_{r}=0.0001$. Ao realizarmos cálculos com essa matriz na forma SVD em um computador, devido à natureza da arimética de ponto flutuante, haverá um acúmulo de erros decorrente dos produtos com a entrada $0.0001$. Nesse caso, como $0.0001$ está muito próximo de $0$, acaba sendo mais benéfico (do ponto de vista de minimização de erros) "truncarmos" o posto de $A$ para $r-1$, isto é, consideramos $\sigma_{r}=0$.

Primeiramente, precisamos de uma métrica que nos permita determinar o quão "próximas" estão duas matrizes, assim definimos uma norma para matrizes. Em particular, existem diferentes tipos de normas para matrizes (assim como existem para vetores), mas para os própositos desse tópico nos será útil a *norma 2*, pela relação que ela possui com os valores singulares.

:::{prf:definition} Norma 2 matricial
 
Seja $A\in \mathbb{R}^{m\times n}$, definimos a norma 2 de $A$ como:

$$
\lVert A \rVert_{2}=\sup _{\lVert x \rVert_{2}=1 }\lVert Ax \rVert_{2} \quad (x \in \mathbb{R}^{n}) 
$$

onde $\lVert x \rVert_{2}$ corresponde à norma 2 (ou norma euclidiana) para vetores do $\mathbb{R}^{n}$.

:::

Essa é a definição mais comum, mas verifica-se que ela é equivalente a seguinte, que explicita a relação dessa norma com os valores singulares:

:::{prf:definition} Norma 2 matricial via valores singulares

Seja $A\in \mathbb{R}^{m\times n}$, sua norma 2 é dada pelo maior valor singular de $A$. Ou seja,

$$
\lVert A \rVert_{2}=\sigma_{\max}(A) 
$$

:::

Essa equivalência entre as duas definições fica evidente quando pensamos geometricamente. A primeira definição diz respeito ao maior "alongamento" na norma 2 vetorial que $A$ causa, entre todos os vetores unitários do ${} \mathbb{R}^{n} {}$, que corresponde justamente ao seu maior valor singular (uma vez que os vetores $v_{1},\dots,v_{n}$ que compõem a matriz $V$ da decomposição SVD formam uma base de $\mathbb{R}^{n}$).

Então, temos a aproximação de matrizes via *truncamento da SVD*:

:::{prf:definition} Matriz $A_{k}$
:label: def-matrizak-eckart-young

Seja $A \in \mathbb{R}^{m\times n}$ com posto $r$ e decomposição SVD $A=U\Sigma V^{T}$, fixado $k$ entre $1,\dots,r-1$ definimos a matriz $A_{k}$ como:

$$
A_{k}:=U\Sigma_{k}V^{T}
$$

onde $\Sigma_{k}$ é a matriz $\Sigma$ com $\sigma_{i}=0$ para $i=k+1,\dots,r$.

:::

Observe que $A_{k}$ possui posto $k$.

:::{prf:theorem} Eckart-Young
:label: teo-eckart-young

Seja $A\in \mathbb{R}^{m\times n}$ com posto ${} r>1 {}$ e $k=1,\dots,r-1$, então $A_{k}$ é a matriz que melhor aproxima $A$ segundo a norma 2. Isto é, para toda matriz $B\in \mathbb{R}^{m\times n}$ com posto $k$, tem-se

$$
\lVert A-A_{k} \rVert_{2} \leq \lVert A-B \rVert _{2} 
$$

Equivalentemente, 

$$
\lVert A-A_{k} \rVert_{2}=\min \{ \lVert A-B \rVert _{2}:B\in \mathbb{R}^{m\times n}\text{ e }\text{posto}(B)=k \} 
$$

Além disso, $\lVert A-A_{k} \rVert=\sigma_{k+1}$.

:::

:::{prf:proof}

Começamos pela igualdade $\lVert A-A_{k} \rVert_{2}=\sigma_{k+1}$. Devemos mostrar que $\sigma_{k+1}$ é o maior valor singular de $A-A_{k}$. Mas observe que 

$$
A-A_{k}=U\Sigma V^{T}-U\Sigma_{k}V^{T}= U(\Sigma-\Sigma_{k})V^{T}
$$

e pela definição de $\Sigma_{k}$ concluímos que $\sigma_{k+1}$ é de fato o maior valor singular.

Agora, para $B\in \mathbb{R}^{m\times n}$ com posto $k$, mostremos que $\sigma_{k+1}\leq \lVert A-B \rVert_{2}$.

Sejam $v_{1},\dots v_{n}$ os vetores que compõem as colunas de $V$, defina $W:=[v_{1},\dots,v_{k+1}]$. Temos então $(W+N(B))\subseteq \mathbb{R}^{n}$, pois $W,N(B)\subseteq \mathbb{R}^{n}$. Logo,

$$
\dim (W+N(B))=\dim W+\dim N(B)-\dim(W \cap N(B))\leq n
$$

Por outro lado, observe que $\dim W=k+1$ (pela definição de $W$) e $\dim N(B)=n-k$ (pois $B$ tem posto $k$). Portanto,

$$
k+1+n-k-\dim(W\cap N(B))\leq n
$$

$$
\implies \dim(W\cap N(B))\geq 1
$$

indicando que $(W\cap N(B)) \neq \emptyset$. 

Sendo assim, consideremos $v\in (W\cap N(B))$ tal que $\lVert v \rVert_{2}=1$. Pela definição de $W$ (dado que $v_{1},\dots,v_{k+1}$ são ortonormais) e como, em particular, $v\in W$, temos 

$$
v=\alpha_{1}v_{1}+\dots+\alpha_{k+1}v_{k+1}, \quad \text{com }\alpha_{1},\dots,\alpha_{k+1}\in \mathbb{R}
$$

Como $\lVert v \rVert_{2}=1$, temos $\langle v , v \rangle=\lVert v \rVert_{2}^{2}=1^{2}=1$. Mas, pela ortonormalidade de $v_{1},\dots,v_{k+1}$:

$$
\begin{align}
\langle v , v \rangle=\langle \alpha v_{1}+\dots \alpha_{k+1}v_{k+1} , \alpha v_{1}+\dots \alpha_{k+1}v_{k+1} \rangle=\alpha_{1}^{2}+\dots+\alpha_{k+1}^{2}
\end{align}
$$

Logo,

$$
\alpha_{1}^{2}+\dots+\alpha_{k+1}^{2}=1
\label{eq:igualdade-eckart}
$$

Além disso, $v\in N(B)$, então:

$$
(A-B)v=Av-0=A(\alpha_{1}v_{1}+\dots+\alpha_{k+1}v_{k+1})=\alpha_{1}Av_{1}+\dots+\alpha_{k+1}Av_{k+1}
$$

e temos que $Av_{i}=\sigma_{i}u_{i}$, para $i=1,\dots,k+1$. Em particular, $u_{1},\dots,u_{k+1}$ são ortonormais, utilizando esses fatos temos

$$
\lVert (A-B)v \rVert _{2}^{2}=\langle (A-B)v , (A-B)v \rangle=\left\langle  \sum_{i=1}^{k+1} \alpha_{i}\sigma_{i}v_{i} , \sum_{i=1}^{k+1} \alpha_{i}\sigma_{i}v_{i}  \right\rangle= \sum_{i=1}^{k+1}(\alpha_{i}\sigma_{i})^{2}
$$

Mas, $\sum_{i=1}^{k+1}(\alpha_{i}\sigma_{i})^{2}\geq \sigma_{k+1}^{2}\sum_{i=1}^{k+1}a_{i}^{2}=\sigma_{k+1}^{2}$ (utilizando {eq}`eq:igualdade-eckart`). Portanto, considerando que $\lVert A-B \rVert_{2}$ é equivalente ao máximo de ${} \lVert (A-B)x \rVert$ para todo ${} x\in \mathbb{R}^{n}$ tal que $\lVert x \rVert_{2}=1$ (pela primeira definição da norma 2 matricial), concluímos:

$$
\sigma_{k+1}\leq \lVert (A-B)v \rVert_{2}\leq \lVert A-B \rVert_{2}   
$$


:::

O tópico [](../aplicacoes/svd.md) mostra como essa ideia de aproximação de matrizes pode ser aplicada.

### Pseudoinversa

A decomposição SVD também nos permite construir uma generalização da ideia de inversa para uma matriz qualquer, que não precisa nem mesmo ser quadrada.

:::{prf:definition} Pseudoinversa de Moore-Penrose
:label: def-pseudoinversa

Seja $A=U\Sigma V^{T}$. A ***pseudoinversa*** de $A$ é a matriz:

$$
A^{+}=V\Sigma^{+}U^{T}
$$

Onde $\Sigma^{+}$ é obtida invertendo os valores singulares não nulos de $\Sigma$ (isto é, se $\sigma_{i}\neq 0$ faz-se $\frac{1}{\sigma_{i}}$) e tomando a transposta. 

:::

Para ilustrar melhor como obter ${} \Sigma^{+} {}$, se posto de $A$ é igual a $r$ e seja: 

$$
\Sigma =
\begin{bmatrix}
\sigma_1 &        &        &        & \cdots &        & 0 \\
         & \sigma_2 &      &        & \cdots &        & 0 \\
         &        & \ddots &        &        &        & \vdots \\
         &        &        & \sigma_r &       &        & 0 \\
         &        &        &        & 0      &        & 0 \\
\vdots   & \vdots &        &        & \vdots & \ddots & \vdots \\
0        & 0      & \cdots &        & 0      & \cdots & 0
\end{bmatrix}
$$

A matriz resultante da inversão dos $\sigma_{i}$ ($i=1,\dots,r$) é:

$$
\Sigma' =
\begin{bmatrix}
\frac{1}{\sigma_{1}} &        &        &        & \cdots &        & 0 \\
         & \frac{1}{\sigma_{2}} &      &        & \cdots &        & 0 \\
         &        & \ddots &        &        &        & \vdots \\
         &        &        & \frac{1}{\sigma_{r}} &       &        & 0 \\
         &        &        &        & 0      &        & 0 \\
\vdots   & \vdots &        &        & \vdots & \ddots & \vdots \\
0        & 0      & \cdots &        & 0      & \cdots & 0
\end{bmatrix}
$$

E então, $\Sigma^{+}=(\Sigma')^{T}$.

O caráter de "inversa" da matriz $A^{+}$ se dá pelas seguintes propriedades que ela satisfaz:

1. $AA^{+}A=A$
2. $A^{+}AA^{+}=A^{+}$
3. $(AA^{+})^{T}=AA^{+}$
4. $(A^{+}A)^{T}=A^{+}A$

Tais propriedades são verificadas sem muita dificuldade considerando-se a decomposição SVD de $A$ e as propriedades das matrizes $U$, $V$, $\Sigma $ e $\Sigma^{+}$. Note que valem as igualdades mesmo sem a garantia de que $AA^{+}$ e $A^{+}A$ são iguais as identidades nos espaços correspondentes (em particular, isso valerá quando $A$ é quadrada e invertível, tendo-se $A^{+}=A^{-1}$). Por isso, ${} A^{+} {}$ é uma generalização da inversa.

Essas quatro propriedades são chamadas de **condições de Penrose** e definem, na verdade, um tipo específico de pseudoinversa (daí o nome "pseudoinversa de Moore-Penrose"). Em geral, essa é a pseudoinversa mais conhecida e utilizada, mas existem outros tipos (normalmente definidas para atender condições computacionais específicas).

Uma das principais aplicações da pseudoinversa se dá na obtenção de soluções para o problema de quadrados mínimos, abordado no tópico [](../aplicacoes/quadradosminimos.md).
