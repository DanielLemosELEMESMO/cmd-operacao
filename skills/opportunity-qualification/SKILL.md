# Opportunity Qualification

## Objetivo

Avaliar uma oportunidade comercial de forma consistente, explicar a prioridade e recomendar a próxima ação sem assumir que todo lead deve ser abordado.

## Entradas mínimas

- descrição original da oportunidade;
- fonte e URL quando disponíveis;
- empresa/contato quando disponíveis;
- orçamento declarado ou estimado;
- prazo declarado;
- contexto atual da capacidade da equipe, quando acessível.

Nunca invente informação ausente. Marque incerteza explicitamente.

## Processo

### 1. Identifique a natureza da oportunidade

Classifique em uma das categorias:

- `quick_cash`
- `small_project`
- `medium_project`
- `large_project`
- `recurring`
- `partnership`

Parcerias e recorrência devem ser consideradas separadamente do ticket da primeira venda.

### 2. Avalie fit técnico — 0 a 20

Considere:

- domínio tecnológico;
- stack;
- complexidade;
- integrações;
- prazo;
- dependências externas;
- necessidade de capacidades não disponíveis.

### 3. Avalie fit comercial — 0 a 20

Considere:

- orçamento/ticket provável;
- clareza da demanda;
- urgência;
- facilidade de contratação;
- maturidade aparente do comprador;
- custo comercial para fechar.

### 4. Avalie fit estratégico — 0 a 15

Considere:

- geração de case;
- entrada em mercado relevante;
- proximidade com produtos/competências desejadas;
- potencial de indicação;
- aprendizado reutilizável.

### 5. Avalie recorrência/parceria — 0 a 20

Considere:

- demanda contínua;
- manutenção/evolução;
- agência ou intermediário com vários clientes;
- white label;
- possibilidade de canal comercial;
- LTV potencial.

### 6. Avalie capacidade atual — 0 a 15

Considere somente informações disponíveis sobre:

- disponibilidade;
- prazo;
- conflito com entregas atuais;
- necessidade de parceiros/subcontratação.

Se não houver contexto de capacidade, não invente. Indique `não avaliado` e reduza a confiança.

### 7. Avalie risco — 0 a 10

10 significa risco baixo e 0 risco muito alto.

Considere:

- escopo vago;
- prazo irreal;
- orçamento incompatível;
- sinais de cliente problemático;
- dependências externas;
- risco jurídico/operacional;
- tecnologia desconhecida;
- plataforma/fonte duvidosa.

## Score

Score máximo: 100.

```text
technicalFit      0–20
commercialFit     0–20
strategicFit      0–15
recurrenceFit     0–20
capacityFit       0–15
risk              0–10
```

Classes:

- A: 80–100
- B: 60–79
- C: 40–59
- D: 0–39

O score não substitui julgamento. Uma oportunidade de parceria pode merecer prioridade mesmo com ticket inicial baixo.

## Saída obrigatória

```text
OPORTUNIDADE: <título>
CLASSE: A/B/C/D
SCORE: <0-100>
CONFIANÇA: baixa/média/alta
TIPO: <categoria>

RESUMO
<2-4 linhas>

PONTUAÇÃO
- Fit técnico: x/20
- Fit comercial: x/20
- Fit estratégico: x/15
- Recorrência/parceria: x/20
- Capacidade: x/15 ou não avaliado
- Risco: x/10

POR QUE VALE / NÃO VALE ATENÇÃO
- ...

INCERTEZAS
- ...

PRÓXIMA AÇÃO
<ignorar | investigar | abordar | responder | marcar reunião | outra>

ABORDAGEM
Se a próxima ação exigir contato, apresente apenas um rascunho. Não envie automaticamente.
```

## Aprovação humana

Exigir aprovação antes de:

- primeira abordagem externa;
- envio de preço;
- promessa de prazo;
- proposta final;
- negociação;
- qualquer compromisso contratual.

## Aprendizado

Quando o resultado real estiver disponível, registrar:

- respondeu?;
- reunião?;
- proposta?;
- fechou?;
- valor;
- margem estimada;
- recorrência;
- motivo da perda.

Esses dados deverão futuramente recalibrar pesos e heurísticas.
