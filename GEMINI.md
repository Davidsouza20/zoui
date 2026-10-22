# GEMINI.md

Instruções obrigatórias para o Gemini ao trabalhar neste repositório. Estas regras são coerentes com [`AGENTS.md`](AGENTS.md) e [`CLAUDE.md`](CLAUDE.md) — nenhuma delas é mais permissiva que as outras.

## Leitura obrigatória antes de qualquer tarefa

Antes de analisar o código, responder perguntas técnicas ou fazer qualquer alteração, leia integralmente [`.docs-ai/MASTER.md`](.docs-ai/MASTER.md) — ponto de entrada obrigatório da documentação técnica, com índice completo, regras de evidência/segurança, roteamento por tipo de alteração e política de ADRs.

## Fluxo obrigatório de sincronização com `origin/release`

Antes de iniciar qualquer análise ou alteração:

1. Leia este arquivo e o `.docs-ai/MASTER.md`.
2. Identifique a branch atual e rode `git status`, preservando qualquer alteração local existente.
3. Rode `git fetch origin release`.
4. **Se `origin/release` não existir** (confirmado em 2026-10-21 — único remote é `origin`, única branch remota é `main`), registre isso e siga direto para a tarefa, sem bloquear.
5. **Se `origin/release` existir**, faça merge não interativo dela na branch atual, resolvendo conflitos em código e documentação (incluindo `AGENTS.md`, `CLAUDE.md`, `GEMINI.md` e `.docs-ai/`) antes de começar a tarefa. Não descarte alterações de nenhum dos lados sem análise. Se a resolução exigir uma decisão de negócio, pare e pergunte ao usuário.

## Regras essenciais

- Não invente informação técnica — toda afirmação precisa de evidência rastreável (arquivo, símbolo, rota, comando). Use os marcadores definidos em `.docs-ai/_convencoes-internas.md` para incerteza.
- Nunca reproduza segredos (senhas, tokens, chaves, dados pessoais) — use marcadores como `<API_TOKEN>`.
- Toda nova funcionalidade, correção de bug ou mudança de comportamento exige testes automatizados na mesma alteração. Sem teste viável, pare e peça autorização explícita ao usuário antes de considerar a tarefa concluída.
- Alterações de comportamento seguem duas etapas: implementar e testar → pedir confirmação explícita → só então atualizar `.docs-ai/` e o ADR correspondente (política completa em `.docs-ai/12-decisoes-arquiteturais/README.md`). Tarefas exclusivamente documentais não exigem essa pausa.
- Siga o roteamento mínimo de documentação por tipo de alteração descrito em `.docs-ai/MASTER.md` (seção 7).
