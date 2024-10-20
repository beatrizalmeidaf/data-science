# Análise de Limpeza e Tratamento de Dados em R

Este projeto tem como objetivo realizar a **limpeza e tratamento** de um conjunto de dados de municípios, focando na análise de **PIB**, **valores empenhados** e na relação entre esses dois indicadores.

## Objetivos
- Limpar e tratar os dados do dataset de municípios.
- Visualizar a distribuição do **PIB** e do **valor empenhado**.
- Identificar os municípios com os maiores **PIBs** e **valores empenhados**.
- Analisar a proporção entre **valor empenhado** e **PIB** para entender o uso dos recursos financeiros.

## Ferramentas Utilizadas
- **R**: Linguagem utilizada para a análise de dados.
- **Pacote base do R**: Para manipulação e visualização de dados.
- **brewer.pal**: Função usada para aplicar paletas de cores harmoniosas nos gráficos.

## Descrição dos Dados
O dataset contém informações de municípios, incluindo:
- **MUNICÍPIO**: Nome do município.
- **PIB**: Produto Interno Bruto do município.
- **VALOREMPENHO**: Valor total empenhado pelo município.

## Análise Realizada
1. **Carregamento e resumo dos dados**: Foram carregados e explorados, identificando os principais valores de interesse.
   
2. **Visualização gráfica**:
   - **Boxplots**: Gerados para mostrar a distribuição dos valores de **PIB** e **VALORES EMPENHADOS**, utilizando cores para destacar as características dos dados.
   - **Histograma**: Distribuição das variáveis **PIB** e **VALORES EMPENHADOS** foi visualizada para verificar padrões.

3. **Identificação dos maiores valores**:
   - **Maiores valores empenhados**: Identificamos os municípios com os 10 maiores valores empenhados e os visualizamos em gráficos de barras.
   - **Maiores PIBs**: Da mesma forma, foram destacados os municípios com os 10 maiores PIBs.

4. **Proporção entre valor empenhado e PIB**: Calculamos a proporção entre o valor empenhado e o PIB, identificando os municípios onde o maior percentual do PIB foi empenhado. Esse indicador é útil para entender como os municípios estão utilizando seus recursos.

## Próximos Passos
- Explorar outras variáveis e relações presentes no dataset.
- Realizar análises preditivas para estimar tendências futuras de empenho com base no PIB.

Este projeto traz uma abordagem visual e quantitativa dos dados dos municípios, permitindo a compreensão das dinâmicas econômicas e de empenho de recursos.
