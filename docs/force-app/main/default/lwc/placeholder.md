---
title: placeholder
summary: Componente Lightning Web para exibir uma mensagem de placeholder com um logotipo estático.
---

# placeholder

## Descrição
O componente `placeholder` exibe uma mensagem de placeholder junto com um logotipo estático. Ele utiliza um recurso estático (`bike_assets`) para carregar o logotipo.

## Atributos

### `message`
- **Tipo**: `String`
- **Descrição**: A mensagem de placeholder exibida no componente.

## Exemplo de Uso
```html
<template>
    <c-placeholder message="Nenhum dado disponível no momento."></c-placeholder>
</template>
```

```javascript
import { LightningElement } from 'lwc';

export default class ParentComponent extends LightningElement {
    message = 'Nenhum dado disponível no momento.';
}
```

## Relacionamentos

- Utiliza: Recurso estático `bike_assets` para carregar o logotipo.