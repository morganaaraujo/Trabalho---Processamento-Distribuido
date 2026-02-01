# Currency Streaming com Kafka e Spark

Pipeline de dados em streaming usando Kafka e Spark Structured Streaming para coletar cotações de moedas, publicar eventos e persistir os dados em formato Parquet.

---

## Informações Acadêmicas

**Disciplina:** Processamento Distribuído

**Estudantes:**

* Morgana Araújo dos Santos
* Vicente de Paula Ferreira Filho
* Vitor Brava Estevam

---

## O que é este projeto?

Este projeto:

* Coleta cotações de moedas (USD, EUR, GBP, JPY vs BRL) via Yahoo Finance
* Publica cada cotação como evento JSON no Kafka
* Consome os eventos com Spark Structured Streaming
* Persiste os dados processados em arquivos Parquet

---

## Requisitos do Sistema

Necessário Linux ou WSL2 (Windows).

Motivos:

* Kafka e Spark possuem melhor compatibilidade com ambientes Unix-like
* Docker apresenta maior estabilidade nesses ambientes

### Requisitos mínimos:

* Linux (Ubuntu, Debian, etc) ou WSL2
* Docker
* Docker Compose
* Python 3.9 ou superior
* Java 11 ou 17 (obrigatório para Spark)

---

## Tecnologias Utilizadas

* Docker e Docker Compose
* Apache Kafka
* Apache Zookeeper
* Apache Spark 3.5 (PySpark)
* Yahoo Finance (yfinance)
* Parquet

---

## Como Executar

### 1. Subir Kafka e Zookeeper

No diretório do projeto, execute:

```bash
docker compose up -d
```

Verifique se os containers estão ativos:

```bash
docker ps
```

---

### 2. Criar ambiente Python (opcional, recomendado)

```bash
python -m venv venv
source venv/bin/activate
```

---

### 3. Executar o Notebook

Inicie o Jupyter:

```bash
jupyter notebook
```

Abra o arquivo `notebook.ipynb` e execute as células na ordem em que aparecem.

---

## Saída Gerada

Os dados processados serão salvos em:

```
data/parquet/currency/
```

Os checkpoints do Spark ficarão em:

```
data/checkpoints/currency/
```

---
