---
title: Valores Singulares
subject: Tópicos Avançados
---

Vimos no [Teorema Espectral](teorema-espectral.md) que é possível decompor qualquer matriz simétrica como o produto entre 3 matrizes, sendo uma delas diagonal (contendo os autovalores) e as outras duas ortogonais (de transição entre a base canônica e a base ortonormal de autovetores). Esse tópico apresenta uma espécie de "generalização" do Teorema Espectral para uma matriz qualquer de dimensão $m \times n$.

A ideia geral é similar, queremos decompor uma matriz $A\in \mathcal{M}_{m\times n}(\mathbb{R})$ como o produto entre 3 matrizes:

$$
A=U\Sigma V^{T}
$$

Em particular, nos seria interessante que tais matrizes tenham propriedades similares ao caso do Teorema Espectral, com $U$ e $V^{T}$ ortogonais e $\Sigma$ diagonal. Mas note que, se $A$ não é quadrada, essa configuração não é possível, já que para tal deveríamos ter 3 matrizes quadradas, cujo produto não resultaria em uma matriz não quadrada. Como veremos, o que obteremos será o seguinte:

- $U$ é uma matriz ortogonal $m\times m$;
- $\Sigma$ é uma matriz "diagonal" $m\times n$ (diagonal no sentido de ter valores não nulos somente nas entradas de linha e coluna com mesmo índice);
- $V^{T}$ é a transposta de uma matriz ortogonal $n\times n$.

O teorema seguinte, que leva o nome do tópico, é a base para essa ideia. Ele nos indica quais serão os valores da diagonal de $\Sigma$, chamados de *valores singulares*, e quais os vetores que irão compor as matrizes $U$ e $V^{T}$.

