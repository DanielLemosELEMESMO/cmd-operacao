# Arquitetura inicial

## Objetivo

Estruturar o CMD+ OS como uma camada operacional independente de fornecedor de IA e preparada para evoluir de ferramenta interna para produto multiempresa.

## Arquitetura conceitual

```text
                 Humanos
                    ↕
          ChatGPT / Claude / agentes
                    ↓
             Skills / Playbooks
                    ↓
               MCP Gateway
                    ↓
              Domain Services
        ┌───────────┼───────────┐
        │           │           │
   Commercial     Client      Projects
        │           │           │
        └───────────┼───────────┘
                    ↓
                 Core
                    ↓
          Store + Event Log
                    ↓
  Trello / Gmail / WhatsApp / Calendar
      GitHub / Figma / Web / Marketplaces
```

## Decisões iniciais

### 1. Domínio acima de ferramenta

Preferir operações como:

```text
create_followup()
register_interaction()
move_opportunity()
create_project_handoff()
```

em vez de expor diretamente:

```text
create_trello_card()
send_gmail_message()
```

As integrações concretas ficam atrás dos serviços de domínio.

### 2. Separação entre processo e capacidade

- **Skill/playbook:** descreve como executar uma atividade.
- **MCP/API:** fornece ações e acesso a dados.

### 3. Trello como cockpit inicial

A CMD+ já possui boards de Funil de Vendas, Operação e Produtos. Eles podem ser usados como interface inicial sem exigir UI própria.

A longo prazo:

```text
CMD+ Core / Postgres = fonte estrutural de verdade
Trello = projeção visual / cliente operacional
```

### 4. Cloudflare para MCPs leves

Workers podem hospedar servidores MCP pequenos, stateless e baratos. O primeiro MCP deve ser mínimo e validar a comunicação entre agentes e operação real antes de ampliar o escopo.

### 5. Productização desde o início

Evitar entidades e regras codificadas exclusivamente para CMD+ quando uma abstração de workspace/tenant resolver o mesmo problema.

Por exemplo:

```text
Workspace
Organization
User
IntegrationConnection
Opportunity
Company
Contact
Interaction
WorkItem
Project
Decision
Event
```

Configurações específicas da CMD+ devem ficar como dados, templates ou políticas do workspace.

## Níveis de autonomia

### Leitura
Pode ser altamente automatizada.

### Organização
Pode ter autonomia ampla com auditoria.

### Comunicação e compromissos
Por padrão exige aprovação humana para:

- primeira abordagem;
- orçamento;
- preço;
- prazo;
- contrato;
- negociação;
- comunicação sensível.

## Event-driven

Eventos desejáveis:

```text
opportunity.created
opportunity.qualified
opportunity.contacted
interaction.received
meeting.completed
proposal.sent
contract.signed
project.created
work_item.created
pull_request.opened
pull_request.merged
release.deployed
client.approved
```

Esses eventos futuramente poderão disparar automações e agentes.
