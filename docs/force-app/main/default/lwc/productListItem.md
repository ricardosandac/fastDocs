---
title: productListItem
summary: Componente Lightning Web para exibir um registro Product__c com navegação para a página do registro.
---

# productListItem

## Descrição
O componente `productListItem` é um componente de apresentação projetado para exibir um registro `Product__c`. Ele inclui um botão "Ver Detalhes" que navega para a página do registro do produto usando o `NavigationMixin`.

## Atributos

### `product`
- **Tipo**: `Object`
- **Descrição**: O registro `Product__c` a ser exibido. Deve conter todos os campos usados pelo componente.

## Métodos

### `handleViewDetailsClick`
Navega para a página do registro do produto.

## Exemplo de Uso
```html
<template>
    <c-product-list-item product={product}></c-product-list-item>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    product = {
        Id: 'a0123456789XYZ',
        Name: 'Mountain Bike',
        Price__c: 1200
    };
}
```

## Relacionamentos

- Utiliza: [NavigationMixin](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_navigate).