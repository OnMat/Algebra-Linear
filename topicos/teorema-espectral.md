---
title: Teorema Espectral
subject: Tópicos Avançados
---

O *Teorema Espectral* é um importante resultado na Álgebra Linear, diz respeito à existência de uma base ortonormal formada por autovetores de um operador auto-adjunto para o espaço vetorial o qual ele atua. Dividiremos-o em dois casos que, na prática, são correspondentes: Operadores auto-adjuntos e matrizes simétricas. Naturalmente, o segundo caso é um corolário do primeiro.

### Teorema Espectral (Operadores auto-adjuntos)

:::{prf:theorem} Teorema Espectral para operadores auto-adjuntos
:label: teorema-espectral
Para todo operador auto-adjunto $A:V\to V$, num espaço vetorial de dimensão finita munido de produto interno, existe uma base ortonormal $\{ u_{1},\dots,u_{n} \}\subset V$ formada por **autovetores** de $A$.
:::

A demonstração requer alguns resultados prévios.

:::{prf:lemma}
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$ munido de produto interno. Então autovetores associados a autovalores distintos são ortogonais.
:::

```{admonition} Demonstração
:class: dropdown
Sejam $v,w\in V$ autovetores associados a autovalores distintos $\lambda$ e $\mu$, respectivamente. Ou seja, $Tv=\lambda v$ e $Tw=\mu w$. Dado que $T$ é auto-adjunto, temos que $$
\langle Tv , w \rangle=\langle v , Tw \rangle.
$$
Logo, 
\begin{align}
\langle \lambda v ,  w \rangle &= \langle v , \mu w \rangle \\
\lambda \langle v , w \rangle &= \mu \langle v , w \rangle \\
(\lambda-\mu)\langle v , w \rangle &= 0
\end{align}

Como $\lambda \neq \mu$, então necessariamente $\langle v , w \rangle= 0$. Ou seja, $v$ e $w$ são ortogonais.
```
