---
title: Operadores Auto-Adjuntos
subject: Tópicos Avançados
---

:::{prf:definition}
:label: autoadjunto

Um operador $T$ é dito autoadjunto se $\langle Tx, y \rangle = \langle x, Ty \rangle$.
:::

:::{prf:proposition}
Seja $T$ um operador linear auto-adjunto sobre um espaço vetorial $V$ munido de produto interno. Então, autovetores associados a autovalores distintos são ortogonais.
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
