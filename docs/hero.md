---
title: hero
layout: default
---

# hero

**Caminho Relativo:** `force-app/main/default/lwc/hero`

## Visão Geral
O componente `hero` é um Lightning Web Component (LWC) que exibe um banner hero com suporte a imagens ou vídeos. Ele é configurável para diferentes posições de texto, opacidade de sobreposição e outros atributos visuais.

## Estrutura
### Propriedades
- `@api title`: Título do banner.
- `@api slogan`: Slogan exibido no banner.
- `@api buttonText`: Texto do botão.
- `@api heroDetailsPosition`: Posição do texto no banner (ex.: `left`, `right`, `default`).
- `@api resourceUrl`: URL do recurso (imagem ou vídeo).
- `@api imgOrVideo`: Tipo de recurso (`Image` ou `Video`).
- `@api internalResource`: Indica se o recurso é interno.
- `@api overlay`: Aplica uma sobreposição escura ao banner.
- `@api opacity`: Define a opacidade da sobreposição (0 a 10).
- `@api buttonClickProductOrFamilyName`: Nome do produto ou família de produtos para navegação ao clicar no botão.

### Métodos
- `get resUrl`: Retorna a URL do recurso com base no tipo e na configuração de recurso interno.
- `get isVideo`: Verifica se o recurso é um vídeo.
- `get isImg`: Verifica se o recurso é uma imagem.
- `get isOverlay`: Verifica se a sobreposição está ativada.
- `get heroDetailsPositionClass`: Retorna a classe CSS apropriada para a posição do texto.
- `renderedCallback()`: Atualiza a opacidade da sobreposição com base na configuração.

## Relacionamentos
- Utiliza o recurso estático `bike_assets` para imagens internas.
- Configurável no `Community Builder` com propriedades como título, slogan, opacidade, etc.

## Exemplos
### Código de Exemplo
```javascript
renderedCallback() {
    const overlay = this.template.querySelector('div');
    if (overlay) {
        overlay.style.opacity = parseInt(this.opacity, 10) / 10;
    }
}
```

[← Voltar ao índice](index.md)