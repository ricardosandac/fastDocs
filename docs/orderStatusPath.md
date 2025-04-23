---
title: orderStatusPath
layout: default
---

# orderStatusPath

**Caminho Relativo:** `force-app/main/default/lwc/orderStatusPath`

## Visão Geral
O componente `orderStatusPath` é um Lightning Web Component (LWC) que exibe um caminho baseado em um campo de lista de opções (`picklist`) de um registro de pedido (`Order__c`). Ele também suporta a API de streaming para atualizar o status em tempo real com base em eventos de plataforma.

## Estrutura
### Propriedades
- `@api recordId`: ID do registro do pedido (`Order__c`).
- `recordTypeId`: ID do tipo de registro associado ao pedido.
- `picklistValue`: Valor atual do campo de lista de opções.
- `pathItems`: Itens do caminho gerados com base nos valores da lista de opções.
- `errorMessage`: Mensagem de erro exibida em caso de falha.

### Métodos
- `connectedCallback()`: Inscreve-se no canal de eventos de plataforma para atualizações em tempo real.
- `disconnectedCallback()`: Cancela a inscrição no canal de eventos ao desconectar o componente.
- `handleManufacturingEvent(event)`: Atualiza o status do pedido com base no evento recebido.
- `handlePathItemClick(event)`: Atualiza o valor do campo de lista de opções ao clicar em um item do caminho.
- `setPicklistValue(value)`: Atualiza o valor do campo de lista de opções no servidor.
- `refreshPathItems()`: Atualiza os itens do caminho com base nos valores da lista de opções e no valor atual.
- `reportError(baseMessage, cause)`: Exibe mensagens de erro formatadas.

### Funções Auxiliares
- `getPathItemCssClasses(isCurrent, isCompleted)`: Retorna as classes CSS apropriadas para um item do caminho com base no estado atual e concluído.

## Relacionamentos
- Utiliza a API de streaming (`lightning/empApi`) para receber eventos de plataforma.
- Chama os métodos `getRecord`, `updateRecord`, `getPicklistValues` e `getObjectInfo` do LDS.
- Depende do módulo `ldsUtils` para processar erros.

## Exemplos
### Código de Exemplo
```javascript
async connectedCallback() {
    const isEmpApiEnabled = await isEmpEnabled();
    if (!isEmpApiEnabled) {
        this.reportError('The EMP API is not enabled.');
        return;
    }
    setDebugFlag(true);
    onError((error) => {
        this.reportError('EMP API error', error);
    });

    try {
        this.subscription = await subscribe(
            '/event/Manufacturing_Event__e',
            -1,
            (event) => {
                this.handleManufacturingEvent(event);
            }
        );
    } catch (error) {
        this.reportError('EMP API error: failed to subscribe', error);
    }
}
```

[← Voltar ao índice](index.md)