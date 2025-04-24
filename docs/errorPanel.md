---
title: errorPanel
layout: default
---

# errorPanel

**Caminho Relativo:** `force-app/main/default/lwc/errorPanel`

## Visão Geral
O componente `errorPanel` é um Lightning Web Component (LWC) que exibe mensagens de erro de forma amigável ao usuário. Ele suporta dois tipos de exibição: uma ilustração de "sem dados" e uma mensagem inline.

## Estrutura
### Propriedades
- `@api errors`: Um único erro ou uma lista de erros retornados pelo LDS.
- `@api friendlyMessage`: Mensagem genérica ou amigável ao usuário (padrão: "Error retrieving data").
- `@api type`: Tipo de mensagem de erro (ex.: `inlineMessage`).

### Métodos
- `get errorMessages`: Retorna uma lista de mensagens de erro processadas pela função `reduceErrors`.
- `handleShowDetailsClick()`: Alterna a exibição de detalhes do erro.
- `render()`: Renderiza o template apropriado com base no tipo de mensagem (`inlineMessage` ou `noDataIllustration`).

## Relacionamentos
- Importa a função `reduceErrors` do módulo `c/ldsUtils`.
- Utiliza templates HTML personalizados:
  - `noDataIllustration.html`
  - `inlineMessage.html`

## Exemplos
### Código de Exemplo
```javascript
handleShowDetailsClick() {
    this.viewDetails = !this.viewDetails;
}

render() {
    if (this.type === 'inlineMessage') return inlineMessage;
    return noDataIllustration;
}
```

[← Voltar ao índice](index.md)