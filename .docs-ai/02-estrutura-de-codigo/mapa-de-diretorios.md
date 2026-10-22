---
titulo: "Mapa de diretórios"
modulo: "geral"
tipo: "arquitetura"
status_documentacao: "confirmado"
fontes_principais:
  - "."
ultima_analise: "2026-10-21"
---

# Mapa de diretórios

Estrutura real do repositório na raiz, excluindo `.git/`:

```
gestao-financeira/
├── index.html          # único arquivo de código do repositório
└── .docs-ai/            # documentação técnica (esta pasta)
```

### Evidências
- Comando: `ls -a` na raiz do repositório (2026-10-21)
- Responsabilidade observada: confirma que não há `src/`, `assets/`, `public/`, `package.json` ou qualquer outro artefato de código além de `index.html`.

Não há subpastas de código, ativos estáticos separados (imagens, CSS, JS externos ao HTML) ou qualquer estrutura de projeto além do arquivo único.
