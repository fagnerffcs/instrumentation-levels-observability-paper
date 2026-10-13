# Protocolo de Revisão Rápida — Parsifal Export

**Título:** Níveis de Instrumentação e seu Impacto na Observabilidade: Uma Revisão da Literatura Científica
**Autores:** Fagner Silva, Jackson Raniel, Vinícius Cardoso Garcia
**Data de Registro:** 15 de Janeiro de 2026
**Ferramenta de Gestão:** Parsifal (parsifal.co)

---

## 1. Objetivos do Estudo
Mapear e analisar o panorama atual das abordagens e níveis de instrumentação de sistemas computacionais, avaliando suas capacidades diagnósticas e os compromissos (*trade-offs*) em relação ao *overhead* de desempenho e consumo de recursos.

## 2. Questões de Pesquisa (Research Questions - RQs)
- **RQ01:** Quais níveis de instrumentação existem e quais características de observabilidade cada um fornece?
- **RQ02:** Como diferentes abordagens de instrumentação impactam o desempenho do sistema e a utilização de recursos?
- **RQ03:** Quais estratégias e melhores práticas permitem uma observabilidade eficaz minimizando a sobrecarga de desempenho?

## 3. Estratégia de Busca
### String Principal:
`("observability" OR "monitoring") AND ("instrumentation" OR "profiling" OR "tracing") AND ("performance impact" OR "overhead" OR "resource utilization")`

### Bases de Dados Consultadas:
1. IEEE Xplore
2. ACM Digital Library
3. SpringerLink
4. ScienceDirect

### Recorte Temporal:
2003 – 2025

## 4. Critérios de Elegibilidade

### Critérios de Inclusão (IC):
- **IC01:** Foco primário na avaliação ou proposta de níveis de instrumentação (hardware, kernel, runtime, bytecode ou aplicação) para observabilidade.
- **IC02:** Estudos que apresentam análises quantitativas ou qualitativas do overhead e do impacto no desempenho sistêmico.
- **IC03:** Artigos publicados entre 2003 e 2025.
- **IC04:** Artigos escritos na língua inglesa.

### Critérios de Exclusão (EC):
- **EC01:** Estudos duplicados entre as bases.
- **EC02:** Literatura cinzenta (*gray literature*), como posts de blogs, manuais comerciais, pre-prints sem revisão por pares e whitepapers.
- **EC03:** Estudos onde a instrumentação é mencionada apenas como ferramenta periférica, sem compor o objeto de estudo principal.
- **EC04:** Resumos expandidos, pôsteres e trabalhos curtos (*short papers*) com menos de 4 páginas.

## 5. Procedimento de Extração de Dados
Para cada estudo aprovado na leitura de texto completo, foram extraídos os seguintes campos:
- Nível de Instrumentação (Hardware, Kernel/SO, VM/Runtime, Aplicação/Bytecode, Adaptativo)
- Ferramenta / Arquitetura Proposta
- Granularidade e Métricas de Overhead (CPU, Latência, Memória)
- Capacidades Diagnósticas e Riqueza Semântica
- Casos de Uso e Contextos Aplicação