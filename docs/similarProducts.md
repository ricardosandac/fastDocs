---
title: similarProducts
layout: default
---

# similarProducts

**Caminho Relativo:** `force-app/main/default/lwc/similarProducts`

## Visão Geral
O componente `similarProducts` é um Lightning Web Component (LWC) que exibe uma lista de produtos similares com base na família de produtos (`Product_Family__c`). Ele utiliza o Lightning Data Service (LDS) e chamadas Apex para buscar os dados necessários.

## Estrutura
### Propriedades
- `@api recordId`: ID do registro do produto atual.
- `@api familyId`: ID da família de produtos associada ao produto atual.

### Métodos
- `get errors()`: Retorna uma lista de erros, se houver, das chamadas LDS ou Apex.
- `get hasNoSimilarProducts()`: Retorna `true` se não houver produtos similares encontrados.

## Relacionamentos
- Utiliza o LDS para buscar o campo `Product_Family__c` do produto atual.
- Chama o método Apex `getSimilarProducts` da classe `ProductController` para buscar produtos similares.

## Exemplos
### Código de Exemplo
```javascript
@wire(getRecord, { recordId: '$recordId', fields })
product;

@wire(getSimilarProducts, {
    productId: '$recordId',
    familyId: '$product.data.fields.Product_Family__c.value'
})
similarProducts;

get errors() {
    const errors = [this.product.error, this.similarProducts.error].filter(
        (error) => error
    );
    return errors.length ? errors : undefined;
}

get hasNoSimilarProducts() {
    return this.similarProducts.data.length === 0;
}
```

[← Voltar ao índice](index.md)