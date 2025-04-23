---
title: orderItemTile
layout: default
---

# orderItemTile

**Caminho Relativo:** `force-app/main/default/lwc/orderItemTile`

## Visão Geral
O componente `orderItemTile` é um Lightning Web Component (LWC) que exibe informações de um item de pedido (`Order_Item__c`). Ele permite editar e excluir itens de pedido diretamente na interface do usuário.

## Estrutura
### Propriedades
- `@api orderItem`: Representa o registro `Order_Item__c` a ser exibido.

### Variáveis Internas
- `isModified`: Indica se o componente possui alterações não salvas.
- `form`: Armazena os valores alterados do formulário antes de serem salvos.

### Métodos
- `handleFormChange(evt)`: Atualiza os valores do formulário e marca o componente como modificado.
- `saveOrderItem()`: Dispara um evento para salvar as alterações no item de pedido.
- `deleteOrderItem()`: Dispara um evento para excluir o item de pedido.

## Relacionamentos
- Dispara os eventos personalizados:
  - `orderitemchange`: Para salvar alterações no item de pedido.
  - `orderitemdelete`: Para excluir o item de pedido.

## Exemplos
### Código de Exemplo
```javascript
handleFormChange(evt) {
    this.isModified = true;
    const field = evt.target.dataset.fieldName;
    let value = parseInt(evt.detail.value.trim(), 10);
    if (!Number.isInteger(value)) {
        value = 0;
    }
    this.form[field] = value;
}

saveOrderItem() {
    const event = new CustomEvent('orderitemchange', {
        detail: Object.assign({}, { Id: this.orderItem.Id }, this.form)
    });
    this.dispatchEvent(event);
    this.isModified = false;
}

deleteOrderItem() {
    const event = new CustomEvent('orderitemdelete', {
        detail: { id: this.orderItem.Id }
    });
    this.dispatchEvent(event);
}
```

[← Voltar ao índice](index.md)