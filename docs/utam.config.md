---
title: utam.config.js
summary: Configuração do UTAM (UI Test Automation Model) para o projeto.
---

# utam.config.js

## Descrição
O arquivo `utam.config.js` configura o UTAM (UI Test Automation Model) para o projeto, definindo máscaras de arquivos para objetos de página e aliases para remapeamento de elementos personalizados.

## Configurações

### Máscaras de Arquivos
- **Configuração**: `pageObjectsFileMask`
- **Descrição**: Define as máscaras de arquivos para localizar objetos de página UTAM.
- **Valor**: `['force-app/**/__utam__/**/*.utam.json']`

### Aliases
- **Configuração**: `alias`
- **Descrição**: Remapeia os imports de elementos personalizados.
- **Valor**:
  ```json
  {
      "utam-sfdx/": "../"
  }
  ```

## Exemplo de Uso
Este arquivo é automaticamente utilizado pelo UTAM ao executar testes de interface do usuário no projeto.

## Relacionamentos

- Utiliza: [UTAM](https://github.com/salesforce/utam-js).