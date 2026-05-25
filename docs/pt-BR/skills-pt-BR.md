# Índice de Skills (PT-BR)

> Tradução não-oficial. Para cada skill, ver o SKILL.md original linkado.

## Engineering

- **[diagnose](../../skills/engineering/diagnose/SKILL.md)** — Loop disciplinado de diagnóstico para bugs difíceis e regressões de performance: reproduzir → minimizar → hipotetizar → instrumentar → corrigir → testar contra regressão. Use quando o usuário disser "diagnostique isso", "debug isso", relatar um bug, falha ou regressão de desempenho.
- **[grill-with-docs](../../skills/engineering/grill-with-docs/SKILL.md)** — Sessão de sabatina que testa seu plano contra o modelo de domínio existente, refina a terminologia e atualiza a documentação (CONTEXT.md, ADRs) à medida que decisões surgem. Use quando quiser estressar um plano contra a linguagem e decisões documentadas do projeto.
- **[improve-codebase-architecture](../../skills/engineering/improve-codebase-architecture/SKILL.md)** — Encontra oportunidades de aprofundamento na arquitetura do código, guiado pela linguagem de domínio em CONTEXT.md e pelas decisões em docs/adr/. Use para melhorar arquitetura, achar refactors, consolidar módulos acoplados ou tornar o código mais testável e navegável por IA.
- **[prototype](../../skills/engineering/prototype/SKILL.md)** — Constrói um protótipo descartável para amadurecer um design antes de se comprometer. Roteia entre duas vertentes: app de terminal executável para perguntas de estado/lógica de negócio, ou várias variações radicais de UI alternáveis numa rota só. Use para prototipar, validar modelo de dados/máquina de estados, ou explorar opções de design.
- **[setup-matt-pocock-skills](../../skills/engineering/setup-matt-pocock-skills/SKILL.md)** — Configura um bloco `## Agent skills` em AGENTS.md/CLAUDE.md e a pasta `docs/agents/` para que as skills de engenharia conheçam o issue tracker do repo, o vocabulário de labels de triagem e o layout de docs de domínio. Rode antes do primeiro uso de to-issues, to-prd, triage, diagnose, tdd, improve-codebase-architecture ou zoom-out.
- **[tdd](../../skills/engineering/tdd/SKILL.md)** — Desenvolvimento orientado a testes com loop red-green-refactor. Use para construir features ou corrigir bugs via TDD, testes de integração, ou desenvolvimento test-first.
- **[to-issues](../../skills/engineering/to-issues/SKILL.md)** — Quebra um plano, spec ou PRD em issues independentes no tracker do projeto, usando fatias verticais "bala traçante". Use para converter um plano em issues ou decompor trabalho em tickets.
- **[to-prd](../../skills/engineering/to-prd/SKILL.md)** — Transforma o contexto atual da conversa num PRD e publica no tracker do projeto. Use quando quiser gerar um PRD a partir da discussão atual.
- **[triage](../../skills/engineering/triage/SKILL.md)** — Triagem de issues por uma máquina de estados guiada por papéis de triagem. Use para criar issue, triar, revisar bugs/feature requests, preparar issues para um agente AFK ou gerenciar o workflow.
- **[zoom-out](../../skills/engineering/zoom-out/SKILL.md)** — Pede ao agente para "dar um zoom out" e fornecer contexto mais amplo ou perspectiva de alto nível. Use quando não conhecer uma seção do código ou precisar entender como ela se encaixa no todo.

## Productivity

- **[caveman](../../skills/productivity/caveman/SKILL.md)** — Modo de comunicação ultra-comprimido. Reduz o uso de tokens em ~75% removendo encheção, artigos e cortesias, mantendo precisão técnica total. Use ao dizer "modo caveman", "fala como caveman".
- **[grill-me](../../skills/productivity/grill-me/SKILL.md)** — Entrevista o usuário implacavelmente sobre um plano ou design até chegar a entendimento compartilhado, resolvendo cada ramo da árvore de decisão. Use para estressar um plano ou pedir "me sabatine".
- **[handoff](../../skills/productivity/handoff/SKILL.md)** — Compacta a conversa atual num documento de handoff para outro agente continuar o trabalho.
- **[write-a-skill](../../skills/productivity/write-a-skill/SKILL.md)** — Cria novas agent skills com estrutura adequada, disclosure progressivo e recursos empacotados. Use ao querer criar, escrever ou montar uma nova skill.

## Misc

- **[git-guardrails-claude-code](../../skills/misc/git-guardrails-claude-code/SKILL.md)** — Configura hooks do Claude Code para bloquear comandos git perigosos (push, reset --hard, clean, branch -D etc.) antes da execução. Use para prevenir operações destrutivas ou adicionar hooks de segurança git.
- **[migrate-to-shoehorn](../../skills/misc/migrate-to-shoehorn/SKILL.md)** — Migra arquivos de teste de asserções `as` para @total-typescript/shoehorn. Use ao mencionar shoehorn, substituir `as` em testes ou precisar de dados de teste parciais.
- **[scaffold-exercises](../../skills/misc/scaffold-exercises/SKILL.md)** — Cria estruturas de diretório de exercícios com sections, problems, solutions e explainers que passam no lint. Use para esqueletar exercícios ou montar uma nova seção de curso.
- **[setup-pre-commit](../../skills/misc/setup-pre-commit/SKILL.md)** — Configura hooks pre-commit com Husky + lint-staged (Prettier), type-check e testes no repo atual. Use para adicionar pre-commit hooks, configurar Husky/lint-staged ou rodar formatação/typecheck/testes no commit.
