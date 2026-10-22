# Convenções internas da documentação `.docs-ai/`

## Metadados obrigatórios

Todo documento (exceto `README.md`, `MASTER.md` e este arquivo) deve começar com:

```yaml
---
titulo: "..."
modulo: "..."
tipo: "visao-geral|arquitetura|modulo|fluxo|inventario|integracao|persistencia|endpoint|operacao|adr"
status_documentacao: "confirmado|parcialmente-confirmado|hipotese|nao-localizado|requer-validacao-humana"
fontes_principais:
  - "caminho/da/evidencia"
ultima_analise: "AAAA-MM-DD"
---
```

`ultima_analise` só deve ser atualizada quando o documento for efetivamente revisado.

## Formato de evidências

Afirmações técnicas relevantes devem citar:

```
### Evidências
- Arquivo: `caminho/exato`
- Símbolo: `id, classe, função ou elemento`
- Responsabilidade observada: descrição objetiva
```

Neste repositório, a evidência principal de quase todo documento é `index.html` (único arquivo de código), citando o `id` do elemento HTML ou o trecho de script correspondente.

## Estados de código

- `Ativo`
- `Descontinuado`
- `Possivelmente descontinuado`
- `Código órfão`
- `Não foi possível determinar`

## Regras de incerteza

- Fato comprovado por código/config/execução: afirme diretamente.
- Indício sem comprovação completa: "Hipótese técnica baseada nas evidências encontradas. Requer validação manual."
- Ausência de evidência: "Não foi possível confirmar esta informação apenas pelas evidências disponíveis." (a ausência de documentação não comprova que o comportamento não existe).

## Segurança

Nunca reproduzir senhas, tokens, chaves, cookies, dados pessoais ou strings de conexão. Usar marcadores (`<API_TOKEN>`, `<PERSONAL_DATA>`, etc.). O Measurement ID do GA4 (`G-EWHZQ9692Z`) é uma exceção deliberada: é um identificador público por natureza (necessário no HTML client-side para o GA4 funcionar), não uma credencial secreta.
