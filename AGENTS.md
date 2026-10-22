# AGENTS.md

Instruções obrigatórias para qualquer agente de IA que analise ou modifique este repositório.

## Leitura obrigatória antes de qualquer tarefa

Antes de analisar o código, responder perguntas técnicas ou fazer qualquer alteração, leia integralmente:

1. [`.docs-ai/MASTER.md`](.docs-ai/MASTER.md) — ponto de entrada obrigatório da documentação técnica.

O `MASTER.md` contém o índice completo da documentação (`.docs-ai/`), as regras de evidência e segurança, o roteamento de documentação por tipo de alteração e a política de ADRs. Não duplique esse conteúdo aqui — esta página só resume o fluxo de sincronização e as regras mais críticas.

## Fluxo obrigatório de sincronização com `origin/release`

Antes de iniciar qualquer análise ou alteração:

1. Leia este arquivo e o `.docs-ai/MASTER.md`.
2. Identifique a branch atual e rode `git status`, preservando qualquer alteração local existente (nunca descarte, resete ou sobrescreva trabalho não commitado sem autorização explícita).
3. Rode `git fetch origin release`.
4. **Se a branch `origin/release` não existir** (situação confirmada em 2026-10-21 — este repositório tem apenas a branch remota `main`), registre esse fato e siga direto para a tarefa, sem bloquear.
5. **Se `origin/release` existir**, faça merge não interativo dela na branch de trabalho atual. Resolva qualquer conflito tanto em código quanto em documentação (incluindo `AGENTS.md`, `CLAUDE.md`, `GEMINI.md` e tudo em `.docs-ai/`) antes de iniciar a tarefa, preservando alterações legítimas de ambos os lados. Não escolha automaticamente "ours" ou "theirs" para todos os arquivos. Se a resolução depender de uma decisão de negócio, pare e pergunte ao usuário.

## Regras essenciais

- **Não invente.** Toda afirmação técnica precisa de evidência rastreável no código/configuração/histórico. Quando não for possível confirmar, diga isso explicitamente.
- **Nunca reproduza segredos** (senhas, tokens, chaves, dados pessoais) na documentação ou em respostas. Use marcadores (`<API_TOKEN>`, etc.).
- **Toda nova funcionalidade ou correção de bug exige testes automatizados na mesma alteração**, na camada de teste mais adequada disponível para este tipo de projeto. Se for tecnicamente inviável, explique o impedimento e peça autorização explícita ao usuário antes de considerar a tarefa concluída.
- **Alterações de comportamento** seguem duas etapas: implementar + testar → pedir confirmação explícita ao usuário → só então atualizar `.docs-ai/` e o ADR correspondente. Tarefas exclusivamente documentais não exigem essa pausa.
- **Mantenha código e documentação sincronizados.** Use o roteamento mínimo por tipo de alteração descrito em `.docs-ai/MASTER.md` (seção 7) para saber quais documentos revisar a cada mudança.
