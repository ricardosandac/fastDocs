---
title: paginator
summary: Componente Lightning Web para controle de paginação em listas de itens.
---

# paginator

## Descrição
O componente `paginator` fornece controles de paginação para navegar por uma lista de itens. Ele emite eventos personalizados para notificar componentes pai sobre mudanças de página e calcula dinamicamente o número total de páginas.

## Atributos

### `pageNumber`
- **Tipo**: `Number`
- **Descrição**: O número da página atual.

### `pageSize`
- **Tipo**: `Number`
- **Descrição**: O número de itens por página.

### `totalItemCount`
- **Tipo**: `Number`
- **Descrição**: O número total de itens na lista.

## Métodos

### `handlePrevious`
Dispara o evento `previous` para navegar para a página anterior.

### `handleNext`
Dispara o evento `next` para navegar para a próxima página.

### `currentPageNumber`
- **Descrição**: Retorna o número da página atual, considerando se há itens na lista.

### `isNotFirstPage`
- **Descrição**: Retorna `true` se a página atual não for a primeira.

### `isNotLastPage`
- **Descrição**: Retorna `true` se a página atual não for a última.

### `totalPages`
- **Descrição**: Calcula o número total de páginas com base no número total de itens e no tamanho da página.

## Exemplo de Uso
```html
<template>
    <c-paginator
        page-number={pageNumber}
        page-size={pageSize}
        total-item-count={totalItemCount}
        onprevious={handlePrevious}
        onnext={handleNext}
    ></c-paginator>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    pageNumber = 1;
    pageSize = 10;
    totalItemCount = 100;

    handlePrevious() {
        this.pageNumber -= 1;
    }

    handleNext() {
        this.pageNumber += 1;
    }
}
```

## Relacionamentos

- Utilizado por: Componentes que implementam listas paginadas.