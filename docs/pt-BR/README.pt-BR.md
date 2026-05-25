> Tradução não-oficial para PT-BR do README original. Fonte: [README.md](../../README.md)

<p>
  <a href="https://www.aihero.dev/s/skills-newsletter">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://res.cloudinary.com/total-typescript/image/upload/v1777382277/skills-repo-dark_2x.png">
      <source media="(prefers-color-scheme: light)" srcset="https://res.cloudinary.com/total-typescript/image/upload/v1777382277/skill-repo-light_2x.png">
      <img alt="Skills" src="https://res.cloudinary.com/total-typescript/image/upload/v1777382277/skill-repo-light_2x.png" width="369">
    </picture>
  </a>
</p>

# Skills Para Engenheiros de Verdade

[![skills.sh](https://skills.sh/b/mattpocock/skills)](https://skills.sh/mattpocock/skills)

Minhas skills de agente que uso todo dia pra fazer engenharia de verdade — não vibe coding.

Desenvolver aplicações reais é difícil. Abordagens como GSD, BMAD e Spec-Kit tentam ajudar tomando conta do processo. Mas ao fazer isso, tiram o seu controle e tornam difícil resolver bugs no próprio processo.

Estas skills foram projetadas para serem pequenas, fáceis de adaptar e combináveis. Funcionam com qualquer modelo. São baseadas em décadas de experiência em engenharia. Mexa nelas. Faça-as suas. Aproveite.

Se você quer acompanhar mudanças nestas skills, e quaisquer novas que eu criar, pode se juntar a outros ~60.000 devs na minha newsletter:

[Inscreva-se na Newsletter](https://www.aihero.dev/s/skills-newsletter)

## Início Rápido (setup de 30 segundos)

1. Rode o instalador do skills.sh:

```bash
npx skills@latest add mattpocock/skills
```

2. Escolha as skills que você quer, e em quais agentes de programação quer instalá-las. **Garanta que você selecione `/setup-matt-pocock-skills`**.

3. Rode `/setup-matt-pocock-skills` no seu agente. Ele vai:
   - Perguntar qual issue tracker você quer usar (GitHub, Linear ou arquivos locais)
   - Perguntar quais labels você aplica em tickets quando faz triagem (`/triage` usa labels)
   - Perguntar onde você quer salvar os documentos que criamos

4. Pronto — você está pronto pra começar.

## Por Que Estas Skills Existem

Eu construí estas skills como uma forma de corrigir modos de falha comuns que vejo no Claude Code, Codex e outros agentes de programação.

### #1: O Agente Não Fez O Que Eu Queria

> "Ninguém sabe exatamente o que quer"
>
> David Thomas & Andrew Hunt, [The Pragmatic Programmer](https://www.amazon.co.uk/Pragmatic-Programmer-Anniversary-Journey-Mastery/dp/B0833F1T3V)

**O Problema**. O modo de falha mais comum em desenvolvimento de software é desalinhamento. Você acha que o dev sabe o que você quer. Depois vê o que ele construiu — e percebe que ele não te entendeu de jeito nenhum.

É a mesma coisa na era da IA. Existe um gap de comunicação entre você e o agente. A correção pra isso é uma **sessão de grilling** — fazer o agente te perguntar questões detalhadas sobre o que você está construindo.

**A Correção** é usar:

- [`/grill-me`](./skills/productivity/grill-me/SKILL.md) — para usos fora de código
- [`/grill-with-docs`](./skills/engineering/grill-with-docs/SKILL.md) — igual ao [`/grill-me`](./skills/productivity/grill-me/SKILL.md), mas adiciona mais coisas boas (veja abaixo)

Estas são minhas skills mais populares. Elas te ajudam a alinhar com o agente antes de começar, e a pensar profundamente sobre a mudança que você está fazendo. Use-as _toda_ vez que quiser fazer uma mudança.

### #2: O Agente É Verboso Demais

> Com uma linguagem ubíqua, conversas entre desenvolvedores e expressões do código são todas derivadas do mesmo modelo de domínio.
>
> Eric Evans, [Domain-Driven-Design](https://www.amazon.co.uk/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215)

**O Problema**: No início de um projeto, devs e as pessoas pra quem estão construindo o software (os especialistas de domínio) geralmente falam línguas diferentes.

Senti a mesma tensão com meus agentes. Agentes geralmente são jogados num projeto e precisam descobrir o jargão conforme vão. Então usam 20 palavras quando 1 bastaria.

**A Correção** pra isso é uma linguagem compartilhada. É um documento que ajuda os agentes a decodificar o jargão usado no projeto.

<details>
<summary>
Exemplo
</summary>

Aqui está um exemplo de [`CONTEXT.md`](https://github.com/mattpocock/course-video-manager/blob/076a5a7a182db0fe1e62971dd7a68bcadf010f1c/CONTEXT.md), do meu repo `course-video-manager`. Qual é mais fácil de ler?

- **ANTES**: "Tem um problema quando uma lição dentro de uma seção de um curso é tornada 'real' (ou seja, recebe um lugar no sistema de arquivos)"
- **DEPOIS**: "Tem um problema com a cascata de materialização"

Essa concisão se paga sessão após sessão.

</details>

Isso está embutido no [`/grill-with-docs`](./skills/engineering/grill-with-docs/SKILL.md). É uma sessão de grilling, mas que te ajuda a construir uma linguagem compartilhada com a IA, e a documentar decisões difíceis de explicar em ADRs.

É difícil explicar quão poderoso isso é. Pode ser a única técnica mais legal deste repo. Experimente e veja.

> [!TIP]
> Uma linguagem compartilhada tem muitos outros benefícios além de reduzir verbosidade:
>
> - **Variáveis, funções e arquivos são nomeados consistentemente**, usando a linguagem compartilhada
> - Como resultado, o **codebase fica mais fácil de navegar** para o agente
> - O agente também **gasta menos tokens pensando**, porque tem acesso a uma linguagem mais concisa

### #3: O Código Não Funciona

> "Sempre dê passos pequenos e deliberados. A taxa de feedback é seu limite de velocidade. Nunca pegue uma tarefa grande demais."
>
> David Thomas & Andrew Hunt, [The Pragmatic Programmer](https://www.amazon.co.uk/Pragmatic-Programmer-Anniversary-Journey-Mastery/dp/B0833F1T3V)

**O Problema**: Digamos que você e o agente estão alinhados sobre o que construir. O que acontece quando o agente _ainda assim_ produz porcaria?

É hora de olhar pros seus loops de feedback. Sem feedback sobre como o código que ele produz realmente roda, o agente vai voar às cegas.

**A Correção**: Você precisa do trio usual de loops de feedback: tipos estáticos, acesso ao browser e testes automatizados.

Para testes automatizados, um loop red-green-refactor é crítico. É onde o agente escreve um teste que falha primeiro, depois corrige o teste. Isso ajuda a dar ao agente um nível consistente de feedback que resulta em código muito melhor.

Eu construí uma **skill [`/tdd`](./skills/engineering/tdd/SKILL.md)** que você pode encaixar em qualquer projeto. Ela encoraja red-green-refactor e dá ao agente bastante orientação sobre o que faz testes bons e ruins.

Para debugging, também construí uma skill **[`/diagnose`](./skills/engineering/diagnose/SKILL.md)** que embrulha as melhores práticas de debugging em um loop simples.

### #4: Construímos Uma Bola de Lama

> "Invista no design do sistema _todos os dias_."
>
> Kent Beck, [Extreme Programming Explained](https://www.amazon.co.uk/Extreme-Programming-Explained-Embrace-Change/dp/0321278658)

> "Os melhores módulos são profundos. Eles permitem que muita funcionalidade seja acessada através de uma interface simples."
>
> John Ousterhout, [A Philosophy Of Software Design](https://www.amazon.co.uk/Philosophy-Software-Design-2nd/dp/173210221X)

**O Problema**: A maioria dos apps construídos com agentes são complexos e difíceis de mudar. Como agentes podem acelerar radicalmente o coding, eles também aceleram a entropia do software. Codebases ficam mais complexos a uma taxa sem precedentes.

**A Correção** pra isso é uma abordagem radicalmente nova para o desenvolvimento com IA: se importar com o design do código.

Isso está embutido em cada camada destas skills:

- [`/to-prd`](./skills/engineering/to-prd/SKILL.md) te questiona sobre quais módulos você está tocando antes de criar um PRD
- [`/zoom-out`](./skills/engineering/zoom-out/SKILL.md) diz ao agente para explicar código no contexto do sistema todo

E crucialmente, [`/improve-codebase-architecture`](./skills/engineering/improve-codebase-architecture/SKILL.md) te ajuda a resgatar um codebase que virou uma bola de lama. Recomendo rodá-la no seu codebase a cada poucos dias.

### Resumo

Os fundamentos de engenharia de software importam mais do que nunca. Estas skills são meu melhor esforço pra condensar esses fundamentos em práticas repetíveis, para te ajudar a entregar os melhores apps da sua carreira. Aproveite.

## Referência

### Engineering

Skills que uso diariamente pra trabalho de código.

- **[diagnose](./skills/engineering/diagnose/SKILL.md)** — Loop disciplinado de diagnóstico para bugs difíceis e regressões de performance: reproduzir → minimizar → levantar hipóteses → instrumentar → corrigir → teste de regressão.
- **[grill-with-docs](./skills/engineering/grill-with-docs/SKILL.md)** — Sessão de grilling que desafia seu plano contra o modelo de domínio existente, refina terminologia e atualiza `CONTEXT.md` e ADRs inline.
- **[triage](./skills/engineering/triage/SKILL.md)** — Triagem de issues através de uma máquina de estados de papéis de triagem.
- **[improve-codebase-architecture](./skills/engineering/improve-codebase-architecture/SKILL.md)** — Encontra oportunidades de aprofundamento em um codebase, informado pela linguagem de domínio em `CONTEXT.md` e as decisões em `docs/adr/`.
- **[setup-matt-pocock-skills](./skills/engineering/setup-matt-pocock-skills/SKILL.md)** — Faz o scaffold da config por repo (issue tracker, vocabulário de labels de triagem, layout de docs de domínio) que as outras skills de engenharia consomem. Rode uma vez por repo antes de usar `to-issues`, `to-prd`, `triage`, `diagnose`, `tdd`, `improve-codebase-architecture` ou `zoom-out`.
- **[tdd](./skills/engineering/tdd/SKILL.md)** — Desenvolvimento orientado a testes com um loop red-green-refactor. Constrói features ou corrige bugs uma fatia vertical por vez.
- **[to-issues](./skills/engineering/to-issues/SKILL.md)** — Quebra qualquer plano, spec ou PRD em issues do GitHub pegáveis de forma independente, usando fatias verticais.
- **[to-prd](./skills/engineering/to-prd/SKILL.md)** — Transforma o contexto atual da conversa em um PRD e submete como issue do GitHub. Sem entrevista — só sintetiza o que você já discutiu.
- **[zoom-out](./skills/engineering/zoom-out/SKILL.md)** — Diz ao agente para dar um zoom out e oferecer contexto mais amplo ou uma perspectiva de mais alto nível sobre uma seção desconhecida de código.
- **[prototype](./skills/engineering/prototype/SKILL.md)** — Constrói um protótipo descartável pra dar corpo a um design — ou um app de terminal executável para questões de estado/lógica de negócio, ou várias variações radicalmente diferentes de UI alternáveis a partir de uma única rota.

### Productivity

Ferramentas gerais de workflow, não específicas de código.

- **[caveman](./skills/productivity/caveman/SKILL.md)** — Modo de comunicação ultra-comprimido. Corta uso de tokens em ~75% derrubando enrolação e mantendo acurácia técnica completa.
- **[grill-me](./skills/productivity/grill-me/SKILL.md)** — Seja entrevistado implacavelmente sobre um plano ou design até que cada ramo da árvore de decisão esteja resolvido.
- **[handoff](./skills/productivity/handoff/SKILL.md)** — Compacta a conversa atual em um documento de handoff para que outro agente possa continuar o trabalho.
- **[write-a-skill](./skills/productivity/write-a-skill/SKILL.md)** — Cria novas skills com estrutura adequada, divulgação progressiva e recursos empacotados.

### Misc

Ferramentas que mantenho por perto mas raramente uso.

- **[git-guardrails-claude-code](./skills/misc/git-guardrails-claude-code/SKILL.md)** — Configura hooks do Claude Code para bloquear comandos git perigosos (push, reset --hard, clean, etc.) antes que executem.
- **[migrate-to-shoehorn](./skills/misc/migrate-to-shoehorn/SKILL.md)** — Migra arquivos de teste de asserções de tipo `as` para @total-typescript/shoehorn.
- **[scaffold-exercises](./skills/misc/scaffold-exercises/SKILL.md)** — Cria estruturas de diretório de exercícios com seções, problemas, soluções e explicações.
- **[setup-pre-commit](./skills/misc/setup-pre-commit/SKILL.md)** — Configura hooks pre-commit do Husky com lint-staged, Prettier, type checking e testes.
