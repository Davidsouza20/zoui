---
titulo: "MASTER — Ponto de entrada da documentação técnica"
modulo: "geral"
tipo: "visao-geral"
status_documentacao: "confirmado"
fontes_principais:
  - "index.html"
  - ".git"
ultima_analise: "2026-10-21"
---

# MASTER — Documentação técnica do repositório `gestao-financeira` (produto "Zoui")

Este arquivo é o **ponto de entrada obrigatório** para qualquer humano ou agente (IA) que for analisar, documentar ou alterar este repositório. Leia-o por completo antes de abrir qualquer outro documento ou de modificar o código.

## 1. O que é este repositório

Landing page estática de captura de leads para o produto **Zoui** ("Organize o financeiro do seu negócio pelo WhatsApp"). Todo o sistema está contido em um único arquivo versionado: [`index.html`](../index.html). Não há backend próprio, build, testes ou pipeline de CI/CD neste repositório.

Detalhes confirmados: [`00-visao-geral/mapa-inicial-do-sistema.md`](00-visao-geral/mapa-inicial-do-sistema.md).

## 2. Procedimento de leitura

Ordem recomendada para quem está chegando agora:

1. Este `MASTER.md`.
2. [`00-visao-geral/mapa-inicial-do-sistema.md`](00-visao-geral/mapa-inicial-do-sistema.md) — visão geral do produto e da stack.
3. [`01-arquitetura/arquitetura-atual.md`](01-arquitetura/arquitetura-atual.md) — como as peças se conectam.
4. [`02-estrutura-de-codigo/pontos-de-entrada.md`](02-estrutura-de-codigo/pontos-de-entrada.md) — onde cada comportamento está implementado dentro de `index.html`.
5. [`05-fluxos/captura-de-lead.md`](05-fluxos/captura-de-lead.md) — o único fluxo de negócio do sistema.
6. [`07-integracoes/matriz-de-integracoes.md`](07-integracoes/matriz-de-integracoes.md) e [`10-inventarios/inventario-de-integracoes.md`](10-inventarios/inventario-de-integracoes.md) — serviços de terceiros.
7. [`11-pendencias-de-entendimento/pontos-nao-confirmados.md`](11-pendencias-de-entendimento/pontos-nao-confirmados.md) — o que ainda não foi comprovado.

## 3. Índice completo

- `00-visao-geral/`
  - [`mapa-inicial-do-sistema.md`](00-visao-geral/mapa-inicial-do-sistema.md)
  - [`glossario.md`](00-visao-geral/glossario.md)
  - [`relatorio-de-cobertura.md`](00-visao-geral/relatorio-de-cobertura.md)
- `01-arquitetura/`
  - [`arquitetura-atual.md`](01-arquitetura/arquitetura-atual.md)
- `02-estrutura-de-codigo/`
  - [`mapa-de-diretorios.md`](02-estrutura-de-codigo/mapa-de-diretorios.md)
  - [`pontos-de-entrada.md`](02-estrutura-de-codigo/pontos-de-entrada.md)
- `05-fluxos/`
  - [`captura-de-lead.md`](05-fluxos/captura-de-lead.md)
- `07-integracoes/`
  - [`matriz-de-integracoes.md`](07-integracoes/matriz-de-integracoes.md)
- `08-interfaces/`
  - [`mapa-de-interfaces.md`](08-interfaces/mapa-de-interfaces.md)
- `09-operacao/`
  - [`deploy-e-rollback.md`](09-operacao/deploy-e-rollback.md)
- `10-inventarios/`
  - [`inventario-de-integracoes.md`](10-inventarios/inventario-de-integracoes.md)
- `11-pendencias-de-entendimento/`
  - [`pontos-nao-confirmados.md`](11-pendencias-de-entendimento/pontos-nao-confirmados.md)
  - [`perguntas-para-validacao-humana.md`](11-pendencias-de-entendimento/perguntas-para-validacao-humana.md)
- `12-decisoes-arquiteturais/`
  - [`README.md`](12-decisoes-arquiteturais/README.md)
  - [`ADR-0000-template.md`](12-decisoes-arquiteturais/ADR-0000-template.md)

### Áreas do template padrão intencionalmente não criadas

A árvore documental completa sugerida pelo processo de documentação inclui pastas que não têm conteúdo real neste repositório (sem backend, sem persistência própria, sem múltiplos módulos). Elas foram omitidas para não criar documentos vazios. Ver justificativa detalhada em [`00-visao-geral/relatorio-de-cobertura.md`](00-visao-geral/relatorio-de-cobertura.md): `03-persistencia/`, `04-modulos/`, `06-apis-e-endpoints/`, `atores-e-perfis.md`, `01-arquitetura/jobs-crons-e-processos.md`, `01-arquitetura/infraestrutura.md`, `09-operacao/ambiente-de-desenvolvimento.md`, `09-operacao/monitoramento-e-logs.md`, `10-inventarios/inventario-de-modulos.md`, `inventario-de-dados.md`, `inventario-de-jobs.md`.

Se, no futuro, o repositório ganhar backend, build, testes ou múltiplos módulos, essas pastas devem ser criadas seguindo os mesmos padrões deste documento.

## 4. Natureza evolutiva da documentação

Esta documentação é um **mapa, não a fonte absoluta da verdade**. Ela reflete o melhor conhecimento confirmado em `ultima_analise` de cada documento. Antes de tomar qualquer decisão, valide o documento relevante contra o estado atual de `index.html` e do histórico Git. Se houver divergência entre o documentado e o código, registre a divergência no documento afetado e atualize `ultima_analise`.

