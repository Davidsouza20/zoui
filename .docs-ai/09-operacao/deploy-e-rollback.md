---
titulo: "Deploy e rollback"
modulo: "geral"
tipo: "operacao"
status_documentacao: "nao-localizado"
fontes_principais:
  - "."
  - ".git"
ultima_analise: "2026-10-21"
---

# Deploy e rollback

Não foi possível confirmar esta informação apenas pelas evidências disponíveis.

### Evidências de ausência
- Arquivo: raiz do repositório
- Responsabilidade observada: inexistência de `Dockerfile`, `vercel.json`, `netlify.toml`, `now.json`, `.github/workflows/*`, `.gitlab-ci.yml` ou qualquer outro arquivo de configuração de build/deploy (confirmado por listagem completa da raiz em 2026-10-21).
- O repositório não possui `package.json` nem scripts de build — consistente com o uso do Tailwind via CDN (sem etapa de compilação).

## O que é conhecido

- O remote `origin` aponta para `https://github.com/Davidsouza20/zoui.git`, com apenas a branch `main`.
- O conteúdo é um único `index.html` estático, compatível com qualquer hospedagem de arquivo estático (GitHub Pages, Vercel, Netlify, S3, etc.) sem necessidade de build — mas **nenhuma dessas opções está confirmada** por configuração presente no repositório.

Hipótese técnica baseada nas evidências encontradas. Requer validação manual: dado que não há pipeline de deploy no repositório, o deploy pode ser manual (upload direto do `index.html` a algum provedor) ou pode existir uma integração de hospedagem configurada fora do repositório (ex.: um provedor que lê diretamente do GitHub sem arquivo de configuração commitado). Essa hipótese não deve ser tratada como fato até confirmação humana.

Pergunta de validação registrada em [`../11-pendencias-de-entendimento/perguntas-para-validacao-humana.md`](../11-pendencias-de-entendimento/perguntas-para-validacao-humana.md).

Não há, portanto, procedimento de rollback documentável a partir do código — qualquer rollback hoje dependeria do controle de versão Git (`git revert`/checkout de commit anterior) e da forma de deploy real, que não está confirmada.
