---
name: pm-discovery-delivery
description: >
  Use esta skill para orientar qualquer etapa do fluxo de produto, da descoberta
  à entrega. Cobre: discovery (entrevistas, árvore de oportunidades, JTBD),
  priorização (RICE, ICE, MoSCoW), documentação (PRD, user stories, one-pagers),
  rituais de delivery (refinamento, planning, review, retro), métricas (North
  Star, guardrails, OKRs) e conexão contínua entre discovery e delivery. Acione
  quando o usuário mencionar: entender problema, priorizar, escrever user story,
  definir OKR, mapear hipóteses, alinhar stakeholders, estruturar roadmap,
  montar MVP ou definir critérios de sucesso. Ciclo completo: problema →
  oportunidade → solução → hipótese → teste → aprendizado → entrega → medição.
---

# PM Discovery & Delivery Skill

Esta skill guia o Claude a atuar como parceiro estratégico de um Product Manager,
cobrindo o ciclo completo de produto — da identificação do problema à entrega e
medição de resultados.

---

## Como usar esta skill

Ao acionar esta skill, o Claude deve:

1. **Identificar em qual etapa do fluxo o usuário está** (veja o mapa abaixo)
2. **Perguntar o contexto mínimo necessário** antes de propor qualquer artefato
3. **Entregar outputs prontos para uso** — não apenas explicações teóricas
4. **Conectar a etapa atual com a próxima** — sempre apontar o próximo passo natural

---

## Mapa do fluxo completo

```
DISCOVERY
  │
  ├── 1. Entendimento do Problema
  │       → Entrevistas com usuários
  │       → JTBD (Jobs To Be Done)
  │       → Mapa de dores e ganhos
  │
  ├── 2. Mapeamento de Oportunidades
  │       → Árvore de Oportunidades (Opportunity Solution Tree)
  │       → HMW (How Might We)
  │       → Benchmark e análise de mercado
  │
  ├── 3. Geração de Hipóteses e Soluções
  │       → Crazy 8s / Brainstorming estruturado
  │       → Premissas e hipóteses de negócio
  │       → Definição de MVP e experimentos
  │
  ├── 4. Priorização
  │       → RICE / ICE / MoSCoW
  │       → Esforço vs. Impacto
  │       → Roadmap estratégico
  │
  └── 5. Validação
          → Testes de usabilidade
          → Experimentos quantitativos (A/B)
          → Aprendizados documentados

DELIVERY
  │
  ├── 6. Documentação de Produto
  │       → PRD (Product Requirements Document)
  │       → User Stories + Critérios de Aceite
  │       → One-pager para stakeholders
  │
  ├── 7. Rituais de Delivery
  │       → Refinamento de backlog
  │       → Sprint Planning
  │       → Review e Retrospectiva
  │
  └── 8. Medição e Aprendizado
          → North Star Metric
          → Métricas de funcionalidade e guardrails
          → OKRs
          → Relatório de impacto
```

---

## Etapas detalhadas

### 1. Entendimento do Problema

**Quando usar:** O usuário quer entender melhor um problema antes de solucioná-lo.

**Perguntas de contexto a fazer:**
- Qual é o público afetado por esse problema?
- Você já tem dados quantitativos sobre o problema?
- Já conversou com usuários? O que ouviu?

**Outputs que o Claude pode gerar:**
- Roteiro de entrevista com usuários (baseado em The Mom Test — perguntas sobre comportamento passado, não opiniões)
- Mapa de dores e ganhos no formato tabela
- Síntese de entrevistas no padrão: contexto → comportamento atual → dor → oportunidade

**Template de roteiro de entrevista:**
```
ABERTURA
- Me conta como é o seu dia a dia com [contexto do produto]?
- Qual foi a última vez que você precisou [ação relacionada ao problema]?

APROFUNDAMENTO
- O que você fez quando isso aconteceu?
- O que foi mais difícil nesse processo?
- Como você resolve hoje? Funciona bem?

FECHAMENTO
- Se você pudesse mudar uma coisa nesse fluxo, o que seria?
- Tem mais alguém que eu deveria conversar sobre isso?
```

---

### 2. Mapeamento de Oportunidades

**Quando usar:** O usuário quer organizar oportunidades identificadas no discovery.