## 5. Regras de evidência e segurança

- Toda afirmação técnica relevante deve ter evidência rastreável (arquivo, símbolo/ID, rota ou comando). Ver convenções completas em [`_convencoes-internas.md`](_convencoes-internas.md).
- Quando não for possível confirmar algo, use: "Não foi possível confirmar esta informação apenas pelas evidências disponíveis."
- Quando houver indícios mas não comprovação completa, use: "Hipótese técnica baseada nas evidências encontradas. Requer validação manual."
- Nunca reproduza segredos (senhas, tokens, chaves, cookies, dados pessoais) na documentação. Use marcadores (`<DB_PASSWORD>`, `<API_TOKEN>`, etc.). Se encontrar um segredo versionado, registre apenas a pendência de segurança e o caminho do arquivo, sem expor o valor.
- O Measurement ID do Google Analytics 4 (`G-EWHZQ9692Z`), presente em `index.html`, é citado nesta documentação por ser um identificador público por natureza do GA4 client-side — não é um segredo.

## 6. Fluxo obrigatório de desenvolvimento

Toda nova tarefa neste repositório, antes de qualquer análise ou alteração, deve seguir:

1. Ler as instruções de raiz (`AGENTS.md`, `CLAUDE.md`, `GEMINI.md`) e este `MASTER.md`.
2. Identificar a branch atual e rodar `git status`, preservando qualquer alteração local existente.
3. Rodar `git fetch origin release`.
4. **Se `origin/release` não existir** (caso confirmado em 2026-10-21 — único remote é `origin` → `https://github.com/Davidsouza20/zoui.git`, com única branch remota `main`), registrar esse fato e seguir direto para a análise da tarefa, sem bloquear.
5. Se `origin/release` existir (cenário futuro), fazer merge não interativo de `origin/release` na branch de trabalho, resolver eventuais conflitos de código e documentação preservando ambos os lados, validar e só então iniciar a tarefa.
6. Validar a documentação relevante (`.docs-ai/`) contra o estado atual de `index.html` antes de decidir o que alterar.
7. Implementar apenas o solicitado. Para mudanças de comportamento, seguir o fluxo de duas etapas (implementar + testar → pedir confirmação → só então atualizar documentação) descrito no processo de desenvolvimento contínuo. Tarefas exclusivamente documentais (como a criação inicial desta documentação) não exigem esse pedido intermediário.
8. Toda nova funcionalidade, correção de bug ou mudança de comportamento deve incluir testes automatizados na mesma alteração, na camada mais adequada disponível para este tipo de projeto (ex.: testes de snapshot/HTML, verificação de acessibilidade, scripts de smoke test). Se não houver suíte de testes no repositório no momento da mudança, isso deve ser registrado explicitamente e a criação da suíte mínima necessária faz parte da própria mudança, salvo impossibilidade técnica justificada e aceita explicitamente pelo usuário.
9. Atualizar a documentação afetada (ver roteamento abaixo) e o ADR correspondente após confirmação do usuário.

## 7. Roteamento mínimo por tipo de alteração

| Tipo de alteração neste repositório | Documentos a revisar no mínimo |
|---|---|
| Texto, copy ou estrutura visual da landing page | `08-interfaces/mapa-de-interfaces.md`, `05-fluxos/captura-de-lead.md` |
| Alteração no embed do Tally (ID do formulário, parâmetros) | `07-integracoes/matriz-de-integracoes.md`, `10-inventarios/inventario-de-integracoes.md`, `05-fluxos/captura-de-lead.md` |
| Alteração no GA4 (Measurement ID, eventos, parâmetros) | `07-integracoes/matriz-de-integracoes.md`, `10-inventarios/inventario-de-integracoes.md`, `05-fluxos/captura-de-lead.md` |
| Alteração de hospedagem, domínio ou deploy | `09-operacao/deploy-e-rollback.md`, `01-arquitetura/arquitetura-atual.md` |
| Introdução de backend, build, framework JS ou múltiplos arquivos | `01-arquitetura/arquitetura-atual.md`, `02-estrutura-de-codigo/*`, possível criação das pastas hoje omitidas (ver seção 3) |
| Qualquer mudança de comportamento | ADR correspondente em `12-decisoes-arquiteturais/` |

Este é o mínimo. Siga referências cruzadas e revise qualquer outro documento afetado.

## 8. Política de ADRs

Toda alteração aprovada que afete comportamento técnico deve criar ou atualizar um ADR em `12-decisoes-arquiteturais/`, seguindo o padrão `ADR-NNNN-titulo-curto.md` e o template em [`ADR-0000-template.md`](12-decisoes-arquiteturais/ADR-0000-template.md). Ver política completa em [`12-decisoes-arquiteturais/README.md`](12-decisoes-arquiteturais/README.md).

## 9. Critérios de conclusão

Uma tarefa de documentação inicial é considerada concluída quando `AGENTS.md`, `CLAUDE.md` e `GEMINI.md` existirem na raiz e apontarem para este `MASTER.md`; o mapa geral, os pontos de entrada, a arquitetura observável, as integrações e as pendências estiverem registrados; fatos, hipóteses e pendências estiverem separados; e a cobertura estiver documentada com suas limitações.

Uma alteração de desenvolvimento só é considerada concluída quando o comportamento solicitado estiver implementado e testado, o usuário tiver confirmado, a documentação afetada e o ADR tiverem sido atualizados, e nenhuma pendência de sincronização com `origin/release` estiver em aberto.
