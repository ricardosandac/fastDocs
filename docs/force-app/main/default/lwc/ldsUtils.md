---
title: ldsUtils
summary: Módulo utilitário para processar erros do Lightning Data Service (LDS).
---

# ldsUtils

## Descrição
O módulo `ldsUtils` fornece funções utilitárias para trabalhar com erros do Lightning Data Service (LDS). Ele ajuda a reduzir erros em mensagens amigáveis e utilizáveis.

## Funções

### `reduceErrors`
Reduz um ou mais erros do LDS em uma lista de mensagens de erro.

#### Parâmetros
- `errors` (FetchResponse | FetchResponse[]): Um único erro ou uma lista de erros retornados pelo LDS.

#### Retorno
- `String[]`: Uma lista de mensagens de erro extraídas.

#### Exemplo de Uso
```javascript
import { reduceErrors } from 'c/ldsUtils';

const errors = [
    { body: [{ message: 'Error 1' }, { message: 'Error 2' }] },
    { body: { message: 'Error 3' } },
    { message: 'Error 4' },
    'Error 5'
];

const errorMessages = reduceErrors(errors);
console.log(errorMessages);
// Saída: ['Error 1', 'Error 2', 'Error 3', 'Error 4', 'Error 5']
```

## Relacionamentos

- Utilizado por: [errorPanel](./errorPanel.md).