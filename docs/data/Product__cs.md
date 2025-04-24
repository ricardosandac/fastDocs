---
title: Product__cs.json
summary: Dados de exemplo para registros do objeto personalizado Product__c.
---

# Product__cs.json

## Descrição
O arquivo `Product__cs.json` contém dados de exemplo para registros do objeto personalizado `Product__c`. Ele é usado para carregar dados de exemplo em um ambiente Salesforce, como um scratch org, para fins de teste e desenvolvimento.

## Estrutura

### Campos
- **`attributes`**:
  - **`type`**: Define o tipo do objeto. Valor: `Product__c`.
  - **`referenceId`**: Identificador de referência único para o registro.
- **`Name`**: Nome do produto.
- **`Product_Family__c`**: Referência à família do produto.
- **`Description__c`**: Descrição detalhada do produto.
- **`MSRP__c`**: Preço sugerido do produto.
- **`Level__c`**: Nível do produto (ex.: `Beginner`, `Racer`).
- **`Category__c`**: Categoria do produto (ex.: `Commuter`, `Mountain`).
- **`Material__c`**: Material do produto (ex.: `Aluminum`, `Carbon`).
- **`Picture_URL__c`**: URL da imagem do produto.
- **Especificações Técnicas**:
  - **`Battery__c`**: Capacidade da bateria.
  - **`Charger__c`**: Especificações do carregador.
  - **`Motor__c`**: Especificações do motor.
  - **`Fork__c`**: Tipo de garfo.
  - **`Front_Brakes__c`**: Tipo de freio dianteiro.
  - **`Rear_Brakes__c`**: Tipo de freio traseiro.

## Exemplo de Registro
```json
{
    "attributes": {
        "type": "Product__c",
        "referenceId": "Product__cRef1"
    },
    "Name": "FUSE X1",
    "Product_Family__c": "@FuseRef",
    "Description__c": "Lorem ipsum dolor sit amet...",
    "MSRP__c": 2500,
    "Level__c": "Beginner",
    "Category__c": "Commuter",
    "Material__c": "Aluminum",
    "Picture_URL__c": "https://s3-us-west-2.amazonaws.com/dev-or-devrl-s3-bucket/sample-apps/ebikes/fusex1.jpg",
    "Battery__c": "401Wh",
    "Charger__c": "41V4A",
    "Motor__c": "251 watt, 75Nm",
    "Fork__c": "Air spring",
    "Front_Brakes__c": "Dual-pivot caliper brake",
    "Rear_Brakes__c": "Dual-pivot caliper brake"
}
```

## Exemplo de Uso
Este arquivo pode ser usado com o Salesforce CLI para carregar dados de exemplo:
```bash
sfdx force:data:tree:import -f data/Product__cs.json
```

## Relacionamentos

- Utiliza: [Salesforce CLI](https://developer.salesforce.com/tools/sfdxcli).