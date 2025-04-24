---
title: accountMap
summary: Componente Lightning Web para exibir um mapa com base no endereço de cobrança de uma conta.
---

# accountMap

## Descrição
O componente `accountMap` exibe um mapa com marcadores baseados no endereço de cobrança de um registro de Conta. Ele utiliza o módulo `lightning/uiRecordApi` para buscar os campos do endereço de cobrança.

## Atributos

### `recordId`
- **Tipo**: `String`
- **Descrição**: O ID do registro da Conta cujos dados de endereço serão exibidos no mapa.

## Métodos

### `wiredRecord`
Método chamado automaticamente pelo serviço `@wire` para buscar os dados do registro da Conta e atualizar os marcadores do mapa.

#### Parâmetros
- `error`: Contém informações de erro, caso a consulta falhe.
- `data`: Contém os dados do registro retornados pela consulta.

#### Comportamento
- Atualiza os marcadores do mapa com base nos campos de endereço de cobrança.
- Define `error` caso ocorra um problema na consulta.

## Exemplo de Uso
```html
<template>
    <lightning-map
        if:true={markers.length}
        markers={markers}
        zoom-level={zoomLevel}
    ></lightning-map>
    <template if:true={error}>
        <p>{error}</p>
    </template>
</template>
```

```javascript
import { LightningElement, api, wire } from 'lwc';
import { getRecord, getFieldValue } from 'lightning/uiRecordApi';

import BILLING_CITY from '@salesforce/schema/Account.BillingCity';
import BILLING_COUNTRY from '@salesforce/schema/Account.BillingCountry';
import BILLING_POSTAL_CODE from '@salesforce/schema/Account.BillingPostalCode';
import BILLING_STATE from '@salesforce/schema/Account.BillingState';
import BILLING_STREET from '@salesforce/schema/Account.BillingStreet';

const fields = [
    BILLING_CITY,
    BILLING_COUNTRY,
    BILLING_POSTAL_CODE,
    BILLING_STATE,
    BILLING_STREET
];

export default class AccountMap extends LightningElement {
    @api recordId;

    zoomLevel = 14;
    markers = [];
    error;

    @wire(getRecord, { recordId: '$recordId', fields })
    wiredRecord({ error, data }) {
        if (data) {
            this.markers = [];
            this.error = undefined;
            const street = getFieldValue(data, BILLING_STREET);
            if (street) {
                this.markers = [
                    {
                        location: {
                            City: getFieldValue(data, BILLING_CITY),
                            Country: getFieldValue(data, BILLING_COUNTRY),
                            PostalCode: getFieldValue(
                                data,
                                BILLING_POSTAL_CODE
                            ),
                            State: getFieldValue(data, BILLING_STATE),
                            Street: street
                        }
                    }
                ];
            }
        } else if (error) {
            this.markers = [];
            this.error = error;
        }
    }
}
```

## Relacionamentos

- Veja também: [lightning-map](https://developer.salesforce.com/docs/component-library/bundle/lightning-map/documentation).