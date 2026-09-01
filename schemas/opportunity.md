# Opportunity

Contrato inicial para oportunidades comerciais, independente da fonte.

```ts
export interface Opportunity {
  id: string;
  workspaceId: string;

  title: string;
  description?: string;

  source: {
    type: string;
    platform?: string;
    url?: string;
    externalId?: string;
  };

  companyId?: string;
  contactId?: string;

  location?: {
    country?: string;
    city?: string;
  };

  language?: string;
  category?: string;
  opportunityType?: 'quick_cash' | 'small_project' | 'medium_project' | 'large_project' | 'recurring' | 'partnership';

  estimatedBudget?: {
    currency?: string;
    min?: number;
    max?: number;
  };

  estimatedEffortHours?: {
    min?: number;
    max?: number;
  };

  qualification?: {
    technicalFit?: number;
    commercialFit?: number;
    strategicFit?: number;
    recurrenceFit?: number;
    capacityFit?: number;
    risk?: number;
    confidence?: number;
    score?: number;
    scoreReason?: string;
  };

  stage:
    | 'discovered'
    | 'qualified'
    | 'approach_ready'
    | 'contacted'
    | 'responded'
    | 'meeting'
    | 'diagnosis'
    | 'proposal'
    | 'negotiation'
    | 'won'
    | 'lost'
    | 'handoff';

  ownerId?: string;

  lastInteractionAt?: string;
  nextAction?: string;
  nextActionAt?: string;

  lostReason?: string;
  wonValue?: number;

  rawData?: unknown;

  createdAt: string;
  updatedAt: string;
}
```

## Regras

- `workspaceId` existe desde o início para evitar acoplamento ao uso interno da CMD+.
- `rawData` preserva a entrada original para reprocessamento futuro.
- o score é derivado; não deve substituir os componentes de qualificação.
- estágios representam o domínio comercial e não listas específicas do Trello.
- adapters podem mapear estes estágios para Trello, CRM ou UI própria.
