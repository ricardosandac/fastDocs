---
title: placeholder
layout: default
---

# placeholder

**Caminho Relativo:** `force-app/main/default/lwc/placeholder`

## Visão Geral
O componente `placeholder` é um Lightning Web Component (LWC) que exibe uma mensagem personalizada e um logotipo estático. Ele é útil para exibir mensagens de espera ou informações temporárias.

## Estrutura
### Propriedades
- `@api message`: Mensagem personalizada exibida no componente.

### Variáveis Internas
- `logoUrl`: URL do logotipo estático, obtido do recurso estático `bike_assets`.

## Relacionamentos
- Utiliza o recurso estático `bike_assets` para carregar o logotipo.

## Exemplos
### Código de Exemplo
```javascript
import BIKE_ASSETS_URL from '@salesforce/resourceUrl/bike_assets';

export default class Placeholder extends LightningElement {
    @api message;

    /** Url for bike logo. */
    logoUrl = `${BIKE_ASSETS_URL}/logo.svg`;
}
```

[← Voltar ao índice](index.md)