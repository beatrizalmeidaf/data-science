# Análise e Modelagem de Diabetes com Regressão Logística

## Descrição do Projeto

Este projeto tem como objetivo analisar um conjunto de dados sobre diabetes e construir um modelo de Regressão Logística para prever a presença de diabetes em indivíduos. O foco está na exploração dos dados, no tratamento de valores ausentes e na avaliação do desempenho do modelo.

## Objetivos

1. Carregar e explorar o conjunto de dados sobre diabetes.
2. Tratar dados ausentes e realizar a imputação.
3. Analisar a correlação entre as variáveis.
4. Construir um modelo de Regressão Logística para prever diabetes.
5. Avaliar o desempenho do modelo utilizando métricas como precisão, recall, F1-score e matriz de confusão.
6. Gerar a curva ROC para visualizar o desempenho do modelo.

## Ferramentas Utilizadas

- **Python**: Linguagem de programação utilizada para implementar o código.
- **Pandas**: Biblioteca para manipulação e análise de dados.
- **NumPy**: Biblioteca para operações numéricas.
- **Matplotlib**: Biblioteca para visualização de dados.
- **Seaborn**: Biblioteca para visualizações estatísticas.
- **Scikit-learn**: Biblioteca para aprendizado de máquina, utilizada para construir o modelo de Regressão Logística e avaliação de desempenho.
- **Statsmodels**: Biblioteca para realizar análises estatísticas e regressão.

## Conjunto de Dados

O conjunto de dados utilizado neste projeto é o "Pima Indians Diabetes Database", que contém informações sobre mulheres indígenas americanas com dados sobre saúde. O conjunto de dados tem as seguintes colunas:

- `pregnant`: Número de gestações.
- `glucose`: Nível de glicose no sangue.
- `bp`: Pressão arterial diastólica.
- `skin`: Espessura da pele.
- `insulin`: Nível de insulina no sangue.
- `bmi`: Índice de Massa Corporal.
- `pedigree`: Valor de pedigree de diabetes.
- `age`: Idade do paciente.
- `label`: 0 (sem diabetes) ou 1 (com diabetes).

### Exemplo de Dados

| pregnant | glucose | bp | skin | insulin | bmi  | pedigree | age | label |
|----------|---------|----|------|---------|------|----------|-----|-------|
| 6        | 148     | 72 | 35   | 0       | 33.6 | 0.627    | 50  | 1     |
| 1        | 85      | 66 | 29   | 0       | 26.6 | 0.351    | 31  | 0     |
| ...      | ...     | ...| ...  | ...     | ...  | ...      | ... | ...   |

## Passos do Código

1. **Importação de Bibliotecas**: As bibliotecas necessárias são importadas.
2. **Carregamento de Dados**: O conjunto de dados é carregado usando o Pandas.
3. **Exploração Inicial**: São exibidas as primeiras entradas do conjunto de dados e algumas estatísticas descritivas.
4. **Tratamento de Dados**:
   - Identificação e substituição de valores zero por `NaN` nas colunas relevantes.
   - Imputação dos valores nulos com a média de cada coluna.
5. **Visualização**: Histogramas e um mapa de calor são gerados para analisar a distribuição dos dados e a correlação entre as variáveis.
6. **Divisão do Conjunto de Dados**: Os dados são divididos em conjuntos de treino e teste, garantindo que as proporções das classes sejam mantidas.
7. **Construção do Modelo**: Um modelo de Regressão Logística é treinado com os dados de treino.
8. **Avaliação do Modelo**: O desempenho do modelo é avaliado com uma matriz de confusão, métricas de classificação e uma curva ROC.
9. **Teste com Novos Dados**: O modelo é testado com variáveis aleatórias para prever a probabilidade de diabetes.

## Resultados

As principais métricas do modelo incluem:

- **Acurácia**: 78%
- **Recall**: 52% (para casos com diabetes)
- **Precision**: 76% (para casos com diabetes)
- **F1-score**: 62% (para casos com diabetes)

## Como Executar o Código

1. Certifique-se de que o Python e as bibliotecas necessárias estão instaladas.
2. Faça o download do arquivo `diabetes.csv` e coloque-o no mesmo diretório do seu script.
3. Execute o script Python em um ambiente que suporte a execução de código Python.

## Conclusão

Este projeto fornece uma visão geral do uso de Regressão Logística para prever diabetes, além de enfatizar a importância da exploração e tratamento de dados para construir modelos de aprendizado de máquina eficazes.
