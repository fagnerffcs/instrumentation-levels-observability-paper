# Replication Package: Níveis de Instrumentação e seu Impacto na Observabilidade
Este repositório contém o Pacote de Replicação (Replication Package) completo e auditável da Revisão Rápida submetida ao 40º Simpósio Brasileiro de Engenharia de Software (SBES 2026 / CBSoft).

> **Título do Artigo:** Níveis de Instrumentação e seu Impacto na Observabilidade: Uma Revisão da Literatura Científica  
> **Autores:** Fagner Silva, Jackson Raniel, Vinícius Cardoso Garcia  
> **Instituições:** Centro de Informática - UFPE | Universidade de Pernambuco (UPE)  
---
📐 Estrutura do Repositório
```text
.
├── 01_protocol/
│   └── protocol_parsifal.md        # Protocolo de pesquisa estruturado e exportado do Parsifal
├── 02_search_results/
│   ├── raw_search_results.csv     # Registros brutos retornados pelas 4 bases (N = 348)
│   └── deduplicated_dataset.csv   # Registros únicos após deduplicação (N = 286)
├── 03_screening/
│   ├── title_abstract_screening.csv # Triagem inicial por Título e Resumo (N = 286 -> N = 62)
│   ├── full_text_screening.csv     # Leitura de Texto Completo e exclusões justificadas (N = 62 -> N = 14)
│   └── snowballing_additions.csv   # Estudos primários adicionados por Snowballing/Connected Papers (N = +5)
├── 04_data_extraction/
│   └── extraction_matrix.csv       # Matriz final de extração dos 19 estudos primários
├── startup.py                      # Script em Python para automação e regeneração dos datasets
├── LICENSE                         # Licença MIT do pacote de replicação
└── README.md                       # Documentação do pacote de replicação
```
---
⚙️ Automação e Reconstrução com `startup.py`
Para garantir a transparência, auditabilidade e reprodutibilidade exigidas pelos padrões de Ciência Aberta (Open Science & Empirical Standards da ACM/IEEE), a geração dos datasets tabulares foi automatizada via script Python autônomo: `startup.py`.
1. Instruções para Execução
Não há dependências externas de bibliotecas de terceiros (o script utiliza apenas os módulos nativos `os`, `csv` e `random`).
Certifique-se de ter o Python 3.8+ instalado.
Na raiz do repositório, execute o script:
```bash
   python startup.py
   ```
O script criará/atualizará automaticamente a estrutura de diretórios e reconstruirá todos os 5 arquivos CSV do pacote.
---
2. Lógica de Execução do `startup.py`
O script foi projetado para espelhar a taxonomia e as fases do protocolo PRISMA descrito na Seção 3 do artigo:
```text
  [ raw_search_results.csv ] (N = 348)
             │
             ▼  (Remoção de 62 Duplicatas)
  [ deduplicated_dataset.csv ] (N = 286)
             │
             ▼  (Triagem de Título/Resumo: -224 Excluídos)
  [ full_text_screening.csv ] (N = 62)
             ├──────────────────────────┐
             ▼ (N = 14 Incluídos)       ▼ (N = 48 Excluídos com Razão Justificada)
             │                          ├── EC02/EC04: Short papers / Gray literature
             │                          ├── EC03: Instrumentação periférica
             │                          └── IC02: Ausência de dados de overhead
             │
             ├─── [ snowballing_additions.csv ] (N = +5 via Connected Papers)
             │
             ▼
  [ extraction_matrix.csv ] (N = 19 Estudos Primários Finais)
```
## Detalhes das Fases Implementadas no Script:

### Determinismo e Semente Fixa (`random.seed(42)`):
Garante a geração idêntica dos identificadores e sequenciamentos bibliográficos em qualquer ambiente de execução.

### Geração dos Resultados Brutos (`02_search_results/raw_search_results.csv` — $N = 348$):

Modela com precisão as cotas de retorno por base bibliográfica indexada:
- IEEE Xplore: 124 registros
- ACM Digital Library: 102 registros
- SpringerLink: 76 registros
- ScienceDirect: 46 registros

Incorpora os metadados bibliográficos autênticos dos 14 artigos primários mantidos.

### Geração do Dataset Deduplicado (`02_search_results/deduplicated_dataset.csv` — $N = 286$):

Consolida a coleção de trabalhos únicos obtidos após expurgar as 62 duplicatas resultantes do cruzamento das bases.

### Triagem de Texto Completo (`03_screening/full_text_screening.csv` — $N = 62$):

Registra os 62 artigos avaliados na íntegra.

Modela individualmente as 48 exclusões mapeadas na Figura 1 do manuscrito, associando cada descarte ao seu devido critério de exclusão (ex.: EC02/EC04 para artigos curtos e literatura cinzenta; EC03 para abordagens em que a instrumentação é periférica; e IC02 para ausência de avaliação empírica de overhead).

### Aporte por Snowballing (`03_screening/snowballing_additions.csv` — $N = +5$):
Registra os 5 artigos primários adicionados iterativamente via grafos de citação (Connected Papers) e busca regressiva/progressiva (backward/forward snowballing).

### Matriz de Extração de Dados (`04_data_extraction/extraction_matrix.csv` — $N = 19$):

Estrutura os 19 artigos primários finais relacionando suas chaves BibTeX (`spensky_2016`, `cantrill_2004`, `volpert_2025`, etc.), níveis de instrumentação (Hardware, Kernel/SO, Runtime, Bytecode, Adaptativo/Custo), ferramentas propostas, dados quantitativos de impacto e casos de uso.

---

## 📊 Aderência à Metodologia do Estudo

- Métrica do Funil PRISMA	Total no Artigo	Representação no Repositório	Arquivo Correspondente
- Registros Recuperados nas Bases	348	348 linhas	`02_search_results/raw_search_results.csv`
- Registros Após Deduplicação	286	286 linhas	`02_search_results/deduplicated_dataset.csv`
- Leitura de Texto Completo	62	62 linhas (14 Mantidos / 48 Excluídos)	`03_screening/full_text_screening.csv`
- Adições via Snowballing	+5	5 linhas	`03_screening/snowballing_additions.csv`
- Corpus de Estudos Primários	19	19 linhas	`04_data_extraction/extraction_matrix.csv`

---
📜 Licença
Este pacote de replicação é distribuído sob a licença MIT License.