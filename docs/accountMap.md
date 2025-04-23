---
title: accountMap
layout: default
---

# accountMap

**Caminho Relativo:** `force-app/main/default/lwc/accountMap`

## Visão Geral
O componente `accountMap` é um Lightning Web Component (LWC) que exibe um mapa com marcadores baseados no endereço de cobrança de uma conta. Ele utiliza a API `lightning/uiRecordApi` para buscar e processar os dados da conta.

## Estrutura
### Propriedades
- `@api recordId`: ID do registro da conta.
- `zoomLevel`: Nível de zoom do mapa (padrão: 14).
- `markers`: Array de marcadores do mapa.
- `error`: Armazena erros encontrados durante a busca de dados.

### Métodos
- `wiredRecord`: Método decorado com `@wire` para buscar os dados da conta e configurar os marcadores do mapa.

## Relacionamentos
- Importa campos do objeto `Account`:
  - `BillingCity`
  - `BillingCountry`
  - `BillingPostalCode`
  - `BillingState`
  - `BillingStreet`
- Utiliza o componente `lightning-map` para exibir o mapa.
- Exibe o componente `c-error-panel` em caso de erro.

## Exemplos
### Código de Exemplo
```javascript
@wire(getRecord, { recordId: '$recordId', fields })
wiredRecord({ error, data }) {
    if (data) {
        this.markers = [
            {
                location: {
                    City: getFieldValue(data, BILLING_CITY),
                    Country: getFieldValue(data, BILLING_COUNTRY),
                    PostalCode: getFieldValue(data, BILLING_POSTAL_CODE),
                    State: getFieldValue(data, BILLING_STATE),
                    Street: getFieldValue(data, BILLING_STREET)
                }
            }
        ];
    } else if (error) {
        this.error = error;
    }
}
```