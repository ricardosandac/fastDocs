---
title: heroDetails
layout: default
---

# heroDetails

**Caminho Relativo:** `force-app/main/default/lwc/heroDetails`

## Visão Geral
O componente `heroDetails` é um Lightning Web Component (LWC) que exibe detalhes sobre um produto ou família de produtos. Ele é projetado para ser exibido sobre um vídeo ou imagem no componente `hero`.

## Estrutura
### Propriedades
- `@api title`: Título do componente (padrão: "Hero Details").
- `@api slogan`: Slogan exibido no componente.
- `@api recordName`: Nome do registro (produto ou família de produtos) para buscar informações adicionais.

### Métodos
- `@wire getRecordInfo`: Método Apex que busca informações do registro com base no nome do produto ou família de produtos.

### Variáveis Internas
- `recordInfoData`: Armazena os dados ou erros retornados pelo método `getRecordInfo`.
- `hrefUrl`: URL gerada para navegação com base no tipo de registro (`Product__c` ou outro).

## Relacionamentos
- Chama o método Apex `getRecordInfo` da classe `ProductRecordInfoController`.
- Gera URLs dinâmicas para navegação com base nos dados retornados.

## Exemplos
### Código de Exemplo
```javascript
@wire(getRecordInfo, { productOrFamilyName: '$recordName' })
recordInfo({ error, data }) {
    this.recordInfoData = { error, data };
    if (!error && data) {
        if (data[1] === 'Product__c') {
            this.hrefUrl = `product/${data[0]}`;
        } else {
            this.hrefUrl = `detail/${data[0]}`;
        }
    }
}
```

[← Voltar ao índice](index.md)