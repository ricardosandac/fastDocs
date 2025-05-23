---
title: TestOrderController
summary: Classe de teste para verificar o comportamento do OrderController.
---

# TestOrderController

## Descrição
A classe `TestOrderController` é responsável por testar o comportamento do controlador `OrderController`, garantindo que o método `getOrderItems` funcione conforme esperado.

## Métodos de Teste

### `setup`
Configura os dados de teste necessários para os métodos de teste.

#### Comportamento Verificado
- Cria uma conta, um pedido, um produto e um item de pedido para uso nos testes.

#### Exemplo de Uso
```apex
@isTest
static void setup() {
    Account acc = new Account(Name = 'Sample Account');
    insert acc;

    Order__c order = new Order__c(Account__c = acc.Id);
    insert order;

    Product__c p = new Product__c(Name = 'Sample Product');
    insert p;

    Order_Item__c orderItem = new Order_Item__c(
        Order__c = order.Id,
        Product__c = p.Id
    );
    insert orderItem;
}
```

### `testGetOrderItems`
Testa o método `getOrderItems` do controlador `OrderController`.

#### Comportamento Verificado
- Garante que o número correto de itens de pedido seja retornado para um pedido específico.

#### Exemplo de Uso
```apex
@isTest
static void testGetOrderItems() {
    Order__c testOrder = [SELECT Id FROM Order__c];
    List<Order_Item__c> orderItems = OrderController.getOrderItems(testOrder.Id);
    Assert.areEqual(1, orderItems.size());
}
```

## Relacionamentos

- Veja também: [OrderController](./OrderController.md).