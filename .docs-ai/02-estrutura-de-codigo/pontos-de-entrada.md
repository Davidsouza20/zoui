---
titulo: "Pontos de entrada"
modulo: "geral"
tipo: "arquitetura"
status_documentacao: "confirmado"
fontes_principais:
  - "index.html"
ultima_analise: "2026-10-21"
---

# Pontos de entrada

## `index.html` — único ponto de entrada

Documento servido diretamente ao visitante. Dentro dele, os comportamentos estão organizados em blocos `<script>` inline, na ordem em que aparecem no arquivo:

### 1. Bootstrap do Google Analytics 4 (`<head>`, linhas 12–24)
Carrega `gtag.js` de forma assíncrona e inicializa `dataLayer`/`gtag` com o Measurement ID `G-EWHZQ9692Z`.

#### Evidências
- Arquivo: `index.html`
- Símbolo: `gtag("config", "G-EWHZQ9692Z")` (linha 23)
- Responsabilidade observada: inicializa o rastreamento de pageview padrão do GA4 para esta propriedade.

### 2. Configuração do Tailwind CDN (`<head>`, linhas 26–40)
Carrega o Tailwind em modo CDN ("Play CDN") e estende o tema com a cor customizada `whatsapp` (`DEFAULT #25D366`, `dark #1DA851`), usada nos elementos visuais com identidade de marca do WhatsApp.

#### Evidências
- Arquivo: `index.html`
- Símbolo: `tailwind.config = { theme: { extend: { colors: { whatsapp: {...} } } } }` (linhas 27–40)
- Responsabilidade observada: define apenas uma extensão de cor; não há customização de outros tokens de design.

### 3. Loader do embed do Tally (`<body>`, final do documento, linhas 412–432)
Garante que o script oficial `https://tally.so/widgets/embed.js` seja carregado uma única vez e, ao carregar (ou se o objeto global `Tally` já existir), chama `Tally.loadEmbeds()` — ou, como fallback, atribui manualmente `src` a cada `<iframe data-tally-src>` ainda sem `src`.

#### Evidências
- Arquivo: `index.html`
- Símbolo: função `v()` (linhas 415–423), checagem `d.querySelector('script[src="' + w + '"]') == null` (linha 425)
- Responsabilidade observada: inicializa os dois embeds de formulário (`#cta-hero` e `#cta-final`) e evita duplicar o carregamento do script do Tally.

### 4. Listener de conversão (`<body>`, final do documento, linhas 435–457)
Escuta eventos `message` da `window`. Se a origem for exatamente `https://tally.so` e o payload (já em objeto ou decodificado via `JSON.parse` de string) tiver `event === "Tally.FormSubmitted"`, dispara `gtag("event", "generate_lead", { form_id: payload.payload.formId })`.

#### Evidências
- Arquivo: `index.html`
- Símbolo: `window.addEventListener("message", function (event) {...})` (linha 436); `gtag("event", "generate_lead", {...})` (linhas 453–455)
- Responsabilidade observada: converte o evento de submissão do formulário Tally em um evento de conversão rastreável no GA4.

## Elementos de UI com `id` relevante

- `#cta-hero` (linha 99): contêiner do formulário de inscrição na seção hero.
- `#cta-final` (linha 373): contêiner do formulário de inscrição na seção de fechamento.

Detalhamento de cada seção visual em [`../08-interfaces/mapa-de-interfaces.md`](../08-interfaces/mapa-de-interfaces.md).
