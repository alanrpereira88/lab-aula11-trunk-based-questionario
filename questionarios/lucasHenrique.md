# Questionário — Estratégias de Branching

**Nome:** _lucas henrique conde rodrigues_
**Data:** _data_
**Turma:** DevOps I — 2025

> Responda com suas próprias palavras, em frases completas. Mínimo de 3 frases por questão.
> Respostas vagas ou idênticas às de colegas não serão aceitas.

---

## ROUND 1 — entregar via `short/q1q4-[nome]` com `--no-ff`

---

### Q1 — Git Flow: o papel da branch `develop`

No Git Flow, existe uma branch chamada `develop`, separada da `main`. Qual é o propósito dela? Por que o Git Flow não faz merge de features direto na `main`?

**Resposta:**

_develop é usada para testes e a main é o produto principal._

---

### Q2 — GitHub Flow: por que o Pull Request é obrigatório

No GitHub Flow, nenhuma mudança chega à `main` sem passar por um Pull Request. O que um PR permite que um merge direto não permitiria? Por que esse modelo adota essa regra?

**Resposta:**

_O Pull Request funciona como uma trava de segurança e qualidade: ele obriga que o código seja revisado por outros desenvolvedores e validado por testes automáticos antes de entrar na main. Esse modelo é adotado para evitar que erros humanos quebrem o produto final e para garantir que a equipe esteja sempre alinhada sobre o que está sendo alterado._

---

### Q3 — Trunk-Based: branches curtas e automação

No Trunk-Based Development, os desenvolvedores criam branches que duram poucas horas. O que tornaria isso perigoso sem um bom suporte técnico? O que precisa existir no projeto para que integrar rápido em `main` seja seguro?

**Resposta:**

_Integrar direto na main sem suporte é arriscado porque qualquer erro quebra o sistema todo na hora. Para ser seguro, é essencial ter testes automáticos e um pipeline de CI/CD, que conferem e barram erros antes que eles cheguem ao produto final._

---

### Q4 — Feature Flags

Leia o arquivo [`docs/feature-flags.md`](../docs/feature-flags.md) neste repositório antes de responder. O que são feature flags e qual problema elas resolvem no Trunk-Based Development? Por que sem feature flags seria mais difícil commitar código incompleto em `main`?

**Resposta:**

_Feature Flags são "interruptores" que permitem ligar ou desligar funções no código sem novo deploy. Elas resolvem o risco de quebrar o sistema ao integrar funcionalidades inacabadas na main. Sem elas, commitar código incompleto seria impossível, pois ele ficaria exposto ao usuário final, causando erros ou exibindo recursos que ainda não funcionam._

---

## ROUND 2 — entregar via `short/q5q8-[nome]` sem `--no-ff`

---

### Q5 — O que o `--no-ff` garante no histórico

Você acabou de usar `--no-ff` no Round 1. O que ele garantiu no histórico? Por que o Git Flow adota essa convenção em vez do merge padrão? Qual a diferença visual no `git log --graph`?

**Resposta:**

_Escreva aqui._

---

### Q6 — Comparativo: Git Flow vs GitHub Flow

Descreva em 2 a 3 frases a principal diferença entre Git Flow e GitHub Flow no dia a dia do desenvolvedor. Foque no que muda na prática, não só na quantidade de branches.

**Resposta:**

_Escreva aqui._

---

### Q7 — Escolha justificada

Uma equipe de 4 pessoas desenvolve um app mobile com lançamentos a cada 3 meses e ciclo longo de testes. Qual dos três workflows você escolheria? Justifique considerando o ritmo de lançamentos e o tamanho do time.

**Resposta:**

_Escreva aqui._

---

### Q8 — Reflexão sobre a prática

Dentre os três workflows que você praticou na aula 11.1, qual foi o mais desafiador? Descreva o que tornou ele mais difícil — pode ser um comando, uma regra do workflow, ou a lógica por trás de uma etapa.

**Resposta:**

_Escreva aqui._
