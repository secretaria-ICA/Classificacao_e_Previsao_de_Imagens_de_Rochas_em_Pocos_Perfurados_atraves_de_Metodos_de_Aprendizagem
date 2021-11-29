<!-- antes de enviar a versão final, solicitamos que todos os comentários, colocados para orientação ao aluno, sejam removidos do arquivo -->
# Classificação e previsão de imagens de rochas em poços perfurados por meio de métodos de aprendizagem supervisionados por aprendizagem profunda e modelos pré-treinados

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

Este trabalho se propõe a classificar as rochas através de suas imagens adquiridas durante as atividades geológicas (perfuração), utilizando uma técnica de Deep Learning e modelos pré treinados. 

Utilizamos uma base do Kaggle (https://www.kaggle.com/tanyadayanand/geological-image-similarity/metadata) de setembro de 2020 para iniciarmos esse estudo, embora os dados estejam em inglês, os conceitos básicos são os mesmos. O trabalho envolveu a análise de XXX modelos diferentes, em todos eles foram considerados as etapas: análise exploratória de dados, missing values e reavaliação dos atributos pelo peso.

### 2. Modelagem

Primeiramente foi feita a análise dos dados para entender quais atributos manter no modelo, em seguida foi criado um dataframe (data_df) com a divisão entre as imagens (path) e as identificações das rochas (labels).
    
Após isso, as imagens foram convertidas de 28 por 28 para 32 por 32 para que possam abranger só modelos utilizados. O rótulo foi associado a uma rocha. Houve a conversão dos dados de imagens e rótulos em matrizes numpy, enquanto dimensiona os pixels. Os atributos dos rótulos foram codificados em tags (binarias) e, além disso foi verificado quais atributos apresentaram missing values.

O balanceamento dos dados e processos para gerar as duas bases tratadas, nesse momento foi inserida a funcionalidade de Split Data para gerar as duas bases, a de treino (0.8 de partição) e a de teste (0.2 de partição). A seguir, foi novamente realizado esse processo para gerar a base de validação.
    
Realizei a criação do Data Augumentation com a finalidade da criação de mais dados aleatórios de acordo com a necessidade futura de testes em outros modelos.

Diferentes modelos foram testados usando os seguintes algoritmos de classificação: Deep Learning, VGG16, Inception V3 e Neural Net.

Foram testados dois modelos de Machine Learning para classificação supervisionada (Deep Learning, pre treinado VGG16, Inception V3) sendo adotado o modelo XXXX por apresentar as melhores métricas de avaliação.

2.1. Parâmetros do modelo

Os melhores parâmetros encontrados para o modelo são:

•	INIT_LR = 1e-3
•	EPOCHS = 200
•	BS=24

2.2. Modelos treinados

Foram treinados dois modelos distintos, sendo eles:

•	Modelo Conv2D 

![image](https://user-images.githubusercontent.com/58257963/137184214-503ab3de-3788-46c7-aa2b-cd16df302fc0.png)

•	Modelo VGG16

![image](https://user-images.githubusercontent.com/58257963/138980731-df213d27-2a5a-48f6-898c-d74d21555272.png)

•	Inception V3


Foram gerados três modelos distintos, pois xxxxxx. Por isso a idéia é que o usuário possa escolher o classificador que melhor se adeque aos dados do usuário.

2.3. Métricas principais de avaliação dos modelos

![image](https://user-images.githubusercontent.com/58257963/143921190-eb309c34-d8fc-4a3c-8450-a96ba1faa952.png)

•	Conv2D (a) (26/11/2021) – 

![image](https://user-images.githubusercontent.com/58257963/143920858-0f6f8803-eaee-47c7-8903-b32baf7b104e.png)

•	Conv2D (b) (19/10/2021) – 

![image](https://user-images.githubusercontent.com/58257963/138979855-fd9418f2-64d3-4d37-9dcd-1cb775585060.png)

•	Conv2D (c) (26/10/2021) – 

- Precisão de treinamento e validação, bem como a perda -

![image](https://user-images.githubusercontent.com/58257963/138979611-bbebfb9c-0010-4dae-a21b-8304016f4442.png)

![image](https://user-images.githubusercontent.com/58257963/138325256-02079288-32ab-4947-a128-5945f7f0183d.png)

•	VGG16 (a)

- Precisão de treinamento e validação, bem como a perda - 

- Matrix de Confusão:
 
- Calculate the confusion matrix and use it to derive the precision, sensitivity and specificitye --- > acc: 

- Matrix de Confusão com mapa de calor (Usando Data augumentation):

### 3. Resultados

- Conv2D (a) – 

- Relatório de classificação:

Podemos resumir o desempenho do nosso classificador da seguinte forma: 
- Precision: que é a capacidade de encontrar somente as amostras relevantes. A maioria das amostras estão com o percentual perto de 1.00. Somente a classe andesite apresentou uma leve variação, respectivamente, de 0.04%.
- Recall: que é a capacidade de encontrar todas as amostras positivas. Somente as classes andesite e quartzite apresentaram, respectivamente, uma variação de 0.04% e 0.03%.
-f1-Score: média harmônica de precisão e recall.

![image](https://user-images.githubusercontent.com/58257963/143924268-8db1bf90-3c2d-4045-92bf-6c1e1c87ff2a.png)

- Matrix de Confusão:

![image](https://user-images.githubusercontent.com/58257963/143924317-d1b558bc-45b7-45d0-b320-6a60125675b8.png)

- Calculate the confusion matrix and use it to derive the precision, sensitivity and specificitye --- 

    Accuracy_score: 0.9833

    Precision:

        [0.95881226 0.97810945 1.         0.98842105 0.98192771 0.99408284]

    Recall or Sensitivity:

        [0.97468354 0.99493927 1.         0.97104447 0.98291457 0.97674419]


- Matrix de Confusão com mapa de calor (Usando Data augumentation):
- 
![image](https://user-images.githubusercontent.com/58257963/143924716-194c050e-18e2-4f6c-8d60-f02cf5507699.png)

Com a técnica de data augumentation, ou seja, aumento dos dados de teste para realização das predições, houve piora na classe schist, em relação aos - Conv2D (b) e (c), ambos abaixo, que já apresentavam na Matriz de confusão (pura) um “erro” com relação a classificação das imagens das respectivas rochas. 

- Conv2D (b) – 

- Relatório de classificação:

Podemos resumir o desempenho do nosso classificador da seguinte forma: 
- Precision: que é a capacidade de encontrar somente as amostras relevantes. A maioria das amostras estão com o percentual perto de 1.00. Somente a classe andesite apresentou uma leve variação, respectivamente, de 0.03%.
- Recall: que é a capacidade de encontrar todas as amostras positivas. Somente as classes andesite e quartzite apresentaram, respectivamente, uma variação de 0.04% e 0.03%.

![image](https://user-images.githubusercontent.com/58257963/138981188-92f68aca-5bd1-4903-a67b-92b1e8be8e0c.png)


- Matrix de Confusão:

![image](https://user-images.githubusercontent.com/58257963/138981288-2bebd90a-9314-4ece-9790-df753f4ff806.png)

- Calculate the confusion matrix and use it to derive the precision, sensitivity and specificitye --- > acc: 0.3308

- Matrix de Confusão com mapa de calor (Usando Data augumentation):

![image](https://user-images.githubusercontent.com/58257963/138981388-a39e832b-e3db-4475-bbd3-f1d35cb43648.png)

- Conv2D (c) – 

- Relatório de classificação:

![image](https://user-images.githubusercontent.com/58257963/138979188-ddf453d3-5808-42c7-b89f-4910fc3397ed.png)

 Podemos resumir o desempenho do nosso classificador da seguinte forma: 
- Precision: que é a capacidade de encontrar somente as amostras relevantes. A maioria das amostras estão com o percentual perto de 1.00. Somente as classes andesite e gneiss apresentaram uma leve variação, respectivamente, de 0.03% e 0.03%.
- Recall: que é a capacidade de encontrar todas as amostras positivas. Somente as classes andesite, quartzite e schist apresentaram, respectivamente, uma variação de 0.03, 0.03 e 0.03%.
-f1-Score: média harmônica de precisão e recall.

- Matrix de Confusão:

![image](https://user-images.githubusercontent.com/58257963/138979372-5e93c7ad-cf6e-4c41-8406-9f0cdf08e371.png)
 
- Calculate the confusion matrix and use it to derive the precision, sensitivity and specificitye --- > acc: 0.3258

- Matrix de Confusão com mapa de calor (Usando Data augumentation):

![image](https://user-images.githubusercontent.com/58257963/138979415-97277119-4586-49f0-810b-e9d8d19c3677.png)



O modelo com a melhor acurácia foi o Deep Learning Modelo Conv2D (A) com 98.29% e o pior foi pre treinado VGG16 Model com 97.45%. Podemos destacar também que o modelo Deep Learning também é eficiente com aplicações tais como: reconhecimento de fala e imagem, processamento de linguagem natural, sistemas de recomendação, dentre outros. 

Particularmente nesse trabalho, existe a oportunidade de um direcionamento para xxxxxxxxxxxxxxxx.

### 4. Conclusões



---

Matrícula: 192.190.138

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
