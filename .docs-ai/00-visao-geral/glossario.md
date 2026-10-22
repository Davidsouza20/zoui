---
titulo: "Glossário"
modulo: "geral"
tipo: "visao-geral"
status_documentacao: "confirmado"
fontes_principais:
  - "index.html"
ultima_analise: "2026-10-21"
---

# Glossário

- **Zoui**: nome do produto anunciado pela landing page — um assistente que registraria movimentações financeiras a partir de fotos de comprovantes ou áudios enviados via WhatsApp. (`index.html`, `<title>`, linha 6)
- **Acesso Antecipado / Beta**: fase de pré-lançamento em que o produto está, segundo a página; a página existe para captar inscrições para essa fase. (`index.html`, badge "Acesso Antecipado", linha 57; seção CTA final, linhas 360–369)
- **Lead**: visitante que preenche o formulário de inscrição (Tally) na página. Evento correspondente no GA4: `generate_lead`.
- **Tally / Tally.so**: serviço externo (`tally.so`) usado para hospedar e renderizar os formulários de inscrição embutidos via `<iframe>`. (`index.html`, linhas 102–111, 376–385, 412–432)
- **GA4 (Google Analytics 4)**: plataforma de analytics do Google usada para rastrear visitas e o evento de conversão `generate_lead`. Identificada pelo Measurement ID `G-EWHZQ9692Z`. (`index.html`, linhas 12–24)
- **`cta-hero`**: `id` do bloco de formulário de inscrição exibido na seção principal (hero) da página. (`index.html`, linha 99)
- **`cta-final`**: `id` do bloco de formulário de inscrição exibido na seção de fechamento, no final da página. (`index.html`, linha 373)
- **`generate_lead`**: nome do evento customizado disparado no GA4 quando o formulário Tally é enviado com sucesso. (`index.html`, linha 453)
