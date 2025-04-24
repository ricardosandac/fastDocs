---
title: orderBuilder
layout: default
---

# orderBuilder

**Caminho Relativo:** `force-app/main/default/lwc/orderBuilder`

## Visão Geral
O componente `orderBuilder` é um Lightning Web Component (LWC) que permite criar, atualizar e excluir itens de pedido (`Order_Item__c`) relacionados a um pedido (`Order__c`). Ele utiliza operações DML do LDS e chamadas Apex para gerenciar os dados.

## Estrutura
### Propriedades
- `@api recordId`: ID do registro do pedido (`Order__c`).
- `orderItems`: Lista de itens do pedido (`Order_Item__c`).
- `orderPrice`: Preço total do pedido, calculado com base nos itens.
- `orderQuantity`: Quantidade total de itens no pedido.
- `error`: Armazena erros encontrados durante as operações.

### Métodos
- `setOrderItems(orderItems)`: Atualiza os itens do pedido e recalcula a quantidade e o preço.
- `handleDrop(event)`: Lida com o evento de arrastar e soltar para criar um novo item de pedido.
- `handleDragOver(event)`: Permite o evento de arrastar sobre o componente.
- `handleOrderItemChange(evt)`: Atualiza os detalhes de um item de pedido.
- `handleOrderItemDelete(evt)`: Exclui um item de pedido.

### Funções Auxiliares
- `getQuantity(orderItem)`: Calcula a quantidade total de um item de pedido.
- `getPrice(orderItem, quantity)`: Calcula o preço total de um item de pedido com base na quantidade.
- `calculateOrderSummary(orderItems)`: Calcula a quantidade e o preço total de todos os itens do pedido.

## Relacionamentos
- Utiliza o módulo `ldsUtils` para processar erros do LDS.
- Chama o método Apex `getOrderItems` da classe `OrderController` para buscar itens do pedido.
- Realiza operações DML com os métodos `createRecord`, `updateRecord` e `deleteRecord` do LDS.

## Exemplos
### Código de Exemplo
```javascript
handleDrop(event) {
    event.preventDefault();
    const product = JSON.parse(event.dataTransfer.getData('product'));

    const fields = {};
    fields[ORDER_FIELD.fieldApiName] = this.recordId;
    fields[PRODUCT_FIELD.fieldApiName] = product.Id;
    fields[PRICE_FIELD.fieldApiName] = Math.round(
        getSObjectValue(product, PRODUCT_MSRP_FIELD) * DISCOUNT
    );

    const recordInput = {
        apiName: ORDER_ITEM_OBJECT.objectApiName,
        fields
    };
    createRecord(recordInput)
        .then(() => refreshApex(this.wiredOrderItems))
        .catch((e) => {
            this.dispatchEvent(
                new ShowToastEvent({
                    title: 'Error creating order',
                    message: reduceErrors(e).join(', '),
                    variant: 'error'
                })
            );
        });
}
```

[← Voltar ao índice](index.md)