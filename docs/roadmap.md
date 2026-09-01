# Roadmap

## Fase 0 — Operação assistida

Usar ferramentas existentes antes de construir infraestrutura própria.

- ChatGPT;
- Claude / Claude Code;
- Trello;
- Gmail;
- Calendar;
- GitHub;
- Figma;
- Drive.

Objetivo: observar processos reais e identificar o que merece automação.

## Fase 1 — Contratos de domínio e Skills

- consolidar schema de Opportunity;
- criar `opportunity-qualification`;
- criar `commercial-followup`;
- criar `client-request-triage`;
- criar `project-handoff`;
- definir políticas de aprovação humana.

## Fase 2 — Primeiro MCP

Criar MCP mínimo hospedável em Cloudflare Workers.

Primeiras capacidades sugeridas:

```text
list_sales_items()
get_sales_item()
create_sales_item()
update_sales_item()
```

Inicialmente poderá adaptar diretamente o Trello.

## Fase 3 — Radar de demanda

Primeira vertical comercial completa:

```text
Fonte de demanda
→ normalização
→ Opportunity
→ qualificação
→ score
→ Trello
→ aprovação
→ abordagem
→ follow-up
```

Prioridade inicial: Upwork, seguida de Workana e 99Freelas conforme viabilidade de integração.

## Fase 4 — Prospecção ativa

- Google Places;
- análise de presença digital;
- diagnóstico;
- score;
- oferta inicial padronizada;
- abordagem com aprovação.

## Fase 5 — Comunicação

- Gmail;
- WhatsApp Business;
- Calendar;
- histórico unificado de Interaction;
- inbox operacional.

## Fase 6 — Handoff comercial → execução

Conectar:

- contratos;
- projetos;
- Trello Operação;
- GitHub;
- Figma;
- documentação/specs.

## Fase 7 — Core persistente

Introduzir Postgres/Supabase como fonte estrutural de verdade.

- workspace/tenant;
- opportunities;
- companies;
- contacts;
- interactions;
- projects;
- work items;
- events;
- integrations.

## Fase 8 — MCPs por domínio

- commercial;
- operations;
- projects;
- knowledge.

## Fase 9 — CMD+ Today

Criar uma visão consolidada da empresa:

- oportunidades;
- follow-ups;
- mensagens;
- reuniões;
- projetos;
- riscos;
- PRs;
- decisões pendentes.

## Fase 10 — Productização

Quando a operação interna estiver provada:

- multi-tenant real;
- onboarding de organizações;
- configuração de integrações;
- políticas por workspace;
- catálogo de Skills;
- dashboards;
- planos e billing;
- segurança e auditoria;
- templates por tipo de empresa;
- white label quando fizer sentido.

## Regra de implementação

> Não implementar a fase seguinte apenas porque ela existe no roadmap. Implementar quando o fluxo anterior estiver funcionando e revelar uma necessidade concreta.
