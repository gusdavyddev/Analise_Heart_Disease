# Analise_Heart_Disease

# Atividade Prática - Programação Avançada: Machine Learning

Este repositório contém a entrega da atividade prática da disciplina de **Programação Avançada**. O objetivo do trabalho foi realizar uma Análise Exploratória de Dados (EDA) e aplicar modelos de Machine Learning (KNN e Random Forest) em um dataset de saúde.

---

## Resumo do Trabalho

- **Dataset:** [Heart Disease Dataset (Kaggle)](https://www.kaggle.com/datasets/oktayrdeki/heart-disease)
- **Linguagem:** Python
- **Bibliotecas:** Pandas, NumPy, Matplotlib, Seaborn e Scikit-Learn
- **Modelos testados:** KNN (K-Nearest Neighbors) e Random Forest

---

## Etapas do Projeto

### 1. Tratamento dos Dados
- **Conversão de Categóricas:** As variáveis em texto (como gênero, hábito de fumar e consumo de álcool) foram convertidas para valores numéricos (`0`, `1`, `2`, `3`) para que os algoritmos pudessem processá-las.
- **Tratamento de Nulos:**
  - Colunas categóricas vazias foram preenchidas com a **moda** (valor mais frequente).
  - Colunas numéricas contínuas foram preenchidas com a **média**.

### 2. Análise Exploratória e Correlação
- Foi gerado um gráfico de calor (*Heatmap*) focado na variável alvo (`Heart Disease Status`).
- **Achado:** Notou-se que nenhuma das variáveis numéricas ou categóricas apresentava correlação forte com o resultado final do diagnóstico.

### 3. Divisão de Treino e Teste
- O dataset foi dividido na proporção de **80% para treino** e **20% para teste**.
- **Justificativa:** Essa é uma proporção padrão na literatura que garante dados suficientes para o aprendizado do modelo sem comprometer a etapa de validação.

### 4. Avaliação dos Modelos

| Modelo | Acurácia Obtida |
| :--- | :---: |
| **KNN** | ~80% |
| **Random Forest** | ~80% |

---

## Conclusão e Discussão dos Resultados

Durante a análise da matriz de confusão dos modelos, identificou-se a causa da acurácia estagnar em 80%:

1. **Desbalanceamento de Classes:** O dataset possui **80% de casos negativos (0)** e apenas **20% de casos positivos (1)**.
2. **Comportamento do Algoritmo:** Como as variáveis não possuem correlação direta com o alvo, os modelos aprenderam a "chutar" a classe majoritária (`0`) para 100% das amostras, garantindo 80% de acurácia automática, porém sem acertar os pacientes doentes.
3. **Consideração Final:** O trabalho demonstrou na prática a importância de avaliar métricas adicionais (como *Recall* e *Matriz de Confusão*) para além da acurácia simples em problemas com dados desbalanceados.

Link para o dataset: https://www.kaggle.com/datasets/oktayrdeki/heart-disease/data
