---
title: similarProducts
summary: Componente Lightning Web para exibir produtos similares a um registro Product__c.
---

# similarProducts

## Descrição
O componente `similarProducts` exibe produtos similares a um registro `Product__c` com base no campo `Product_Family__c`. Ele utiliza o método Apex `getSimilarProducts` e rastreia dinamicamente alterações no campo `Product_Family__c`.

## Atributos

### `recordId`
- **Tipo**: `String`
- **Descrição**: O ID do registro `Product__c` para o qual os produtos similares serão buscados.

### `familyId`
- **Tipo**: `String`
- **Descrição**: O ID da família de produtos associado ao registro `Product__c`.

## Métodos

### `errors`
- **Descrição**: Retorna uma lista de erros, se houver, das operações de busca de registro ou produtos similares.

### `hasNoSimilarProducts`
- **Descrição**: Retorna `true` se não houver produtos similares disponíveis.

## Exemplo de Uso
```html
<template>
    <c-similar-products record-id="a0123456789XYZ"></c-similar-products>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    recordId = 'a0123456789XYZ';
}
```

## Relacionamentos

- Utiliza: [getSimilarProducts](../classes/ProductController.md).
- Utiliza: [lightning/uiRecordApi](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.reference_lightning_ui_api).