---
titulo: "Pontos não confirmados"
modulo: "geral"
tipo: "visao-geral"
status_documentacao: "requer-validacao-humana"
fontes_principais:
  - "."
  - "index.html"
ultima_analise: "2026-10-21"
---

# Pontos não confirmados

| Ponto | Por que não foi possível confirmar | Onde está registrado |
|---|---|---|
| Hospedagem/provedor de deploy real | Nenhum arquivo de configuração de build/deploy/CI no repositório | [`../09-operacao/deploy-e-rollback.md`](../09-operacao/deploy-e-rollback.md) |
| Domínio customizado em produção | Não há evidência de domínio no repositório (nem `CNAME`, nem referências) | — |
| Destino final dos dados de lead após o envio do Tally (CRM, planilha, e-mail, webhook) | Configuração do formulário Tally vive na conta Tally.so, fora deste repositório | [`../05-fluxos/captura-de-lead.md`](../05-fluxos/captura-de-lead.md) |
| Schema exato dos campos do formulário de inscrição (`xVx6zJ`) | O conteúdo do formulário é renderizado pelo Tally dentro do iframe; não há schema no repositório | [`../07-integracoes/matriz-de-integracoes.md`](../07-integracoes/matriz-de-integracoes.md) |
| Página de "Política de Privacidade" | Link aponta para `href="#"`, marcado com `TODO` pelo próprio autor do código (`index.html`, linha 401) | [`../08-interfaces/mapa-de-interfaces.md`](../08-interfaces/mapa-de-interfaces.md) |
| Relação entre este repositório e o produto "Zoui" em si (o assistente de WhatsApp) | O repositório contém apenas a landing page de captação; não há evidência do backend/produto aqui | [`../00-visao-geral/mapa-inicial-do-sistema.md`](../00-visao-geral/mapa-inicial-do-sistema.md) |

Perguntas diretas derivadas destes pontos: [`perguntas-para-validacao-humana.md`](perguntas-para-validacao-humana.md).
