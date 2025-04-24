---
title: productFilter
layout: default
---

# productFilter

**Caminho Relativo:** `force-app/main/default/lwc/productFilter`

## Visão Geral
O componente `productFilter` é um Lightning Web Component (LWC) que exibe um painel de filtros para buscar produtos (`Product__c`). Ele permite filtrar produtos com base em critérios como categoria, nível, material, preço máximo e palavras-chave.

## Estrutura
### Propriedades
- `searchKey`: Palavra-chave usada para buscar produtos.
- `maxPrice`: Preço máximo para filtrar produtos.
- `filters`: Objeto que armazena os critérios de filtro selecionados.

### Métodos
- `handleSearchKeyChange(event)`: Atualiza a palavra-chave de busca e dispara o evento de filtro com atraso.
- `handleMaxPriceChange(event)`: Atualiza o preço máximo e dispara o evento de filtro com atraso.
- `handleCheckboxChange(event)`: Atualiza os filtros de categoria, nível e material com base nas caixas de seleção marcadas.
- `delayedFireFilterChangeEvent()`: Dispara o evento de filtro com atraso para evitar chamadas excessivas ao Apex.

## Relacionamentos
- Utiliza o Lightning Message Service para publicar mensagens no canal `ProductsFiltered__c`.
- Obtém valores de lista de opções (`picklist`) dos campos `Category__c`, `Level__c` e `Material__c` do objeto `Product__c`.

## Exemplos
### Código de Exemplo
```javascript
handleSearchKeyChange(event) {
    this.filters.searchKey = event.target.value;
    this.delayedFireFilterChangeEvent();
}

handleCheckboxChange(event) {
    const value = event.target.dataset.value;
    const filterArray = this.filters[event.target.dataset.filter];
    if (event.target.checked) {
        if (!filterArray.includes(value)) {
            filterArray.push(value);
        }
    } else {
        this.filters[event.target.dataset.filter] = filterArray.filter(
            (item) => item !== value
        );
    }
    publish(this.messageContext, PRODUCTS_FILTERED_MESSAGE, {
        filters: this.filters
    });
}
```

[← Voltar ao índice](index.md)