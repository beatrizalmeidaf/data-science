# Regressão Linear para Previsão de Emissões de CO2

Este projeto utiliza um modelo de regressão linear para prever as emissões de CO2 de veículos com base no tamanho do motor. O dataset usado contém dados de consumo de combustível e emissões de CO2 de vários modelos de veículos.

## Objetivo

O principal objetivo deste projeto é:

- Treinar um modelo de regressão linear para prever as emissões de CO2 de veículos com base em características como o tamanho do motor (Engine Size).
- Avaliar o desempenho do modelo utilizando métricas como erro quadrático médio (MSE), erro médio absoluto (MAE), raiz do erro quadrático médio (RMSE) e o coeficiente de determinação (R2-score).
- Analisar a relação entre as variáveis para entender como o tamanho do motor influencia nas emissões de CO2.

## Dataset

O dataset utilizado é o `FuelConsumptionCo2.csv`, que pode ser encontrado [aqui](https://raw.githubusercontent.com/diogocortiz/Crash-Course-IA/master/RegressaoLinear/FuelConsumptionCo2.csv). Ele contém informações sobre:

- Tamanho do motor (Engine Size)
- Classe do veículo (Vehicle Class)
- Tipo de combustível (Fuel Type)
- Consumo de combustível (Fuel Consumption)
- Emissões de CO2 (CO2 Emissions)
- Entre outros.

O dataset possui 1067 registros com 13 colunas.

## Estrutura do Código

1. **Importação de Bibliotecas**: O código usa as seguintes bibliotecas:
    - `matplotlib`: Para visualização de gráficos.
    - `pandas`: Para manipulação de dados.
    - `numpy`: Para cálculos numéricos.
    - `scikit-learn`: Para a construção e avaliação do modelo de regressão linear.
    - `requests`: Para baixar o dataset a partir de uma URL.

2. **Download e Carregamento do Dataset**: O dataset é baixado diretamente da URL e salvo como `FuelConsumptionCo2.csv`. Ele é então carregado em um dataframe usando o `pandas`.

3. **Pré-processamento dos Dados**:
    - São extraídas as colunas de interesse: Tamanho do motor (`ENGINESIZE`) e Emissões de CO2 (`CO2EMISSIONS`).
    - Os dados são divididos em conjunto de treino (80%) e teste (20%) usando `train_test_split`.

4. **Treinamento do Modelo**:
    - Um modelo de regressão linear é treinado nos dados de treino para prever as emissões de CO2 com base no tamanho do motor.

5. **Avaliação do Modelo**:
    - O modelo é avaliado nos dados de teste com base em métricas de desempenho como SSE, MSE, MAE, RMSE e R2-score.

6. **Visualização**:
    - Gráficos de dispersão são usados para visualizar a relação entre o tamanho do motor e as emissões de CO2.
    - A reta de regressão é plotada para os dados de treino e teste.
    - Gráficos comparando valores reais e previstos, bem como a análise de resíduos, são gerados para avaliar a qualidade do modelo.

## Ferramentas e Tecnologias

- **Linguagem**: Python
- **Bibliotecas**: 
    - `matplotlib` para visualização.
    - `pandas` para manipulação de dados.
    - `scikit-learn` para machine learning.
    - `numpy` para operações matemáticas.
    - `requests` para download de arquivos.
    
## Métricas de Avaliação

As seguintes métricas são calculadas para avaliar o desempenho do modelo:

- **SSE (Soma dos Erros ao Quadrado)**: Mede o total dos erros quadrados.
- **MSE (Erro Quadrático Médio)**: Média do quadrado dos erros entre os valores reais e previstos.
- **MAE (Erro Médio Absoluto)**: Média dos valores absolutos das diferenças entre valores reais e previstos.
- **RMSE (Raiz do Erro Quadrático Médio)**: A raiz quadrada do MSE.
- **R2-Score**: Mede a proporção da variância total explicada pelo modelo.

### Resultados Obtidos

- **SSE**: 210991
- **MSE**: 985.94
- **MAE**: 24.10
- **RMSE**: 31.40
- **R2-Score**: 0.68

## Como Executar

1. Certifique-se de que você tenha o Python instalado e as bibliotecas necessárias.
2. Execute o seguinte comando para instalar as bibliotecas:

    ```bash
    pip install pandas numpy scikit-learn matplotlib requests
    ```

3. Baixe e execute o script principal para treinar o modelo e visualizar os resultados.

4. O dataset será automaticamente baixado na execução do código.

## Conclusão

Este projeto demonstra uma aplicação simples de regressão linear para prever as emissões de CO2 com base no tamanho do motor de um veículo. Embora o modelo apresente um bom desempenho, ainda há espaço para melhorias, como a inclusão de mais variáveis no modelo ou o uso de técnicas de machine learning mais complexas.
