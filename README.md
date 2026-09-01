# CMD+ Operação

Sistema operacional interno da CMD+ para integrar aquisição comercial, relacionamento com clientes, operação, desenvolvimento e agentes de IA.

Este repositório nasce com dois objetivos simultâneos:

1. **Operar a CMD+ de forma mais automatizada agora.**
2. **Validar, modularizar e futuramente empacotar a solução como produto para outras empresas.**

## Visão

```text
Mercado
  ↓
Opportunity Engine
  ↓
CRM / Relacionamento
  ↓
Contrato
  ↓
Project Handoff
  ↓
Operação / SDD
  ↓
Figma / GitHub / Entrega
  ↓
Cliente
  ↓
Aprendizado
```

Humanos, ChatGPT, Claude e outros agentes devem operar sobre uma mesma camada de processos e dados.

```text
Humanos + agentes
       ↓
Skills / playbooks
       ↓
MCPs / APIs
       ↓
CMD+ Core
       ↓
Integrações e dados
```

## Princípios

- IA não é a fonte de verdade da empresa.
- Skills codificam **como o trabalho é realizado**.
- MCPs e APIs expõem **o que os agentes conseguem fazer**.
- Integrações externas devem ficar atrás de contratos de domínio sempre que possível.
- Trello pode ser cockpit inicial, mas não deve ser acoplamento permanente.
- Humanos permanecem no loop para preço, prazo, negociação, compromissos e decisões sensíveis.
- O sistema deve registrar eventos e contexto suficiente para aprender com a operação.
- Tudo que for específico da CMD+ deve ser identificável e separável do núcleo futuramente comercializável.

## Domínios iniciais

### Commercial
- descoberta de oportunidades;
- qualificação e score;
- abordagem;
- follow-up;
- proposta;
- negociação;
- fechamento;
- parcerias.

### Client
- contatos;
- histórico de interações;
- WhatsApp;
- e-mail;
- reuniões;
- solicitações;
- pendências e decisões.

### Projects
- handoff comercial;
- especificação;
- experiências e entregáveis;
- Trello;
- Figma;
- GitHub;
- revisão e release.

### Products
- produtos próprios;
- experimentos;
- roadmap;
- lançamento;
- aprendizado.

## Estrutura do repositório

```text
cmd-operacao/
├── docs/               # visão, arquitetura e decisões
├── skills/             # processos reutilizáveis por agentes
├── playbooks/          # rotinas operacionais humanas + IA
├── schemas/            # contratos de domínio
├── integrations/       # documentação/adapters por integração
├── mcp/                # servidores MCP próprios
└── product/            # decisões para futura productização
```

## Primeira vertical a validar

```text
Upwork / fonte de demanda
        ↓
Opportunity
        ↓
Qualificação
        ↓
Score
        ↓
Trello / Funil de Vendas
        ↓
Aprovação humana
        ↓
Abordagem
        ↓
Follow-up
```

Em paralelo, será criada a base para um primeiro MCP hospedável em Cloudflare Workers e Skills que possam ser usadas por ChatGPT, Claude e outros agentes.

## Estado atual

Projeto em fase de definição e implementação incremental. O foco inicial é provar fluxos reais da CMD+ antes de construir abstrações ou interfaces desnecessárias.
