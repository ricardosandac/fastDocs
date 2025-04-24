---
title: OrderController
summary: Controlador Apex para gerenciar itens de pedido associados a um pedido específico.
---

# OrderController

## Descrição
A classe `OrderController` é responsável por gerenciar e recuperar itens de pedido (`Order_Item__c`) associados a um pedido específico no Salesforce.

## Métodos

### `getOrderItems`
Recupera os itens de pedido associados a um pedido específico.

#### Parâmetros
- `orderId` (Id): O ID do pedido para o qual os itens devem ser recuperados.

#### Retorno
- `Order_Item__c[]`: Uma lista de itens de pedido associados ao pedido fornecido.

#### Exemplo de Uso
```apex
// Este método é usado para recuperar itens de um pedido específico.
Id orderId = 'a0123456789XYZ';
Order_Item__c[] items = OrderController.getOrderItems(orderId);
for (Order_Item__c item : items) {
    System.debug('Produto: ' + item.Product__r.Name + ', Quantidade: ' + item.Qty_S__c);
}
```

## Relacionamentos

- Veja também: Objeto `Order_Item__c` e seus campos relacionados, como `Product__r.Name` e `Order__c`.