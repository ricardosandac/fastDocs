---
title: orderStatusPath
summary: Componente Lightning Web para gerenciar o campo Status__c de um registro Order__c com suporte a eventos de plataforma.
---

# orderStatusPath

## Descrição
O componente `orderStatusPath` é um caminho personalizado para gerenciar o campo `Status__c` de um registro `Order__c`. Ele integra-se à API EMP do Salesforce para lidar com eventos de plataforma e atualiza dinamicamente o caminho com base no status atual. O componente também permite que os usuários atualizem o status por meio de interações.

## Atributos

### `recordId`
- **Tipo**: `String`
- **Descrição**: O ID do registro `Order__c` associado ao componente.

## Métodos

### `connectedCallback`
Assina o canal de eventos de plataforma `Manufacturing_Event__e` para receber atualizações de status.

### `disconnectedCallback`
Cancela a assinatura do canal de eventos de plataforma ao desconectar o componente.

### `handleManufacturingEvent`
Lida com eventos de plataforma para atualizar o status do pedido.

#### Parâmetros
- `event` (Object): Evento de plataforma contendo os dados do pedido.

### `handlePathItemClick`
Lida com cliques nos itens do caminho para atualizar o status do pedido.

#### Parâmetros
- `event` (Event): Evento de clique contendo o valor do status selecionado.

### `setPicklistValue`
Atualiza o valor do campo `Status__c` no registro `Order__c`.

#### Parâmetros
- `value` (String): O novo valor do status.

### `refreshPathItems`
Atualiza os itens do caminho com base nos valores do picklist e no status atual.

### `getPathItemCssClasses`
Retorna as classes CSS para um item do caminho com base no status atual e concluído.

#### Parâmetros
- `isCurrent` (Boolean): Indica se o item é o status atual.
- `isCompleted` (Boolean): Indica se o item foi concluído.

#### Retorno
- `String`: Classes CSS para o item do caminho.

### `reportError`
Relata erros exibindo mensagens amigáveis.

#### Parâmetros
- `baseMessage` (String): Mensagem base do erro.
- `cause` (Object): Detalhes adicionais do erro.

## Exemplo de Uso
```html
<template>
    <c-order-status-path record-id="a0123456789XYZ"></c-order-status-path>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    recordId = 'a0123456789XYZ';
}
```

## Relacionamentos

- Utiliza: [ldsUtils.reduceErrors](./ldsUtils.md).