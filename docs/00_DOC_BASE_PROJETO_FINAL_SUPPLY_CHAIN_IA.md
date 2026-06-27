<!-- INICIO_ARQUIVO_FONTE_PROJETO -->

# 00 — Documento Base do Projeto Final: Supply Chain com IA

## 1. Decisão oficial do projeto

Este documento substitui o documento base anterior que orientava o uso dos backups CSV do consultório veterinário.

A partir desta versão, o projeto final seguirá exatamente o enunciado da professora:

> Recriar, fazendo alterações na base de dados, um dos projetos práticos da disciplina: previsão de demanda, otimização de entregas/rotas ou identificação de clusters e detecção de anomalia.

## 2. Decisão sobre o documento base anterior

O documento base anterior deve ser excluído da fonte ativa do projeto.

Motivo:

- ele estava orientado ao uso de dados reais do consultório;
- esse escopo foi cancelado;
- manter o arquivo antigo pode gerar confusão em consultas futuras;
- o novo projeto usará base sintética e seguirá o enunciado acadêmico.

Recomendação segura:

- excluir da fonte ativa do projeto;
- se quiser preservar histórico, salvar fora da fonte ativa, em uma pasta `archive/` ou backup local.

## 3. Projeto escolhido

### Tema

**Segmentação de clientes logísticos e detecção de anomalias operacionais em Supply Chain.**

### Linha do enunciado utilizada

**Identificação de Clusters e Detecção de Anomalia.**

### Justificativa

Essa opção é a mais aderente ao material da Aula 4, pois permite aplicar:

- análise exploratória;
- segmentação;
- K-Means;
- método do cotovelo;
- Silhouette Score;
- PCA para visualização;
- detecção de anomalias;
- interpretação gerencial.

## 4. Problema abordado

Uma empresa fictícia de distribuição atende clientes com diferentes perfis logísticos.

Nem todos os clientes possuem o mesmo volume, frequência, distância, custo, prazo e risco operacional.

Tratar todos da mesma forma pode gerar:

- aumento de custo logístico;
- baixa eficiência operacional;
- pior nível de serviço;
- clientes críticos sem monitoramento;
- dificuldade de priorização;
- decisões baseadas em percepção, não em dados.

## 5. Solução proposta

Criar uma base sintética limpa e pronta para análise, simulando clientes logísticos de uma cadeia de suprimentos.

Depois, aplicar técnicas de analytics para:

1. entender o perfil dos clientes;
2. identificar grupos naturais;
3. avaliar a qualidade dos clusters;
4. detectar clientes fora do padrão;
5. gerar insights e recomendações gerenciais.

## 6. Base de dados oficial

Arquivo principal:

```text
clientes_logisticos_sinteticos_supply_chain.csv
```

Características:

- 6.000 registros;
- 23 colunas;
- sem dados pessoais;
- sem necessidade de ETL pesado;
- pronta para EDA, clusterização e anomalias;
- contém grupos sintéticos para auditoria didática;
- contém anomalias intencionais para validação.

Importante:

- `cluster_teorico_sintetico` não deve ser usado como feature do K-Means;
- `anomalia_sintetica` e `tipo_anomalia_sintetica` não devem ser usados para treinar a detecção;
- essas colunas servem para conferência e interpretação posterior.

## 7. Entregável acadêmico

A entrega principal será um notebook Python no Google Colab.

O notebook deve conter:

1. título do projeto;
2. nomes dos integrantes;
3. problema abordado;
4. solução proposta;
5. base sintética utilizada;
6. análise exploratória;
7. preparação dos dados;
8. clusterização;
9. Elbow Method;
10. Silhouette Score;
11. visualização dos clusters;
12. detecção de anomalias;
13. interpretação dos resultados;
14. insights de negócio;
15. limitações;
16. próximos passos;
17. conclusão.

## 8. Estrutura recomendada do repositório

```text
supply-chain-clustering-anomaly-ai/
│
├── assets/
│   └── images/                         # Gráficos exportados do notebook
│
├── data/
│   └── synthetic/                      # Base sintética pública do projeto
│       └── clientes_logisticos_sinteticos_supply_chain.csv
│
├── docs/
│   ├── 00_DOC_BASE_PROJETO_FINAL_SUPPLY_CHAIN_IA.md
│   └── DICIONARIO_DADOS_CLIENTES_LOGISTICOS.md
│
├── notebooks/
│   └── supply_chain_clustering_anomaly_ai.ipynb
│
├── reports/
│   └── resumo_insights.md              # Opcional
│
├── .gitignore
├── LICENSE
├── README.md
└── requirements.txt
```

## 9. Boas práticas para o notebook

### Texto antes dos códigos

Cada bloco de código deve ser precedido por uma explicação curta.

Padrão obrigatório:

```text
Objetivo: explicar em 1 ou 2 frases o que será feito.
```

Evitar:

- textos longos antes do código;
- explicações repetidas;
- teoria excessiva;
- parágrafos sem objetivo prático.

### Comentários no código

Comentários devem ser:

- concisos;
- objetivos;
- sem ambiguidade;
- úteis para explicar intenção, não obviedades.

