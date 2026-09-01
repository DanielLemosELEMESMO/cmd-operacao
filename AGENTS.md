# AGENTS.md

## Contexto

Este repositório implementa e documenta o **CMD+ OS**, inicialmente usado internamente pela CMD+ e projetado para futuramente se tornar um produto multiempresa.

Antes de implementar qualquer coisa, leia:

1. `README.md`
2. `docs/architecture.md`
3. `docs/roadmap.md`
4. `product/productization.md`
5. schemas relacionados à tarefa
6. Skill/playbook relacionado à tarefa, se existir

## Regra principal

Não implemente todo o roadmap de uma vez.

Trabalhe em **fatias verticais pequenas e utilizáveis**, validando cada integração e processo com a operação real.

## Separação de responsabilidades

### Código

Use para:

- serviços de domínio;
- persistência;
- adapters;
- APIs;
- MCPs;
- webhooks;
- automações determinísticas;
- interfaces próprias.

### Skills / playbooks

Use para:

- procedimentos;
- critérios de decisão;
- instruções a agentes;
- checklists;
- políticas operacionais;
- formatos de saída.

Não transforme um processo puramente instrucional em código sem necessidade.

### Integrações externas

Trello, Gmail, WhatsApp, Calendar, GitHub, Figma, marketplaces e demais serviços devem ser tratados como adapters/capabilities, não como o domínio central.

## Productização

Todo código de Core deve evitar pressupor que existe apenas a CMD+.

Preferir `workspaceId`/tenant e configurações de workspace a regras hardcoded.

Não generalize abstrações sem evidência. O caminho é:

```text
uso interno real → aprendizado → extração do padrão → produto
```

## Convenções

- TypeScript por padrão para serviços e MCPs, salvo justificativa.
- Commits em Conventional Commits, em PT-BR, com verbo no presente: `feat: adiciona ...`, `docs: define ...`, `fix: corrige ...`.
- Não colocar segredos no repositório.
- Registrar decisões arquiteturais relevantes em `docs/`.
- Preferir operações de domínio a operações específicas de fornecedor.
- Escritas externas com impacto comercial devem prever aprovação humana quando aplicável.

## Primeira vertical

A prioridade inicial é provar:

```text
fonte de oportunidade
→ normalização
→ Opportunity
→ qualificação
→ score
→ Trello Funil de Vendas
→ aprovação humana
→ abordagem/follow-up
```

O primeiro MCP deve ser mínimo e pode inicialmente usar Trello como backend operacional.

## Critério de conclusão de uma tarefa

Uma implementação só está concluída quando:

- funciona no fluxo real correspondente;
- possui configuração documentada;
- erros principais são tratados;
- não expõe segredos;
- mantém a separação entre domínio e provider;
- documentação relevante foi atualizada.
