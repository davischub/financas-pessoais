# 💰 Controle de Finanças Pessoais — Dashboard & Análise

> Pipeline completo de análise financeira pessoal: do dado bruto ao dashboard de acompanhamento mensal.

---

## Objetivo

Construir um sistema pessoal de controle financeiro orientado a dados — indo além de planilhas estáticas — com análise de padrões de gastos, metas e projeções.

---

## O Problema

A maioria das pessoas sabe quanto ganha, mas não sabe exatamente onde gasta. Extratos bancários são dados não estruturados. Este projeto transforma esses dados em inteligência financeira acionável.

---

## Funcionalidades

- **Ingestão de extratos** — leitura de CSV exportado do banco
- **Categorização automática** — classificação de transações por palavra-chave
- **Análise de padrões** — média mensal por categoria, outliers, tendências
- **Projeção de gastos** — estimativa dos próximos 3 meses por categoria
- **Dashboard interativo** — visão mensal, anual e por categoria no Power BI
- **Alertas de meta** — comparativo entre orçado e realizado

---

## Pipeline

```
extrato bancário (CSV)
    ↓
parsing e categorização (Python · pandas)
    ↓
armazenamento estruturado (SQLite / PostgreSQL)
    ↓
análise mensal e tendências
    ↓
dashboard (Power BI)
```

---

## Categorias Mapeadas

| Categoria | Exemplos |
|-----------|----------|
| Alimentação | Mercado, restaurante, ifood |
| Transporte | Combustível, uber, ônibus |
| Moradia | Aluguel, condomínio, energia |
| Saúde | Farmácia, consulta, plano |
| Educação | Cursos, livros, mensalidade |
| Lazer | Streaming, cinema, viagem |
| Financeiro | Parcelas, juros, tarifas |

---

## Estrutura do Repositório

```
financas-pessoais/
├── data/
│   ├── raw/                        # Extratos originais (anonimizados)
│   └── processed/                  # Dados categorizados
├── notebooks/
│   ├── 01_ingestao_extrato.ipynb   # Leitura e parsing do CSV
│   ├── 02_categorizacao.ipynb      # Classificação das transações
│   ├── 03_analise_mensal.ipynb     # Análise por período
│   └── 04_projecoes.ipynb          # Tendências e projeções
├── src/
│   ├── parser.py                   # Leitura de extratos
│   ├── categorizer.py              # Motor de categorização
│   └── reports.py                  # Geração de relatórios
├── dashboard/
│   └── financas.pbix               # Power BI
└── README.md
```

---

## Destaques Técnicos

- **Categorização por regras + NLP simples** — sem depender de categorização manual transação a transação
- **Dados anonimizados** — valores reais substituídos por dados sintéticos proporcionais para o repositório público
- **SQL para análises agregadas** — queries mensais, YoY, médias móveis

---

## Stack

`Python 3.11` `pandas` `NumPy` `matplotlib` `SQLite` `Power BI Desktop`

---

## Como Reproduzir

```bash
git clone https://github.com/davischub/financas-pessoais.git
cd financas-pessoais

pip install -r requirements.txt

# Execute os notebooks na ordem (01 → 02 → 03 → 04)
jupyter notebook notebooks/
```

Coloque seu extrato CSV em `data/raw/` antes de executar o notebook 01.
O formato esperado está documentado no notebook de ingestão.

---

## Autor

**Davi Schubert de Camargo**
[LinkedIn](https://linkedin.com/in/davi-schubert) · [davi.schubert@gmail.com](mailto:davi.schubert@gmail.com)
