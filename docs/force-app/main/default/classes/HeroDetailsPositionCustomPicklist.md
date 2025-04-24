---
title: HeroDetailsPositionCustomPicklist
summary: Classe global que implementa um picklist dinâmico com valores predefinidos.
---

# HeroDetailsPositionCustomPicklist

## Descrição
A classe `HeroDetailsPositionCustomPicklist` estende `VisualEditor.DynamicPickList` e fornece um picklist dinâmico com valores predefinidos, como "Left" e "Right". É usada para configurar opções de posição em componentes visuais.

## Métodos

### `getDefaultValue`
Retorna o valor padrão do picklist.

#### Retorno
- `VisualEditor.DataRow`: O valor padrão do picklist, que é "Right".

#### Exemplo de Uso
```apex
// Obtém o valor padrão do picklist
global class MyPicklist extends HeroDetailsPositionCustomPicklist {
    VisualEditor.DataRow defaultValue = getDefaultValue();
    System.debug('Valor padrão: ' + defaultValue);
}
```

### `getValues`
Retorna os valores disponíveis no picklist.

#### Retorno
- `VisualEditor.DynamicPickListRows`: Os valores disponíveis no picklist, incluindo "Left" e "Right".

#### Exemplo de Uso
```apex
// Obtém os valores disponíveis no picklist
global class MyPicklist extends HeroDetailsPositionCustomPicklist {
    VisualEditor.DynamicPickListRows values = getValues();
    for (VisualEditor.DataRow row : values) {
        System.debug('Valor: ' + row);
    }
}
```

## Relacionamentos

- Veja também: [VisualEditor.DynamicPickList](https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_class_VisualEditor_DynamicPickList.htm).