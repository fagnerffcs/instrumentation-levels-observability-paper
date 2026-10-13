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
- **IC01:** Foco primário em observabilidade e técnicas de instrumentação para sistemas de software.
- **IC02:** Contexto relacionado a camadas da pilha computacional (hardware, kernel, runtime ou aplicação).
- **IC03:** Avaliação empírica ou quantificação de sobrecarga (*overhead* de CPU, latência, memória ou vazão).
- **IC04:** Proposta ou análise de ferramentas, *frameworks* ou arquiteturas de telemetria.
- **IC05:** Artigos publicados no recorte temporal de 2003 a 2025.
- **IC06:** Artigos redigidos nos idiomas inglês ou português.

### Critérios de Exclusão (EC):
- **EC01:** Artigos duplicados entre as bases científicas.
- **EC02:** Literatura cinzenta informal e comercial (*gray literature*, e.g., posts de blogs corporativos, fóruns técnicos, manuais comerciais de fornecedores e relatórios de marketing industrial).
- **EC03:** Foco exclusivo em monitoramento operacional genérico sem abordar conceitos ou *trade-offs* de instrumentação e observabilidade.
- **EC04:** Estudos onde a instrumentação é apenas mencionada tangencialmente ou utilizada como ferramenta utilitária secundária, não constituindo a contribuição principal.
- **EC05:** Trabalhos curtos, resumos expandidos e pôsteres com menos de 4 páginas sem detalhamento metodológico ou validação experimental consolidada.

## 5. Procedimento de Extração de Dados
Para cada estudo aprovado na leitura de texto completo, foram extraídos os seguintes campos:
- Nível de Instrumentação (Hardware, Kernel/SO, VM/Runtime, Aplicação/Bytecode, Adaptativo)
- Ferramenta / Arquitetura Proposta
- Granularidade e Métricas de Overhead (CPU, Latência, Memória)
- Capacidades Diagnósticas e Riqueza Semântica
- Casos de Uso e Contextos Aplicação