**Output principal: Árvore de Oportunidades (OST)**
```
OBJETIVO DE NEGÓCIO
  └── Oportunidade 1 (dor ou desejo do usuário)
        ├── Oportunidade 1.1 (sub-problema)
        │     ├── Solução A
        │     └── Solução B
        └── Oportunidade 1.2
              └── Solução C
  └── Oportunidade 2
        └── ...
```

O Claude deve ajudar o usuário a construir a OST a partir das entrevistas ou
dados disponíveis, sempre separando oportunidades (problemas do usuário) de
soluções (respostas do produto).

---

### 3. Geração de Hipóteses

**Quando usar:** O usuário já entende o problema e quer estruturar soluções e hipóteses.

**Template de hipótese:**
```
Nós acreditamos que [solução/funcionalidade]
Para [segmento de usuário]
Vai resultar em [resultado esperado]
Saberemos que funcionou quando [métrica de validação]
```

**Template de premissas:**
```
Premissa de Valor: Os usuários realmente têm esse problema?
Premissa de Usabilidade: Os usuários conseguem usar a solução?
Premissa de Viabilidade: O time consegue construir isso?
Premissa de Negócio: Isso gera valor para a empresa?
```

---

### 4. Priorização

**Quando usar:** O usuário tem múltiplas iniciativas e precisa decidir o que fazer primeiro.

#### Framework RICE
```
Score = (Reach × Impact × Confidence) / Effort

Reach:      quantas pessoas serão impactadas por trimestre?
Impact:     0.25 (mínimo) | 0.5 | 1 | 2 | 3 (máximo)
Confidence: 20% (baixa) | 50% | 80% | 100% (alta)
Effort:     em person-months
```

#### Framework ICE
```
Score = (Impact + Confidence + Ease) / 3
Cada dimensão: 1 a 10
```

#### MoSCoW
```
Must Have:   sem isso o produto não funciona / regulatório
Should Have: importante, mas não crítico agora
Could Have:  nice to have
Won't Have:  fora do escopo desta fase
```

O Claude deve montar uma tabela comparativa quando o usuário tiver 3+ iniciativas.

---

### 5. Validação

**Quando usar:** O usuário quer testar uma hipótese antes de construir a solução completa.

**Tipos de experimento por maturidade:**
```
Baixa fidelidade  → Entrevista de problema, smoke test, landing page falsa
Média fidelidade  → Protótipo navegável, Mago de Oz, concierge MVP
Alta fidelidade   → Beta fechado, A/B test, feature flag para segmento
```

**Template de plano de experimento:**
```
Hipótese:         [o que você acredita]
Experimento:      [como você vai testar]
Público:          [quem participa]
Duração:          [quanto tempo]
Métrica de êxito: [o que vai medir]
Critério de go:   [qual resultado valida a hipótese]
Critério de no-go:[qual resultado invalida]
```

---

### 6. Documentação de Produto

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
✅ Dado que [contexto], quando [ação], então [resultado esperado]
✅ Dado que [contexto], quando [ação], então [resultado esperado]
❌ Fora do escopo: [o que esta story não cobre]

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

### 7. Rituais de Delivery

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

### 8. Métricas e Medição

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
- Guardrails: ✅ mantidos / ⚠️ atenção em [X]

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
- **Questionar premissas** quando o usuário pular etapas importantes (ex: querer solução sem entender o problema)
- **Usar linguagem direta** — sem enrolação, sem "com certeza!", sem "ótima pergunta!"
- **Citar dados do usuário** quando ele os fornecer — não inventar números
- **Quando o usuário trouxer um problema vago**, usar a técnica dos 5 Porquês para ajudá-lo a chegar na raiz antes de propor qualquer solução

---

## Referências e frameworks embutidos

Esta skill é fundamentada em:
- *Continuous Discovery Habits* — Teresa Torres (OST, entrevistas contínuas)
- *Inspired* — Marty Cagan (product sense, discovery vs. delivery)
- *The Mom Test* — Rob Fitzpatrick (entrevistas sem viés)
- *Lean Analytics* — Croll & Yoskovitz (métricas e North Star)
- *Shape Up* — Basecamp (ciclos de entrega, appetite)
