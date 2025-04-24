---
title: createCase
summary: Componente Lightning Web para criar um novo registro de Caso no Salesforce.
---

# createCase

## Descrição
O componente `createCase` permite que os usuários criem um novo registro de Caso no Salesforce. Ele exibe uma mensagem de sucesso ao criar o Caso e dispara um evento personalizado para atualizar componentes relacionados.

## Atributos

### `caseObject`
- **Tipo**: `Object`
- **Descrição**: Representa o objeto `Case` do Salesforce.

### `subjectField`
- **Tipo**: `Object`
- **Descrição**: Campo `Subject` do objeto `Case`.

### `descriptionField`
- **Tipo**: `Object`
- **Descrição**: Campo `Description` do objeto `Case`.

### `productField`
- **Tipo**: `Object`
- **Descrição**: Campo personalizado `Product__c` do objeto `Case`.

### `priorityField`
- **Tipo**: `Object`
- **Descrição**: Campo `Priority` do objeto `Case`.

### `reasonField`
- **Tipo**: `Object`
- **Descrição**: Campo `Reason` do objeto `Case`.

### `categoryField`
- **Tipo**: `Object`
- **Descrição**: Campo personalizado `Case_Category__c` do objeto `Case`.

## Métodos

### `handleCaseCreated`
Método chamado ao criar um novo Caso.

#### Comportamento
- Exibe uma mensagem de sucesso usando o evento `ShowToastEvent`.
- Dispara um evento personalizado `refresh` para notificar componentes relacionados.

## Exemplo de Uso
```html
<template>
    <lightning-record-edit-form
        object-api-name={caseObject}
        onsuccess={handleCaseCreated}
    >
        <lightning-messages></lightning-messages>
        <lightning-input-field field-name={subjectField}></lightning-input-field>
        <lightning-input-field field-name={descriptionField}></lightning-input-field>
        <lightning-input-field field-name={productField}></lightning-input-field>
        <lightning-input-field field-name={priorityField}></lightning-input-field>
        <lightning-input-field field-name={reasonField}></lightning-input-field>
        <lightning-input-field field-name={categoryField}></lightning-input-field>
        <lightning-button type="submit" label="Create Case"></lightning-button>
    </lightning-record-edit-form>
</template>
```

```javascript
import { LightningElement } from 'lwc';
import { ShowToastEvent } from 'lightning/platformShowToastEvent';

import CASE_OBJECT from '@salesforce/schema/Case';
import SUBJECT from '@salesforce/schema/Case.Subject';
import DESCRIPTION from '@salesforce/schema/Case.Description';
import PRODUCT from '@salesforce/schema/Case.Product__c';
import PRIORITY from '@salesforce/schema/Case.Priority';
import CASE_CATEGORY from '@salesforce/schema/Case.Case_Category__c';
import REASON from '@salesforce/schema/Case.Reason';

const TITLE_SUCCESS = 'Case Created!';
const MESSAGE_SUCCESS = 'You have successfully created a Case';

export default class CreateCase extends LightningElement {
    caseObject = CASE_OBJECT;
    subjectField = SUBJECT;
    productField = PRODUCT;
    descriptionField = DESCRIPTION;
    priorityField = PRIORITY;
    reasonField = REASON;
    categoryField = CASE_CATEGORY;

    handleCaseCreated() {
        const evt = new ShowToastEvent({
            title: TITLE_SUCCESS,
            message: MESSAGE_SUCCESS,
            variant: 'success'
        });
        this.dispatchEvent(evt);

        const refreshEvt = new CustomEvent('refresh');
        this.dispatchEvent(refreshEvt);
    }
}
```

## Relacionamentos

- Veja também: [lightning-record-edit-form](https://developer.salesforce.com/docs/component-library/bundle/lightning-record-edit-form/documentation).