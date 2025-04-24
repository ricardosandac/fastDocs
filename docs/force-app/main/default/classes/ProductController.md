---
title: ProductController
summary: Controlador Apex para gerenciar a recuperação de produtos com filtros e paginação.
---

# ProductController

## Descrição
A classe `ProductController` é responsável por gerenciar a recuperação de produtos no Salesforce, permitindo a aplicação de filtros e paginação. Também fornece funcionalidade para buscar produtos similares.

## Métodos

### `getProducts`
Recupera uma lista paginada de produtos com base em filtros fornecidos.

#### Parâmetros
- `filters` (Filters): Objeto contendo os filtros aplicáveis, como palavras-chave, preço máximo, categorias, materiais e níveis.
- `pageNumber` (Integer): Número da página para a paginação.

#### Retorno
- `PagedResult`: Um objeto contendo os resultados paginados, incluindo o número total de itens e os registros da página atual.

#### Exemplo de Uso
```apex
// Recupera produtos com filtros aplicados.
ProductController.Filters filters = new ProductController.Filters();
filters.searchKey = 'Bike';
filters.maxPrice = 1000;
filters.categories = new String[]{'Mountain', 'Road'};
PagedResult result = ProductController.getProducts(filters, 1);
System.debug('Total de produtos encontrados: ' + result.totalItemCount);
for (Product__c product : result.records) {
    System.debug('Produto: ' + product.Name);
}
```

### `getSimilarProducts`
Recupera produtos similares com base no ID da família de produtos, excluindo o produto atual.

#### Parâmetros
- `productId` (Id): O ID do produto atual.
- `familyId` (Id): O ID da família de produtos.

#### Retorno
- `Product__c[]`: Uma lista de produtos similares.

#### Exemplo de Uso
```apex
// Recupera produtos similares a um produto específico.
Id productId = 'a0123456789XYZ';
Id familyId = 'b0123456789ABC';
Product__c[] similarProducts = ProductController.getSimilarProducts(productId, familyId);
for (Product__c product : similarProducts) {
    System.debug('Produto similar: ' + product.Name);
}
```

## Relacionamentos

- Veja também: Objeto `Product__c` e seus campos relacionados, como `Category__c`, `Level__c` e `Material__c`.