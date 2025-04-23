---
title: productTile
layout: default
---

# productTile

**Caminho Relativo:** `force-app/main/default/lwc/productTile`

## Visão Geral
O componente `productTile` é um Lightning Web Component (LWC) que exibe informações de um produto (`Product__c`) em um formato de cartão. Ele suporta funcionalidade de arrastar e soltar e permite a seleção de produtos.

## Estrutura
### Propriedades
- `@api draggable`: Indica se o cartão pode ser arrastado.
- `@api product`: Objeto `Product__c` contendo os dados do produto a serem exibidos.

### Variáveis Internas
- `pictureUrl`: URL da imagem do produto.
- `name`: Nome do produto.
- `msrp`: Preço sugerido do produto.

### Métodos
- `handleClick()`: Dispara o evento `selected` com o ID do produto selecionado.
- `handleDragStart(event)`: Configura os dados do produto para serem transferidos durante o evento de arrastar.

## Relacionamentos
- Dispara eventos personalizados:
  - `selected`: Para notificar a seleção de um produto.

## Exemplos
### Código de Exemplo
```javascript
handleClick() {
    const selectedEvent = new CustomEvent('selected', {
        detail: this.product.Id
    });
    this.dispatchEvent(selectedEvent);
}

handleDragStart(event) {
    event.dataTransfer.setData('product', JSON.stringify(this.product));
}
```

[← Voltar ao índice](index.md)