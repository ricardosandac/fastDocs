---
title: eslint.config.js
summary: Configuração do ESLint para o projeto, incluindo regras para LWC, Jest e UTAM.
---

# eslint.config.js

## Descrição
O arquivo `eslint.config.js` configura o ESLint para o projeto, definindo regras específicas para diferentes partes do código, como componentes Lightning Web (LWC), mocks do Jest e testes UTAM.

## Configurações

### LWC
- **Arquivos**: `force-app/main/default/lwc/**/*.js`
- **Extensões**: `@salesforce/eslint-config-lwc/recommended`

### Testes LWC
- **Arquivos**: `force-app/main/default/lwc/**/*.test.js`
- **Regras**:
  - Desativa `@lwc/lwc/no-unexpected-wire-adapter-usages`
- **Globais**: `node`

### Mocks do Jest
- **Arquivos**: `force-app/test/jest-mocks/**/*.js`
- **Globais**: `node`, `es2021`, `jest`
- **Extensões**: `eslintJs/recommended`

### Testes UTAM
- **Arquivos**: `force-app/test/utam/**/*.js`
- **Globais**: `node`, `es2021`, `jasmine`, `utam`, `browser`
- **Extensões**: `eslintJs/recommended`

## Exemplo de Uso
Este arquivo é automaticamente utilizado pelo ESLint ao executar verificações de lint no projeto.

## Relacionamentos

- Utiliza: [@salesforce/eslint-config-lwc](https://github.com/forcedotcom/eslint-config-lwc).
- Utiliza: [eslint-plugin-jest](https://github.com/jest-community/eslint-plugin-jest).
- Utiliza: [eslint-plugin-jasmine](https://github.com/tlvince/eslint-plugin-jasmine).