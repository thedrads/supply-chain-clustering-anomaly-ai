# Dicionário de Dados — clientes_logisticos_sinteticos_supply_chain.csv

Base sintética, limpa e pronta para análise acadêmica de clusterização e detecção de anomalias em Supply Chain.

| Coluna | Tipo | Descrição | Uso analítico |
|---|---|---|---|
| `cliente_id` | texto | Identificador fictício único do cliente. | Chave de referência. |
| `regiao` | categoria | Região logística do cliente. | Segmentação geográfica. |
| `segmento_negocio` | categoria | Segmento de atuação do cliente. | Análise de perfil. |
| `canal_relacionamento` | categoria | Canal comercial/operacional. | Análise de relacionamento. |
| `porte_cliente` | categoria | Porte comercial do cliente. | Segmentação de potencial. |
| `distancia_cd_km` | numérico | Distância estimada entre o Centro de Distribuição e o cliente. | Custo e complexidade logística. |
| `volume_medio_entregue_kg` | numérico | Volume médio entregue por operação. | Intensidade operacional. |
| `entregas_mes` | inteiro | Quantidade média mensal de entregas. | Frequência/recorrência. |
| `ticket_medio_rs` | numérico | Valor médio por entrega. | Valor econômico. |
| `receita_mensal_estimada_rs` | numérico | Receita estimada mensal do cliente. | Atratividade econômica. |
| `lead_time_medio_dias` | numérico | Tempo médio entre pedido e entrega. | Eficiência operacional. |
| `entregas_no_prazo_pct` | numérico | Percentual de entregas dentro do prazo. | Nível de serviço. |
| `custo_medio_entrega_rs` | numérico | Custo médio por entrega. | Eficiência de custo. |
| `custo_logistico_mensal_rs` | numérico | Custo logístico mensal estimado. | Impacto financeiro. |
| `custo_por_kg_rs` | numérico | Custo médio por kg entregue. | Eficiência unitária. |
| `taxa_ocorrencias_pct` | numérico | Percentual estimado de entregas com ocorrência. | Risco operacional. |
| `variabilidade_demanda_pct` | numérico | Oscilação estimada da demanda. | Instabilidade de consumo. |
| `pedidos_urgentes_pct` | numérico | Percentual de pedidos urgentes. | Pressão operacional. |
| `prioridade_contrato` | categoria | Prioridade contratual fictícia. | Contexto de SLA. |
| `risco_operacional_score` | numérico | Score sintético de risco operacional de 0 a 100. | Detecção de clientes críticos. |
| `anomalia_sintetica` | binário | 1 indica anomalia intencional inserida na base. | Validação de detecção. |
| `tipo_anomalia_sintetica` | categoria | Tipo de anomalia inserida. | Interpretação e validação. |
| `cluster_teorico_sintetico` | categoria | Grupo sintético usado na geração dos dados. | Comparação didática; não deve ser usado como feature no K-Means. |

## Observações

- A base não contém dados reais nem dados pessoais.
- A coluna `cluster_teorico_sintetico` existe apenas para auditoria didática.
- Na modelagem, remova `cliente_id`, `anomalia_sintetica`, `tipo_anomalia_sintetica` e `cluster_teorico_sintetico` das features de clusterização.
- A base foi desenhada para permitir EDA, K-Means, Elbow, Silhouette, PCA e detecção de anomalias.
