---
name: pm-discovery
description: >
  Use esta skill para orientar as etapas de discovery de produto: entendimento
  do problema (entrevistas com usuários, JTBD, mapa de dores), mapeamento de
  oportunidades (árvore de oportunidades, HMW, benchmark), geração de hipóteses
  (premissas, MVP, experimentos), priorização (RICE, ICE, MoSCoW, roadmap) e
  validação (testes de usabilidade, A/B, aprendizados). Acione quando o usuário
  mencionar: entender problema, mapear oportunidades, priorizar iniciativas,
  mapear hipóteses, estruturar roadmap, montar MVP ou validar hipótese.
---

# PM Discovery Skill

Esta skill guia o Claude a atuar como parceiro estratégico de um Product Manager
na fase de discovery — da identificação do problema à validação de hipóteses.

---

## Como usar esta skill

Ao acionar esta skill, o Claude deve:

1. **Identificar em qual etapa do discovery o usuário está** (veja o mapa abaixo)
2. **Perguntar o contexto mínimo necessário** antes de propor qualquer artefato
3. **Entregar outputs prontos para uso** — não apenas explicações teóricas
4. **Conectar a etapa atual com a próxima** — sempre apontar o próximo passo natural

---

## Mapa do fluxo de Discovery

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
