---
title: hero
summary: Componente Lightning Web para exibir uma seção hero com vídeo ou imagem e conteúdo personalizável.
---

# hero

## Descrição
O componente `hero` exibe uma seção hero com vídeo ou imagem, além de título, slogan e botão. Ele permite personalizar a posição do texto, a opacidade do overlay e o tipo de recurso exibido.

## Atributos

### `title`
- **Tipo**: `String`
- **Descrição**: O título exibido na seção hero.

### `slogan`
- **Tipo**: `String`
- **Descrição**: O slogan exibido abaixo do título.

### `buttonText`
- **Tipo**: `String`
- **Descrição**: O texto exibido no botão.

### `heroDetailsPosition`
- **Tipo**: `String`
- **Descrição**: Define a posição do bloco de texto. Valores possíveis: `left`, `right`, ou `default`.

### `resourceUrl`
- **Tipo**: `String`
- **Descrição**: URL do recurso (imagem ou vídeo) a ser exibido.

### `imgOrVideo`
- **Tipo**: `String`
- **Descrição**: Define o tipo de recurso exibido. Valores possíveis: `Image` ou `Video`.

### `internalResource`
- **Tipo**: `Boolean`
- **Descrição**: Indica se o recurso é interno ao Salesforce.

### `overlay`
- **Tipo**: `String`
- **Descrição**: Define se o overlay será exibido. Valores possíveis: `true` ou `false`.

### `opacity`
- **Tipo**: `String`
- **Descrição**: Define a opacidade do overlay (0 a 10).

### `buttonClickProductOrFamilyName`
- **Tipo**: `String`
- **Descrição**: Nome do produto ou família associado ao clique do botão.

## Métodos

### `resUrl`
- **Descrição**: Retorna a URL do recurso, considerando se é interno ou externo.

### `isVideo`
- **Descrição**: Retorna `true` se o recurso for um vídeo.

### `isImg`
- **Descrição**: Retorna `true` se o recurso for uma imagem.

### `isOverlay`
- **Descrição**: Retorna `true` se o overlay estiver habilitado.

### `heroDetailsPositionClass`
- **Descrição**: Retorna a classe CSS correspondente à posição do bloco de texto.

### `renderedCallback`
- **Descrição**: Atualiza a opacidade do overlay após o componente ser renderizado.

## Exemplo de Uso
```html
<template>
    <c-hero
        title="Welcome to E-Bikes"
        slogan="Ride the future"
        button-text="Shop Now"
        hero-details-position="left"
        resource-url="/images/hero.jpg"
        img-or-video="Image"
        internal-resource="true"
        overlay="true"
        opacity="7"
    ></c-hero>
</template>
```

## Relacionamentos

- Veja também: [lightning-overlay](https://developer.salesforce.com/docs/component-library/documentation/en/lwc).