Exemplo bom:

```python
# Remove colunas de auditoria para evitar vazamento na clusterização.
```

Exemplo ruim:

```python
# Aqui estamos removendo algumas coisas que talvez não sejam úteis.
```

### Código Python

Regras:

- seguir PEP 8 sempre que possível;
- usar 4 espaços para indentação;
- usar nomes claros em `snake_case`;
- evitar células gigantes;
- evitar repetição de código;
- criar funções simples quando reduzir repetição;
- preferir código compacto, claro e eficaz;
- evitar comentários em excesso;
- usar imports concentrados no início;
- manter uma célula por etapa lógica.

### Tamanho das células

Cada célula deve ter um propósito claro.

Exemplos:

- célula para imports;
- célula para carregar dados;
- célula para visão geral;
- célula para gráficos de distribuição;
- célula para preparar features;
- célula para Elbow;
- célula para Silhouette;
- célula para K-Means final;
- célula para anomalias;
- célula para insights.

## 10. Boas práticas de visualização

O projeto deve usar visualizações claras e adequadas ao problema.

Bibliotecas principais:

| Biblioteca | Uso no projeto |
|---|---|
| Matplotlib | Base dos gráficos estáticos. |
| Seaborn | Distribuições, boxplots, heatmap e gráficos estatísticos. |
| Plotly | Gráficos interativos opcionais para exploração e apresentação. |
| Scikit-learn | PCA, K-Means, Silhouette e Isolation Forest. |

Gráficos recomendados:

1. distribuição das variáveis principais;
2. boxplots para custo, lead time e nível de serviço;
3. matriz de correlação;
4. gráfico do Elbow Method;
5. gráfico do Silhouette Score;
6. scatterplot PCA 2D dos clusters;
7. boxplots por cluster;
8. ranking de anomalias por risco operacional;
9. comparação entre clusters por médias padronizadas;
10. gráfico final de insights.

Regra de qualidade:

- todo gráfico deve ter título claro;
- eixos devem ser nomeados;
- evitar poluição visual;
- usar paleta consistente;
- explicar o insight abaixo do gráfico.

## 11. Bibliotecas do projeto

### Essenciais

```text
pandas
numpy
matplotlib
seaborn
scikit-learn
plotly
```

### Opcionais

```text
polars
scipy
```

### Não usar neste projeto inicial

```text
prophet
pulp
ortools
```

Motivo:

- Prophet é mais adequado para previsão de demanda;
- PuLP e OR-Tools são mais adequados para otimização;
- o projeto escolhido é clusterização e anomalias.

Essas bibliotecas podem ser citadas como possibilidades futuras, mas não devem aumentar a complexidade da entrega atual.

## 12. Pipeline analítico oficial

```text
Base sintética limpa
        │
        ▼
Análise exploratória
        │
        ▼
Seleção de features
        │
        ▼
Padronização com StandardScaler
        │
        ▼
Elbow Method
        │
        ▼
Silhouette Score
        │
        ▼
K-Means final
        │
        ▼
Interpretação dos clusters
        │
        ▼
Detecção de anomalias
        │
        ▼
Insights e recomendações
```

## 13. Features sugeridas para clusterização

Usar apenas variáveis numéricas operacionais:

```text
distancia_cd_km
volume_medio_entregue_kg
entregas_mes
ticket_medio_rs
receita_mensal_estimada_rs
lead_time_medio_dias
entregas_no_prazo_pct
custo_medio_entrega_rs
custo_logistico_mensal_rs
custo_por_kg_rs
taxa_ocorrencias_pct
variabilidade_demanda_pct
pedidos_urgentes_pct
risco_operacional_score
```

Não usar como feature:

```text
cliente_id
regiao
segmento_negocio
canal_relacionamento
porte_cliente
prioridade_contrato
anomalia_sintetica
tipo_anomalia_sintetica
cluster_teorico_sintetico
```

As variáveis categóricas podem ser usadas depois para interpretação dos clusters.

## 14. Técnica principal

### K-Means

Objetivo:

- agrupar clientes semelhantes;
- encontrar padrões naturais;
- transformar dados operacionais em segmentos gerenciais.

Validação:

- Elbow Method;
- Silhouette Score;
- interpretação de negócio.

### Detecção de anomalias

Abordagem recomendada:

1. começar com regras explicáveis por percentis;
2. depois aplicar Isolation Forest como complemento;
3. comparar os resultados com `anomalia_sintetica` apenas ao final.

## 15. Interpretação esperada dos clusters

A interpretação deve transformar número de cluster em linguagem de negócio.

Exemplo:

| Cluster | Nome gerencial | Interpretação | Ação sugerida |
|---|---|---|---|
| 0 | Clientes estratégicos | Alto volume, alta receita e bom nível de serviço. | Manter prioridade e SLA. |
| 1 | Clientes padrão | Frequência média e custo controlado. | Automatizar rotina. |
| 2 | Clientes de alto custo | Longa distância e custo elevado. | Rever política logística. |
| 3 | Clientes instáveis | Baixo volume e alta variabilidade. | Monitorar demanda e consolidar pedidos. |
| 4 | Clientes críticos | Alto risco, atrasos e ocorrências. | Investigar gargalos e plano de ação. |

