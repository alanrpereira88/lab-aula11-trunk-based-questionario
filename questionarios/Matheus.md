# Questionário — Estratégias de Branching

**Nome:** _seu nome completo_
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

_O objetivo da branch develop é receber novas funcionalidades para que sejam testadas e validadas antes da integração na main._

---

### Q2 — GitHub Flow: por que o Pull Request é obrigatório

No GitHub Flow, nenhuma mudança chega à `main` sem passar por um Pull Request. O que um PR permite que um merge direto não permitiria? Por que esse modelo adota essa regra?

**Resposta:**

_O Pull Request (PR) permite que o codigo seja revisado por alguem da equipe, funcionando como uma barreira antes do codigo ir para a main. O github flow exige pois o codigo da main deve sempre estar funcionando e pronto pra deploy._

---

### Q3 — Trunk-Based: branches curtas e automação

No Trunk-Based Development, os desenvolvedores criam branches que duram poucas horas. O que tornaria isso perigoso sem um bom suporte técnico? O que precisa existir no projeto para que integrar rápido em `main` seja seguro?

**Resposta:**

_Caso a equipe não tenha um suporte técnico, qualquer problema no codigo poderia quebrar o sistema para todos os usuários, atrapalhando toda equipe._

---

### Q4 — Feature Flags

Leia o arquivo [`docs/feature-flags.md`](../docs/feature-flags.md) neste repositório antes de responder. O que são feature flags e qual problema elas resolvem no Trunk-Based Development? Por que sem feature flags seria mais difícil commitar código incompleto em `main`?

**Resposta:**

_As feature flags são técnicas que utilizam variáveis de configuração para ativar ou desativar funcionalidades em produção. Pois a equipe seria forçada a manter branches separadas por dias ou semanas para evitar que interfaces quebradas fossem acidentalmente parar em produção._

---

## ROUND 2 — entregar via `short/q5q8-[nome]` sem `--no-ff`

---

### Q5 — O que o `--no-ff` garante no histórico

Você acabou de usar `--no-ff` no Round 1. O que ele garantiu no histórico? Por que o Git Flow adota essa convenção em vez do merge padrão? Qual a diferença visual no `git log --graph`?

**Resposta:**

_O --no--ff preserva a rastreabilidade ecata de quando a funcionalidade entrou no projeto. O Git Flow adota para que não se misture em uma linha reta de historico. No git log --graph, essa diferença aparece visualmente como uma ramificação lateral._

---

### Q6 — Comparativo: Git Flow vs GitHub Flow

Descreva em 2 a 3 frases a principal diferença entre Git Flow e GitHub Flow no dia a dia do desenvolvedor. Foque no que muda na prática, não só na quantidade de branches.

**Resposta:**

_É o destino do seu código e a velocidade em que ele chega aos usuários finais. No Git Flow, o desenvolvedor integra seu trabalho na branch develop para compor pacotes de um lançamento futuro. Já no GitHub Flow, a mudança aprovada vai direto para a main via Pull Request e entra imediatamente em produção._

---

### Q7 — Escolha justificada

Uma equipe de 4 pessoas desenvolve um app mobile com lançamentos a cada 3 meses e ciclo longo de testes. Qual dos três workflows você escolheria? Justifique considerando o ritmo de lançamentos e o tamanho do time.

**Resposta:**

_Git Flow. Como os lançamentos acontecem só a cada 3 meses e ainda tem um ciclo longo de testes, faz sentido ter as branches develop e release pra estabilizar tudo antes de soltar a versão. Um time pequeno de 4 pessoas e ritmo de entrega mais espaçado, essa estrutura compensa, mesmo sendo mais "burocrática"._

---

### Q8 — Reflexão sobre a prática

Dentre os três workflows que você praticou na aula 11.1, qual foi o mais desafiador? Descreva o que tornou ele mais difícil — pode ser um comando, uma regra do workflow, ou a lógica por trás de uma etapa.

**Resposta:**

_Trunk based. Se tornou difícil por causa de um erro que deixou até o professor em choque._
