---
title: sfdx-project.json
summary: Configuração do projeto Salesforce DX.
---

# sfdx-project.json

## Descrição
O arquivo `sfdx-project.json` define as configurações principais do projeto Salesforce DX, incluindo diretórios de código-fonte, namespace e versão da API.

## Configurações

### Diretórios de Pacotes
- **Configuração**: `packageDirectories`
- **Descrição**: Define os diretórios que contêm o código-fonte do projeto.
- **Valor**:
  ```json
  [
      {
          "path": "force-app",
          "default": true
      }
  ]
  ```

### Namespace
- **Configuração**: `namespace`
- **Descrição**: Define o namespace do projeto. Está vazio neste caso.

### Versão da API
- **Configuração**: `sourceApiVersion`
- **Descrição**: Especifica a versão da API usada no projeto.
- **Valor**: `63.0`

## Exemplo de Uso
Este arquivo é automaticamente utilizado pelo Salesforce CLI ao executar comandos relacionados ao projeto.

## Relacionamentos

- Utiliza: [Salesforce DX](https://developer.salesforce.com/tools/sfdxcli).