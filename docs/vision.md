# Visão do CMD+ OS

## Meta

Construir uma camada operacional para a CMD+ que conecte aquisição, relacionamento, atendimento, projetos, produtos, comunicação, desenvolvimento e agentes de IA em um fluxo contínuo.

O objetivo inicial é operar melhor a CMD+ e gerar mais contratos. O objetivo posterior é transformar os padrões comprovados em um produto para outras empresas.

## North Star

Um gestor deve conseguir perguntar:

> Me dê a situação da empresa hoje.

E receber algo como:

```text
COMERCIAL
3 oportunidades A novas
2 follow-ups atrasados
1 proposta aguardando resposta

CLIENTES
2 solicitações novas
1 risco de relacionamento

OPERAÇÃO
5 entregas em andamento
1 bloqueada

PRODUTOS
2 em desenvolvimento

GITHUB
3 PRs abertos
1 CI falhando

AGENDA
2 reuniões

DECISÕES
1. Aprovar orçamento X
2. Responder cliente Y
3. Definir escopo Z
```

Depois poder dizer:

> Cuide do que puder sem mim e me mostre apenas as decisões.

## Opportunity Engine

### Prospecção ativa

Encontrar empresas que ainda não estão pedindo ajuda, mas demonstram sinais de oportunidade.

Fontes iniciais:

- Google Places;
- web;
- diretórios;
- redes profissionais;
- bases públicas.

Oferta inicial sugerida para outbound: **Site Comercial CMD+**.

Estratégia:

```text
oferta simples
→ relacionamento
→ descoberta de problemas maiores
→ sistemas / automações / produtos
```

### Radar de demanda

Capturar pessoas e empresas que já estão declarando intenção de contratar.

Fontes:

- Upwork;
- Workana;
- 99Freelas;
- LinkedIn;
- Reddit;
- X;
- comunidades;
- fóruns;
- web aberta.

Tipos:

- caixa rápido;
- projeto pequeno;
- projeto médio;
- projeto grande;
- recorrência;
- parceria.

Parcerias devem receber atenção especial. Uma agência com demanda mensal pode ter muito mais valor que um contrato isolado.

## Pipeline comercial

```text
buscar
→ normalizar
→ qualificar
→ score
→ abordar
→ atender
→ acompanhar
→ diagnosticar
→ propor
→ negociar
→ fechar
→ handoff
→ aprender
```

## Relacionamento unificado

WhatsApp, e-mail, reuniões e plataformas devem convergir conceitualmente para `Interaction`.

```text
Interaction
- workspace
- client
- opportunity
- project
- channel
- author
- content
- timestamp
- intent
- urgency
- summary
- nextAction
```

Assim o sistema enxerga o relacionamento, não apenas caixas de entrada separadas.

## Inbox operacional

Eventos de vários canais devem ser triados em uma inbox conceitual:

```text
nova oportunidade
mensagem de cliente
bug
solicitação
proposta aguardando resposta
decisão
alerta
reunião
risco
```

Classificação:

```text
Comercial → Funil de Vendas
Cliente/Entrega → Operação
Produto interno → Produtos
Sem ação → arquivar
```

## Handoff comercial → desenvolvimento

```text
Contrato fechado
→ objetivo
→ escopo
→ não escopo
→ decisões
→ riscos
→ promessas
→ experiências
→ specs
→ Figma
→ issues
→ implementação
→ PR
→ release
```

O contexto comercial não deve ser perdido quando o trabalho entra em execução.

## Ferramentas

### Trello
Cockpit visual inicial para Comercial, Operação e Produtos.

### Gmail
Comunicação, triagem, follow-up e histórico.

### WhatsApp Business
Canal de relacionamento, suporte e comercial com webhook e classificação futura.

### Calendar
Agendamento, preparação e processamento de reuniões.

### GitHub
Estado técnico, issues, PRs, CI, releases e documentação de código.

### Figma
Experiências, fluxos, design e ligação com entregáveis técnicos.

### ChatGPT
Coordenação, pesquisa, análise, gestão, comunicação e operação sobre múltiplas ferramentas.

### Claude / Claude Code
Execução técnica profunda, trabalho dentro de repositórios, specs, código e Skills.

Os dois devem operar a mesma camada de empresa.

## Skills

Skills codificam como o trabalho deve ser realizado.

Exemplos:

- opportunity-radar;
- opportunity-qualification;
- commercial-followup;
- client-request-triage;
- discovery-meeting;
- create-proposal;
- project-handoff;
- sdd-plan;
- design-review;
- code-review;
- release.

## MCP

MCPs expõem capacidades aos agentes.

Preferir ferramentas como:

```text
find_opportunities()
get_opportunity()
qualify_opportunity()
register_interaction()
create_followup()
get_project_status()
create_handoff()
```

Em vez de obrigar agentes a conhecer Trello, Gmail ou qualquer provider específico.

## Cloudflare

Cloudflare Workers é a primeira opção para hospedar MCPs leves e endpoints de integração, desde que o caso seja adequado ao modelo de execução e segurança.

## Dados

Na V0, ferramentas existentes podem armazenar parte do estado.

No Core futuro, Postgres/Supabase deverá concentrar entidades estruturais e event log.

## Human in the loop

Automatizar fortemente:

- leitura;
- pesquisa;
- classificação;
- resumo;
- organização;
- documentação;
- criação de tarefas;
- atualização de estado.

Manter aprovação humana padrão para:

- primeira abordagem;
- preço;
- prazo;
- proposta final;
- negociação;
- contrato;
- comunicação sensível.

## Produto futuro

A productização deve acontecer por dogfooding:

```text
CMD+ usa
→ CMD+ aprende
→ padrões são separados de particularidades
→ segundo workspace valida
→ abstrações amadurecem
→ produto é empacotado
```

A solução futura pode atender especialmente:

- software houses;
- agências;
- consultorias;
- pequenos times de serviço;
- empresas com operação distribuída entre múltiplas ferramentas e agentes de IA.
