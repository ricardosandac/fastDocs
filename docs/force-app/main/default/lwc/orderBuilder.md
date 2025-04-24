---
title: orderBuilder
summary: Componente Lightning Web para gerenciar itens de pedido relacionados a um pedido.
---

# orderBuilder

## Descrição
O componente `orderBuilder` permite gerenciar registros de `Order_Item__c` relacionados a um `Order__c`. Ele suporta operações de CRUD, funcionalidade de arrastar e soltar para adicionar produtos, e calcula dinamicamente o resumo do pedido (quantidade e preço).

## Atributos

### `recordId`
- **Tipo**: `String`
- **Descrição**: O ID do registro `Order__c` associado aos itens do pedido.

### `orderItems`
- **Tipo**: `Array`
- **Descrição**: Lista de registros `Order_Item__c` associados ao pedido.

### `orderPrice`
- **Tipo**: `Number`
- **Descrição**: Preço total do pedido, calculado com base nos itens do pedido.

### `orderQuantity`
- **Tipo**: `Number`
- **Descrição**: Quantidade total de itens no pedido, calculada com base nos itens do pedido.

## Métodos

### `setOrderItems`
Atualiza os itens do pedido e recalcula a quantidade e o preço do pedido.

#### Parâmetros
- `orderItems` (Array): Lista de registros `Order_Item__c`.

### `handleDrop`
Lida com o evento de arrastar e soltar para criar um novo registro de `Order_Item__c`.

#### Parâmetros
- `event` (Event): Evento de arrastar e soltar contendo os dados do produto.

### `handleOrderItemChange`
Lida com alterações nos detalhes de um item do pedido.

#### Parâmetros
- `evt` (Event): Evento contendo as alterações do item do pedido.

### `handleOrderItemDelete`
Lida com a exclusão de um item do pedido.

#### Parâmetros
- `evt` (Event): Evento contendo o ID do item do pedido a ser excluído.

### `hasNoOrderItems`
- **Descrição**: Retorna `true` se não houver itens no pedido.

## Exemplo de Uso
```html
<template>
    <c-order-builder record-id="a0123456789XYZ"></c-order-builder>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    recordId = 'a0123456789XYZ';
}
```

## Relacionamentos

- Utiliza: [OrderController.getOrderItems](../classes/OrderController.md).
- Utiliza: [ldsUtils.reduceErrors](./ldsUtils.md).