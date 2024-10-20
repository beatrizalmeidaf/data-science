```markdown
# Projeto de Previsão de Doença Cardíaca com Regressão Logística

## Descrição do Projeto

Este projeto visa construir um modelo de aprendizado de máquina para prever a presença de doença cardíaca usando um conjunto de dados chamado "Framingham Heart Study". A previsão é feita utilizando Regressão Logística, que é um algoritmo de classificação binária. O objetivo principal é prever a probabilidade de um paciente desenvolver doença cardíaca dentro de um período de 10 anos, com base em características como idade, gênero, hábito de fumar, pressão arterial, entre outros.

## Ferramentas e Bibliotecas Utilizadas

- **Pandas**: Para manipulação e análise de dados.
- **NumPy**: Para operações numéricas e manipulação de arrays.
- **Scikit-Learn**: Para implementação de algoritmos de aprendizado de máquina, divisão do conjunto de dados e métricas de avaliação.
- **Matplotlib**: Para visualização gráfica (não utilizado diretamente no código, mas útil para possíveis melhorias e análises futuras).

## Estrutura do Dataset

O dataset contém as seguintes colunas (features):
- `male`: Gênero do paciente (1 = masculino, 0 = feminino)
- `age`: Idade do paciente
- `education`: Nível de educação
- `currentSmoker`: Se o paciente é fumante atual (1 = sim, 0 = não)
- `cigsPerDay`: Número de cigarros fumados por dia
- `BPMeds`: Se o paciente está tomando medicamentos para pressão arterial
- `prevalentStroke`: Se o paciente já teve um AVC
- `prevalentHyp`: Se o paciente tem hipertensão
- `diabetes`: Se o paciente tem diabetes
- `totChol`: Colesterol total
- `sysBP`: Pressão arterial sistólica
- `diaBP`: Pressão arterial diastólica
- `BMI`: Índice de Massa Corporal
- `heartRate`: Frequência cardíaca
- `glucose`: Nível de glicose
- `TenYearCHD`: Indicador da presença de doença cardíaca em 10 anos (1 = sim, 0 = não)

## Pré-Processamento de Dados

1. **Carregamento do Dataset**: O dataset foi carregado a partir de um arquivo CSV.
2. **Tratamento de Valores Faltantes**: Foram removidas as linhas que continham valores faltantes (`NaN`).
3. **Separação de Features e Labels**: As colunas de características (features) foram separadas da variável alvo (`TenYearCHD`).
4. **Divisão de Treino e Teste**: O dataset foi dividido em 80% para treinamento e 20% para teste.

## Implementação do Modelo

1. **Modelo Utilizado**: Regressão Logística
2. **Treinamento**: O modelo foi treinado usando os dados de treino.
3. **Previsão**: O modelo faz previsões de classes e probabilidades de doença para os dados de teste.

## Avaliação do Modelo

### Matriz de Confusão

A matriz de confusão é utilizada para avaliar o desempenho do modelo, comparando as previsões com os valores reais:
- **TN (True Negatives)**: Número de previsões corretas para pacientes sem a doença.
- **FP (False Positives)**: Número de previsões incorretas indicando presença de doença (falsos positivos).
- **FN (False Negatives)**: Número de previsões incorretas indicando ausência de doença (falsos negativos).
- **TP (True Positives)**: Número de previsões corretas para pacientes com a doença.

### Métricas

- **Acurácia**: Proporção de previsões corretas feitas pelo modelo.

## Resultados

- **Acurácia do Modelo**: 85,5%
- **Exemplo de Previsões**:
  - Previsões de Classes: `[0, 1, 0]` (0 = sem doença, 1 = com doença)
  - Probabilidades: `[[0.85, 0.15], [0.30, 0.70], [0.95, 0.05]]`

## Execução do Código

1. Certifique-se de ter as bibliotecas necessárias instaladas:
   ```bash
   pip install pandas numpy scikit-learn matplotlib
   ```bash
2. Execute o script Python fornecendo o dataset `framingham_heart_disease.csv` no mesmo diretório.

## Melhorias Futuras

- **Escalonamento de Dados**: Normalizar os dados para melhorar a performance e a convergência do modelo.
- **Hiperparâmetros**: Ajustar hiperparâmetros como `max_iter` e experimentar diferentes algoritmos de classificação.
- **Visualização**: Adicionar gráficos para uma melhor interpretação dos dados e resultados.
```
