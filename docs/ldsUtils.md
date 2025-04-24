---
title: ldsUtils
layout: default
---

# ldsUtils

**Caminho Relativo:** `force-app/main/default/lwc/ldsUtils`

## Visão Geral
O módulo `ldsUtils` fornece utilitários para lidar com erros retornados pelo Lightning Data Service (LDS). Ele inclui uma função para reduzir erros em mensagens amigáveis ao usuário.

## Estrutura
### Funções
- `reduceErrors(errors)`: Reduz um ou mais erros do LDS em um array de mensagens de erro.

#### Parâmetros
- `errors`: Um único erro ou uma lista de erros retornados pelo LDS.

#### Retorno
- Um array de strings contendo mensagens de erro processadas.

### Implementação
```javascript
export function reduceErrors(errors) {
    if (!Array.isArray(errors)) {
        errors = [errors];
    }

    return (
        errors
            .filter((error) => !!error)
            .map((error) => {
                if (typeof error === 'string') {
                    return error;
                }
                if (Array.isArray(error.body)) {
                    return error.body.map((e) => e.message);
                } else if (error.body && typeof error.body.message === 'string') {
                    return error.body.message;
                } else if (typeof error.message === 'string') {
                    return error.message;
                }
                return error.statusText;
            })
            .reduce((prev, curr) => prev.concat(curr), [])
            .filter((message) => !!message)
    );
}
```

## Relacionamentos
- Utilizado por outros componentes Lightning Web Components (LWCs) para processar erros do LDS.

[← Voltar ao índice](index.md)