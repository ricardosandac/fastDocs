---
title: productTile
summary: Componente Lightning Web para exibir um registro Product__c com suporte a arrastar e soltar.
---

# productTile

## Descrição
O componente `productTile` é um componente de apresentação projetado para exibir um registro `Product__c`. Ele suporta funcionalidade de arrastar e soltar e emite um evento personalizado `selected` quando o tile é clicado.

## Atributos

### `draggable`
- **Tipo**: `Boolean`
- **Descrição**: Indica se o tile pode ser arrastado.

### `product`
- **Tipo**: `Object`
- **Descrição**: O registro `Product__c` a ser exibido. Deve conter os campos `Picture_URL__c`, `Name` e `MSRP__c`.

## Métodos

### `handleClick`
Emite o evento `selected` com o ID do produto quando o tile é clicado.

### `handleDragStart`
Define os dados do produto no evento de arrastar.

#### Parâmetros
- `event` (Event): Evento de arrastar contendo os dados do produto.

## Exemplo de Uso
```html
<template>
    <c-product-tile
        product={product}
        draggable
        onselected={handleProductSelected}
    ></c-product-tile>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    product = {
        Id: 'a0123456789XYZ',
        Picture_URL__c: '/images/product.jpg',
        Name: 'Mountain Bike',
        MSRP__c: 1200
    };

    handleProductSelected(event) {
        console.log('Produto selecionado:', event.detail);
    }
}
```

## Relacionamentos

- Utilizado por: Componentes que implementam listas de produtos com suporte a arrastar e soltar.