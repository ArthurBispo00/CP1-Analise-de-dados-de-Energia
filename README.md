# ⚡ Análise de Dados de Consumo de Energia Residencial

> Este repositório contém uma análise exploratória de dados e a aplicação de técnicas de machine learning em um conjunto de dados de consumo de energia de uma única residência durante quatro anos. O objetivo é extrair padrões, entender o comportamento do consumo e aplicar modelos preditivos e de segmentação.

Este projeto foi desenvolvido como parte do Checkpoint de Data Science e Machine Learning.

## 📊 Dataset

O conjunto de dados utilizado é o **"Individual Household Electric Power Consumption"**, disponível publicamente no Repositório de Machine Learning da UCI.

- **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)
- **Período:** Dezembro de 2006 a Novembro de 2010.
- **Frequência:** Medições a cada minuto.

## 🚀 Análise Realizada

O notebook `analise_consumo_energia.ipynb` está dividido em duas partes principais:

### Parte 1: Análise Exploratória e Pré-processamento

Nesta seção, realizamos a preparação e a primeira exploração dos dados para extrair insights iniciais.
- **Limpeza de Dados:** Carregamento do dataset, tratamento de valores ausentes e conversão de tipos de dados (datas e horas).
- **Engenharia de Features:** Criação de novas colunas como `day_of_week` (dia da semana) e `Total_Sub_metering` (soma do consumo medido).
- **Análise de Consumo:** Cálculo de médias diárias e mensais, e identificação do dia de maior consumo.
- **Análise Comparativa:** Comparação do consumo médio entre dias de semana vs. finais de semana e entre inverno vs. verão.
- **Visualização de Dados:** Geração de gráficos de linha, histogramas e séries temporais para visualizar a distribuição e o comportamento de variáveis como `Global_active_power` e `Voltage`.
- **Análise de Correlação:** Criação de uma matriz de correlação e um heatmap para entender a relação entre as variáveis elétricas.
- **Introdução ao Machine Learning:**
  - Aplicação de **K-Means** para uma primeira segmentação de dias por perfil de consumo.
  - Treinamento de um modelo de **Regressão Linear Simples** para prever `Global_active_power` a partir de `Global_intensity`.

### Parte 2: Tópicos Avançados e Modelagem

Nesta segunda parte, aprofundamos a análise com técnicas mais avançadas.
- **Análise de Séries Temporais:** Reamostragem dos dados por hora para identificar os horários de pico de consumo ao longo de um dia típico.
- **Autocorrelação (ACF):** Análise da autocorrelação da série horária para confirmar estatisticamente a existência de padrões diários (sazonalidade de 24 horas).
- **Redução de Dimensionalidade (PCA):** Aplicação do PCA para reduzir 4 variáveis elétricas para 2 componentes principais, mantendo mais de 80% da informação original.
- **Visualização de Clusters:** Projeção dos clusters do K-Means no espaço 2D criado pelo PCA para visualizar a separação dos grupos.
- **Comparação de Modelos:** Treinamento e comparação de uma **Regressão Linear Simples** vs. uma **Regressão Polinomial** para modelar a relação entre `Voltage` e `Global_active_power`, analisando o erro (RMSE) e o ajuste das curvas.

## 💡 Principais Insights

- O consumo de energia é **maior durante o inverno** e nos **períodos da noite** (entre 19h e 22h).
- Existe um **padrão diário e semanal** muito forte e repetitivo no consumo.
- A variável `Global_intensity` é uma previsora quase perfeita para `Global_active_power`, confirmando a lei da física elétrica.
- A **voltagem (`Voltage`) da rede é muito estável** e não serve como uma boa variável para prever o consumo de energia.
- Os dias podem ser agrupados com sucesso em 3 perfis de consumo: **Baixo, Médio e Alto**.

## 🛠️ Ferramentas Utilizadas

- **Linguagem:** Python 3
- **Bibliotecas Principais:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Statsmodels.
- **Ambiente:** Google Colab.
