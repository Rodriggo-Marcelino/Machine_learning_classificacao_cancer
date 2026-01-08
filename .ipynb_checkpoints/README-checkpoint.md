# 🧠 Classificação de Tumores – Breast Cancer Wisconsin Dataset

Este projeto tem como objetivo aplicar **Machine Learning** para a **classificação de tumores de mama** como **benignos** ou **malignos**, utilizando o dataset *Breast Cancer Wisconsin (Diagnostic)*.

O foco principal é a construção de um **pipeline simples, robusto e bem justificado**, utilizando o algoritmo **XGBoost Classifier**.

---

## 📊 Dataset

- **Fonte:** Breast Cancer Wisconsin (Diagnostic)
- **Instâncias:** 569
- **Atributos:** 30 variáveis numéricas
- **Variável alvo:** `diagnosis`

### Classes
- `B` → Benigno  
- `M` → Maligno  

---

## 🧹 Pré-processamento dos Dados

As seguintes etapas foram realizadas:

- Remoção da coluna `id`, por ser apenas um identificador
- Remoção da coluna final composta apenas por valores nulos
- Transformação da variável alvo `diagnosis` em valores ordinais:
  - `0` → Benigno
  - `1` → Maligno
- Não foi necessário criar variáveis *dummies*, pois todas as variáveis preditoras são numéricas

### ⚠️ Escalonamento
Não foi aplicado escalonamento (normalização ou padronização), pois o algoritmo utilizado é baseado em **árvores de decisão**, que **não são sensíveis à escala dos dados**.

---

## 🤖 Modelo Utilizado

### XGBoost Classifier (XGBC)

O **XGBoost** foi escolhido por apresentar:

- Excelente desempenho em dados tabulares
- Capacidade de capturar relações não lineares
- Regularização embutida para controle de overfitting
- Alta eficiência computacional

### 🔧 Hiperparâmetros Utilizados

```python
XGBClassifier(
    max_depth=2,
    learning_rate=0.05,
    n_estimators=200,
    subsample=0.8,
    colsample_bytree=0.8,
    min_child_weight=3,
    random_state=0,
    eval_metric='logloss'
)
