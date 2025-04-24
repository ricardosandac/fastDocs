---
title: generate-login-url.js
summary: Script para gerar um arquivo .env com a URL de login de um scratch org do Salesforce.
---

# generate-login-url.js

## Descrição
O script `generate-login-url.js` gera um arquivo `.env` contendo a URL de login de um scratch org do Salesforce. Ele utiliza o CLI do Salesforce para obter a URL e grava as informações no arquivo.

## Funcionalidades

### `getScratchOrgLoginUrl`
- **Descrição**: Obtém a URL de login do scratch org executando um comando CLI do Salesforce.
- **Retorno**: Uma string contendo a URL de login.

### `generateLoginUrl`
- **Descrição**: Gera o arquivo `.env` com a URL de login e a data/hora de geração.
- **Passos**:
  1. Obtém a URL de login usando `getScratchOrgLoginUrl`.
  2. Cria um arquivo `.env` com o conteúdo:
     ```
     SALESFORCE_LOGIN_URL=<url>
     SALESFORCE_LOGIN_TIME=<timestamp>
     ```

## Exemplo de Uso
Este script é executado diretamente no terminal:
```bash
node scripts/generate-login-url.js
```

## Relacionamentos

- Utiliza: [Node.js `child_process`](https://nodejs.org/api/child_process.html).
- Utiliza: [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli).