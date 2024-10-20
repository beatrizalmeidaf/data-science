# Previsão de Doença Cardíaca

## Descrição
Este projeto visa desenvolver um modelo de previsão de doença cardíaca utilizando Regressão Logística. O modelo é treinado em um conjunto de dados que contém informações sobre fatores de risco associados a doenças cardíacas. O objetivo principal é prever a probabilidade de um paciente desenvolver uma doença cardíaca com base em suas características.

## Objetivos
- Desenvolver um modelo preditivo que classifique pacientes com base na presença ou ausência de doenças cardíacas.
- Avaliar a precisão do modelo utilizando métricas apropriadas, como matriz de confusão e acurácia.

## Ferramentas Utilizadas
- **Python**: Linguagem de programação utilizada para desenvolver o modelo.
- **Pandas**: Biblioteca para manipulação de dados.
- **Scikit-learn**: Biblioteca para aprendizado de máquina, usada para modelagem e avaliação.
- **Matplotlib**: Biblioteca para visualização de dados (embora não utilizada neste código, é comum em projetos de ciência de dados).
- **NumPy**: Biblioteca para manipulação de arrays e operações matemáticas.

## Dados
O conjunto de dados utilizado é o **Framingham Heart Study**, que contém as seguintes colunas:

- `male`: Sexo do paciente (0 = feminino, 1 = masculino)
- `age`: Idade do paciente
- `education`: Nível educacional
- `currentSmoker`: Indica se o paciente é fumante (0 = não, 1 = sim)
- `cigsPerDay`: Número de cigarros fumados por dia
- `BPMeds`: Uso de medicamentos para pressão arterial (0 = não, 1 = sim)
- `prevalentStroke`: Histórico de AVC (0 = não, 1 = sim)
- `prevalentHyp`: Hipertensão prévia (0 = não, 1 = sim)
- `diabetes`: Histórico de diabetes (0 = não, 1 = sim)
- `totChol`: Colesterol total
- `sysBP`: Pressão arterial sistólica
- `diaBP`: Pressão arterial diastólica
- `BMI`: Índice de Massa Corporal
- `heartRate`: Frequência cardíaca
- `glucose`: Nível de glicose
- `TenYearCHD`: Indica se o paciente desenvolveu doença cardíaca em 10 anos (0 = não, 1 = sim)

### Observações
- O conjunto de dados pode conter valores ausentes (NaN), que são removidos antes da modelagem.
- As colunas de características (features) e a variável alvo (target) são separadas para treinamento do modelo.

## Execução do Código

### 1. Importação de Bibliotecas
```python
import pandas as pd
import sklearn.model_selection as ms
import numpy as np
from sklearn.metrics import confusion_matrix, accuracy_score
from sklearn.linear_model import LogisticRegression
```

### 2. Carregamento do Conjunto de Dados
```python
dataset = pd.read_csv("framingham_heart_disease.csv")
dataset = dataset.dropna()
```

### 3. Preparação dos Dados
```python
X = dataset.iloc[:, :-1].values
y = dataset.iloc[:, -1].values
X_train, X_test, y_train, y_test = ms.train_test_split(X, y, test_size=1/5, random_state=0)
```

### 4. Treinamento do Modelo
```python
classifier = LogisticRegression()
classifier.fit(X_train, y_train)
```

### 5. Previsão e Avaliação
```python
y_pred = classifier.predict(X_test)
cm = confusion_matrix(y_test, y_pred)
accuracy = accuracy_score(y_test, y_pred)
```

## Resultados
- A matriz de confusão fornece uma visão detalhada sobre o desempenho do modelo, mostrando os verdadeiros positivos (TP), verdadeiros negativos (TN), falsos positivos (FP) e falsos negativos (FN).
- A acurácia do modelo é calculada para verificar a proporção de previsões corretas.

### Exemplo de Previsão
```python
# Prever a classe de um novo paciente
predict = classifier.predict([[1, 30, 4, 0, 0, 0, 0, 0, 0, 195, 130, 70, 80, 20, 56]])
print(predict)  # Resultado: [0] (não tem a doença)
```

## Considerações Finais
O modelo desenvolvido é um primeiro passo na análise preditiva de doenças cardíacas. Melhorias podem incluir o ajuste de hiperparâmetros, a utilização de outros algoritmos de aprendizado de máquina e a implementação de técnicas de validação cruzada para melhorar a robustez das previsões.
