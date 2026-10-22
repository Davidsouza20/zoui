---
titulo: "Matriz de integrações"
modulo: "geral"
tipo: "integracao"
status_documentacao: "parcialmente-confirmado"
fontes_principais:
  - "index.html"
ultima_analise: "2026-10-21"
---

# Matriz de integrações

| Integração | Como é carregada | Dados que trafegam (observados) | Estado |
|---|---|---|---|
| Google Analytics 4 (GA4) | `<script async src="https://www.googletagmanager.com/gtag/js?id=G-EWHZQ9692Z">` (linhas 13–16) + `gtag("config", "G-EWHZQ9692Z")` (linha 23) | Pageview padrão do GA4; evento customizado `generate_lead` com parâmetro `form_id` (linhas 453–455) | `Ativo` |
| Tally.so (formulário de inscrição) | `<iframe data-tally-src="https://tally.so/embed/xVx6zJ?alignLeft=1&hideTitle=1&transparentBackground=1&dynamicHeight=1">` em `#cta-hero` (linhas 102–111) e `#cta-final` (linhas 376–385); loader `https://tally.so/widgets/embed.js` (linhas 412–432) | Dados preenchidos pelo visitante no formulário (não visíveis neste repositório — ficam na conta Tally); evento `postMessage` `Tally.FormSubmitted` com `payload.formId` (linha 450) | `Ativo` |
| Tailwind CSS (CDN) | `<script src="https://cdn.tailwindcss.com">` (linha 26) | Nenhum dado de usuário — apenas entrega de CSS utilitário em tempo de execução no navegador | `Ativo` |

### Evidências
- Arquivo: `index.html`
- Responsabilidade observada: classificação `Ativo` justificada pela presença e carregamento efetivo de cada script/iframe no único arquivo do repositório, sem indícios de código morto ou comentado desativando essas integrações.

## Observações de segurança e privacidade

- O formulário Tally coleta dados fornecidos pelo visitante (nome, contato, etc. — o schema exato do formulário `xVx6zJ` não está neste repositório, pois reside na configuração da conta Tally). Nenhum dado pessoal de visitante é armazenado ou processado neste repositório.
- O listener de `message` restringe o processamento a `event.origin === "https://tally.so"` (linha 437), evitando que mensagens de outras origens dispare eventos falsos de `generate_lead`.
- Não há chave de API, token ou segredo embutido nessas integrações — o Measurement ID do GA4 é um identificador público de propriedade, não uma credencial.
