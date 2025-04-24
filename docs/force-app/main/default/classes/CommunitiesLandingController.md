---
title: CommunitiesLandingController
summary: Controlador Apex que redireciona usuários para a página inicial apropriada com base em suas credenciais.
---

# CommunitiesLandingController

## Descrição
A classe `CommunitiesLandingController` é um controlador Apex que redireciona o usuário para a página inicial apropriada com base em suas credenciais ou na ausência delas.

## Métodos

### `forwardToStartPage`
Redireciona o usuário para a página inicial da comunidade.

#### Retorno
- `PageReference`: Referência à página inicial da comunidade.

#### Exemplo de Uso
```apex
// Este método é usado para redirecionar o usuário ao carregar a página.
CommunitiesLandingController controller = new CommunitiesLandingController();
PageReference startPage = controller.forwardToStartPage();
System.debug('Redirecionando para: ' + startPage.getUrl());
```

## Construtores

### `CommunitiesLandingController`
Construtor padrão da classe.

## Relacionamentos

- Veja também: [Network.communitiesLanding](https://developer.salesforce.com/docs/atlas.en-us.apexref.meta/apexref/apex_System_Network.htm)