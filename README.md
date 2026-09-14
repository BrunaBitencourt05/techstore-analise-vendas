# 📊 Análise de Vendas com Python e SQL

Este projeto consiste em um estudo de análise de dados utilizando **Python** (`pandas`) e **SQL** (`sqlite3`) para manipular e extrair insights estratégicos a partir de uma base de dados de vendas.

O projeto foi desenvolvido e executado em ambiente Jupyter Notebook (`.ipynb`).

---

## 🚀 Tecnologias Utilizadas

- **Python**: Linguagem principal do projeto.
- **Pandas**: Manipulação e análise de estruturas de dados.
- **SQLite3**: Banco de dados relacional para execução de consultas SQL.
- **Google Colab / Jupyter Notebook**: Ambiente de desenvolvimento interativo.

---

## 🔍 Principais Análises Realizadas

1. **Contagem Total de Registros**: Verificação do volume geral da base de dados.
2. **Filtragem por Categorias**: Identificação de vendas específicas (ex: eletrônicos).
3. **Cálculo de Faturamento**: Criação da coluna `receita_total` calculando `quantidade * preco_unitario`.
4. **Produto Mais Vendido**: Consulta SQL utilizando agregação (`SUM`) e agrupamento (`GROUP BY`) para determinar o produto campeão de vendas em volume.
5. **Região de Maior Faturamento**: Identificação da região com maior valor financeiro gerado em compras.

---

## 🛠️ Consultas SQL em Destaque

<details>
<summary>Clique para ver os exemplos de queries utilizadas</summary>

```sql
-- Produto mais vendido em quantidade de unidades
SELECT produto, SUM(quantidade) AS total_vendido 
FROM vendas 
GROUP BY produto 
ORDER BY total_vendido DESC 
LIMIT 1;

-- Região com maior valor total de compras
SELECT regiao, SUM(quantidade * preco_unitario) AS maior_valor 
FROM vendas 
GROUP BY regiao 
ORDER BY maior_valor DESC 
LIMIT 1;
