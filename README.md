# IA Educa

Projeto de análise e visualização de desafios docentes usando um pipeline de dados em Python e um dashboard interativo exportado em HTML.

## Visão Geral

O projeto **IA Educa** transforma dados de pesquisa de docentes em um fluxo estruturado de analítica, seguindo a arquitetura de ingestão Bronze → Silver → Gold.

O objetivo é identificar, modelar e priorizar as dores dos professores com métricas como frequência, impacto, criticidade, taxa de dor aguda e potencial de automação.

## O que está incluído

- `\[final\]_IAEduca_Pipeline.ipynb`: notebook principal contendo o pipeline completo.
- `dashboard_final_v2.html`: dashboard final exportado em HTML.
- `df_consolidado.csv`: base de dados consolidada para análise.
- `text.md`: guia de interpretação das visualizações e métricas.

## Arquitetura do pipeline

O notebook segue três camadas principais:

1. **Camada Bronze: Ingestão de Dados**
   - Leitura de dados do Google Sheets via URL CSV.
   - Importação inicial dos dados brutos.

2. **Camada Silver: Limpeza e Transformação**
   - Renomeação de colunas e tratamento de valores ausentes.
   - Explosão de campos com múltiplos valores.
   - Unpivot e extração de metadados de perguntas de frequência e impacto.
   - Cálculo de score de criticidade usando média geométrica.
   - Classificação de desafios por potencial de automação.

3. **Camada Gold: Modelagem Dimensional**
   - Criação de tabelas de dimensão e fato (`dim_docente`, `dim_desafio`, `fact_avaliacao`).
   - Estruturação do modelo em estilo star schema.

## Principais métricas e visualizações

O dashboard e o notebook geram insights chave para as decisões pedagógicas:

- **Matriz de Decisão (Frequência × Impacto)**
- **Ranking de Criticidade**
- **Taxa de Dor Aguda (TDA)**
- **Índice de Potencial de Automação (IPA)**
- Análises por perfil de docentes, nível de IA, modalidade e área de atuação
- Análise geográfica de participação e intensidade de dores

## Como usar

### Pré-requisitos

- Python 3.10+ recomendado
- Biblioteca `kaleido` (utilizada para exportar gráficos Plotly como imagens)
- Bibliotecas padrão: `pandas`, `numpy`, `re`, `requests`, `plotly`

### Executando o notebook

1. Abra o notebook `\[final\]_IAEduca_Pipeline.ipynb` no Jupyter ou VS Code.
2. Execute as células na ordem, da configuração até a exportação do dashboard.
3. Ao final, o dashboard HTML é gerado como `dashboard_final_v2.html`.

### Executando localmente via terminal

Se desejar rodar o notebook como script, converta-o para Python ou execute com ferramentas como `jupyter nbconvert` / `papermill`.

## Estrutura de arquivos

- `\[final\]_IAEduca_Pipeline.ipynb`: pipeline de dados e criação de dashboard.
- `dashboard_final_v2.html`: visualização final interativa pronta para apresentação.
- `df_consolidado.csv`: arquivo de dados para análise e possíveis experimentos locais.
- `text.md`: documentação complementar com explicações detalhadas das métricas.

## Melhores práticas aplicadas

- Pipeline em camadas para separar responsabilidades de ingestão, transformação e modelagem.
- Tratamento de dados faltantes e padronização de categorias.
- Uso de modelagem dimensional para análises fáceis e escaláveis.
- Exportação de dashboard em HTML para compartilhamento sem dependências adicionais.
- Documentação clara do processo e das métricas utilizadas.

## Futuras melhorias

- adicionar testes automatizados para validação de dados e resultados;
- incluir um script de extração automática a partir de múltiplas fontes;
- adicionar validação de esquema e monitoramento de qualidade de dados;
- gerar versões do dashboard com filtros dinâmicos mais avançados.

## Licença

Este repositório não especifica uma licença. Se desejar, adicione um arquivo `LICENSE` com a licença apropriada para seu uso.
