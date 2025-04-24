---
title: productCard
layout: default
---

# productCard

**Caminho Relativo:** `force-app/main/default/lwc/productCard`

## Visão Geral
O componente `productCard` é um Lightning Web Component (LWC) que exibe os detalhes de um produto (`Product__c`). Ele utiliza o Lightning Message Service para receber notificações de seleção de produtos e permite navegação para o registro do produto.

## Estrutura
### Propriedades
- `recordId`: ID do registro do produto exibido.
- `productName`: Nome do produto exibido.
- `productPictureUrl`: URL da imagem do produto.

### Campos Expostos
- `categoryField`, `levelField`, `msrpField`, `batteryField`, `chargerField`, `motorField`, `materialField`, `forkField`, `frontBrakesField`, `rearBrakesField`: Campos do objeto `Product__c` disponíveis no template.

### Métodos
- `connectedCallback()`: Inscreve-se no canal de mensagens `ProductSelected__c` para receber notificações de seleção de produtos.
- `handleRecordLoaded(event)`: Carrega os dados do registro do produto quando o evento é disparado.
- `handleProductSelected(productId)`: Atualiza o `recordId` com o ID do produto selecionado.
- `handleNavigateToRecord()`: Navega para a página de registro do produto.

## Relacionamentos
- Utiliza o Lightning Message Service para se inscrever no canal `ProductSelected__c`.
- Chama o mixin `NavigationMixin` para navegação entre registros.
- Depende de campos do objeto `Product__c` para exibir informações detalhadas do produto.

## Exemplos
### Código de Exemplo
```javascript
connectedCallback() {
    this.productSelectionSubscription = subscribe(
        this.messageContext,
        PRODUCT_SELECTED_MESSAGE,
        (message) => this.handleProductSelected(message.productId)
    );
}

handleNavigateToRecord() {
    this[NavigationMixin.Navigate]({
        type: 'standard__recordPage',
        attributes: {
            recordId: this.recordId,
            objectApiName: PRODUCT_OBJECT.objectApiName,
            actionName: 'view'
        }
    });
}
```

[← Voltar ao índice](index.md)