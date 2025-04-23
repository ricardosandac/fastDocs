---
title: paginator
layout: default
---

# paginator

**Caminho Relativo:** `force-app/main/default/lwc/paginator`

## Visão Geral
O componente `paginator` é um Lightning Web Component (LWC) que fornece uma interface de paginação para listas de itens. Ele permite navegar entre páginas de forma simples, emitindo eventos para controle externo.

## Estrutura
### Propriedades
- `@api pageNumber`: Número da página atual.
- `@api pageSize`: Número de itens por página.
- `@api totalItemCount`: Número total de itens na lista.

### Métodos
- `handlePrevious()`: Dispara o evento `previous` para navegar para a página anterior.
- `handleNext()`: Dispara o evento `next` para navegar para a próxima página.

### Getters
- `currentPageNumber`: Retorna o número da página atual ou 0 se não houver itens.
- `isNotFirstPage`: Retorna `true` se a página atual não for a primeira.
- `isNotLastPage`: Retorna `true` se a página atual não for a última.
- `totalPages`: Calcula o número total de páginas com base no total de itens e no tamanho da página.

## Relacionamentos
- Dispara eventos personalizados:
  - `previous`: Para navegar para a página anterior.
  - `next`: Para navegar para a próxima página.

## Exemplos
### Código de Exemplo
```javascript
handlePrevious() {
    this.dispatchEvent(new CustomEvent('previous'));
}

handleNext() {
    this.dispatchEvent(new CustomEvent('next'));
}

get totalPages() {
    return Math.ceil(this.totalItemCount / this.pageSize);
}
```

[← Voltar ao índice](index.md)