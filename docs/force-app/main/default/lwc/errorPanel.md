---
title: errorPanel
summary: Componente Lightning Web para exibir mensagens de erro de forma amigável.
---

# errorPanel

## Descrição
O componente `errorPanel` exibe mensagens de erro de forma amigável para o usuário. Ele suporta dois modos de exibição: `inlineMessage` e `noDataIllustration`. O componente também permite alternar entre exibir ou ocultar detalhes do erro.

## Atributos

### `errors`
- **Tipo**: `Array` ou `Object`
- **Descrição**: Um único erro ou uma lista de erros retornados pelo LDS (Lightning Data Service).

### `friendlyMessage`
- **Tipo**: `String`
- **Descrição**: Uma mensagem genérica ou amigável exibida ao usuário. Valor padrão: `Error retrieving data`.

### `type`
- **Tipo**: `String`
- **Descrição**: Define o tipo de mensagem de erro a ser exibida. Valores possíveis: `inlineMessage` ou `noDataIllustration`.

## Métodos

### `errorMessages`
- **Descrição**: Retorna uma lista de mensagens de erro processadas usando o utilitário `reduceErrors`.

### `handleShowDetailsClick`
- **Descrição**: Alterna a exibição dos detalhes do erro.

### `render`
- **Descrição**: Define o template a ser renderizado com base no tipo de mensagem (`type`).

## Exemplo de Uso
```html
<template>
    <c-error-panel
        errors={errors}
        friendly-message="Unable to load data"
        type="inlineMessage"
    ></c-error-panel>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    errors = [
        { message: 'Error 1' },
        { message: 'Error 2' }
    ];
}
```

## Relacionamentos

- Veja também: [reduceErrors](./ldsUtils.md).