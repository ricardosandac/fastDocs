---
title: Accounts.json
summary: Dados de exemplo para registros do objeto Account.
---

# Accounts.json

## Descrição
O arquivo `Accounts.json` contém dados de exemplo para registros do objeto `Account`. Ele é usado para carregar dados de exemplo em um ambiente Salesforce, como um scratch org, para fins de teste e desenvolvimento.

## Estrutura

### Campos
- **`attributes`**:
  - **`type`**: Define o tipo do objeto. Valor: `Account`.
  - **`referenceId`**: Identificador de referência único para o registro.
- **`Name`**: Nome da conta.
- **`BillingStreet`**: Rua do endereço de cobrança.
- **`BillingCity`**: Cidade do endereço de cobrança.
- **`BillingState`**: Estado do endereço de cobrança.
- **`BillingPostalCode`**: CEP do endereço de cobrança.
- **`BillingCountry`**: País do endereço de cobrança.

## Exemplo de Registro
```json
{
    "attributes": {
        "type": "Account",
        "referenceId": "AccountRef1"
    },
    "Name": "Wheelworks",
    "BillingStreet": "480 Trapelo Road",
    "BillingCity": "Belmont",
    "BillingState": "MA",
    "BillingPostalCode": "02478",
    "BillingCountry": "USA"
}
```

## Exemplo de Uso
Este arquivo pode ser usado com o Salesforce CLI para carregar dados de exemplo:
```bash
sfdx force:data:tree:import -f data/Accounts.json
```

## Relacionamentos

- Utiliza: [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli).