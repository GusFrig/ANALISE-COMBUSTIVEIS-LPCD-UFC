# ANALISE-COMBUSTIVEIS-LPCD-UFC

# Análise de Produção de Combustíveis (Etanol)

Este projeto consiste em um script de análise de dados desenvolvido em Python para o processamento, limpeza e identificação de anomalias em dados históricos de produção de combustíveis (Etanol Anidro e Hidratado) no Brasil.

## 🎯 Objetivo do Projeto
O objetivo explícito do código é realizar um **diagnóstico de qualidade de dados** (Data Quality) em um dataset de produção de combustíveis. O script foca em três pilares principais:
1.  **Identificação de Dados Faltantes:** Localizar colunas com valores nulos que podem comprometer a análise.
2.  **Detecção de Duplicidade:** Verificar a existência de registros repetidos.
3.  **Análise de Outliers:** Utilizar métodos estatísticos e visuais para identificar volumes de produção que fogem drasticamente do padrão, o que pode indicar erros de digitação ou eventos excepcionais.

## 🛠️ Tecnologias e Bibliotecas
O projeto utiliza as principais ferramentas da stack de Data Science em Python:
* **Pandas & Numpy:** Manipulação de estruturas de dados e operações matemáticas.
* **Matplotlib & Seaborn:** Geração de gráficos estatísticos estáticos (Boxplots).
* **Plotly Express:** Criação de visualizações interativas para inspeção detalhada de pontos fora da curva.
* **Re (Regex):** Preparação para manipulação de padrões de texto (se necessário).

## 🚀 Funcionamento do Código

O fluxo de execução está organizado nas seguintes etapas:

### 1. Extração e Carga (ETL Inicial)
O código realiza a leitura de um arquivo CSV hospedado remotamente. Inclui um bloco de tratamento de erros (`try/except`) para garantir que o script não quebre caso a URL esteja inacessível.

### 2. Diagnóstico de Integridade
* **Check de Nulos:** O script filtra o dataset para exibir apenas as colunas que possuem valores ausentes.
* **Check de Duplicados:** Realiza a contagem de linhas redundantes.

### 3. Análise Estatística (Identificação de Outliers)
Para identificar valores atípicos na produção de Etanol Anidro e Hidratado, o código:
* Gera **Boxplots** para visualizar a dispersão e os limites interquartis.
* Utiliza a função `melt` para reestruturar os dados (unpivot), facilitando a comparação entre os diferentes tipos de combustíveis em um único eixo.

### 4. Visualização Interativa
O código culmina em um gráfico de dispersão interativo (`px.scatter`). Esta ferramenta permite que o analista passe o mouse sobre os pontos para identificar:
* O estado e a região do registro.
* O período (mês/ano).
* O volume exato produzido.

## 📂 Como Executar
1. Clone o repositório.
2. Certifique-se de ter o Python instalado.
3. Instale as dependências:
   ```bash
   pip install pandas numpy matplotlib seaborn plotly
