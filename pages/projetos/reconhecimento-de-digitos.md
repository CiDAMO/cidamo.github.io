---
layout: projeto
title: "Reconhecimento de Dígitos"
description: >
   Desenvolvemos classificadores capazes de reconhecer
   dígitos escritos manualmente em imagens digitalizadas.
img: reconhecimento-de-digitos.png
permalink: "/projetos/reconhecimento-de-digitos/"
tags:
  - classificação-de-imagens
  - machine-learning
membros:
  - egmara
  - renandomingues
  - joaofassina

key: projeto
date: 2019-07-15
---

## Objetivo

O objetivo do projeto foi desenvolver classificadores capazes de reconhecer dígitos
escritos manualmente em imagens digitalizadas, usando banco de dados e tratamento
de imagem próprios com implementações em Python.

![]({{site.urlimg}}/{{page.permalink}}/objetivo.png)

## Banco de Dados

Nosso banco de dados foi construído solicitando o preenchimento de 15 folhas com
15 linhas cada, sendo que cada indivíduo preencheu uma folha.

![]({{site.urlimg}}/{{page.permalink}}/bancodedados.png)

## Tratamento

O tratamento das imagens foi feito usando a biblioteca OpenCV. Primeiro
a imagem é convertida para escala de cinza, borrada e então binarizada. Em seguida
cada dígito é identificado por seus contornos, cortado, centralizado e
redimensionado para 28x28 pixels.

![]({{site.urlimg}}/{{page.permalink}}/tratamento.png)

Depois disso a imagem é invertida, ou seja, o dígito é dado por pixels brancos (255)
com fundo preto (0). Antes de passar para o classificador ainda ocorre a
normalização, trocando os valores de 255 por 1, e a conversão de matriz
28x28 para vetor 784x1. Visualmente as imagens do banco de dados desenvolvido ficaram
parecidas com as do MNIST.

![]({{site.urlimg}}/{{page.permalink}}/compara.png)

## Classificadores

Com o tratamento das imagens o banco de dados resulta em uma matriz X de
dimensões 2250x784, sendo que cada uma das 2250 linhas representa um algarismo.
Como foi solicitado o preenchimento ordenado das folhas, sabemos que o vetor de
referência y repete a ordem [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10] e tem tamanho 2250x1.

A matrix X e o vetor y foram usados para treinar classificadores 
Floresta, Rede Neural e SVC da biblioteca scikit-learn e Rede Neural Convolucional
da biblioteca keras. Alguns dos parâmetros foram otimizados
usando k-fold cross validation. Mais detalhes sobre as implementações estão
disponíveis no
[repositório](https://github.com/Egmara/Machine-Learning-Projeto-UFPR-Reconhecimento-de-algarismos).

```
> floresta_clf = RandomForestClassifier(max_depth = 12, n_estimators = 75)
> redeneural_clf = MLPClassifier(hidden_layer_sizes=(75), alpha=1e-4, solver='lbfgs')
> svc_clf = SVC(kernel='rbf', gamma = 'auto', C = 4)
> clf_cnn = Sequential()
  clf_cnn.add(Conv2D(32, (3, 3), activation='relu', input_shape=(28,28,1)))
  clf_cnn.add(Conv2D(64, (3, 3), activation='relu'))
  clf_cnn.add(MaxPooling2D(pool_size=(2, 2)))
  clf_cnn.add(Dropout(0.25))
  clf_cnn.add(Flatten())
  clf_cnn.add(Dense(128, activation='relu'))
  clf_cnn.add(Dropout(0.5))
  clf_cnn.compile(optimizer='adam', loss='sparse_categorical_crossentropy', metrics=['accuracy'])
  clf_cnn.fit(X, y, epochs=18, batch_size = 200)
```

## Resultados

Como o objetivo era classificar algarismos em imagens diferentes do banco de dados,
os testes foram realizados com fotos contendo dígitos de tamanho e posição
arbitrários. Além disso, os testes foram escritos por pessoas que não contribuíram
com o banco de dados.

![]({{site.urlimg}}/{{page.permalink}}/teste.png)*Exemplo de tratamento de teste.*

Os classificadores treinados com o banco de dados desenvolvido foram testados
com 51 dígitos obtidos dessa forma. As acurácias desses modelos estão disponíveis na
Tabela 1.

| Classificador | Acertos       | Acurácia |
|:-------------:|:-------------:|:--------:|
| RandomForest  |    36/51      |   70.6%  |
|      MLP      |    42/51      |   82.4%  |
|      SVC      |    41/51      |   80.4%  |
|      CNN      |    49/51      |   96.1%  |

_Tabela 1: Acurácias dos classificadores nos testes._

## Conclusão

O banco de dados e tratamento de imagem desenvolvidos foram suficientes para gerar
classificadores relativamente confiáveis, em especial a rede neural convolucional
que apresentou acurácia de 96.1%. O destaque da CNN já era esperado, sendo esse
tipo de classificador o mais usado para classificação de imagens.

Apesar do treinamento com o banco de dados MNIST permitir acurácias
superiores a 99%, deve-se levar em conta que o banco de dados desenvolvido nesse
projeto tem somente 2250 amostras de 15 indivíduos, contra 70000 amostras do MNIST
de 7000 indivíduos. Com isso consideramos os resultados satisfatórios.

Mais detalhes sobre o projeto estão disponíveis no
[repositório](https://github.com/Egmara/Machine-Learning-Projeto-UFPR-Reconhecimento-de-algarismos),
no [notebook](https://github.com/Egmara/Machine-Learning-Projeto-UFPR-Reconhecimento-de-algarismos/blob/master/Apresentacao.ipynb)
e nos [slides](https://github.com/Egmara/Machine-Learning-Projeto-UFPR-Reconhecimento-de-algarismos/blob/master/SlidesApresentacao.pdf).