## 16. Limitações que devem aparecer no trabalho

O projeto deve declarar limitações com clareza:

- a base é sintética;
- os resultados não representam uma empresa real;
- os clusters dependem das variáveis escolhidas;
- K-Means exige escolha prévia de K;
- variáveis com escala diferente precisam de padronização;
- anomalia nem sempre significa erro ou problema;
- a análise apoia decisão, mas não substitui avaliação gerencial.

## 17. Uso de IA Generativa

O projeto deve declarar que foi desenvolvido com apoio de IA generativa.

Texto sugerido:

```text
Este projeto acadêmico foi desenvolvido com apoio de Inteligência Artificial Generativa para estruturação, revisão, organização do código, documentação e apoio à interpretação dos resultados. Todas as decisões finais, validações, ajustes e conclusões foram revisadas pelo autor.
```

## 18. GitHub — padrão ouro

O repositório deve ser profissional, mesmo sendo acadêmico.

Obrigatório:

- nome claro do repositório;
- README completo;
- estrutura organizada;
- `.gitignore` adequado;
- `requirements.txt`;
- notebook em `notebooks/`;
- base sintética em `data/synthetic/`;
- imagens em `assets/images/`;
- declaração de uso de IA;
- licença, se o repositório for público.

Nome sugerido do repositório:

```text
supply-chain-clustering-anomaly-ai
```

## 19. Commits por etapa concluída

Regra:

> Uma etapa concluída = um commit claro.

Padrão de commits:

```text
tipo: descrição curta no infinitivo ou presente
```

Exemplos:

```text
chore: criar estrutura inicial do projeto
docs: adicionar documento base do projeto
data: adicionar base sintética de clientes logísticos
feat: implementar análise exploratória inicial
feat: aplicar clusterização com k-means
feat: adicionar validação com elbow e silhouette
feat: implementar detecção de anomalias
docs: adicionar interpretação dos resultados
docs: finalizar readme do projeto
```

Antes de cada commit, validar:

- notebook executa sem erro;
- arquivos estão nas pastas corretas;
- README está coerente;
- não há arquivos temporários;
- não há dados sensíveis;
- imagens e tabelas principais foram salvas, se necessário.

## 20. Micro passo a passo obrigatório para GitHub

A parte de GitHub deve ser conduzida em microetapas.

Fluxo:

1. criar repositório;
2. criar estrutura de pastas;
3. adicionar `.gitignore`;
4. adicionar base sintética;
5. adicionar notebook inicial;
6. criar README inicial;
7. fazer primeiro commit;
8. desenvolver etapa por etapa;
9. revisar README final;
10. publicar versão final.

Cada etapa deve ter:

- objetivo;
- comando ou ação;
- verificação;
- commit sugerido.

## 21. Modelo de README desejado

O README deve seguir o padrão profissional do exemplo fornecido pelo usuário.

Seções obrigatórias:

1. título com emoji e descrição clara;
2. badges;
3. botão para abrir no Google Colab;
4. resumo executivo;
5. sumário;
6. sobre o projeto;
7. problema de negócio;
8. solução analítica;
9. pipeline;
10. principais resultados;
11. visualizações;
12. insights e recomendações;
13. estrutura do repositório;
14. tecnologias utilizadas;
15. como executar;
16. dataset;
17. declaração de uso de IA;
18. autor;
19. licença.

## 22. Ordem recomendada de desenvolvimento

1. preparar estrutura do projeto;
2. salvar base sintética;
3. iniciar notebook;
4. carregar dados;
5. fazer varredura inicial;
6. EDA;
7. selecionar features;
8. padronizar dados;
9. Elbow Method;
10. Silhouette Score;
11. K-Means final;
12. PCA e gráficos;
13. perfil dos clusters;
14. anomalias por regra;
15. Isolation Forest;
16. comparação das anomalias;
17. insights finais;
18. limitações;
19. conclusão;
20. README;
21. revisão final;
22. commit final.

## 23. Critérios de aceite

O projeto só estará pronto quando cumprir todos os pontos:

- responde ao enunciado;
- usa uma prática da disciplina;
- muda a base de dados;
- possui problema abordado;
- apresenta solução;
- interpreta resultados;
- contém insights claros;
- notebook roda do início ao fim;
- README está profissional;
- GitHub está organizado;
- uso de IA está declarado.

## 24. Referências de boas práticas

- PEP 8 — Style Guide for Python Code: https://peps.python.org/pep-0008/
- Zen de Python: https://pt.wikipedia.org/wiki/Zen_de_Python
- Padrões de commits: https://github.com/iuricode/padroes-de-commits
- Guia de boas práticas para Git: https://github.com/sampaiodias/git-boas-praticas
- Referência de notebook/Colab: https://colab.research.google.com/github/Rogerio-mack/Visualizacao-de-Dados-em-Python/blob/main/c0_parte_1.ipynb

<!-- FIM_ARQUIVO_FONTE_PROJETO -->
