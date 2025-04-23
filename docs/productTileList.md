---
title: productTileList
layout: default
---

# productTileList

**Caminho Relativo:** `force-app/main/default/lwc/productTileList`

## Visão Geral
O componente `productTileList` é um Lightning Web Component (LWC) que carrega e exibe uma lista de produtos (`Product__c`) em formato de cartões. Ele suporta paginação, filtros e integração com o Lightning Message Service para comunicação entre componentes.

## Estrutura
### Propriedades
- `@api searchBarIsVisible`: Indica se a barra de busca deve ser exibida.
- `@api tilesAreDraggable`: Indica se os cartões de produtos podem ser arrastados.

### Variáveis Internas
- `pageNumber`: Número da página atual.
- `pageSize`: Número de itens por página.
- `totalItemCount`: Número total de itens correspondentes aos filtros.
- `filters`: Objeto contendo os critérios de filtro aplicados.

### Métodos
- `connectedCallback()`: Inscreve-se no canal de mensagens `ProductsFiltered__c` para receber atualizações de filtros.
- `handleProductSelected(event)`: Publica uma mensagem no canal `ProductSelected__c` com o ID do produto selecionado.
- `handleSearchKeyChange(event)`: Atualiza os filtros com base na palavra-chave de busca.
- `handleFilterChange(message)`: Atualiza os filtros com base na mensagem recebida.
- `handlePreviousPage()`: Navega para a página anterior.
- `handleNextPage()`: Navega para a próxima página.

## Relacionamentos
- Utiliza o Lightning Message Service para comunicação entre componentes:
  - Canal `ProductsFiltered__c` para receber filtros.
  - Canal `ProductSelected__c` para notificar a seleção de produtos.
- Chama o método Apex `getProducts` da classe `ProductController` para buscar produtos.

## Exemplos
### Código de Exemplo
```javascript
connectedCallback() {
    this.productFilterSubscription = subscribe(
        this.messageContext,
        PRODUCTS_FILTERED_MESSAGE,
        (message) => this.handleFilterChange(message)
    );
}

handleProductSelected(event) {
    publish(this.messageContext, PRODUCT_SELECTED_MESSAGE, {
        productId: event.detail
    });
}

handleNextPage() {
    this.pageNumber = this.pageNumber + 1;
}
```

[← Voltar ao índice](index.md)