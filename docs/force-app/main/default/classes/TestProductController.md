---
title: TestProductController
summary: Classe de teste para verificar o comportamento do ProductController.
---

# TestProductController

## Descrição
A classe `TestProductController` é responsável por testar o comportamento do controlador `ProductController`, garantindo que os métodos `getProducts` e `getSimilarProducts` funcionem conforme esperado.

## Métodos de Teste

### `createProducts`
Configura os dados de teste necessários para os métodos de teste.

#### Comportamento Verificado
- Cria uma família de produtos e dois produtos para uso nos testes.

#### Exemplo de Uso
```apex
@isTest
static void createProducts() {
    Product_Family__c family = new Product_Family__c(
        Name = 'TestFamily',
        Category__c = 'Mountain'
    );
    insert family;

    insert new List<Product__c>{
        new Product__c(
            Name = 'Sample Bike 1',
            MSRP__c = 1000,
            Category__c = 'Mountain',
            Level__c = 'Beginner',
            Material__c = 'Carbon',
            Product_Family__c = family.Id
        ),
        new Product__c(
            Name = 'Sample Bike 2',
            MSRP__c = 1200,
            Category__c = 'Mountain',
            Level__c = 'Racer',
            Material__c = 'Carbon',
            Product_Family__c = family.Id
        )
    };
}
```

### `getProducts_works`
Testa o método `getProducts` do controlador `ProductController`.

#### Comportamento Verificado
- Garante que o produto correto seja retornado com base nos filtros aplicados.

#### Exemplo de Uso
```apex
@isTest
static void getProducts_works() {
    ProductController.Filters filters = new ProductController.Filters();
    filters.searchKey = 'Sample';
    filters.maxPrice = 2000;
    filters.categories = new List<String>{ 'Mountain' };
    filters.levels = new List<String>{ 'Beginner' };
    filters.materials = new List<String>{ 'Carbon' };

    PagedResult result = ProductController.getProducts(filters, 1);

    Assert.areEqual(1, result.records.size());
    Assert.areEqual('Sample Bike 1', ((Product__c) result.records[0]).Name);
}
```

### `getSimilarProducts_works`
Testa o método `getSimilarProducts` do controlador `ProductController`.

#### Comportamento Verificado
- Garante que o produto similar correto seja retornado com base no ID da família de produtos.

#### Exemplo de Uso
```apex
@isTest
static void getSimilarProducts_works() {
    Product__c baseProduct = [
        SELECT Id, Name, Product_Family__c
        FROM Product__c
        WHERE Name = 'Sample Bike 1'
    ];

    Product__c[] similarProducts = ProductController.getSimilarProducts(
        baseProduct.Id,
        baseProduct.Product_Family__c
    );

    Assert.areEqual(1, similarProducts.size());
    Assert.areEqual('Sample Bike 2', similarProducts[0].Name);
}
```

## Relacionamentos

- Veja também: [ProductController](./ProductController.md).