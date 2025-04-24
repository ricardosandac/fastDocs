---
title: PagedResult
summary: Estrutura de dados para armazenar informações de paginação e registros retornados.
---

# PagedResult

## Descrição
A classe `PagedResult` é uma estrutura de dados utilizada para armazenar informações de paginação, como o tamanho da página, o número da página atual, o total de itens e os registros retornados. É amplamente utilizada em métodos que implementam paginação em consultas no Salesforce.

## Atributos

### `pageSize`
- **Tipo**: `Integer`
- **Descrição**: O número de registros por página.

### `pageNumber`
- **Tipo**: `Integer`
- **Descrição**: O número da página atual.

### `totalItemCount`
- **Tipo**: `Integer`
- **Descrição**: O número total de itens disponíveis.

### `records`
- **Tipo**: `Object[]`
- **Descrição**: A lista de registros retornados para a página atual.

## Exemplo de Uso
```apex
// Exemplo de como instanciar e usar a classe PagedResult
PagedResult result = new PagedResult();
result.pageSize = 10;
result.pageNumber = 1;
result.totalItemCount = 100;
result.records = new List<Object>{};
System.debug('Página: ' + result.pageNumber + ' de ' + (result.totalItemCount / result.pageSize));
```