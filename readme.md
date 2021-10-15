<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Classificação e Predição de imagens de rochas em poços perfurados via métodos de Aprendizado Supervisionado por classificação geologica das imagens

#### Aluno: [Fabio Basson](https://github.com/fabiobasson/Bi-Master/blob/mai)
#### Orientador: [Felipe Borges](https://github.com/FelipeBorgesC) e [Manoela Kohler](https://github.com/link_do_github).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

<!-- para os links a seguir, caso os arquivos estejam no mesmo repositório que este README, não há necessidade de incluir o link completo: basta incluir o nome do arquivo, com extensão, que o GitHub completa o link corretamente -->
- [Link para o código](https://github.com/fabiobasson/Bi-Master). <!-- caso não aplicável, remover esta linha -->

- [Link para a monografia](https://link_da_monografia.com). <!-- caso não aplicável, remover esta linha -->

---

### Resumo

<!-- trocar o texto abaixo pelo resumo do trabalho, em português -->

Uma empresa de pesquisa geológica deseja criar uma ferramenta para identificar e classificar os dados de suas imagens. Esta ferramenta possuirá uma capacidade de pesquisa em que um analista fornece uma imagem de interesse e é apresentada a outras imagens com carater de classificatório das mesmas.
A tarefa é criar o componente de deeep learning para este aplicativo de identificação e classificação de imagem. O modelo deve retornar a classificação ea predição das imagens com base nas imagens de entrada.


### Abstract <!-- Opcional! Caso não aplicável, remover esta seção -->

<!-- trocar o texto abaixo pelo resumo do trabalho, em inglês -->

A geological survey company wants to create a tool to identify and classify their image data. This tool will have a search capability in which an analyst provides an image of interest and is presented to other images as a classifier.
The task is to create the deep learning component for this image identification and classification application. The model should return the classification and prediction of the images based on the input images.


### 1. Introdução

Esta monografia visa apresentar a aplicação de métodos de aprendizado supervisionado à predição de imagens de rochas em poços de perfuração e representa um novo estudo a ser desenvolvido por equipe técnica da Petrobras. 

O uso de deep learning para o processo de orçamentação apresenta uma série de vantagens, entre elas, a redução de HH envolvido, melhoria no grau de assertividade, celeridade na resposta e possibilidade de testar diferentes cenários de projeto em menor tempo. 

Este trabalho se propõe a classificar as rochas através de suas imagens adquiridas durante as atividades geológicas (perfuração), utilizando uma técnica de Deep Learning. 

Utilizamos uma base do Kaggle (https://www.kaggle.com/tanyadayanand/geological-image-similarity/metadata) de setembro de 2020 para iniciarmos esse estudo, embora os dados estejam em inglês, os conceitos básicos são os mesmos. O trabalho envolveu a análise de XXX modelos diferentes, em todos eles foram considerados as etapas: análise exploratória de dados, missing values e reavaliação dos atributos pelo peso.

### 2. Modelagem

Primeiramente foi feita a análise dos dados para entender quais atributos manter no modelo, em seguida foi criado um dataframe (data_df) com a divisão entre as imagens (path) e as identificações das rochas (labels).
    
Após isso, as imagens foram convertidas de 28 por 28 para 32 por 32 para que possam abranger só modelos utilizados. O rótulo foi associado a uma rocha. Houve a conversão dos dados de imagens e rótulos em matrizes numpy, enquanto dimensiona os pixels. Os atributos dos rótulos foram codificados em tags (binarias) e, além disso foi verificado quais atributos apresentaram missing values.

O balanceamento dos dados e processos para gerar as duas bases tratadas, nesse momento foi inserida a funcionalidade de Split Data para gerar as duas bases, a de treino (0.8 de partição) e a de teste (0.2 de partição). A seguir, foi novamente realizado esse processo para gerar a base de validação.
    
Realizei a criação do Data Augumentation com a finalidade da criação de mais dados aleatórios de acordo com a necessidade futura de testes em outros modelos.

Diferentes modelos foram testados usando os seguintes algoritmos de classificação: Decision Tree, Deep Learning, VGG16, KNN, Naive Bayes, SVM, Random Forest, Random Tree e Neural Net.

Foram testados dois modelos de Machine Learning para classificação supervisionada (Deep Learning e pre treinado VGG16) sendo adotado o modelo XXXX por apresentar as melhores métricas de avaliação.

2.1. Parâmetros do modelo

Os melhores parâmetros encontrados para o modelo são:

•	INIT_LR = 1e-3
•	EPOCHS = 200
•	BS=24

2.2. Modelos treinados

Foram treinados dois modelos distintos, sendo eles:

•	Modelo A 

![image](https://user-images.githubusercontent.com/58257963/137184214-503ab3de-3788-46c7-aa2b-cd16df302fc0.png)

•	Modelo B

![image](https://user-images.githubusercontent.com/58257963/137194205-9f4f1b72-6c8d-4b06-86eb-86881ba54e22.png)

Foram gerados dois modelos distintos, pois xxxxxx. Por isso a idéia é que o usuário possa escolher o classificador que melhor se adeque aos dados do usuário.

2.3. Métricas principais de avaliação dos modelos

![image](https://user-images.githubusercontent.com/58257963/137534387-6386534d-0bf4-4e51-8595-fa603e9eb976.png)

•	Acurácia da classificação: 0,9307
•	Erro da classificação: 0,0693
•	Precisão: 0,9057
•	Recall: 0,9600


### 3. Resultados

O modelo com a melhor acurácia foi o Deep Learning Modelo Conv2D (A) com 98.29% e o pior foi pre treinado VGG16 Model com 97.45%. Podemos destacar também que o modelo Deep Learning também é eficiente com aplicações tais como: reconhecimento de fala e imagem, processamento de linguagem natural, sistemas de recomendação, dentre outros. Particularmente nesse trabalho, existe a oportunidade de um direcionamento para xxxxxxxxxxxxxxxx.

### 4. Conclusões



---

Matrícula: 192.190.138

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
