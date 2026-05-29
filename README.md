# Lab — Trunk-Based Development: Questionário

**DevOps I · Unidade 2 · Aula 11**

---

## Objetivo

Praticar o fluxo real de Trunk-Based Development enquanto responde questões sobre estratégias de branching. A atividade tem **dois rounds** que usam formas diferentes de integrar à `main` — ao final você vai ver a diferença no histórico com `git log --graph`.

---

## Os dois rounds

| | Round 1 | Round 2 |
|--|---------|---------|
| **Questões** | Q1 a Q4 | Q5 a Q8 |
| **Branch** | `short/q1q4-[seu-nome]` | `short/q5q8-[seu-nome]` |
| **Merge** | `git merge --no-ff` | `git merge` (fast-forward) |
| **Resultado no log** | merge commit explícito | histórico linear |

---

## Instruções detalhadas

Leia [`docs/instrucoes.md`](docs/instrucoes.md) antes de começar.

---

## Template

Copie [`questionarios/_template.md`](questionarios/_template.md) para `questionarios/[seu-nome].md` e preencha ao longo dos dois rounds.

---

## Comparativo final

Ao terminar os dois rounds, o professor vai rodar com a turma:

```bash
git pull origin main
git log --oneline --graph --all
```

Você vai ver no mesmo histórico os dois padrões lado a lado.
