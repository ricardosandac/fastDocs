---
title: heroDetails
summary: Componente Lightning Web para exibir detalhes sobre um vídeo ou imagem com base em informações de registro.
---

# heroDetails

## Descrição
O componente `heroDetails` exibe detalhes sobre um vídeo ou imagem, incluindo título, slogan e informações de registro. Ele utiliza um método Apex para buscar informações do registro e gera dinamicamente uma URL com base no tipo de registro.

## Atributos

### `title`
- **Tipo**: `String`
- **Descrição**: O título exibido no componente. Valor padrão: `Hero Details`.

### `slogan`
- **Tipo**: `String`
- **Descrição**: O slogan exibido abaixo do título.

### `recordName`
- **Tipo**: `String`
- **Descrição**: O nome do registro usado para buscar informações adicionais.

## Métodos

### `recordInfo`
- **Descrição**: Método chamado automaticamente pelo serviço `@wire` para buscar informações do registro usando o método Apex `getRecordInfo`.

#### Parâmetros
- `error`: Contém informações de erro, caso a consulta falhe.
- `data`: Contém os dados do registro retornados pela consulta.

#### Comportamento
- Atualiza a URL (`hrefUrl`) com base no tipo de registro (`Product__c` ou outro).

## Exemplo de Uso
```html
<template>
    <c-hero-details
        title="Product Details"
        slogan="Explore the features"
        record-name="SampleProduct"
    ></c-hero-details>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    recordName = 'SampleProduct';
}
```

## Relacionamentos

- Veja também: [ProductRecordInfoController.getRecordInfo](../classes/ProductRecordInfoController.md).