---
title: productTileList
summary: Componente Lightning Web para carregar e exibir uma lista de registros Product__c com suporte a filtros e paginação.
---

# productTileList

## Descrição
O componente `productTileList` é um contêiner que carrega e exibe uma lista de registros `Product__c`. Ele integra-se ao Lightning Message Service para lidar com alterações de filtros e eventos de seleção de produtos. O componente também suporta paginação e filtragem dinâmica.

## Atributos

### `searchBarIsVisible`
- **Tipo**: `Boolean`
- **Descrição**: Indica se a barra de pesquisa deve ser exibida.

### `tilesAreDraggable`
- **Tipo**: `Boolean`
- **Descrição**: Indica se os tiles de produtos podem ser arrastados.

## Métodos

### `connectedCallback`
Assina o canal de mensagens `ProductsFiltered__c` para receber alterações de filtros.

### `handleProductSelected`
Publica o evento `ProductSelected__c` com o ID do produto selecionado.

#### Parâmetros
- `event` (Event): Evento contendo o ID do produto selecionado.

### `handleSearchKeyChange`
Atualiza os filtros com base na palavra-chave de pesquisa.

#### Parâmetros
- `event` (Event): Evento contendo o valor da palavra-chave.

### `handleFilterChange`
Atualiza os filtros com base na mensagem recebida do canal `ProductsFiltered__c`.

#### Parâmetros
- `message` (Object): Mensagem contendo os filtros aplicados.

### `handlePreviousPage`
Navega para a página anterior na lista de produtos.

### `handleNextPage`
Navega para a próxima página na lista de produtos.

## Exemplo de Uso
```html
<template>
    <c-product-tile-list
        search-bar-is-visible
        tiles-are-draggable
    ></c-product-tile-list>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    handleProductSelected(event) {
        console.log('Produto selecionado:', event.detail.productId);
    }
}
```

## Relacionamentos

- Utiliza: [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel).
- Publica: Canal de mensagens `ProductSelected__c`.
- Assina: Canal de mensagens `ProductsFiltered__c`.