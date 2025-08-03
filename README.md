## Predição de Turnover (Rotatividade) de Funcionários com Machine Learning

### Sobre o projeto:

Este foi um projeto realizado como parte do Bootcamp [Re]Start Data Girls, da trilha Cientista de Dados. Foi utilizado o dataset “IBM HR Analytics Attrition & Performance”.

### 🎯 Objetivo:

Construir um modelo preditivo que identifique padrões de rotatividade (attrition) e ajude a empresa fictícia Data Girls S.A a prever quais colaboradores têm maior propensão a sair da organização.

### Perguntas Norteadoras:

- Quais características mais influenciam na rotatividade de funcionários?
- Qual perfil de colaborador tem maior propensão a sair da empresa?
- Um modelo de ML pode prever com boa precisão a saída de um funcionário?
- Que ações a empresa pode tomar com base nessas previsões?

---

### 📌 Dados utilizados:
- **Dataset:** [Kaggle – IBM HR Analytics Employee Attrition](https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset)
- **Amostra:** 1470 funcionários
- **Variáveis:** 35 colunas

---

### 📌 Etapas Realizadas

**1.Leitura e Exploração Inicial**

- Dataset lido e visualizado com ```pandas```.

- Verificada a dimensão: 1470 linhas × 35 colunas

- ✅ Nenhum dado nulo presente.

- Distribuição de Attrition:

    - **Não:** 83.9%

    - **Sim:** 16.1% → ⚠️ Classe desbalanceada

**2. Limpeza e Preparação dos Dados**

- Conversão de variáveis categóricas via ```OneHotEncoder```.

- Variáveis como ```EmployeeNumber```, ```Over18```, ```StandardHours``` e ```EmployeeCount``` foram removidas por não agregar valor ao modelo.

- ```StandardScaler``` aplicado para modelos que requerem normalização.

- ```X.shape```: (1470, 44) — após dummies

- ```y.shape```: (1470,) — target binário (```Attrition```)

**3. Análise Exploratória (EDA)**

- Análise univariada e bivariada de variáveis-chave como idade, tempo de empresa, função, estado civil, viagens e horas extras.

- Boxplots, histograms, heatmaps, correlações

- As variáveis com maior correlação com Attrition:

    - 🔺 Positivas: OverTime, MaritalStatus_Single, JobRole_Sales Rep

    - 🔻 Negativas: Age, MonthlyIncome, TotalWorkingYears

**4. Modelagem Preditiva**

**Modelos Testados:**

- Regressão Logística (com StandardScaler)

- XGBoost


**Tuning de Hiperparâmetros:**

- GridSearchCV (Regressão Logística)

- RandomizedSearchCV (XGBoost)


**Melhor Modelo: Regressão Logística com Tuning**

- Recall da classe positiva (Attrition = Yes) = 0.69

- Melhor equilíbrio entre explicabilidade e desempenho

---

**5. Avaliação dos Modelos**

🎯 Regressão Logística

| Métric    | **Classe 0** | **Classe 1** | 
|----------------------    |----------    |
| Precision | 0.93         | 0.37         | 
| Recall    | 0.77         | 0.69         | 
| F1-Score  | 0.84         | 0.48         | 
| Accuracy  | 0.76         |              | 

🎯 XGBoost

| Métric    | **Classe 0** | **Classe 1** | 
|-----------------------------------------|
| Precision | 0.90         | 0.41         | 
| Recall    | 0.87         | 0.48         | 
| F1-Score  | 0.88         | 0.44         | 
| Accuracy  | 0.81         |              |


🔍 **Análise de Erros**

**Falsos Positivos (FP):** Funcionários previstos para sair, mas que ficaram → risco de gasto desnecessário com retenção

**Falsos Negativos (FN):** Funcionários previstos para ficar, mas que saíram → impacto direto na perda de talentos


🔥 **Explicação com SHAP (Regressão Logística)**

- Gráfico ```SHAP bar``` → mostra variáveis com maior impacto:

    - ```OverTime```, ```NumCompaniesWorked```, ```JobSatisfaction```, ```Age```

- Gráfico ```SHAP waterfall``` → explicação individual (decisão personalizada por funcionário)

---

🧠 **Principais Achados**

- Funcionários que fazem hora extra ou viajam com frequência têm mais chance de sair.

- Jovens, solteiros e de cargos operacionais estão mais propensos à rotatividade.

- Funcionários com maior tempo de empresa, renda e experiência têm menor probabilidade de saída.

📌 **Recomendações para o RH**

| Fator de Risco                | Ação Recomendada                       |
| ----------------------------- | -------------------------------------- |
| OverTime frequente            | Reavaliar carga horária e bem-estar    |
| Viagens frequentes            | Oferecer flexibilidade ou compensações |
| Cargos com alta rotatividade  | Investir em treinamentos e engajamento |
| Baixa satisfação no trabalho  | Pesquisas de clima e escuta ativa      |
| Funcionários jovens/solteiros | Criar planos de carreira e retenção    |

---

### 🛠️ 📚 Tecnologias utilizadas

- ```Python```

- ```Pandas```, ```NumPy```, ```Matplotlib```, ```Seaborn```

- ```Scikit-learn```, ```XGBoost```

- ```SHAP``` para interpretabilidade

- ```Jupyter Notebook```

---

## 🙋‍♀️ Autora:

**Keylla Souza de Carvalho**