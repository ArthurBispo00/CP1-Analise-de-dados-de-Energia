# ⚡ Análise de Dados e Machine Learning para Consumo de Energia

> Este repositório contém a análise completa de dois datasets sobre consumo de energia, desenvolvida como parte do Checkpoint de Data Science e Machine Learning. O projeto abrange desde a limpeza e análise exploratória de dados até a aplicação de técnicas avançadas de machine learning e visualização interativa.

## 👨‍💻 Integrantes

- Arthur Bispo de Lima - RM:557568
- João Paulo Moreira dos Santos RM:557808
  
## 📊 Datasets Utilizados

1.  **Individual Household Electric Power Consumption**
    * **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)
    * **Descrição:** Medições de consumo elétrico a cada minuto de uma única residência por quatro anos.

2.  **Appliances Energy Prediction**
    * **Fonte:** [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/374/appliances+energy+prediction)
    * **Descrição:** Consumo de energia de eletrodomésticos e dados de sensores de temperatura e umidade.

## 🚀 Análise Realizada

A análise foi dividida em quatro partes principais:

### Parte 1 & 2: Análise Profunda do Consumo Residencial (Python)

No notebook `analise_consumo_energia.ipynb`, realizamos uma exploração completa do primeiro dataset:
- **Análise Exploratória (EDA):** Limpeza de dados, tratamento de valores ausentes, visualização de padrões diários, mensais e sazonais (inverno vs. verão).
- **Engenharia de Features:** Criação de novas variáveis para enriquecer a análise.
- **Análise de Séries Temporais:** Uso de reamostragem e autocorrelação (ACF) para confirmar estatisticamente os ciclos diários de consumo.
- **Machine Learning (Não Supervisionado):**
  - **K-Means:** Para segmentar os dias em 3 perfis distintos (consumo baixo, médio e alto).
  - **PCA:** Para reduzir 4 dimensões elétricas para 2, visualizando a separação dos clusters.
- **Modelagem Preditiva:** Comparação entre Regressão Linear e Polinomial.

### Parte 3: Modelagem Preditiva de Consumo de Eletrodomésticos (Python)

Ainda no mesmo notebook, focamos no segundo dataset para prever o consumo:
- **Análise de Correlação:** Investigamos a relação entre fatores ambientais (temperatura, umidade) e o consumo, concluindo que a correlação é fraca.
- **Modelagem de Regressão:** Comparamos a performance de uma **Regressão Linear Múltipla** (R² de 17%) com um **Random Forest Regressor**, que se mostrou muito superior por capturar relações não-lineares.
- **Modelagem de Classificação:** Transformamos o problema para prever "consumo alto vs. baixo". O **Random Forest Classifier** alcançou uma **acurácia de 90%**, mostrando-se um modelo robusto e equilibrado na análise da matriz de confusão.

### Parte 4: Análise Visual com Orange Data Mining

Utilizamos a ferramenta visual Orange Data Mining para replicar etapas chave da análise de forma interativa e sem código:
- **Fluxo Visual:** Construímos um pipeline usando widgets para importar, amostrar, visualizar distribuições, criar gráficos de dispersão e aplicar clustering.
- **Validação Visual:** Confirmamos visualmente os padrões encontrados no Python, como a distribuição assimétrica do consumo e a falta de correlação entre voltagem e corrente.
- **Clustering Interativo:** Aplicamos K-Means sobre os sub-medidores, identificando e visualizando claramente os diferentes perfis de uso dos eletrodomésticos (ex: "repouso", "cozinha ativa", "climatização ativa").

## 💡 Principais Insights

- O consumo de energia residencial possui fortes **padrões diários, semanais e sazonais**.
- A correlação entre **potência ativa e corrente elétrica é quase perfeita**, como esperado pela física.
- Fatores ambientais (temperatura, umidade) são **preditores fracos** para o consumo de eletrodomésticos, que é mais influenciado pelo **comportamento humano**.
- Modelos não-lineares como o **Random Forest são drasticamente superiores** para modelar relações complexas, alcançando **90% de acurácia** na tarefa de classificação.
- Ferramentas visuais como o **Orange Data Mining** são excelentes para validar rapidamente as hipóteses levantadas na análise via código.

## 🛠️ Ferramentas Utilizadas

- **Linguagem:** Python 3
- **Bibliotecas Principais:** Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn, Statsmodels.
- **Ambiente de Desenvolvimento:** Google Colab.
- **Ferramenta de Análise Visual:** Orange Data Mining.
