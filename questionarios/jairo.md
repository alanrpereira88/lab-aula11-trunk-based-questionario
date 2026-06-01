Q1 — Git Flow: o papel da branch develop
No Git Flow, existe uma branch chamada develop, separada da main. Qual é o propósito dela? Por que o Git Flow não faz merge de features direto na main?

Resposta:
A branch develop serve como a nossa linha de frente para integrar o código de todas as novas funcionalidades que a equipe está desenvolvendo. O Git Flow não joga as features direto na main porque ela é sagrada e só deve conter código 100% estável que já está rodando ou pronto para rodar em produção. Fazendo o merge primeiro na develop, a gente consegue juntar o trabalho de todo mundo, testar de forma integrada e criar branches de release para homologação sem correr o risco de quebrar o ambiente do cliente final.

Q2 — GitHub Flow: por que o Pull Request é obrigatório
No GitHub Flow, nenhuma mudança chega à main sem passar por um Pull Request. O que um PR permite que um merge direto não permitiria? Por que esse modelo adota essa regra?

Resposta:
O Pull Request abre um espaço obrigatório para code review, permitindo que a equipe revise o código, sugira refatorações e discuta a implementação antes de juntar tudo na branch principal. Além do fator humano, o PR é o gatilho perfeito para rodar o pipeline de CI, executando os testes automatizados de forma isolada para garantir que aquela alteração não quebre nada. Esse modelo adota essa regra rígida porque no GitHub Flow a main é integrada direto com o deploy contínuo, ou seja, qualquer merge direto sem validação prévia colocaria bugs em produção imediatamente.


Q3 — Trunk-Based: branches curtas e automação
No Trunk-Based Development, os desenvolvedores criam branches que duram poucas horas. O que tornaria isso perigoso sem um bom suporte técnico? O que precisa existir no projeto para que integrar rápido em main seja seguro?

Resposta:
Subir alterações para a branch principal toda hora seria um caos sem suporte técnico, porque o risco de um desenvolvedor sobrescrever o código do outro ou introduzir um bug crítico na main é gigantesco. Para que esse processo de integração rápida funcione com segurança, o projeto precisa obrigatoriamente de uma esteira de CI/CD muito madura e com excelente cobertura de testes automatizados. A automação precisa validar cada pequeno commit em questão de minutos, dando feedback rápido para o time se algo quebrar.

Q4 — Feature Flags
Leia o arquivo docs/feature-flags.md neste repositório antes de responder. O que são feature flags e qual problema elas resolvem no Trunk-Based Development? Por que sem feature flags seria mais difícil commitar código incompleto em main?

Resposta:
Feature flags são essencialmente variáveis ou condicionais no código que permitem ativar ou desativar uma funcionalidade em tempo de execução sem precisar fazer um novo deploy. No Trunk-Based, elas resolvem o problema de termos que subir códigos de features longas que ainda não estão prontas, mantendo o trecho de código "escondido" do usuário final. Sem o uso de feature flags seria quase impossível commitar código incompleto na main, já que qualquer código integrado iria direto para o ar, quebrando a aplicação ou exibindo telas inacabadas para os usuários.

Q5 — O que o --no-ff garante no histórico

A flag --no-ff força o Git a criar um commit de merge dedicado, mesmo que as branches estivessem alinhadas de forma linear. O Git Flow adota essa prática porque ela mantém o histórico do projeto bem documentado, deixando explícito exatamente onde começou e terminou o desenvolvimento de uma feature específica. Visualmente, quando rodamos o git log --graph, o merge padrão (fast-forward) esmaga tudo em uma linha reta só, enquanto o --no-ff desenha aquela famosa "curva" ou ramificação que se abre e depois fecha de volta na branch principal.

Q6 — Comparativo: Git Flow vs GitHub Flow

No dia a dia com o Git Flow, o ritmo de trabalho é mais cadenciado e burocrático, já que passamos por várias branches (feature, develop, release) e o código demora a ver a cor da produção. No GitHub Flow o processo é muito mais ágil e dinâmico: o desenvolvedor cria uma branch curta a partir da main, abre o PR, recebe o feedback e, assim que o merge é aprovado, a alteração já vai direto para o ar em produção.

Q7 — Escolha justificada
Resposta:
Eu escolheria o Git Flow para esse cenário de desenvolvimento mobile. Como o ciclo de lançamento é bem espaçado (a cada 3 meses) e exige um período longo de testes e homologação para evitar bugs críticos nas lojas de apps, a estrutura de branches de release e develop do Git Flow se encaixa perfeitamente para estabilizar a build. Além disso, como o time é bem enxuto, com apenas 4 pessoas, a complexidade de gerenciar essas branches extras do fluxo não gera gargalos e garante uma organização robusta para as entregas trimestrais.

Q8 — Reflexão sobre a prática
Resposta:
Para mim, o Trunk-Based Development foi o fluxo mais desafiador de praticar por exigir uma mudança radical na forma de pensar o desenvolvimento. O mais difícil é pegar um problema complexo e ter a disciplina de quebrar o código em commits minúsculos que duram poucas horas, perdendo aquela zona de conforto de passar dias isolado em uma branch de feature própria. Além disso, a lógica de ter que usar feature flags para subir códigos intencionalmente incompletos na main exige uma atenção técnica muito maior para não quebrar a aplicação em produção.