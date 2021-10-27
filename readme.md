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


•	Inception V3


Foram gerados três modelos distintos, pois xxxxxx. Por isso a idéia é que o usuário possa escolher o classificador que melhor se adeque aos dados do usuário.

2.3. Métricas principais de avaliação dos modelos

![image](https://user-images.githubusercontent.com/58257963/138978346-54b32979-5864-46fe-b74c-4b24c7bf9605.png)

•	Conv2D (g)

- Precisão de treinamento e validação, bem como a perda - 

![image](https://user-images.githubusercontent.com/58257963/138978530-954499b9-849a-4540-8788-02213bf97e45.png)


No gráfico acima training e validation acurracy, verifica-se que a acurácia de treinamento sobe nas primeiras 15 épocas, e se estabiliza na vigésima (20ª) época, com a acurácia de treinamento de 0.9786 na execução final do modelo na época 64.

Já a acurária de validação tem um comportamento variável até a vigésima (20ª) época, e se estabiliza após a mesma, com a acurácia de validação de 0.9786 na execução final do modelo na época 64.

Uma observação, vista no gráfico é um pico nas épocas 29-30, conforme abaixo, aonde o “val_acurracy” cai de 0.9738 para 0.9145

Epoch 29/200
749/749 [==============================] - 6s 8ms/step - loss: 0.0969 - accuracy: 0.9660 - val_loss: 0.0759 - val_accuracy: 0.9738

Epoch 30/200
749/749 [==============================] - 7s 9ms/step - loss: 0.0979 - accuracy: 0.9661 - val_loss: 0.2468 - val_accuracy: 0.9145

![image](https://user-images.githubusercontent.com/58257963/138325169-978231af-bd88-4d5a-b9bd-52c69b8816a4.png)

No gráfico acima, training e validation loss, verifica-se que o loss treinamento desce bruscamente nas primeiras 25 épocas, vindo a se estabilizar entre a 30-35 época, com o loss de treinamento numa linha quase continua, até a execução final do modelo na época 64, com loss: 0.0611.

Já o loss de validação tem um comportamento bem variável até a 30ª época, vindo após isto, se estabilizar numa linha quase continua, até a execução final do modelo na época 64, com loss: 0.0611.

![image](https://user-images.githubusercontent.com/58257963/138325256-02079288-32ab-4947-a128-5945f7f0183d.png)



### 3. Resultados

O modelo com a melhor acurácia foi o Deep Learning Modelo Conv2D (A) com 98.29% e o pior foi pre treinado VGG16 Model com 97.45%. Podemos destacar também que o modelo Deep Learning também é eficiente com aplicações tais como: reconhecimento de fala e imagem, processamento de linguagem natural, sistemas de recomendação, dentre outros. 

Particularmente nesse trabalho, existe a oportunidade de um direcionamento para xxxxxxxxxxxxxxxx.

### 4. Conclusões



---

Matrícula: 192.190.138

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
