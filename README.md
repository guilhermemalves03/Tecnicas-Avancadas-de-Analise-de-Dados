# Técnicas Avançadas de Análise de Dados

Este repositório contém os projetos práticos desenvolvidos no âmbito da unidade curricular de **Técnicas Avançadas de Análise de Dados**. O trabalho divide-se em duas grandes vertentes: Análise Estatística Clássica e Machine Learning aplicado a Séries Temporais Financeiras.

**Autores:**
* Guilherme Alves
* Tomás Gonçalves
* Bárbara Baptista
* João Simões

---

## 1. Projeto de Machine Learning: Previsão de Ações (PayPal)

### 🎯 Objetivo
Explorar a viabilidade de prever a direção do preço das ações do PayPal (PYPL) e a sua volatilidade utilizando algoritmos de Deep Learning (LSTM) e Regressão (SVR), com foco em estratégias de gestão de risco.

### 🧠 Metodologia
O projeto seguiu um pipeline rigoroso de Data Science:
1.  **Análise de Séries Temporais:** Verificação de estacionariedade (Testes ADF e KPSS) e análise de autocorrelação.
2.  **Feature Engineering:** Criação de indicadores técnicos (RSI, MACD, Bollinger Bands) e métricas de volatilidade realizada.
3.  **Modelagem de Volatilidade (SVR):** Utilização de *Support Vector Regression* para prever a magnitude dos movimentos (volatilidade).
4.  **Classificação de Tendência (LSTM):** Rede Neural Recorrente para classificar o movimento do dia seguinte como "Alta" (1) ou "Baixa" (0).

### 📊 Resultados e Análise Crítica
Ao contrário de muitos "modelos de caixa preta" que prometem retornos irreais, a nossa análise revelou a dificuldade intrínseca de prever mercados eficientes.

* **Desafio da Acurácia:** O modelo LSTM obteve uma **Acurácia Global de ~48%**, estatisticamente semelhante a um lançamento de moeda. Isso confirma a hipótese de passeio aleatório (*random walk*) em curtos prazos.
* **O Valor do Recall:** Apesar da baixa acurácia, ajustamos o modelo para ser sensível a quedas. Conseguimos um **Recall de 80% para a classe 'Down'**.
    * *Significado:* O modelo raramente acerta quando a ação vai subir, mas é excelente a alertar quando a ação vai cair.
* **Aplicação Real:** O modelo não serve para *trading* agressivo de lucro, mas demonstrou potencial como ferramenta de **Gestão de Risco** (Hedging), permitindo evitar os piores dias de negociação.

| Métrica (Teste) | Classe 'Down' (Queda) | Classe 'Up' (Alta) |
| :--- | :---: | :---: |
| **Precision** | 0.48 | 0.50 |
| **Recall** | **0.80** | 0.19 |
| **F1-Score** | 0.60 | 0.28 |

---

## 2. Projeto de Estatística: Análise Multivariada

### 🎯 Objetivo
Aplicação de métodos estatísticos robustos para validar hipóteses e reduzir a dimensionalidade em datasets clássicos (Iris Dataset e Student Performance).

### 🧪 Técnicas Aplicadas
* **MANOVA (Multivariate Analysis of Variance):** Para testar se existem diferenças estatisticamente significativas entre os centróides das espécies de flores considerando todas as variáveis simultaneamente.
* **PCA (Principal Component Analysis):** Redução de dimensionalidade para visualização da estrutura dos dados, demonstrando que a maior parte da variância explicada reside nos dois primeiros componentes principais.
* **Regressão Linear Múltipla:** Análise de fatores que influenciam o desempenho dos estudantes.

---

## 🛠️ Tecnologias e Bibliotecas
* **Linguagem:** Python 3.x
* **Machine Learning/DL:** TensorFlow (Keras), Scikit-Learn, XGBoost.
* **Estatística:** SciPy, Statsmodels.
* **Visualização:** Matplotlib, Seaborn.
* **Dados:** Yahoo Finance API (`yfinance`).

## ⚠️ Isenção de Responsabilidade
Este projeto tem fins estritamente educacionais e académicos. Nenhuma informação aqui contida constitui aconselhamento financeiro ou recomendação de investimento.
