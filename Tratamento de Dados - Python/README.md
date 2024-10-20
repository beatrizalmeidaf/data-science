## README.md

# Análise e Tratamento de Dados Meteorológicos

Este projeto tem como objetivo realizar a análise e tratamento de dados meteorológicos, utilizando bibliotecas populares para manipulação, visualização e aplicação de técnicas estatísticas. O foco é explorar os dados, identificar inconsistências, preencher valores ausentes e corrigir possíveis anomalias nos dados.

## Objetivos

1. **Importação e manipulação de dados:** Leitura de um arquivo CSV contendo dados meteorológicos, como aparência do céu, temperatura, umidade, vento e a possibilidade de realizar uma atividade ao ar livre.
2. **Exploração e visualização dos dados:** Verificar a distribuição dos dados categóricos e numéricos, gerar gráficos e sumarizar estatísticas descritivas.
3. **Tratamento de valores ausentes e anômalos:** Identificar valores ausentes e corrigir dados fora do domínio esperado para cada coluna.
4. **Limpeza dos dados:** Substituir valores incorretos e preencher valores ausentes com a mediana dos dados ou outras abordagens adequadas.

## Ferramentas Utilizadas

- **Pandas:** Biblioteca para manipulação e análise de dados estruturados, permitindo fácil leitura de arquivos CSV, tratamento de dados e geração de estatísticas.
- **Seaborn:** Biblioteca utilizada para visualização gráfica dos dados, como gráficos de barra e boxplots.
- **Statistics:** Biblioteca nativa do Python, utilizada para calcular medidas estatísticas, como a mediana, para preenchimento de valores ausentes.

## Estrutura dos Dados

O arquivo `tempo.csv` contém as seguintes colunas:
- **Aparência:** Descreve o estado do céu (ex: sol, nublado, chuva).
- **Temperatura:** Valor numérico da temperatura em graus.
- **Umidade:** Percentual de umidade do ar.
- **Vento:** Indica se há ou não vento (FALSO ou VERDADEIRO).
- **Jogar:** Indica se as condições são propícias para realizar uma atividade ao ar livre (sim ou não).

### Exemplo dos Dados:

| Aparência | Temperatura | Umidade | Vento     | Jogar |
|-----------|-------------|---------|-----------|-------|
| sol       | 85          | 85      | FALSO     | não   |
| sol       | 80          | 90      | VERDADEIRO| não   |
| nublado   | 83          | 86      | FALSO     | sim   |
| chuva     | 70          | NaN     | FALSO     | sim   |
| chuva     | 68          | 80      | FALSO     | sim   |

## Passos Realizados

1. **Leitura do CSV:** O arquivo `tempo.csv` foi lido utilizando a função `pd.read_csv()` do Pandas, com o separador `;`.
   ```python
   dataset = pd.read_csv("tempo.csv", sep=";")
   ```

2. **Visualização inicial dos dados:** Foram visualizadas as primeiras linhas da planilha para entender a estrutura.
   ```python
   dataset.head()
   ```

3. **Análise de dados categóricos:** O agrupamento por categorias nas colunas "Aparência", "Vento" e "Jogar" foi realizado para entender a distribuição dos dados. Foi observado que havia uma categoria incorreta ("menos") na coluna "Aparência", que foi substituída pela categoria "sol".
   ```python
   dataset.loc[dataset['Aparencia'] == 'menos', 'Aparencia'] = "sol"
   ```

4. **Análise de valores ausentes:** Identificamos valores ausentes nas colunas de "Vento" e "Umidade". O valor ausente em "Vento" foi substituído por "FALSO", e o valor ausente em "Umidade" foi substituído pela mediana dos valores.
   ```python
   dataset['Vento'].fillna('FALSO', inplace=True)
   dataset['Umidade'] = dataset['Umidade'].fillna(mediana)
   ```

5. **Tratamento de valores anômalos:** Valores fora do domínio esperado nas colunas numéricas, como temperaturas fora do intervalo aceitável (-130°C a 130°C), foram substituídos pela mediana.
   ```python
   dataset.loc[(dataset['Temperatura'] < -130) | (dataset['Temperatura'] > 130), 'Temperatura'] = mediana
   ```

6. **Visualização gráfica:** Foram criados gráficos de barra e boxplots para facilitar a interpretação dos dados.
   ```python
   srn.boxplot(dataset['Temperatura']).set_title('Temperatura')
   ```

## Como Executar

1. Instale as bibliotecas necessárias:
   ```bash
   pip install pandas seaborn
   ```
2. Execute o código Python para análise dos dados:
   ```bash
   python script.py
   ```

## Conclusão

Este projeto demonstrou a aplicação de técnicas de manipulação e análise de dados para tratar inconsistências e valores ausentes em um conjunto de dados meteorológicos. A limpeza dos dados permite uma análise mais precisa e confiável para a tomada de decisões.
