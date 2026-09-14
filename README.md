# 🛒 TechStore - Análise Exploratória de Vendas

Este repositório contém a solução do desafio de análise de dados da empresa fictícia **TechStore**. O objetivo principal é realizar uma Análise Exploratória de Dados (EDA) em Python e SQL a partir de um histórico de vendas em formato CSV, respondendo a perguntas estratégicas de negócio.

---

## 📌 Objetivos do Projeto

- **Carregamento e Exploração:** Importar e inspecionar a base de dados de vendas (`vendas.csv`).
- **Consultas de Negócio:**
  - Identificar o produto mais vendido em quantidade de unidades.
  - Mapear a região com maior faturamento em vendas.
  - Filtrar registros por categorias específicas (ex: Eletrônicos).
  - Calcular a receita total gerada (`quantidade * preco_unitario`).
- **Manipulação de Dados:** Utilizar rotinas em **Python (Pandas)** e **SQL (SQLite3)** dentro de um ambiente notebook interativo.

---

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Pandas**: Leitura, limpeza e transformação de dados.
- **SQLite3**: Execução de consultas SQL diretamente sobre DataFrames.
- **Jupyter Notebook / Google Colab**: Ambiente de execução da análise (`.ipynb`).

---

## 📊 Principais Consultas SQL Aplicadas

<details>
<summary>Clique para ver as queries executadas</summary>

```sql
-- Produto campeão em unidades vendidas
SELECT produto, SUM(quantidade) AS total_vendido 
FROM vendas 
GROUP BY produto 
ORDER BY total_vendido DESC 
LIMIT 1;

-- Região líder em faturamento total
SELECT regiao, SUM(quantidade * preco_unitario) AS maior_valor 
FROM vendas 
GROUP BY regiao 
ORDER BY maior_valor DESC 
LIMIT 1;
