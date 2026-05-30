# Questionário — Estratégias de Branching

**Nome:** Rafae de Miranda Florindo
**Data:** 29/05/2026
**Turma:** DevOps I — 2025

> Responda com suas próprias palavras, em frases completas. Mínimo de 3 frases por questão.
> Respostas vagas ou idênticas às de colegas não serão aceitas.

---

## ROUND 1 — entregar via `short/q1q4-[nome]` com `--no-ff`

---

### Q1 — Git Flow: o papel da branch `develop`

No Git Flow, existe uma branch chamada `develop`, separada da `main`. Qual é o propósito dela? Por que o Git Flow não faz merge de features direto na `main`?


**Resposta:**

A branch develop serve como uma área de integração onde as features vão sendo juntadas e testadas antes de chegar na main. A ideia é que a main fique sempre com código estável e pronto pra produção, sem versões incompletas. Por isso o Git Flow não faz merge de feature direto na main: tudo passa primeiro pela develop, e só quando está fechado e testado é que vira uma release pra main.

---

### Q2 — GitHub Flow: por que o Pull Request é obrigatório

No GitHub Flow, nenhuma mudança chega à `main` sem passar por um Pull Request. O que um PR permite que um merge direto não permitiria? Por que esse modelo adota essa regra?

**Resposta:**

O Pull Request permite que outras pessoas revisem o código, deixem comentários e que os testes automáticos rodem antes de qualquer coisa entrar na main. Num merge direto isso tudo seria pulado, e código com erro poderia ir parar na main sem ninguém perceber. O GitHub Flow adota essa regra justamente pra manter a main sempre confiável e pronta pra deploy.

---

### Q3 — Trunk-Based: branches curtas e automação

No Trunk-Based Development, os desenvolvedores criam branches que duram poucas horas. O que tornaria isso perigoso sem um bom suporte técnico? O que precisa existir no projeto para que integrar rápido em `main` seja seguro?

**Resposta:**

Integrar várias vezes ao dia seria perigoso sem suporte porque cada merge poderia quebrar a main e ninguém ia perceber na hora. Pra isso funcionar com segurança, o projeto precisa ter testes automatizados rodando a cada commit (CI) e um pipeline rápido que dê retorno logo. Também ajuda muito ter feature flags, pra conseguir mandar código incompleto sem ele entrar em funcionamento.

---

### Q4 — Feature Flags

Leia o arquivo [`docs/feature-flags.md`](../docs/feature-flags.md) neste repositório antes de responder. O que são feature flags e qual problema elas resolvem no Trunk-Based Development? Por que sem feature flags seria mais difícil commitar código incompleto em `main`?

**Resposta:**

Feature flags são como interruptores que ligam ou desligam uma funcionalidade sem precisar mudar o código ou fazer um novo deploy. Elas resolvem o problema de mandar código ainda não terminado pra main, porque a parte incompleta fica escondida atrás da flag desligada. Sem elas seria difícil commitar código incompleto, já que ele estaria ativo e poderia quebrar ou confundir o que está em produção.

---

## ROUND 2 — entregar via `short/q5q8-[nome]` sem `--no-ff`

---

### Q5 — O que o `--no-ff` garante no histórico

Você acabou de usar `--no-ff` no Round 1. O que ele garantiu no histórico? Por que o Git Flow adota essa convenção em vez do merge padrão? Qual a diferença visual no `git log --graph`?

**Resposta:**

O --no-ff garantiu que ficasse registrado no histórico um merge commit, mostrando que aquela branch existiu de verdade. O Git Flow usa essa convenção pra não perder a informação de que um grupo de commits veio de uma mesma feature. No git log --graph a diferença aparece visualmente: com --no-ff surge aquela "bolha" mostrando a branch separada e voltando, enquanto no fast-forward fica tudo numa linha reta só.

---

### Q6 — Comparativo: Git Flow vs GitHub Flow

Descreva em 2 a 3 frases a principal diferença entre Git Flow e GitHub Flow no dia a dia do desenvolvedor. Foque no que muda na prática, não só na quantidade de branches.

**Resposta:**

Na prática, o Git Flow é mais pesado: o desenvolvedor lida com várias branches (develop, release, hotfix) e segue um processo mais cheio de etapas. Já no GitHub Flow o dia a dia é mais simples, basicamente só a main mais branches curtas com PR, e a entrega é contínua. Então a maior diferença é o ritmo: o GitHub Flow integra e entrega mais rápido, e o Git Flow segura mais pra organizar releases.

---

### Q7 — Escolha justificada

Uma equipe de 4 pessoas desenvolve um app mobile com lançamentos a cada 3 meses e ciclo longo de testes. Qual dos três workflows você escolheria? Justifique considerando o ritmo de lançamentos e o tamanho do time.

**Resposta:**

Pra esse time eu escolheria o Git Flow. Como os lançamentos acontecem só a cada 3 meses e ainda tem um ciclo longo de testes, faz sentido ter as branches develop e release pra estabilizar tudo antes de soltar a versão. Com um time pequeno de 4 pessoas e ritmo de entrega mais espaçado, essa estrutura mais organizada compensa, mesmo sendo mais "burocrática".

---

### Q8 — Reflexão sobre a prática

Dentre os três workflows que você praticou na aula 11.1, qual foi o mais desafiador? Descreva o que tornou ele mais difícil — pode ser um comando, uma regra do workflow, ou a lógica por trás de uma etapa.

**Resposta:**

Pra mim o mais desafiador foi o Git Flow, por causa da quantidade de branches e regras pra lembrar. Ficar controlando quando usar develop, release e quando o merge vai pra main me confundiu mais do que os outros dois. O Trunk-Based pareceu mais simples no comando, mas a lógica de confiar tanto em automação e feature flags também deu o que pensar.