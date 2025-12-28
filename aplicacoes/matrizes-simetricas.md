---
title: 12. Máximos e mínimos utilizando matrizes simétricas
subject: Aplicações
---

# Máximos e mínimos locais de funções de duas variáveis

A modelagem matemática de fenômenos físicos (em áreas como Mecânica Clássica, Termodinâmica, Óptica, etc.), de processos da Engenharia e Economia - entre outras atividades de grande relevância para o empreendimento humano - naturalmente recai sobre o estudo de funções de múltiplas variáveis, uma vez que estes lidam com intricados fatores que interagem entre si e dependem uns dos outros. Em particular, **funções de duas variáveis** aparecem com bastante frequência nos exemplos citados.

Considere, por exemplo, a modelagem do lucro de uma empresa dado em função do preço dos seus dois principais produtos, $L(p_{1},p_{2})$. Encontrar os valores de $p_{1}$ e $p_{2}$ que maximizariam o lucro é um problema clássico do *Cálculo Diferencial e Integral*, que envolve determinar os chamados **pontos de máximo e mínimo locais** da função $L(p_{1},p_{2})$. 

Munidos das ferramentas do Cálculo, as propriedades de [matrizes simétricas e operadores auto-adjuntos](../topicos/operadores-auto-adjuntos.md) nos permitem uma análise do problema sob a ótica da Álgebra Linear, o que por muitas vezes oferece uma solução mais prática.

A ideia central é analisarmos as propriedades da ***matriz Hessiana***, uma das principais ferramentas do Cálculo Vetorial, que é constituída das derivadas parciais de segunda ordem da função, que naturalmente nos fornecem informações sobre os pontos de máximo e mínimo, chamados **pontos críticos**.

:::{note} Definição 12.1 Matriz Hessiana

Dada uma função $f(x,y)$, sua ***matriz Hessiana*** é dada por

$$
H(x,y)=\begin{bmatrix}
\frac{\partial^{2}f}{\partial x^{2}}(x,y) & \frac{\partial^{2}f}{\partial y\partial x}(x,y) \\
\frac{\partial^{2}f}{\partial x\partial y}(x,y)  & \frac{\partial^{2}f}{\partial y^{2}}(x,y)
\end{bmatrix}
$$

:::

Para o caso em que as derivadas de segunda ordem são contínuas, tem-se que $\frac{\partial^{2}f}{\partial x\partial y}=\frac{\partial^{2}f}{\partial y\partial x}$. Logo, **a matriz Hessiana é simétrica** e sabemos, por [](#lema2), que possuirá autovalores reais. Em suma, isto nos permite classificar os pontos críticos com base nos seus autovalores.

Similarmente à estratégia usual do Cálculo, inicialmente devemos encontrar pontos que são candidatos a **máximos, mínimos ou pontos de sela**. Tais pontos satisfazem o seguinte sistema:

$$
\nabla f(x,y)=0 \implies \begin{cases}
f_{x}(x,y)=0 \\
f_{y}(x,y)=0
\end{cases}
\label{eq:sistema}
$$

onde $\nabla f(x,y)$ é o ***gradiente*** de $f$, outro elemento protagonista do Cálculo Vetorial, que basicamente consiste do vetor cujas coordenadas são as derivadas de $f$ em cada variável respectiva.

A partir daí, calculamos a matriz Hessiana para os pontos encontrados e encontramos seus autovalores. A natureza do ponto crítico é então determinada pelos sinais dos seus autovalores, $\lambda_{1}$ e $\lambda_{2}$:

- **Mínimo local**: $\lambda_{1}>0$ e $\lambda_{2}>0$ (a Hessiana é **definida positiva**);
- **Máximo local**: $\lambda_{1}<0$ e $\lambda_{2}<0$ (a Hessiana é **definida negativa**);
- **Ponto de sela**: $\lambda_{1}\cdot \lambda_{2}<0$ (a Hessiana é **indefinida**);

Para o caso em que algum autovalor for zero, **o teste é inconclusivo**. É necessária análise de derivadas de ordem superior.

Assim, a forma diagonal da matriz Hessiana nos revela a curvatura da função nas direções dos autovetores. Por exemplo, se $\lambda_{1}>0$ e $\lambda_{2}>0$ a função tem concavidade para cima em todas as direções.

Tomemos um exemplo prático: Considere $f(x,y)=x^{2}+2y^{2}$. Utilizando {eq}`eq:sistema` encontramos o ponto crítico $(0,0)$, cuja Hessiana é dada por $H(0,0)=\begin{bmatrix}2 & 0\\ 0 & 4\end{bmatrix}$, já diagonal. Encontramos que seus autovalores são $\lambda_{1}=2>0$ e $\lambda_{2}=4>0$, resultando na conclusão que $(0,0)$ é um mínimo local.

```{figure} graph.png
:width: 300px
:align: center
:name: fig-3d-plot

Gráfico 3D da função $f(x,y)=x^{2}+2y^{2}$
```

Trazendo para um cenário análogo ao exemplo da função de lucro discutida no início, se tal $f$ corresponde a um custo dependente dos parâmetros $(x,y)$, sabemos que tomando-os $(0,0)$ **estaríamos minimizando o custo**.

