```markdown
# Análise de PIB e Valores Empenhados dos Municípios

Este projeto tem como objetivo analisar dados de PIB e valores empenhados de diferentes municípios. A análise inclui a visualização dos dados por meio de gráficos e a exploração das proporções entre o valor empenhado e o PIB, destacando tanto os municípios com as menores quanto as maiores proporções.

## Objetivos
- Analisar a distribuição do **PIB** e dos **valores empenhados** dos municípios.
- Identificar os municípios com os menores e maiores valores de **PIB** e **valores empenhados**.
- Calcular e visualizar a proporção entre **valor empenhado** e **PIB**.
- Comparar os municípios com as menores e maiores proporções.

## Dados Utilizados

O arquivo `dados.csv` contém informações sobre os municípios e seus respectivos valores de PIB e empenhos. As colunas relevantes são:
- **CODIGO**: Código do município.
- **MUNICIPIO**: Nome do município.
- **PIB**: Produto Interno Bruto do município.
- **VALOREMPENHO**: Valor empenhado pelo município.

## Ferramentas Utilizadas
O código foi desenvolvido em Python utilizando as seguintes bibliotecas:
- **pandas**: Manipulação de dados.
- **seaborn**: Visualização de dados, especialmente para gerar histogramas.
- **numpy**: Operações com arrays multidimensionais.
- **matplotlib**: Geração de gráficos e visualizações.

## Passos Realizados

### 1. Carregamento e Visualização Inicial dos Dados
Os dados foram carregados a partir de um arquivo CSV, e as primeiras linhas do dataset foram visualizadas:

```python
import pandas as pd
data = pd.read_csv("dados.csv", sep=";")
data.head()
```

### 2. Análise dos Dados: Histogramas
Foram gerados gráficos de histogramas para visualizar a distribuição do PIB e dos valores empenhados dos municípios:

```python
import seaborn as srn
srn.histplot(data.PIB, kde=True, bins=10).set(title='PIB')
srn.histplot(data.VALOREMPENHO, kde=True, bins=10).set(title='VALOR EMPENHO')
```

### 3. Análise dos 10 Menores PIBs
Os 10 municípios com os menores valores de PIB foram identificados e visualizados em um gráfico de barras:

```python
agrupado = data.sort_values('PIB').head(10)
agrupado.plot.bar(x='MUNICIPIO', y='PIB', color='blue')
```

### 4. Análise dos 10 Menores Valores Empenhados
Da mesma forma, foi gerado um gráfico de barras para os 10 municípios com os menores valores empenhados:

```python
agrupadov = data.sort_values('VALOREMPENHO').head(10)
agrupadov.plot.bar(x='MUNICIPIO', y='VALOREMPENHO', color='red')
```

### 5. Cálculo da Proporção Entre Valor Empenhado e PIB
Uma nova coluna chamada **PROPORCAO** foi criada para armazenar a relação entre o valor empenhado e o PIB:

```python
data["PROPORCAO"] = data["VALOREMPENHO"] / data["PIB"]
```

Os gráficos a seguir mostram os municípios com as 10 menores e as 10 maiores proporções:

```python
prop_menores = data.sort_values('PROPORCAO').head(10)
prop_maiores = data.sort_values('PROPORCAO', ascending=False).head(10)

# Gráficos lado a lado
import matplotlib.pyplot as plt
fig, axes = plt.subplots(1, 2, figsize=(14, 6))

prop_menores.plot.bar(x='MUNICIPIO', y='PROPORCAO', color='green', ax=axes[0]).set(title="Menores Proporções")
prop_maiores.plot.bar(x='MUNICIPIO', y='PROPORCAO', color='purple', ax=axes[1]).set(title="Maiores Proporções")

plt.tight_layout()
plt.show()
```

## Como Executar o Projeto

1. Instale as dependências necessárias:
   ```bash
   pip install pandas seaborn matplotlib numpy
   ```

2. Carregue o dataset `dados.csv` e execute o script para gerar as visualizações e realizar a análise.

## Melhorias Futuras
- Explorar outros tipos de análises estatísticas, como correlação entre as variáveis.
- Utilizar algoritmos de aprendizado de máquina para prever o valor empenhado com base em outras variáveis econômicas.
- Incluir mais dados relacionados aos municípios, como a população e o IDH, para enriquecer a análise.

```
