---
title: Espaços Vetoriais
subject: Fundamentos
---

O conceito de **Espaço Vetorial** é a base onde se constrói a Álgebra Linear. Começamos com sua definição.

:::{prf:definition} Espaço Vetorial

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

...

:::
