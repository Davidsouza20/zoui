---
titulo: "Mapa de interfaces"
modulo: "geral"
tipo: "modulo"
status_documentacao: "confirmado"
fontes_principais:
  - "index.html"
ultima_analise: "2026-10-21"
---

# Mapa de interfaces

Única interface do sistema: a landing page em `index.html`, composta pelas seções abaixo (ordem de topo a baixo do documento).

| Seção | Linhas | Conteúdo / responsabilidade observada |
|---|---|---|
| `<header>` | 44–67 | Barra fixa (`sticky top-0`) com logo "Zoui", badge "Acesso Antecipado" e link âncora `#cta-hero` ("Garantir Vaga") que rola até o formulário do hero. |
| Seção "HERO" | 70–245 | Título e subtítulo de proposta de valor; bloco de formulário `#cta-hero` (embed Tally); mockup estático (HTML/SVG) simulando uma conversa de WhatsApp com o "Zoui Assistente", ilustrando o caso de uso (comprovante enviado → resposta automática com despesa registrada, saldo livre e lembrete de boleto). |
| Seção "BENEFÍCIOS" | 248–353 | Três cards de benefício: "Zero Digitação e Atrito", "Clareza do Lucro Real", "Radar de Contas a Pagar", cada um com ícone SVG inline e texto descritivo. |
| Seção "FECHAMENTO / CTA FINAL" | 356–391 | Chamada final ("As vagas do Beta gratuito são limitadas") e segundo bloco de formulário `#cta-final` (mesmo embed Tally `xVx6zJ`). |
| `<footer>` | 394–409 | Copyright "© 2026 Zoui" e link "Política de Privacidade" apontando para `href="#"` — âncora vazia, sem página de destino real. |

### Evidências
- Arquivo: `index.html`
- Símbolo: comentários de seção `<!-- ===================== HEADER ===================== -->` e equivalentes (linhas 43, 69, 247, 355, 393), usados como delimitadores no próprio código.
- Responsabilidade observada: cada seção é um bloco visual independente dentro do único documento.

## Pendência de conteúdo identificada

- O link "Política de Privacidade" no rodapé aponta para `href="#"` com um comentário no próprio código: `<!-- TODO: criar página real de política de privacidade e trocar o href abaixo -->` (`index.html`, linha 401). Esta é uma pendência marcada pelo próprio autor do código, não uma suposição desta documentação.

### Evidências
- Arquivo: `index.html`
- Símbolo: comentário `TODO` na linha 401; `<a href="#">Política de Privacidade</a>` (linhas 402–407)
- Responsabilidade observada: confirma, por comentário explícito no código-fonte, que a página de política de privacidade ainda não existe.
