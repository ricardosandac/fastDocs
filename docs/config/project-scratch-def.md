---
title: project-scratch-def.json
summary: Configuração do scratch org para o projeto Salesforce DX.
---

# project-scratch-def.json

## Descrição
O arquivo `project-scratch-def.json` define as configurações do scratch org para o projeto Salesforce DX, incluindo o nome da organização, edição, recursos habilitados e configurações específicas.

## Configurações

### Nome da Organização
- **Configuração**: `orgName`
- **Descrição**: Define o nome da organização.
- **Valor**: `Ebikes`

### Edição
- **Configuração**: `edition`
- **Descrição**: Especifica a edição do scratch org.
- **Valor**: `Developer`

### Dados de Exemplo
- **Configuração**: `hasSampleData`
- **Descrição**: Indica se o scratch org deve incluir dados de exemplo.
- **Valor**: `false`

### Recursos Habilitados
- **Configuração**: `features`
- **Descrição**: Lista os recursos habilitados no scratch org.
- **Valores**:
  - `Communities`
  - `Walkthroughs`
  - `EnableSetPasswordInApi`

### Configurações
- **Configuração**: `settings`
- **Descrição**: Define configurações específicas para o scratch org.
- **Valores**:
  - **`communitiesSettings`**: Habilita redes.
  - **`experienceBundleSettings`**: Habilita metadados de pacotes de experiência.
  - **`lightningExperienceSettings`**: Habilita o Lightning Experience no desktop.
  - **`mobileSettings`**: Desabilita o armazenamento criptografado no Salesforce1.
  - **`userEngagementSettings`**: Habilita a orquestração em sandbox.

## Exemplo de Uso
Este arquivo é utilizado ao criar um scratch org com o Salesforce CLI:
```bash
sfdx force:org:create -f config/project-scratch-def.json
```

## Relacionamentos

- Utiliza: [Salesforce DX](https://developer.salesforce.com/tools/sfdxcli).