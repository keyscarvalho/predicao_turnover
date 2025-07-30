## Predição de Turnover (Rotatividade) de Funcionários com Machine Learning

### Sobre o projeto:

Este foi um projeto realizado como parte do Bootcamp [Re]Start Data Girls, da trilha Cientista de Dados. Foi utilizado o dataset “IBM HR Analytics Attrition & Performance”, com objetivo de construir um modelo preditivo que identifique padrões de rotatividade (attrition) e ajude a empresa fictícia Data Girls S.A a prever quais colaboradores têm maior propensão a sair da organização.

### Perguntas Norteadoras:

- Quais características mais influenciam na rotatividade de funcionários?
- Qual perfil de colaborador tem maior propensão a sair da empresa?
- Um modelo de ML pode prever com boa precisão a saída de um funcionário?
- Que ações a empresa pode tomar com base nessas previsões?

---

### 📌 Etapas Realizadas

**1. Leitura e Exploração dos Dados**
- Importação dos dados
- Exploração inicial dos dados

**2. Limpeza e Preparação**
- Lidando com valores nulos ou ausentes
- Seleciando variáveis mais relevantes
- Enconding variáveis categóricas
- Prepando os dados para análise e modelagem

**3. Análise Exploratória de Dados (EDA):**
- Avaliando distribuição e relação das variáveis com o alvo
- Identificando características que contribuem para a rotatividade

**4. Modelagem Preditiva**
- Treinar a avaliar modelos de machine learning (Regressão Logística e XGBoost)

**5. Avaliação dos Modelos**
- Tunar hiperparâmetros e comparar performances por métricas (accuracy, precision, recall, f1-score)
- Análise dos erros
- Direcionar recomendações ao RH baseado nos no achados

**6. Interpretação com SHAP**
- Visualização global e local dos fatores que mais influenciam a decisão do modelo

### 📌 Dataset: [Kaggle – IBM HR Analytics Employee Attrition](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)

---

## 📊 Resultados

| Modelo               | Accuracy | Recall (classe 1) | F1-score (classe 1) |
|----------------------|----------|-------------------|---------------------|
| Regressão Logística  | 0.76     | **0.69**          | 0.48                |
| XGBoost (tuned)      | **0.81** | 0.48              | 0.44                |

🔍 Mesmo com menor recall, o XGBoost foi interpretado com SHAP por ser mais complexo e ilustrar o uso de explicabilidade de modelos.

---

### 💡 Recomendações para o RH

- Reduzir carga de **hora extra**.
- Melhorar **benefícios financeiros** (como plano de ações).
- Focar em **jovens talentos** com alto risco de saída.
- Estimular **vínculo com gestores** e clima organizacional.

---

### 🛠️ Tecnologias Utilizadas

**- Python:** Pandas, Numpy, Matplotlib, Seaborn, Scikit-learn, XGBoost, SHAP
**- Notebook:** VSCode (Jupyter Notebook)

---

## 🙋‍♀️ Autora

**Keylla Souza de Carvalho**  
Cientista de Dados em formação | Bootcamp [RE]Start 2025