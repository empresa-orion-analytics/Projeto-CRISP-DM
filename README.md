# 📊 Customer Churn Prediction – Lakehouse + Machine Learning

Projeto completo de Data Engineering e Machine Learning utilizando arquitetura Lakehouse no Databricks, seguindo a metodologia CRISP-DM.

Os dados foram obtidos do Kaggle e estruturados em um pipeline completo até modelagem preditiva de churn.

---

# 📦 Dataset

Fonte dos dados:

Superstore Dataset – Kaggle  
https://www.kaggle.com/datasets/cemeraan/3a-superstore/data

O dataset simula transações de uma rede varejista contendo:

- Pedidos
- Clientes
- Produtos
- Categorias
- Filiais

---

# 🏗 Arquitetura do Projeto

O projeto foi implementado no Databricks utilizando:

- Unity Catalog
- Delta Tables
- Volumes para ML
- Apache Spark (PySpark)

## Estrutura Lakehouse

Kaggle CSV → Unity Catalog → Bronze → Silver → Gold → ML → Evaluation


---

# 🗄 Estrutura de Dados (Modelagem Relacional)

Tabelas principais:

- orders
- order_details
- customers
- categories
- branches

Tabelas derivadas:

- gold_rfm
- gold_churn

Relacionamentos principais:

- Orders ↔ Customers
- Orders ↔ Branches
- Order_Details ↔ Categories

---

# 🧱 Camadas de Dados

## 🔹 Bronze
- Ingestão dos CSVs do Kaggle
- Armazenamento bruto no Unity Catalog

## 🔹 Silver
- Limpeza
- Tratamento de nulos
- Padronização de tipos
- Deduplicação

## 🔹 Gold

### 📌 gold_rfm
Criação das métricas:

- Recency
- Frequency
- Monetary

### 📌 gold_churn
Criação da variável alvo (churn) com base em regra de inatividade.

---

# 🤖 Machine Learning

Modelos treinados:

- Logistic Regression
- Random Forest

## Features utilizadas

- recency
- frequency
- monetary

## Técnicas aplicadas

- Tratamento de desbalanceamento com class weights
- Hyperparameter tuning
- Comparação de modelos
- Avaliação com AUC

---

# 📊 Avaliação

Notebooks de avaliação incluem:

- Métricas (AUC)
- Comparação entre modelos
- Análise de performance
- Ajuste de threshold

---

# 🧠 Metodologia

O projeto segue CRISP-DM:

1. Business Understanding
2. Data Understanding
3. Data Preparation
4. Modeling
5. Evaluation

---

# 📂 Estrutura dos Notebooks

# 📂 Estrutura do Projeto

## 01_Business_Understanding
- **01_Contexto_Negocio**  
  - Definição do problema  
  - Objetivos do projeto  
  - Entendimento das regras de negócio  
  - Definição de churn  

## 02_Data_Understanding
- **02_Exploracao_Inicial**  
  - Análise exploratória dos dados (EDA)  
  - Distribuição das variáveis  
  - Identificação de valores nulos  
  - Primeiras hipóteses  

- **03_Analise_Estatistica**  
  - Estatísticas descritivas  
  - Correlações  
  - Testes estatísticos  
  - Insights quantitativos  

## 03_Data_Preparation
- **04_Limpeza**  
  - Tratamento de valores nulos  
  - Remoção de duplicados  
  - Padronização de dados  
  - Encoding de variáveis categóricas  

- **05_Feature_Engineering**  
  - Criação de novas variáveis  
  - Transformações  
  - Normalização / Padronização  
  - Seleção de features  

- **06_Criacao_Target_Churn**  
  - Definição da variável alvo  
  - Regras de construção do churn  
  - Balanceamento de classes  

## 04_Modeling
- **07_Logistic_Regression**  
  - Treinamento do modelo  
  - Ajuste de hiperparâmetros  
  - Interpretação dos coeficientes  

- **08_Random_Forest**  
  - Treinamento do modelo  
  - Feature importance  
  - Ajuste de hiperparâmetros  

## 05_Evaluation
- **09_Metricas**  
  - Accuracy  
  - Precision  
  - Recall  
  - F1-Score  
  - ROC-AUC  

- **10_Comparacao_Modelos**  
  - Comparação entre modelos  
  - Matriz de confusão  
  - Curva ROC  
  - Escolha do modelo final  


---

# 🛠 Stack Tecnológica

- Databricks
- Unity Catalog
- Delta Lake
- Apache Spark
- PySpark ML
- Python

---

# 🎯 Objetivo de Negócio

Antecipar clientes com alta probabilidade de churn para:

- Reduzir perda de receita
- Direcionar campanhas de retenção
- Melhorar LTV

---

# 🚀 Próximos Passos

- Deploy do modelo como endpoint
- Monitoramento de drift
- Integração com CRM
- Dashboard executivo
- Feature Store

---

# 👨‍💻 Autor

Bruno Lima de Santana
Diogo Silva
Giovani Rueda Malafaia
Lucas Vinicius de Souza Costa
Talita Nóbrega
Data Engineering & Machine Learning Project

---

# 📎 Observação

Este projeto tem finalidade educacional e demonstração técnica, simulando um cenário real de retenção de clientes em varejo.

