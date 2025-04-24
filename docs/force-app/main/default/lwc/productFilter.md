---
title: productFilter
summary: Componente Lightning Web para exibir um painel de filtros para pesquisar registros Product__c.
---

# productFilter

## Descrição
O componente `productFilter` exibe um painel de filtros para pesquisar registros `Product__c`. Ele utiliza valores de picklist para categorias, níveis e materiais, e publica alterações nos filtros por meio do Lightning Message Service.

## Atributos

### `searchKey`
- **Tipo**: `String`
- **Descrição**: A palavra-chave usada para pesquisar produtos.

### `maxPrice`
- **Tipo**: `Number`
- **Descrição**: O preço máximo usado para filtrar produtos.

### `filters`
- **Tipo**: `Object`
- **Descrição**: Objeto contendo os filtros aplicados, como `searchKey`, `maxPrice`, `categories`, `levels` e `materials`.

## Métodos

### `handleSearchKeyChange`
Atualiza a palavra-chave de pesquisa e publica as alterações nos filtros.

#### Parâmetros
- `event` (Event): Evento contendo o valor da palavra-chave.

### `handleMaxPriceChange`
Atualiza o preço máximo e publica as alterações nos filtros.

#### Parâmetros
- `event` (Event): Evento contendo o valor do preço máximo.

### `handleCheckboxChange`
Atualiza os filtros de categorias, níveis ou materiais com base nas caixas de seleção marcadas.

#### Parâmetros
- `event` (Event): Evento contendo os valores das caixas de seleção.

### `delayedFireFilterChangeEvent`
Publica as alterações nos filtros com um atraso para evitar chamadas excessivas ao Apex.

## Exemplo de Uso
```html
<template>
    <c-product-filter></c-product-filter>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    handleFilterChange(event) {
        console.log('Filtros aplicados:', event.detail.filters);
    }
}
```

## Relacionamentos

- Utiliza: [Lightning Message Service](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_message_channel).
- Publica: Canal de mensagens `ProductsFiltered__c`.