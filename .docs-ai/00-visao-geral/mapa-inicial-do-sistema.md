---
titulo: "Mapa inicial do sistema"
modulo: "geral"
tipo: "visao-geral"
status_documentacao: "parcialmente-confirmado"
fontes_principais:
  - "index.html"
  - ".git"
ultima_analise: "2026-10-21"
---

# Mapa inicial do sistema

## O que o sistema é

Landing page estática ("single-page", um único HTML) de captura de leads para o produto **Zoui**, anunciado como uma ferramenta para "organizar o financeiro do seu negócio pelo WhatsApp": o usuário final (comerciante/empreendedor) enviaria fotos de comprovantes ou áudios pelo WhatsApp e o produto registraria automaticamente as movimentações financeiras.

### Evidências
- Arquivo: `index.html`
- Símbolo: `<title>Zoui — Organize o financeiro do seu negócio pelo WhatsApp</title>` (linha 6), `<meta name="description">` (linhas 7–10)
- Responsabilidade observada: define o título e a proposta de valor da página.

A página está em fase de "acesso antecipado" / "Beta gratuito" — não há evidência, dentro deste repositório, de que o produto Zoui (o assistente de WhatsApp em si) esteja implementado aqui. Este repositório contém **apenas a landing page de captação de leads**, não o produto.

### Evidências
- Arquivo: `index.html`
- Símbolo: badge `"Acesso Antecipado"` (linha 57), seção "FECHAMENTO / CTA FINAL" com texto "As vagas do Beta gratuito são limitadas" (linhas 356–369)
- Responsabilidade observada: identifica a página como campanha de pré-lançamento, não o produto funcional.

## Stack técnica confirmada

- HTML estático puro, `lang="pt-BR"` (`index.html`, linha 2).
- **Tailwind CSS via CDN** (modo "Play CDN", sem build, sem arquivo de configuração local): `<script src="https://cdn.tailwindcss.com"></script>` (linha 26), com customização inline de tema (`tailwind.config`, linhas 27–40) adicionando a cor `whatsapp` (`DEFAULT: #25D366`, `dark: #1DA851`).
- **Google Analytics 4 (GA4)**: script `gtag.js` carregado de `https://www.googletagmanager.com/gtag/js?id=G-EWHZQ9692Z` (linhas 13–16) e inicializado com `gtag("config", "G-EWHZQ9692Z")` (linha 23).
- **Tally.so**: dois formulários embutidos via `<iframe data-tally-src="https://tally.so/embed/xVx6zJ...">` (linhas 102–111 e 376–385) carregados/redimensionados pelo script oficial `https://tally.so/widgets/embed.js` (linhas 412–432).
- Sem framework JavaScript (React, Vue, etc.), sem bundler, sem gerenciador de pacotes (não há `package.json` no repositório).

## Hospedagem e deploy

Não foi possível confirmar esta informação apenas pelas evidências disponíveis. Não há `Dockerfile`, `vercel.json`, `netlify.toml`, workflows de CI/CD (`.github/workflows`) ou qualquer outro arquivo de configuração de deploy no repositório. Ver detalhes e pergunta de validação em [`../09-operacao/deploy-e-rollback.md`](../09-operacao/deploy-e-rollback.md) e [`../11-pendencias-de-entendimento/perguntas-para-validacao-humana.md`](../11-pendencias-de-entendimento/perguntas-para-validacao-humana.md).

## Repositório Git

- Remote único: `origin` → `https://github.com/Davidsouza20/zoui.git` (confirmado via `git remote -v`).
- Única branch remota: `main` (confirmado via `git branch -r`).
- Branch `release` não existe em `origin` (confirmado via `git fetch origin release`, 2026-10-21).
- Histórico de commits na data da análise: `651ca32` ("ajuste de evento GA4"), `a26f376` ("first commit"), `d1e9078` ("first commit").

## Ausência de testes, backend e CI/CD

Confirmado pela ausência total desses artefatos no repositório: nenhuma pasta de testes, nenhum test runner configurado, nenhum endpoint de API próprio, nenhum workflow de CI/CD. Ver cobertura completa em [`relatorio-de-cobertura.md`](relatorio-de-cobertura.md).
