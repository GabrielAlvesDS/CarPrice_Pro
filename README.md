# CarPrice Pro - Modelo de Precificação de carros 

![cover](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/carprice%20pro_cut.jpg)

<br>

## Objetivo do Projeto
O  CarPrice Pro tem como objetivo principal desenvolver um modelo de machine learning capaz de prever o preço de carros com base em suas características. O projeto também busca criar uma interface de usuário intuitiva para permitir que os usuários possam calcular o valor estimado de um carro de maneira simples e eficiente.

## Descrição do Modelo
O modelo de Machine Learning escolhido é o XGBoostRegressor devido ao seu desempenho superior durante a seleção, apresentando o menor erro (RMSE). Ajustes de hiperparâmetros foram feitos com a biblioteca Optuna, resultando nos parâmetros ideais.

## Conjunto de Dados
O conjunto de dados foi obtido a partir do site WebMotors, contendo 566 mil anúncios de carros no Brasil. A lista completa das features extraídas do WebMotors assim como as selecionadas para treinar o modelo, podem ser visualizadas na figura abaixo:

<img src="https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/Features.png" width="400">

## Pré-processamento de Dados
O pré-processamento envolveu a criação de novas features, a remoção de outliers em features como 'KM', 'AnoModelo', 'AnoFabricacao', 'Fipe' e 'Valor', além da exclusão de registros duplicados. Foram realizadas filtragens para remover dados inconsistentes e irrelevantes. A categorização de variáveis categóricas e a exclusão de features menos relevantes também foram realizadas.

Uma questão importante abordada durante o pré-processamento foi a má distribuição dos dados, que foi corrigida por meio da remoção de outliers. Os histogramas e boxplots apresentados na figura abaixo ilustram como a remoção desses valores atípicos contribuiu para uma distribuição mais equilibrada e representativa das variáveis.

- Histogramas antes da limpeza e filtragem dos dados:
![histogram_1](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/Histogramas%201.png)


- Histogramas após da limpeza e filtragem dos dados:
![histogram_2](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/Histogramas%202.png)


- Boxplot comparando o antes e depois:
![boxplot_horizontal](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/boxplot%20geral%20horizontal.png)

Foi necessário também codificar as variáveis Marca, Modelo e Versão de forma hierárquica, visto que o resultado se mostrou muito superior com essa forma de encoding.

## Treinamento do Modelo
Antes de iniciar o projeto o conjunto de dados foi dividido em treino (80%) e teste (20%). A escolha do XGBoost foi feita após comparar o resultado de sete modelos diferentes, calculados utilizando o cross-validation, como apresentado na figura abaixo.

![results_table](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/resultado%20dos%20algoritmos%20de%20regressao.png)

O treinamento envolveu a busca pelos melhores hiperparâmetros com o Optuna.
 
Como o resultado desejado não foi obtido e se tratando apenas de um projeto para mostrar minhas habilidades com ciência de dados, vou continuar coletando novos dados e enquanto sigo para a próxima etapa de produção. Para isso um filtro adicional foi aplicado para selecionar apenas carros com diferença de preço predito e real abaixo de 10 mil reais.

## Avaliação do Modelo
A métrica principal utilizada para avaliar o desempenho do modelo foi o RMSE (Root Mean Squared Error). O modelo final apresentou um RMSE de 2 mil após filtragem, considerado aceitável para a variação normal de preços de carros anunciados.

![final_results](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/Final%20model%20results.png)

## Visualizações e Análises
Foram realizadas diversas análises exploratórias, incluindo histogramas, boxplots e gráficos de correlação. Hipóteses sobre variáveis como ano do modelo, quilometragem, cor, e outros foram testadas e validadas com visualizações e análises estatísticas.
   
## Instruções para Execução
Para acessar o modelo e solicitar o valor de um veículo, acesse o link abaixo:

https://docs.google.com/spreadsheets/d/1qpC4JApSCmDyH4fDHAwcsKcGn2nrY4JOtJ10SspNqKU/edit#gid=0

Para calcular o valor, basta selecionar/preencher as informações na tabela abaixo e clicar no botão 'Calcular preço do carro'.

<br>

![googlesheets](https://github.com/GabrielAlvesDS/CarPrice_Pro/blob/main/images/googlesheets.png)

<br>

Por favor, aguarde alguns instantes após inserir ou modificar os dados na planilha do Google Sheets, pois algumas listas suspensas, como 'Modelo', 'Ano Fabricação', 'Ano Modelo', 'Versão' e 'Cidade', dependem dessas informações atualizadas para serem totalmente preenchidas.

**Observação:** Devido ao tamanho limitado da base de dados utilizada no treinamento do modelo, nem todos os modelos podem ser selecionados e ter seus preços calculados.

Além disso, para acessar o repositório do webapp com os códigos usados para criar a API e calcular a predição com base no modelo salvo, visite o link abaixo:

https://github.com/GabrielAlvesDS/carprice_pro_app

## Próximos Passos
O desenvolvimento futuro do projeto CarPrice Pro inclui:

**Implementação de um Bot no Telegram:** Está planejada a criação de um bot no Telegram para interagir com os usuários via celular. Esse bot utilizará a API já criada no carprice_pro_app.
**Aumento da Base de Dados:** Pretende-se coletar mais dados da WebMotors para aumentar a quantidade de carros disponíveis para a predição do modelo. Isso contribuirá para melhorar a precisão das estimativas de preços.


Este documento fornece uma visão geral abrangente do projeto CarPrice Pro. Recomenda-se revisar o notebook original para obter detalhes completos sobre o desenvolvimento e a execução 
