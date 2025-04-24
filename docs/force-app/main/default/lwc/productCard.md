---
title: productCard
summary: Componente Lightning Web para exibir detalhes de um registro Product__c.
---

# productCard

## Descrição
O componente `productCard` exibe detalhes de um registro `Product__c`. Ele utiliza o Lightning Message Service para lidar com eventos de seleção de produtos e o NavigationMixin para navegar até a página do registro do produto.

## Atributos

### `recordId`
- **Tipo**: `String`
- **Descrição**: O ID do registro `Product__c` a ser exibido.

### `productName`
- **Tipo**: `String`
- **Descrição**: O nome do produto exibido no cartão.

### `productPictureUrl`
- **Tipo**: `String`
- **Descrição**: A URL da imagem do produto exibida no cartão.

## Métodos

### `connectedCallback`
Assina o canal de mensagens `ProductSelected__c` para receber eventos de seleção de produtos.

### `handleRecordLoaded`
Lida com o carregamento do registro e extrai os campos necessários.

#### Parâmetros
- `event` (Object): Evento contendo os dados do registro carregado.

### `handleProductSelected`
Atualiza o `recordId` com base no produto selecionado.

#### Parâmetros
- `productId` (String): O ID do produto selecionado.

### `handleNavigateToRecord`
Navega até a página do registro do produto usando o NavigationMixin.

## Exemplo de Uso
```html
<template>
    <c-product-card></c-product-card>
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
- Utiliza: [NavigationMixin](https://developer.salesforce.com/docs/component-library/documentation/en/lwc/lwc.use_navigate).