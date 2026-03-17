# ProductBuilder

Ferramentas e skills para Product Managers que querem estruturar seu fluxo de produto — da descoberta à entrega.

---

## Skills Disponíveis

### 1. PM Discovery

Skill focada na fase de descoberta de produto:

- Entendimento do problema (entrevistas com usuários, JTBD, mapa de dores)
- Mapeamento de oportunidades (árvore de oportunidades, HMW, benchmark)
- Geração de hipóteses (premissas, MVP, experimentos)
- Priorização (RICE, ICE, MoSCoW, roadmap)
- Validação (testes de usabilidade, A/B, aprendizados)

> **Link direto:** [PM Discovery SKILL.md](https://github.com/ingridiz/productbuilder/blob/main/.agents/skills/pm-discovery/SKILL.md)

### 2. PM Delivery

Skill focada na fase de entrega de produto:

- Documentação de produto (PRD, user stories, critérios de aceite, one-pagers)
- Rituais de delivery (refinamento, sprint planning, review, retrospectiva)
- Métricas e medição (North Star, guardrails, OKRs, relatório de impacto)

> **Link direto:** [PM Delivery SKILL.md](https://github.com/ingridiz/productbuilder/blob/main/.agents/skills/pm-delivery/SKILL.md)

### 3. PM Discovery & Delivery (Completa)

Skill unificada que cobre o ciclo completo de produto — discovery e delivery em um único arquivo:

- Todas as etapas de Discovery (1-5) + Delivery (6-8) integradas
- Templates completos para cada fase do ciclo
- Instruções de comportamento para o Claude atuar como parceiro estratégico

> **Link direto:** [PM Discovery & Delivery SKILL.md](https://github.com/ingridiz/productbuilder/blob/main/.claude/skills/pm-discovery-delivery.md)

---

## Como usar no Claude

1. Acesse o link da skill desejada acima
2. Copie o conteúdo completo do arquivo
3. No [Claude](https://claude.ai), crie um **Project** e cole o conteúdo em **Custom Instructions** ou **Project Knowledge**
4. Pronto! O Claude vai atuar como parceiro estratégico de produto em todas as conversas dentro desse projeto

Você pode usar as skills separadas (Discovery e Delivery) ou a versão completa unificada, dependendo da sua necessidade.

### Exemplos de uso

- *"Quero entender o problema"* — Guia pelo processo de entrevistas e mapeamento de dores
- *"Preciso priorizar"* — Utilize os frameworks RICE, ICE ou MoSCoW para ranquear iniciativas
- *"Como escrever uma user story"* — Templates prontos com critérios de aceite
- *"Definir OKR"* — Estruture objetivos e key results de forma prática
- *"Montar um MVP"* — Defina hipóteses, premissas e experimentos para validação

---

## Etapas cobertas

```
DISCOVERY (pm-discovery)           DELIVERY (pm-delivery)
  1. Entendimento do Problema        6. Documentação de Produto
  2. Mapeamento de Oportunidades     7. Rituais de Delivery
  3. Geração de Hipóteses            8. Medição e Aprendizado
  4. Priorização
  5. Validação
```

---

## Estrutura do repositório

```
productbuilder/
  .agents/
    skills/
      pm-discovery/
        SKILL.md                     # Skill de Discovery (separada)
      pm-delivery/
        SKILL.md                     # Skill de Delivery (separada)
  .claude/
    skills/
      pm-discovery-delivery.md       # Skill completa (Discovery + Delivery)
  README.md
```

---

## Referências

Baseado em frameworks de:

- *Continuous Discovery Habits* — Teresa Torres
- *Inspired* — Marty Cagan
- *The Mom Test* — Rob Fitzpatrick
- *Lean Analytics* — Croll & Yoskovitz
- *Shape Up* — Basecamp
