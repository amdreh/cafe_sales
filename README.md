# Limpeza e Tratamento de Dados: Cafe Sales Dataset

Este projeto apresenta a limpeza e o tratamento de uma base de dados de vendas de uma cafeteria (`dirty_cafe_sales.csv`). Meu objetivo foi transformar um dataset "sujo" (com erros de preenchimento e tipos de dados incorretos) em um arquivo mais estruturado e confiável para uma futura análise em ferramentas de BI.

## 🛠️ Tecnologias Utilizadas
* **Python** (Linguagem principal)
* **Pandas** (Manipulação e tratamento de dados)
* **Google Colab** (Ambiente de desenvolvimento)

## 📁 Estrutura do Projeto
* `data/`: Contém o dataset original e o arquivo final limpo.
* `notebooks/`: Arquivo Jupyter Notebook (`.ipynb`) com todo o passo a passo da limpeza.

## 📋 Etapas de Limpeza Realizadas

O dataset original apresentava diversas inconsistências que impediriam qualquer análise financeira precisa. Abaixo, as soluções aplicadas:

1.  **Padronização de Categorias:**
    * Identificação de valores como `ERROR` e `UNKNOWN` na coluna de itens.
    * Substituição estratégica por `DESCONHECIDO` para manter a integridade das linhas sem perder volume de dados.

2.  **Tratamento de Datas:**
    * Conversão da coluna de data (originalmente lida como texto) para o formato `datetime`.
    * Uso de `errors='coerce'` para transformar entradas inválidas em valores nulos padrão do Pandas (`NaT`), evitando que erros de digitação corrompessem a análise temporal.

3.  **Tipagem de Dados e Consistência Numérica:**
    * Limpeza e conversão das colunas de preço e quantidade para formatos numéricos (`float` e `int`).
    * Identificação e contagem de valores nulos (`NaN`) para entender a extensão da perda de dados.

4.  **Exportação de Alta Performance:**
    * O arquivo final foi exportado no formato **Parquet**. Diferente do CSV, este formato preserva os tipos de dados configurados no Python, garantindo que o Power BI ou Excel leiam as colunas corretamente de forma automática.

## 📈 Insights de Negócio
Durante o processo, documentei minha lógica de decisão. Por exemplo:
> *"Se a quantidade de linhas com itens desconhecidos fosse baixa, eu poderia optar pela exclusão; porém, optei por rotulá-las para não enviesar o cálculo do faturamento total."*

## 🚀 Como visualizar o projeto
Você pode visualizar o código completo e os resultados diretamente aqui pelo GitHub (no diretório notebooks) ou abrir o notebook no Google Colab pelo botão abaixo para executar as células:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/amdreh/cafe_sales/blob/main/notebooks/Cafe_Sales.ipynb)

---
*Projeto desenvolvido por André Garcia como parte do portfólio de Análise de Dados.*
