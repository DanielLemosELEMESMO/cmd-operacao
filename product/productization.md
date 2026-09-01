# Productização

O CMD+ OS será validado primeiro dentro da própria CMD+ e, quando os fluxos estiverem provados, poderá ser empacotado como produto.

## Hipótese de produto

Uma plataforma operacional para pequenas empresas, agências e times de serviço que conecta:

- aquisição;
- CRM;
- comunicação;
- operação;
- projetos;
- agentes de IA;
- integrações;
- automações.

## Regra central

Toda implementação nova deve responder:

> Isto é regra da CMD+ ou capacidade genérica de uma organização?

Se for específica da CMD+, preferir configuração, policy, template ou Skill de workspace.

Se for genérica, considerar no Core.

## Entidades que devem nascer multi-tenant

```text
Workspace
Organization
User
Role
IntegrationConnection
Opportunity
Company
Contact
Interaction
Project
WorkItem
Decision
Event
Automation
```

## Configurações específicas por workspace

Exemplos:

- pesos de qualificação;
- estágios visuais;
- políticas de aprovação;
- ofertas;
- templates de proposta;
- tom de comunicação;
- integrações habilitadas;
- regras de follow-up;
- Skills disponíveis.

## Evitar

- IDs fixos de boards Trello no domínio;
- nomes CMD+ hardcoded em regras centrais;
- lógica comercial embutida em adapters;
- agentes acessando diretamente múltiplos provedores sem camada comum;
- produto genérico demais antes de validar o caso interno.

## Estratégia

```text
Dogfooding CMD+
↓
Processo comprovado
↓
Separação entre Core e configuração
↓
Segundo workspace piloto
↓
Generalização orientada por uso real
↓
Produto
```
