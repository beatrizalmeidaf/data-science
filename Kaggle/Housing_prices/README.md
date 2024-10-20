# Análise e Predição de Preços de Imóveis

## Visão Geral do Projeto
Este projeto tem como objetivo analisar dados de preços de imóveis e construir modelos preditivos para estimar o valor médio das casas com base em diversas características, como informações geográficas, população, renda e características habitacionais. Foram utilizados diferentes algoritmos de aprendizado de máquina, como Regressão Linear e Regressão Florestal Aleatória, para prever os preços e comparar o desempenho desses modelos.

## Objetivos
- **Limpeza de Dados:** Tratar valores ausentes e remover registros incompletos.
- **Engenharia de Atributos:** Criar novas variáveis, como a proporção de quartos por domicílio e a razão de dormitórios por total de quartos.
- **Visualização de Dados:** Gerar gráficos e mapas de calor para entender as correlações entre as variáveis.
- **Modelagem Preditiva:** Comparar os desempenhos de diferentes modelos para prever o valor mediano dos imóveis.
- **Avaliação dos Modelos:** Medir a precisão dos modelos com base no conjunto de dados de teste.

## Ferramentas Utilizadas
- **Linguagem:** Python
- **Bibliotecas:** 
  - `pandas`: Manipulação e análise de dados.
  - `seaborn` e `matplotlib`: Visualização de dados e criação de gráficos.
  - `scikit-learn`: Construção de modelos de aprendizado de máquina.
  - `numpy`: Cálculos numéricos e transformações logarítmicas.

## Dados
O dataset utilizado contém informações geográficas, demográficas e socioeconômicas relacionadas aos preços de imóveis na Califórnia. As colunas incluem:
- **longitude** e **latitude:** Coordenadas geográficas.
- **housing_median_age:** Idade média das habitações.
- **total_rooms:** Total de quartos na região.
- **total_bedrooms:** Total de dormitórios na região.
- **population:** População total na área.
- **households:** Total de domicílios na área.
- **median_income:** Renda mediana dos moradores.
- **median_house_value:** Valor mediano dos imóveis (variável alvo).
- **ocean_proximity:** Proximidade com o oceano (variável categórica).

O dataset original contém 20.640 registros, mas após o tratamento de dados, 20.433 registros foram mantidos.

## Passos Realizados

### 1. Limpeza de Dados
Foram removidos registros com valores nulos para garantir a consistência dos dados. A função `dropna()` foi utilizada para este processo.

### 2. Engenharia de Atributos
Foram criados novos atributos:
- **bedroom_ratio:** Razão entre o número de dormitórios e o total de quartos.
- **household_rooms:** Razão entre o total de quartos e o número de domicílios.
- **One-hot encoding:** Transformação da variável categórica `ocean_proximity` em variáveis binárias.

### 3. Visualização de Dados
- Histogramas das variáveis foram gerados para observar a distribuição dos dados.
- Mapas de calor de correlação (`heatmap`) foram usados para visualizar a correlação entre as variáveis numéricas.
- Gráficos de dispersão foram criados para analisar a distribuição dos preços em relação à latitude e longitude.

### 4. Transformações Logarítmicas
Foram aplicadas transformações logarítmicas nas variáveis com distribuições assimétricas, como `total_rooms`, `total_bedrooms`, `population` e `households`, para melhorar o desempenho dos modelos preditivos.

### 5. Modelagem
Dois modelos de regressão foram treinados:
- **Regressão Linear:** Utilizada como modelo inicial para prever o valor mediano das casas.
- **Regressão com Floresta Aleatória:** Utilizada para melhorar a precisão preditiva com um modelo mais robusto.

### 6. Avaliação dos Modelos
Os modelos foram avaliados com o conjunto de dados de teste:
- **Regressão Linear:** Atingiu uma pontuação de 0.67.
- **Floresta Aleatória:** Obteve uma pontuação superior de 0.82, mostrando melhor capacidade preditiva.

## Resultados e Conclusões
O modelo de Floresta Aleatória superou o modelo de Regressão Linear, alcançando uma maior precisão nas previsões de preços de imóveis. O uso de engenharia de atributos, como transformações logarítmicas e a criação de novas variáveis, foi essencial para melhorar o desempenho dos modelos.

Este projeto demonstra a importância de entender os dados e aplicar técnicas de modelagem apropriadas para prever com precisão o valor dos imóveis.

## Como Executar
1. Instale as dependências necessárias:
   ```bash
   pip install pandas seaborn matplotlib scikit-learn numpy
   ```
2. Execute o script Python que carrega e processa os dados, treina os modelos e gera as previsões.

## Melhorias Futuras
- Testar outros modelos de aprendizado de máquina, como Gradient Boosting e Redes Neurais.
- Aplicar uma análise mais profunda de hiperparâmetros para otimizar ainda mais o desempenho do modelo.
- Explorar técnicas de clusterização para segmentar melhor os tipos de imóveis e áreas geográficas.
