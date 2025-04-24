---
title: jest.config.js
summary: Configuração do Jest para testes no projeto.
---

# jest.config.js

## Descrição
O arquivo `jest.config.js` configura o Jest para testes no projeto, incluindo arquivos de configuração adicionais e mapeamento de módulos para lidar com dependências específicas do Salesforce.

## Configurações

### Arquivos de Configuração Adicionais
- **Configuração**: `setupFilesAfterEnv`
- **Descrição**: Adiciona arquivos de configuração adicionais para o ambiente de teste.
- **Valor**: `jest-sa11y-setup.js`

### Regex de Testes
- **Configuração**: `testRegex`
- **Descrição**: Define o padrão de regex para localizar arquivos de teste.
- **Valor**: `/__tests__/.*.test.js$`

### Mapeamento de Módulos
- **Configuração**: `moduleNameMapper`
- **Descrição**: Mapeia módulos específicos do Salesforce para mocks personalizados.
- **Valores**:
  - `@salesforce/apex`: `force-app/test/jest-mocks/apex`
  - `lightning/navigation`: `force-app/test/jest-mocks/lightning/navigation`
  - `lightning/messageService`: `force-app/test/jest-mocks/lightning/messageService`
  - `lightning/empApi`: `force-app/test/jest-mocks/lightning/empApi`

## Exemplo de Uso
Este arquivo é automaticamente utilizado pelo Jest ao executar testes no projeto.

## Relacionamentos

- Utiliza: [@salesforce/sfdx-lwc-jest](https://github.com/salesforce/sfdx-lwc-jest).