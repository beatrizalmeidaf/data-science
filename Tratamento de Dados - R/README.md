# Tratamento de Dados Meteorológicos em R

Este projeto tem como objetivo a análise e o tratamento de dados meteorológicos, abordando desde a importação de dados até a correção de valores ausentes e fora do domínio. Através do uso de técnicas estatísticas e de visualização de dados, as anomalias são corrigidas e o conjunto de dados é preparado para uma análise mais precisa.

## Objetivos

1. **Importação e limpeza de dados:** Carregar os dados a partir de um arquivo CSV, identificando e tratando valores ausentes.
2. **Exploração e visualização de dados:** Analisar distribuições de dados categóricos e numéricos, utilizando gráficos como histogramas e boxplots.
3. **Tratamento de valores anômalos:** Identificar e corrigir valores fora do domínio e inconsistências, principalmente nas colunas de temperatura e umidade.
4. **Representação adequada de dados categóricos:** Transformação de variáveis categóricas em fatores, para facilitar análises e visualizações.
5. **Substituição de valores ausentes:** Preencher valores ausentes com medidas estatísticas adequadas, como a mediana.

## Ferramentas Utilizadas

- **R Programming:** Linguagem utilizada para análise de dados.
- **Funções nativas de R:**
  - `read.csv()`: Para leitura de arquivos CSV.
  - `summary()`: Para obter estatísticas descritivas.
  - `boxplot()` e `hist()`: Para visualização de distribuições de variáveis numéricas.
  - `table()`: Para contar ocorrências de variáveis categóricas.
  - `barplot()`: Para visualização das variáveis categóricas.

## Estrutura dos Dados

O arquivo `tempo.csv` contém as seguintes colunas:
- **Aparência:** Descreve o estado do céu (ex: sol, nublado, chuva).
- **Temperatura:** Valor numérico da temperatura em graus Celsius.
- **Umidade:** Percentual de umidade do ar.
- **Vento:** Indica se há ou não vento (FALSO ou VERDADEIRO).
- **Jogar:** Indica se as condições são propícias para realizar atividades ao ar livre (sim ou não).

### Exemplo dos Dados:

| Aparência | Temperatura | Umidade | Vento     | Jogar |
|-----------|-------------|---------|-----------|-------|
| sol       | 85          | 85      | FALSO     | não   |
| sol       | 80          | 90      | VERDADEIRO| não   |
| nublado   | 83          | 86      | FALSO     | sim   |
| chuva     | 70          | NaN     | FALSO     | sim   |
| chuva     | 68          | 80      | FALSO     | sim   |

## Passos Realizados

1. **Leitura do CSV:** O arquivo `tempo.csv` foi lido utilizando a função `read.csv()`, com a conversão de variáveis categóricas em fatores e tratamento de valores ausentes representados como strings vazias.
   ```r
   dados_tempo = read.csv("tempo.csv", sep=";", na.strings = "", stringsAsFactors = TRUE)
   ```

2. **Visualização inicial dos dados:** Foram visualizados os primeiros registros e gerado um resumo estatístico.
   ```r
   head(dados_tempo)
   summary(dados_tempo)
   ```

3. **Exploração de variáveis categóricas:** A variável "Aparência" apresentava uma categoria anômala ("menos"), que foi substituída pela categoria "sol".
   ```r
   dados_tempo[!dados_tempo$Aparencia %in% c("chuva", "nublado", "sol"),]$Aparencia = "sol"
   ```

4. **Exploração de variáveis numéricas:** A análise inicial indicou um valor de temperatura fora do domínio esperado. Além disso, foi identificada a necessidade de corrigir valores de umidade superiores a 100%.
   ```r
   median(dados_tempo$Temperatura, na.rm = TRUE)
   dados_tempo[dados_tempo$Temperatura < -130 | dados_tempo$Temperatura > 130 ,]$Temperatura = median(dados_tempo$Temperatura, na.rm = TRUE)
   ```

5. **Tratamento de valores ausentes:** Na coluna "Umidade", os valores ausentes foram substituídos pela mediana da amostra, e o mesmo processo foi feito com a coluna "Vento", onde valores ausentes foram preenchidos com "FALSO".
   ```r
   median(dados_tempo$Umidade, na.rm = TRUE)
   dados_tempo[is.na(dados_tempo$Umidade),]$Umidade = median(dados_tempo$Umidade, na.rm = TRUE)
   
   dados_tempo[is.na(dados_tempo$Vento),]$Vento = "FALSO"
   ```

6. **Visualizações:** Foram gerados gráficos para as variáveis categóricas e numéricas, como histogramas e boxplots, para facilitar a interpretação e identificação de possíveis anomalias.
   ```r
   boxplot(dados_tempo$Temperatura)
   hist(dados_tempo$Temperatura)
   ```

## Como Executar

1. Instale as dependências necessárias no R.
2. Execute o script R para realizar a análise e o tratamento dos dados:
   ```r
   source("script.R")
   ```

## Conclusão

Este projeto demonstrou o processo de limpeza e exploração de um conjunto de dados meteorológicos. As etapas incluíram a correção de valores fora do domínio, o preenchimento de valores ausentes e a análise visual dos dados. A preparação correta dos dados é essencial para garantir uma análise mais precisa e confiável.

