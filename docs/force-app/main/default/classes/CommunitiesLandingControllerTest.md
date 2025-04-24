---
title: CommunitiesLandingControllerTest
summary: Classe de teste para verificar o comportamento do CommunitiesLandingController.
---

# CommunitiesLandingControllerTest

## Descrição
A classe `CommunitiesLandingControllerTest` é responsável por testar o comportamento do controlador `CommunitiesLandingController`, garantindo que o método `forwardToStartPage` funcione conforme esperado no contexto de teste.

## Métodos de Teste

### `testCommunitiesLandingController`
Testa o método `forwardToStartPage` do controlador `CommunitiesLandingController`.

#### Comportamento Verificado
- Garante que o `PageReference` retornado seja nulo ou tenha uma URL vazia no contexto de teste.

#### Exemplo de Uso
```apex
@IsTest
public with sharing class CommunitiesLandingControllerTest {
    @IsTest(SeeAllData=true)
    public static void testCommunitiesLandingController() {
        // Instancia o controlador
        CommunitiesLandingController controller = new CommunitiesLandingController();
        PageReference pageRef = controller.forwardToStartPage();

        // Verifica o comportamento esperado
        if (pageRef != null) {
            String url = pageRef.getUrl();
            if (url != null) {
                Assert.isTrue(String.isEmpty(url));
            }
        }
    }
}
```

## Relacionamentos

- Veja também: [CommunitiesLandingController](./CommunitiesLandingController.md).