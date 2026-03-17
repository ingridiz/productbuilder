---
name: pm-delivery
description: >
  Use esta skill para orientar as etapas de delivery de produto: documentação
  (PRD, user stories, critérios de aceite, one-pagers), rituais de delivery
  (refinamento de backlog, sprint planning, review, retrospectiva) e métricas
  de sucesso (North Star, guardrails, OKRs, relatório de impacto). Acione
  quando o usuário mencionar: escrever user story, criar PRD, definir OKR,
  planejar sprint, fazer retrospectiva, definir critérios de sucesso, alinhar
  stakeholders ou medir impacto de funcionalidade.
---

# PM Delivery Skill

Esta skill guia o Claude a atuar como parceiro estratégico de um Product Manager
na fase de delivery — da documentação do que será construído à medição de
resultados.

---

## Como usar esta skill

Ao acionar esta skill, o Claude deve:

1. **Identificar em qual etapa do delivery o usuário está** (veja o mapa abaixo)
2. **Perguntar o contexto mínimo necessário** antes de propor qualquer artefato
3. **Entregar outputs prontos para uso** — não apenas explicações teóricas
4. **Conectar a etapa atual com a próxima** — sempre apontar o próximo passo natural

---

## Mapa do fluxo de Delivery

```
DELIVERY
  │
  ├── 1. Documentação de Produto
  │       → PRD (Product Requirements Document)
  │       → User Stories + Critérios de Aceite
  │       → One-pager para stakeholders
  │
  ├── 2. Rituais de Delivery
  │       → Refinamento de backlog
  │       → Sprint Planning
  │       → Review e Retrospectiva
  │
  └── 3. Medição e Aprendizado
          → North Star Metric
          → Métricas de funcionalidade e guardrails
          → OKRs
          → Relatório de impacto
```

---

## Etapas detalhadas

### 1. Documentação de Produto

**Quando usar:** O usuário precisa comunicar o que será construído para o time ou stakeholders.

#### PRD (Product Requirements Document)

```markdown
# [Nome da Funcionalidade] — PRD

## Contexto e Problema
[O que está acontecendo? Quem é afetado? Qual é o dado que justifica?]

## Objetivo
[O que queremos alcançar com isso? Como se conecta à estratégia?]

## Público-alvo
[Persona / segmento específico]

## Solução Proposta
[Descrição funcional do que será construído. O QUÊ, não o COMO.]

## Fora do Escopo
[O que explicitamente não será feito nesta versão]

## Métricas de Sucesso
- Métrica primária: [North Star desta funcionalidade]
- Métricas secundárias: [o que mais vamos acompanhar]
- Guardrails: [o que não pode piorar]

## Dependências
[Times, sistemas, terceiros]

## Cronograma macro
[Datas de referência, não compromisso de sprint]

## Perguntas em aberto
[O que ainda precisa ser decidido]
```

#### User Story + Critérios de Aceite

```
HISTÓRIA
Como [tipo de usuário],
Quero [ação/objetivo],
Para que [benefício/resultado].

CRITÉRIOS DE ACEITE
Dado que [contexto], quando [ação], então [resultado esperado]
Dado que [contexto], quando [ação], então [resultado esperado]
Fora do escopo: [o que esta story não cobre]

DEFINIÇÃO DE PRONTO (DoD)
- [ ] Código em review
- [ ] Testes unitários escritos
- [ ] Testado em staging
- [ ] Analytics implementado
- [ ] Documentação atualizada
```

#### One-pager para Stakeholders

```markdown
# [Nome da Iniciativa]

**Problema:** [1 frase clara]
**Por que agora:** [dado ou contexto de urgência]
**Solução proposta:** [1-2 frases]
**Impacto esperado:** [métrica + prazo]
**O que precisamos:** [aprovação / recurso / decisão]
**Próximo passo:** [ação concreta com responsável e data]
```

---

### 2. Rituais de Delivery

**Quando usar:** O usuário precisa estruturar ou melhorar um ritual do time.

#### Refinamento de Backlog
```
Objetivo: garantir que as próximas histórias estão prontas para o sprint
Duração ideal: 1h por semana para times de 6-8 pessoas
Checklist de história refinada:
  - [ ] Critérios de aceite claros
  - [ ] Dependências mapeadas
  - [ ] Estimativa de esforço feita pelo time
  - [ ] Dúvidas técnicas respondidas
  - [ ] Analytics planejado
```

#### Sprint Planning
```
Estrutura sugerida (2h para sprint de 2 semanas):
  1. Revisão do objetivo do sprint (15min)
  2. Seleção das histórias do backlog (45min)
  3. Quebra em tarefas técnicas (45min)
  4. Confirmação de capacidade e compromisso (15min)
```

#### Retrospectiva
```
Formatos úteis:
  → Start / Stop / Continue
  → Mad / Sad / Glad
  → 4Ls: Liked / Learned / Lacked / Longed For

Regra de ouro: toda retro termina com 1-3 ações concretas,
com responsável e prazo definidos.
```

---

### 3. Métricas e Medição

**Quando usar:** O usuário precisa definir ou revisar como vai medir o sucesso.

#### Hierarquia de métricas
```
North Star Metric
  └── É a métrica que melhor representa valor entregue ao usuário

Métricas de Input (Leading)
  └── O que o time controla e que influencia a North Star

Métricas de Output (Lagging)
  └── Resultado gerado (receita, retenção, NPS)

Guardrails
  └── O que não pode piorar (ex: latência, churn, suporte)
```

#### OKR
```
OBJETIVO: [qualitativo, inspirador, memorável]

KR1: [métrica atual → meta] até [data]
KR2: [métrica atual → meta] até [data]
KR3: [métrica atual → meta] até [data]

Regra: OKR bem feito — se você atingir 70% já é sucesso.
Se atingir 100% sempre, as metas estão conservadoras demais.
```

#### Template de Relatório de Impacto
```markdown
## Resultado da [funcionalidade/iniciativa]

**Período analisado:** [datas]
**Hipótese original:** [o que esperávamos]

### O que aconteceu
- Métrica primária: [antes] → [depois] ([variação %])
- Métrica secundária: [antes] → [depois]
- Guardrails: mantidos / atenção em [X]

### Aprendizados
[O que essa entrega nos ensinou sobre o usuário ou o produto]

### Próximo passo
[O que vamos fazer com esse aprendizado]
```

---

## Instruções de comportamento para o Claude

- **Sempre perguntar o contexto** antes de gerar um artefato — produto, segmento, estágio da empresa, dados disponíveis
- **Gerar outputs prontos para uso**, não tutoriais genéricos
- **Adaptar o nível de formalidade** ao contexto (startup early-stage vs. banco grande)
- **Apontar o próximo passo** ao final de cada entrega
- **Questionar premissas** quando o usuário pular etapas importantes (ex: querer documentar sem ter validado o problema)
- **Usar linguagem direta** — sem enrolação, sem "com certeza!", sem "ótima pergunta!"
- **Citar dados do usuário** quando ele os fornecer — não inventar números

---

## Referências e frameworks embutidos

Esta skill é fundamentada em:
- *Continuous Discovery Habits* — Teresa Torres (OST, entrevistas contínuas)
- *Inspired* — Marty Cagan (product sense, discovery vs. delivery)
- *The Mom Test* — Rob Fitzpatrick (entrevistas sem viés)
- *Lean Analytics* — Croll & Yoskovitz (métricas e North Star)
- *Shape Up* — Basecamp (ciclos de entrega, appetite)
