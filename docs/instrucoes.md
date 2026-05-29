# Instruções de Entrega

## Antes de começar

```bash
git clone git@github-univertix:alanrpereira88/lab-aula11-trunk-based-questionario.git
cd lab-aula11-trunk-based-questionario
```

---

## Round 1 — com `--no-ff` (Q1 a Q4)

O `--no-ff` força a criação de um **merge commit explícito**, mesmo que o fast-forward fosse possível. O histórico vai registrar que existiu uma branch.

```bash
# 1. Garantir que a main está atualizada
git checkout main
git pull origin main

# 2. Criar branch curta
git checkout -b short/q1q4-[seu-nome]

# 3. Copiar o template
cp questionarios/_template.md questionarios/[seu-nome].md

# 4. Responder Q1 e Q2, depois commitar
git add questionarios/[seu-nome].md
git commit -m "docs(q1q4): Q1 e Q2 - [seu-nome]"

# 5. Responder Q3 e Q4, depois commitar
git add questionarios/[seu-nome].md
git commit -m "docs(q1q4): Q3 e Q4 - [seu-nome]"

# 6. Integrar na main COM --no-ff e deletar a branch
git checkout main
git merge --no-ff short/q1q4-[seu-nome] -m "merge(q1q4): integra respostas de [seu-nome]"
git branch -d short/q1q4-[seu-nome]
git push origin main
```

---

## Round 2 — sem `--no-ff` / fast-forward (Q5 a Q8)

Sem `--no-ff`, o Git faz **fast-forward**: os commits da branch aparecem diretamente na `main`, como se nunca tivessem estado em outra branch. Histórico linear, sem merge commit.

```bash
# 1. Atualizar main (pode ter chegado commits de colegas)
git checkout main
git pull origin main

# 2. Criar branch curta
git checkout -b short/q5q8-[seu-nome]

# 3. Abrir o arquivo e responder Q5 e Q6
git add questionarios/[seu-nome].md
git commit -m "docs(q5q8): Q5 e Q6 - [seu-nome]"

# 4. Responder Q7 e Q8
git add questionarios/[seu-nome].md
git commit -m "docs(q5q8): Q7 e Q8 - [seu-nome]"

# 5. Integrar na main SEM --no-ff e deletar a branch
git checkout main
git merge short/q5q8-[seu-nome]
git branch -d short/q5q8-[seu-nome]
git push origin main
```

---

## Se der conflito no push

Outro aluno fez push antes de você. Resolva assim:

```bash
git pull origin main --rebase
git push origin main
```

---

## Critérios de avaliação

- [ ] Arquivo `questionarios/[seu-nome].md` presente na `main` com todas as 8 questões respondidas
- [ ] Round 1: merge commit visível no `git log` (gerado pelo `--no-ff`)
- [ ] Round 2: commits diretos na `main` sem merge commit extra (fast-forward)
- [ ] Branches `short/` deletadas após cada round
- [ ] Mensagens de commit no padrão Conventional Commits
