---
title: Decomposição em Valores Singulares
subject: Tópicos Avançados
---

Vimos no [Teorema Espectral](teorema-espectral.md) que é possível decompor qualquer matriz simétrica como o produto entre 3 matrizes, sendo uma delas diagonal (contendo os autovalores) e as outras duas ortogonais (de transição entre a base canônica e a base ortonormal de autovetores). Esse tópico apresenta uma espécie de "generalização" do Teorema Espectral para uma matriz qualquer de dimensão $m \times n$.

A ideia geral é similar, queremos decompor uma matriz $A\in \mathcal{M}_{m\times n}(\mathbb{R})$ como o produto entre 3 matrizes:

$$
A=U\Sigma V^{T}
$$

Em particular, nos seria interessante que tais matrizes tenham propriedades similares ao caso do Teorema Espectral, com $U$ e $V^{T}$ ortogonais e $\Sigma$ diagonal. Mas note que se $A$ não é quadrada essa configuração não é possível, já que para tal deveríamos ter 3 matrizes quadradas, cujo produto não resultaria em uma matriz não quadrada. Como veremos, o que obteremos será o seguinte:

- $U$ é uma matriz ortogonal $m\times m$;
- $\Sigma$ é uma matriz "diagonal" $m\times n$ (diagonal no sentido de ter valores não nulos somente nas entradas de linha e coluna com mesmo índice);
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

Seja $A\in \mathcal{M}_{m\times n}(\mathbb{R})$, com posto igual a $r$. Existem números reais $\sigma_{1}\geq \dots\geq \sigma_{r}>0$, chamados de *valores singulares* de $A$, e bases ortonormais $\{ v_{1},\dots,v_{n} \}$ de $\mathbb{R}^{n}$ e $\{ u_{1},\dots,u_{m} \}$ de $\mathbb{R}^{m}$, tais que:

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

Dessa forma, $v_{1},\dots,v_{n}$ constituirão as colunas da matriz $V$ e são chamados de *vetores singulares à direita*, enquanto $u_{1},\dots,u_{m}$ constituirão as colunas de $U$ e são chamados de *vetores singulares à esquerda*.
