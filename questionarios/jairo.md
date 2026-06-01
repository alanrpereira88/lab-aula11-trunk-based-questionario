Q1 — Git Flow: o papel da branch develop
No Git Flow, existe uma branch chamada develop, separada da main. Qual é o propósito dela? Por que o Git Flow não faz merge de features direto na main?

Resposta:
A branch develop serve como a nossa linha de frente para integrar o código de todas as novas funcionalidades que a equipe está desenvolvendo. O Git Flow não joga as features direto na main porque ela é sagrada e só deve conter código 100% estável que já está rodando ou pronto para rodar em produção. Fazendo o merge primeiro na develop, a gente consegue juntar o trabalho de todo mundo, testar de forma integrada e criar branches de release para homologação sem correr o risco de quebrar o ambiente do cliente final.

Q2 — GitHub Flow: por que o Pull Request é obrigatório
No GitHub Flow, nenhuma mudança chega à main sem passar por um Pull Request. O que um PR permite que um merge direto não permitiria? Por que esse modelo adota essa regra?

Resposta:
O Pull Request abre um espaço obrigatório para code review, permitindo que a equipe revise o código, sugira refatorações e discuta a implementação antes de juntar tudo na branch principal. Além do fator humano, o PR é o gatilho perfeito para rodar o pipeline de CI, executando os testes automatizados de forma isolada para garantir que aquela alteração não quebre nada. Esse modelo adota essa regra rígida porque no GitHub Flow a main é integrada direto com o deploy contínuo, ou seja, qualquer merge direto sem validação prévia colocaria bugs em produção imediatamente.
---

### Q3 — Trunk-Based: branches curtas e automação

No Trunk-Based Development, os desenvolvedores criam branches que duram poucas horas. O que tornaria isso perigoso sem um bom suporte técnico? O que precisa existir no projeto para que integrar rápido em `main` seja seguro?

**Resposta:**

_Escreva aqui._

---

### Q4 — Feature Flags

Leia o arquivo [`docs/feature-flags.md`](../docs/feature-flags.md) neste repositório antes de responder. O que são feature flags e qual problema elas resolvem no Trunk-Based Development? Por que sem feature flags seria mais difícil commitar código incompleto em `main`?

**Resposta:**

_Escreva aqui._

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
