# Decisões arquiteturais (ADRs)

Toda alteração aprovada que afete comportamento técnico deste repositório deve criar um novo ADR ou atualizar um existente.

## Nomenclatura

`ADR-NNNN-titulo-curto.md`, numeração sequencial a partir de `0001`. O arquivo [`ADR-0000-template.md`](ADR-0000-template.md) é apenas o template-base e não representa uma decisão real.

## Status permitidos

- `proposto`
- `aceito`
- `substituido`
- `rejeitado`

## Quando criar um novo ADR vs. atualizar um existente

- **Atualizar** um ADR existente quando a decisão continuar igual e apenas receber novas evidências ou consequências.
- **Criar um novo ADR** quando a decisão mudar materialmente. Nesse caso, marcar o anterior como `substituido` e adicionar referências cruzadas entre os dois.

## O que não é um ADR

Mudanças exclusivamente textuais (copy da landing page, ajuste de estilo visual) não exigem ADR, salvo quando modificarem uma decisão arquitetural vigente (ex.: trocar o Tailwind CDN por um build local, trocar o Tally por outro provedor de formulário, introduzir um backend). ADR não é changelog — deve explicar o porquê da decisão e as consequências aceitas, não apenas o que mudou.

Nenhum ADR foi criado ainda neste repositório (confirmado em 2026-10-21 — esta documentação inicial é exclusivamente descritiva e não altera comportamento).
