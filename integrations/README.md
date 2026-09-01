# Integrações

Integrações conectam o domínio do CMD+ OS a ferramentas externas.

## Prioridades

- Trello;
- Gmail;
- Google Calendar;
- WhatsApp Business;
- GitHub;
- Figma;
- Google Drive;
- Upwork e demais fontes de demanda;
- Google Places / Web.

## Diretriz

O domínio não deve depender de IDs, nomes de listas, campos ou peculiaridades de um provider.

Adapters traduzem entre:

```text
Domain Model ↔ Provider Model
```

Exemplo:

```text
Opportunity.stage = proposal
        ↓ adapter Trello
Lista "Em Negociação" ou configuração equivalente do workspace
```

## Conexões existentes

A operação atual já usa ferramentas externas diretamente através de ChatGPT/Claude quando conveniente. Isso é aceitável na fase inicial.

Só criar integração própria quando houver necessidade de:

- automação recorrente;
- contexto compartilhado entre agentes;
- webhook/evento;
- auditoria;
- productização;
- abstração de fornecedor;
- fluxo impossível ou frágil via integração existente.

## Segurança

- segredos somente em secrets/env/config segura;
- menor privilégio possível;
- registrar ações externas relevantes;
- respeitar APIs e termos oficiais das plataformas;
- não automatizar ações proibidas por fornecedores.
