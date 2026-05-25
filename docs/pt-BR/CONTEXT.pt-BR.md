> Tradução não-oficial para PT-BR. Fonte: [CONTEXT.md](../../CONTEXT.md)

# Matt Pocock Skills

Uma coleção de agent skills (slash commands e comportamentos) carregados pelo Claude Code. As skills são organizadas em buckets e consumidas pela configuração por repositório emitida por `/setup-matt-pocock-skills`.

## Linguagem

**Issue tracker** (rastreador de issues):
A ferramenta que hospeda as issues de um repositório — GitHub Issues, Linear, uma convenção local em markdown `.scratch/`, ou similar. Skills como `to-issues`, `to-prd`, `triage` e `qa` leem e escrevem nele.
_Evitar_: backlog manager, backlog backend, issue host

**Issue** (unidade de trabalho rastreada):
Uma única unidade de trabalho rastreada dentro de um **Issue tracker** — um bug, tarefa, PRD ou fatia produzida por `to-issues`.
_Evitar_: ticket (use apenas ao citar sistemas externos que as chamam de tickets)

**Triage role** (papel de triagem):
Um rótulo canônico de máquina de estados aplicado a uma **Issue** durante a triagem (ex.: `needs-triage`, `ready-for-afk`). Cada role mapeia para uma string de label real no **Issue tracker** via `docs/agents/triage-labels.md`.

## Relacionamentos

- Um **Issue tracker** contém muitas **Issues**
- Uma **Issue** carrega um **Triage role** por vez

## Ambiguidades sinalizadas

- "backlog" era anteriormente usado para significar tanto a *ferramenta* que hospeda issues quanto o *corpo de trabalho* dentro dela — resolvido: a ferramenta é o **Issue tracker**; "backlog" não é mais usado como termo de domínio.
- "backlog backend" / "backlog manager" — resolvido: colapsados em **Issue tracker**.
