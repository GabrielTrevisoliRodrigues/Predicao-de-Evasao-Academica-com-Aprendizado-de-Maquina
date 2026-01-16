# 🎓 Predição de Evasão Acadêmica com Aprendizado de Máquina

Este projeto apresenta um **pipeline completo de Machine Learning** aplicado ao problema de **evasão acadêmica**, utilizando dados socioeconômicos e de desempenho acadêmico de estudantes.

O objetivo central é **identificar antecipadamente alunos com maior risco de evasão**, permitindo que instituições de ensino adotem **ações preventivas** baseadas em dados.

---

## 🎯 Objetivo do Projeto

- Analisar e compreender o comportamento dos dados educacionais
- Selecionar variáveis relevantes com base em análise estatística
- Construir e comparar modelos de classificação supervisionada
- Otimizar e avaliar o modelo final
- Interpretar os resultados de forma aplicada ao contexto educacional

---

## 📊 Etapa 1 — Análise Exploratória dos Dados (EDA)

Durante a EDA, observou-se que:

- Todas as variáveis são numéricas, exceto a variável alvo (*evasão*)
- Não existem valores faltantes nem duplicados
- O dataset original possui **36 features**

### 🔍 Análises realizadas
- **Análise univariada**: estudo de simetria e assimetria das distribuições
- **Análise bivariada**:
  - Correlação entre variáveis para evitar redundâncias
  - Correlação ponto-bisserial entre cada feature e o target

Com base nessas análises, foram selecionadas **13 variáveis mais relevantes** para a modelagem.

---

## ⚙️ Etapa 2 — Pré-processamento

Para as 13 features selecionadas, foram aplicadas as seguintes etapas:

1. **PowerTransformer** para reduzir a assimetria das distribuições
2. **StandardScaler** para padronização (média zero e desvio padrão igual a 1)
3. Divisão do dataset em **conjuntos de treino e teste**

---

## 🤖 Etapa 3 — Modelagem

Foram treinados e avaliados quatro modelos de classificação:

| Modelo | Descrição |
|------|-----------|
| Logistic Regression | Modelo linear utilizado como baseline |
| KNN (K-Nearest Neighbors) | Classificação baseada em proximidade |
| Random Forest | Ensemble de árvores para redução de variância |
| Gradient Boosting | Modelo baseado em boosting de classificadores fracos |

---

## 📈 Etapa 4 — Avaliação dos Modelos

As métricas utilizadas foram:

- Accuracy  
- Precision  
- Recall  
- F1-score  

### 🎯 Importância do Recall
No contexto da evasão acadêmica, **minimizar falsos negativos** é fundamental — ou seja, evitar que alunos em risco não sejam identificados pelo modelo.  
Por isso, o **Recall** foi adotado como métrica principal de avaliação.

### 🧾 Resultados
Todos os modelos apresentaram desempenho consistente, com métricas variando entre **0.86 e 0.89**.  
O **Gradient Boosting Classifier** apresentou desempenho ligeiramente superior e foi selecionado para a etapa de otimização.

---

## 🔧 Etapa 5 — Otimização e Interpretação

Foi aplicado **GridSearchCV** ao modelo de Gradient Boosting para ajuste de hiperparâmetros.  
A otimização não resultou em ganhos significativos, indicando que o modelo inicial já estava bem ajustado.

Mesmo assim, o Gradient Boosting foi mantido como **modelo final**, apresentando o melhor equilíbrio entre recall e desempenho geral.

O projeto também contempla análise de **interpretabilidade**, reforçando a transparência das decisões do modelo.

---

## 📂 Estrutura do Projeto

```text
├── Dia 1 - EDA inicial.ipynb
├── Dia 2 - EDA e Pré-processamento.ipynb
├── Dia 3 - Modelagem e Baseline.ipynb
├── Dia 4 – Otimização e Interpretação.ipynb
├── avaliacao_gradient_boosting.json

