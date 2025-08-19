---
title: Compressão de imagens utilizando Decomposição em Valores Singulares
subject: Aplicações
---

Um dos principais exemplos de como matrizes podem ser aplicadas no meio computacional é o processamento de imagens. Em geral, a maioria dos softwares lidam com imagens tratando-as como uma matriz de *pixels* (à nível de manipulação e processamento, já o armazenamento em disco é feito utilizando outros formatos mais eficientes, como os conhecidos formatos *.JPG*, *.PNG*, entre outros), com dimensões correspondentes as da resolução da imagem. 

Um *pixel* é a unidade fundamental que compõe uma imagem, ele é basicamente uma cor sólida. A composição de milhares de pixels (por exemplo, uma imagem de resolução 800 x 600 contém $800\cdot 600=480000$ pixels) resulta na imagem como a enxergamos. A cor de um pixel é armazenada como um conjunto de números, que representam as escalas de cada espectro principal de cor e luz, que unidos formam a cor desejada - logo, na verdade uma imagem é uma matriz tridimensional, pois cada pixel que a compõe armazena mais de um valor. 

O *RGB* é um dos sistemas de cores mais conhecidos e utilizados, cuja sigla vem do inglês *Red* (Vermelho), *Green* (Verde) e *Blue* (Azul), uma vez que todas as outras cores (ou pelo menos a maioria) podem ser obtidas através da adição dessas três. Se pensarmos na representação matricial de uma imagem de resolução $m\times n$ no formato RGB, o que teremos serão 3 matrizes de dimensão $m\times n$, uma para cada uma das cores base.

Como vimos no [Teorema de Eckart-Young](#teo-eckart-young), é possível aproximar uma matriz por outra de mesma dimensão e posto menor, descartando (anulando) os valores singulares de índice maior ao do posto escolhido, na sua decomposição SVD. Então, quais seriam os efeitos de aplicar essa técnica às matrizes RGB de uma imagem? Acontece que, na verdade, esse é um método de *compressão de imagens* válido, que é aplicado em algumas situações no meio digital.

O conceito de *comprimir* uma imagem consiste em reduzir o seu tamanho (a quantidade de informações que ela armazena, o que é refletido no espaço que ela ocupa em disco), de maneira que não haja uma perda significativa na sua qualidade. Existem diversos métodos de compressão de imagens, cada um com propósitos diferentes, e a **compressão via SVD truncada** é um deles. Em geral, é mais utilizado quando lida-se com imagens de complexidade menor, onde a estrutura global é mais importante (muito comum no contexto de *Visão Computacional*), tendo como vantagem um controle maior do nível de compressão, definido diretamente pelo posto $k$ para o qual serão aproximadas as matrizes originais.

Nesse tópico, mostraremos uma implementação (relativamente simples) desse método de compressão na linguagem *Python*, fazendo uso dos conceitos vistos no tópico de [Valores Singulares](../topicos/valores-singulares.md) e recursos oferecidos por *bibliotecas* da linguagem Python. Analisaremos os efeitos da compressão em uma imagem de teste, considerando valores diferentes para o posto $k$ de aproximação.

A ideia geral para o algoritmo provém do que discutimos até agora:

1. Receber uma imagem e "quebrá-la" nas 3 matrizes RGB correspondentes;
2. Decompor em valores singulares cada uma das 3 matrizes;
3. Fazer a redução do posto para cada uma delas;
4. Reconstruir a imagem a partir das novas matrizes aproximadas.

Felizmente, as bibliotecas *Numpy* e *PIL* do Python fornecem implementações dos principais recursos que precisaremos. Aqui está a implementação do algoritmo: 

```{code-block} python
:caption: Algoritmo de compressão de imagem via SVD truncada
:linenos:

from PIL import Image
import numpy as np

# Abre uma imagem e extrai as matrizes R, G, B
imagem_original = Image.open("original.jpg")
matriz_original = np.array(imagem_original)
matriz_r = matriz_original[:, :, 0]
matriz_g = matriz_original[:, :, 1]
matriz_b = matriz_original[:, :, 2]

# Decompõe as matrizes RGB em valores singulares
Ur, Sr, Vrt = np.linalg.svd(matriz_r)
Ug, Sg, Vgt = np.linalg.svd(matriz_g)
Ub, Sb, Vbt = np.linalg.svd(matriz_b)

k = 100 #posto escolhido

# Trunca as matrizes SVD do RGB para o posto k
Ukr = Ur[:, :k]
Skr = Sr[:k]
Vtkr = Vrt[:k, :]

Ukg = Ug[:, :k]
Skg = Sg[:k]
Vtkg = Vgt[:k, :]

Ukb = Ub[:, :k]
Skb = Sb[:k]
Vtkb = Vbt[:k, :]

# Reconstrói as matrizes RGB a partir da forma SVD truncada
R_approx = Ukr @ np.diag(Skr) @ Vtkr
G_approx = Ukg @ np.diag(Skg) @ Vtkg
B_approx = Ukb @ np.diag(Skb) @ Vtkb

# 3. Reconstrói a imagem a partir das novas matrizes RGB 
imagem_reconstruida = np.stack((R_approx, G_approx, B_approx), axis=-1).astype(np.uint8)
Image.fromarray(imagem_reconstruida).save("reconstruida.jpg")

```

Observe que ...
