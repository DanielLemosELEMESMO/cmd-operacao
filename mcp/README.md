# MCPs

Os MCPs do projeto expõem capacidades de domínio para agentes como ChatGPT, Claude e Codex.

## Princípio

Não criar MCP por fornecedor sem necessidade.

Evitar como arquitetura central:

```text
trello-mcp
gmail-mcp
whatsapp-mcp
```

Preferir:

```text
cmdplus-commercial-mcp
cmdplus-operations-mcp
cmdplus-projects-mcp
cmdplus-knowledge-mcp
```

## Primeiro MCP

O primeiro experimento deve ser mínimo e hospedável em Cloudflare Workers.

Capacidades sugeridas:

```text
list_sales_items()
get_sales_item()
create_sales_item()
update_sales_item()
```

Inicialmente, essas operações podem ser adaptadas diretamente ao Trello para validar o fluxo.

Depois, a mesma interface pode passar a operar sobre o CMD+ Core/Postgres sem exigir que os agentes mudem sua forma de uso.

## Regras

- autenticar endpoints;
- não expor tokens ou segredos;
- validar entradas;
- registrar ações relevantes;
- separar leitura de escrita;
- exigir aprovação humana para ações sensíveis quando aplicável;
- usar nomes de domínio, não nomes de fornecedor, na interface pública sempre que possível.
