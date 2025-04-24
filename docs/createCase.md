---
title: createCase
layout: default
---

# createCase

**Caminho Relativo:** `force-app/main/default/lwc/createCase`

## Visão Geral
O componente `createCase` é um Lightning Web Component (LWC) que permite criar registros de `Case` no Salesforce. Ele utiliza o componente `lightning-record-edit-form` para gerenciar o formulário de criação.

## Estrutura
### Propriedades
- `caseObject`: Representa o objeto `Case`.
- Campos do objeto `Case`:
  - `subjectField`
  - `productField`
  - `descriptionField`
  - `priorityField`
  - `reasonField`
  - `categoryField`

### Métodos
- `handleCaseCreated`: Exibe uma notificação de sucesso e dispara um evento personalizado `refresh` após a criação do caso.

## Relacionamentos
- Utiliza o componente `lightning-record-edit-form` para criar registros.
- Exibe mensagens de sucesso com `ShowToastEvent`.

## Exemplos
### Código de Exemplo
```javascript
handleCaseCreated() {
    const evt = new ShowToastEvent({
        title: 'Case Created!',
        message: 'You have successfully created a Case',
        variant: 'success'
    });
    this.dispatchEvent(evt);

    const refreshEvt = new CustomEvent('refresh');
    this.dispatchEvent(refreshEvt);
}
```

### Template HTML
```html
<lightning-record-edit-form
    object-api-name={caseObject}
    onsuccess={handleCaseCreated}
>
    <lightning-messages></lightning-messages>
    <lightning-input-field field-name={subjectField}></lightning-input-field>
    <lightning-input-field field-name={descriptionField}></lightning-input-field>
    <lightning-button type="submit" variant="brand" label="Submit"></lightning-button>
</lightning-record-edit-form>
```