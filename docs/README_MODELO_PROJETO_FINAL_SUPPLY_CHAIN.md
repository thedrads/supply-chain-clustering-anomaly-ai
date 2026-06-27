# 🚚 Supply Chain AI — Segmentação de Clientes e Detecção de Anomalias

### 🎓 Projeto Final | MBA em IA e Análise de Dados Aplicadas a Negócios — SENAC

---

[![Abrir no Google Colab](https://colab.research.google.com/assets/colab-badge.svg)](COLE_AQUI_O_LINK_DO_COLAB)

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-2.0+-150458?style=for-the-badge&logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.3+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Plotly](https://img.shields.io/badge/Plotly-Visualização-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)](https://plotly.com/python/)
[![Status](https://img.shields.io/badge/Status-Em%20desenvolvimento-yellow?style=for-the-badge)]()

> Projeto acadêmico de IA aplicada a Supply Chain para segmentar clientes logísticos e identificar anomalias operacionais usando análise exploratória, K-Means, Elbow Method, Silhouette Score, PCA e detecção de outliers.

---

## 📑 Sumário

- [Sobre o Projeto](#-sobre-o-projeto)
- [Problema de Negócio](#-problema-de-negócio)
- [Solução Analítica](#-solução-analítica)
- [Pipeline](#-pipeline)
- [Dataset](#-dataset)
- [Principais Resultados](#-principais-resultados)
- [Visualizações](#-visualizações)
- [Insights e Recomendações](#-insights-e-recomendações)
- [Estrutura do Repositório](#-estrutura-do-repositório)
- [Tecnologias Utilizadas](#-tecnologias-utilizadas)
- [Como Executar](#-como-executar)
- [Declaração de Uso de IA](#-declaração-de-uso-de-ia)
- [Autor](#-autor)
- [Licença](#-licença)

---

## 🎯 Sobre o Projeto

Este projeto foi desenvolvido como entrega final da disciplina **Supply Chain & Logística Inteligente com IA**.

A proposta foi recriar uma das práticas da disciplina, alterando a base de dados e aplicando técnicas de análise de dados e machine learning para apoiar decisões logísticas.

A linha escolhida foi:

> **Identificação de Clusters e Detecção de Anomalia.**

---

## 💼 Problema de Negócio

Uma empresa fictícia de distribuição atende clientes com perfis operacionais distintos.

Alguns clientes possuem alto volume, boa recorrência e baixo risco. Outros apresentam alto custo, longas distâncias, atrasos, baixa pontualidade ou comportamento fora do padrão.

O problema é:

> Como segmentar clientes logísticos e identificar operações anômalas para apoiar decisões de custo, nível de serviço e priorização?

---

## 🧠 Solução Analítica

A solução aplica um pipeline de analytics com:

1. análise exploratória dos dados;
2. seleção de variáveis operacionais;
3. padronização das features;
4. definição de grupos com Elbow Method e Silhouette Score;
5. clusterização com K-Means;
6. visualização com PCA;
7. detecção de anomalias;
8. interpretação dos resultados e recomendações.

---

## 🔬 Pipeline

```text
Base sintética
      │
      ▼
EDA
      │
      ▼
Preparação das features
      │
      ▼
StandardScaler
      │
      ▼
Elbow + Silhouette
      │
      ▼
K-Means
      │
      ▼
PCA e visualizações
      │
      ▼
Anomalias
      │
      ▼
Insights de negócio
```

---

## 📋 Dataset

| Informação | Detalhe |
|---|---|
| Origem | Base sintética criada para o projeto |
| Arquivo | `clientes_logisticos_sinteticos_supply_chain.csv` |
| Registros | 6.000 |
| Colunas | 23 |
| Dados pessoais | Não possui |
| Uso | EDA, clusterização e anomalias |

---

## 📈 Principais Resultados

> Preencher após a execução final do notebook.

| Resultado | Valor |
|---|---:|
| Número final de clusters | A definir |
| Silhouette Score | A definir |
| Clientes anômalos identificados | A definir |
| Cluster mais crítico | A definir |
| Cluster mais estratégico | A definir |

---

## 📊 Visualizações

> Inserir os gráficos exportados em `assets/images/`.

Exemplos:

```markdown
<p align="center">
  <img src="assets/images/pca_clusters.png" alt="Clusters visualizados com PCA" width="700">
</p>
```

---

## 💡 Insights e Recomendações

> Preencher após a análise final.

Exemplos esperados:

1. clientes estratégicos devem receber SLA prioritário;
2. clientes de alto custo devem ter política logística revisada;
3. clientes instáveis podem se beneficiar de consolidação de pedidos;
4. anomalias críticas devem ser investigadas operacionalmente;
5. o monitoramento contínuo reduz risco de decisões reativas.

---

## 📁 Estrutura do Repositório

```text
supply-chain-clustering-anomaly-ai/
│
├── assets/
│   └── images/
├── data/
│   └── synthetic/
├── docs/
├── notebooks/
├── reports/
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

---

## 🧰 Tecnologias Utilizadas

| Categoria | Tecnologia | Uso |
|---|---|---|
| Linguagem | Python | Desenvolvimento analítico |
| Dados | Pandas | Manipulação e análise |
| Dados | NumPy | Operações numéricas |
| Visualização | Matplotlib | Gráficos estáticos |
| Visualização | Seaborn | Visualizações estatísticas |
| Visualização | Plotly | Gráficos interativos |
| Machine Learning | Scikit-learn | K-Means, PCA, métricas e anomalias |
| Ambiente | Google Colab | Execução do notebook |
| Versionamento | Git/GitHub | Controle de versão |

---

## 🚀 Como Executar

### Google Colab

1. Clique no botão **Abrir no Google Colab**.
2. Faça upload ou carregue o arquivo `clientes_logisticos_sinteticos_supply_chain.csv`.
3. Execute as células em sequência.

### Local

```bash
git clone https://github.com/thedrads/supply-chain-clustering-anomaly-ai.git
cd supply-chain-clustering-anomaly-ai
pip install -r requirements.txt
jupyter notebook notebooks/supply_chain_clustering_anomaly_ai.ipynb
```

---

## 🤖 Declaração de Uso de IA

Este projeto acadêmico foi desenvolvido com apoio de Inteligência Artificial Generativa para estruturação, revisão, organização do código, documentação e apoio à interpretação dos resultados.

Todas as decisões finais, validações, ajustes e conclusões foram revisadas pelo autor.

---

## 👤 Autor

<table>
  <tr>
    <td align="center">
      <a href="https://github.com/thedrads">
        <img src="https://github.com/thedrads.png" width="100px;" alt="Fábio Andrade"/><br>
        <sub><b>Fábio Andrade</b></sub>
      </a>
    </td>
  </tr>
</table>

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/thedrads)

---

## 📄 Licença

Este projeto pode ser disponibilizado sob licença MIT, se o repositório for público.
