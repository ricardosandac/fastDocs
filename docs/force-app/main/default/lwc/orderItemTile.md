---
title: orderItemTile
summary: Componente Lightning Web para exibir e gerenciar registros individuais de Order_Item__c.
---

# orderItemTile

## Descrição
O componente `orderItemTile` exibe e gerencia registros individuais de `Order_Item__c`. Ele permite editar e excluir itens por meio de eventos personalizados. Este componente utiliza referências dinâmicas ao esquema para maior flexibilidade.

## Atributos

### `orderItem`
- **Tipo**: `Object`
- **Descrição**: O registro `Order_Item__c` a ser exibido e gerenciado.

## Métodos

### `handleFormChange`
Lida com alterações no formulário e marca o item como modificado.

#### Parâmetros
- `evt` (Event): Evento contendo o campo e o valor alterados.

### `saveOrderItem`
Dispara um evento para salvar as alterações no registro `Order_Item__c`.

### `deleteOrderItem`
Dispara um evento para excluir o registro `Order_Item__c`.

## Exemplo de Uso
```html
<template>
    <c-order-item-tile
        order-item={orderItem}
        onorderitemchange={handleOrderItemChange}
        onorderitemdelete={handleOrderItemDelete}
    ></c-order-item-tile>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    orderItem = {
        Id: 'a0123456789XYZ',
        Price__c: 100,
        Qty_S__c: 2,
        Qty_M__c: 1,
        Qty_L__c: 0
    };

    handleOrderItemChange(event) {
        console.log('Item alterado:', event.detail);
    }

    handleOrderItemDelete(event) {
        console.log('Item excluído:', event.detail.id);
    }
}
```

## Relacionamentos

- Utilizado por: [orderBuilder](./orderBuilder.md).