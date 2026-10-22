---
titulo: "Relatório de cobertura"
modulo: "geral"
tipo: "visao-geral"
status_documentacao: "confirmado"
fontes_principais:
  - "."
  - "index.html"
  - ".git"
ultima_analise: "2026-10-21"
---

# Relatório de cobertura

## Total localizado vs. inventariado vs. analisado

- Arquivos de código no repositório: **1** (`index.html`), confirmado por listagem completa da raiz (`ls -a`, excluindo `.git/`) em 2026-10-21.
- Arquivos de código lidos integralmente: **1/1 (100%)** — `index.html`, 461 linhas, lido por completo.
- Integrações identificadas e analisadas: **3/3** — GA4, Tally.so, Tailwind CDN (ver [`../10-inventarios/inventario-de-integracoes.md`](../10-inventarios/inventario-de-integracoes.md)).
- Seções de interface identificadas e analisadas: **5/5** — header, hero, benefícios, CTA final, footer (ver [`../08-interfaces/mapa-de-interfaces.md`](../08-interfaces/mapa-de-interfaces.md)).
- Fluxos de negócio identificados e analisados: **1/1** — captura de lead (ver [`../05-fluxos/captura-de-lead.md`](../05-fluxos/captura-de-lead.md)).

## Comandos usados para as contagens (reproduzíveis)

```sh
# Lista todos os arquivos versionados, excluindo .git
git ls-files

# Remote e branches
git remote -v
git branch -r
git fetch origin release   # confirma ausência da branch release

# Estado do working tree
git status
git log --oneline
```

## Áreas não verificadas / não aplicáveis

As pastas abaixo do template documental padrão não foram criadas por ausência de conteúdo real a documentar, não por falta de verificação:

| Pasta não criada | Motivo |
|---|---|
| `03-persistencia/` | Não há banco de dados, schema, ou persistência própria — toda "persistência" de leads é delegada ao Tally.so, fora deste repositório |
| `04-modulos/` | Não há separação em módulos de domínio/backend — único arquivo HTML |
| `06-apis-e-endpoints/` | Não há API própria; a única comunicação é com serviços de terceiros via scripts/iframe, já cobertos em `07-integracoes/` |
| `00-visao-geral/atores-e-perfis.md` | Único "ator" é o visitante anônimo da página; não há perfis distintos de usuário |
| `01-arquitetura/jobs-crons-e-processos.md` | Não há jobs, filas ou processos agendados |
| `01-arquitetura/infraestrutura.md` | Nenhuma configuração de infraestrutura (containers, servidores) presente no repositório |
| `01-arquitetura/ciclo-de-requisicao.md` | Não há backend que processe requisições além da entrega estática do HTML |
| `09-operacao/ambiente-de-desenvolvimento.md` | Não há passos de setup além de abrir o `index.html`; nenhuma ferramenta de desenvolvimento configurada |
| `09-operacao/monitoramento-e-logs.md` | Não há logging ou monitoramento próprio além do GA4 (já coberto em `07-integracoes/`) |
| `10-inventarios/inventario-de-modulos.md`, `inventario-de-dados.md`, `inventario-de-jobs.md` | Não aplicável — sem módulos, dados persistidos ou jobs próprios |

## Limitações da técnica utilizada

- A análise foi feita por leitura integral do único arquivo de código e inspeção do histórico/configuração Git — não há execução em runtime (o site não foi aberto em navegador real nem houve inspeção de rede ao vivo), portanto comportamentos de carregamento dinâmico de terceiros (Tally, GA4, Tailwind) são descritos com base no código, não em observação de tráfego real.
- Não há acesso às configurações internas das contas Tally.so ou Google Analytics (ex.: para onde os leads são encaminhados, outros eventos configurados no GA4 fora do código) — essas informações, se existirem, estão fora do escopo rastreável por este repositório.
- Não foi possível confirmar onde e como o site é hospedado/deployado (ver [`../09-operacao/deploy-e-rollback.md`](../09-operacao/deploy-e-rollback.md)).

## Separação entre estado versionado e estado observado

Todas as afirmações desta documentação referem-se ao **estado versionado** do repositório na branch `main`, commit `651ca32` ("ajuste de evento GA4"), conforme `git log` em 2026-10-21. Nenhuma inspeção do ambiente de produção/runtime foi realizada.
